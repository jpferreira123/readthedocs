# REGRAS DE NEGÓCIO

## Introdução

Este documento visa explicar como criar regras de negócio no Framework Prodígio.
Requisitos: Possuir as classes de domínio já modeladas.


## Criando primeira regra de negócio

As regras de negócios encontram-se nas classes terminadas em RN que herdam de BaseRN e são localizadas no pacote de negócio.
No exemplo a seguir iremos nos certificar de que um objeto do tipo FuncionarioVO só será persistido no banco caso possua o atributo nome preenchido. 
Primeiramente criaremos a lógica de validação:

	package  br.gov.prod.prod.tutorial.negocio.funcionario;
	/* imports omitidos */
	public class FuncionarioRN extends TutorialBaseRN{
		public void verificaNome(FuncionarioVO funcionarioVO) {
			if (funcionarioVO.getNome() == null || funcionarioVO.getNome().isEmpty())   
			{
				/* instruções*/
			}
		}
	}

Agora iremos adicionar a anotação @RegraDeNegocio em nosso método da seguinte maneira:

	@RegraDeNegocio(autor = "Autor", codigo = "CODIGO_DA_REGRA", ordem = 1, fluxo = "gravar", momentoDeExecucao = MomentoDeExecucao.ANTES)
	public void verificaNome(FuncionarioVO funcionarioVO) {
		if (funcionarioVO.getNome() == null || funcionarioVO.getNome().isEmpty())   
		{
			/*instruções */
		}
	}

Nos resta apenas implementar as instruções. No caso lançaremos a exceção ViolacaoDeRegraEx com a mensagem relativa ao erro:

	@RegraDeNegocio(autor = "Autor", codigo = "CODIGO_DA_REGRA", ordem = 1, fluxo = "gravar", momentoDeExecucao = MomentoDeExecucao.ANTES)
	public void verificaNome(FuncionarioVO funcionarioVO) {
		if (funcionarioVO.getNome() == null || funcionarioVO.getNome().isEmpty())   
		{
			throw new ViolacaoDeRegraEx(“O funcionário precisa de um nome.”);
		}
	}
