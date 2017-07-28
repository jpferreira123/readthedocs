# Componente BandBoxBind

## Introdução
Esta seção visa explicar como utilizar o componente ``bandboxbind`` do Framework Prodígio.

Requisitos: Possuir as classes de domínio já modeladas e página .zul já configurada.

## Listando valores com bandboxbind utilizando Enum

Basta criar o componente ``bandboxbind`` em sua página .zul da seguinte maneira: 

	<bandboxbind id="nomeDoEnumNaClasseDominio"/>

## Vinculando objetos ao bandboxbind

Crie o componente ``bandboxbind`` e adicione os seguintes atributos substituindo o valor de ``nomeDoObjeto`` pelo valor correspondente ao que deseja vincular:

	<bandboxbind nomeDoObjeto="classecontrole.objetoAtual. nomeDoObjetoNaClasseDominio"/>

Podemos também adicionar o atributo ``labelValorList`` que define como os valores serão listados no ``bandboxbind``:

	<bandboxbind nomeDoObjeto="classecontrole.objetoAtual. nomeDoObjetooNaClasseControle" labelValorList=”NomeDoAtributo:atributoDaClasse”/>

Utilizando a anotação ``@Lookup`` na classe de domínio obtemos uma atualização automática dos dados do ``bandboxbind`` quando algum objeto for adicionado, excluído ou modificado. 


## Aninhando bandboxbind

Usaremos como exemplo o vínculo de três objetos: País, Estado e Cidade. Onde País possuí um HashSet de Estados que possuí um HashSet de Cidades.

Crie os componentes ``bandboxbind`` seguindo a seguinte estrutura:

	/* restante do código da página .zul */
	<label value="País:"></ label>
	<bandboxbind nomeDoObjeto="classecontrole.objetoAtual.paisVO"  identificador="pais"/>
	<label value="Estado:"></label>
	<bandboxbind nomeDoObjeto="classecontrole.objetoAtual.estadoVO" identificador="estado" metodoFiltro="filtrarEstado" dependeDoComponente="pais"/> 
	<label value="Cidade:"></label>
	<bandboxbind nomeDoObjeto="classecontrole.objetoAtual.cidadeVO" metodoFiltro="filtrarCidade" dependeDoComponente="estado"/>
	/* restante do código da página .zul */


Observe bem os atributos ``identificador``, ``dependenteDoComponente`` e ``metodoFiltro`` eles são cruciais para o funcionamento do vínculo.

Agora precisamos criar os filtros para os componentes. Abra a classe de controle de sua página .zul definida no atributo apply e crie os seguintes métodos seguindo a nomenclatura definida no atributo ``metodoFiltro`` de seus componentes:


	/*Os métodos filtram e retornam as listas com os objetos que irão preencher os bandboxbind dependidos*/
	@SuppressWarnings({ "rawtypes", "unchecked" })
	public List filtrarEstado(Bandboxbind bandboxbind){
	
		/*Recupera o COMPONENTE dependido, logo será recuperado o componente com o identificador que seja igual ao valor do atributo dependenteDoComponente do bandboxbind que possuir este método(filtrarEstado) como metodoFiltro*/	
		Bandboxbind componentDependido = (Bandboxbind)ProHelperView.recuperaBandboxParaAninhar(getWindowAtual(), bandboxbind.getDependeDoComponente());
	
		/*Recupera o OBJETO selecionado no COMPONENTE dependido*/
		PaisVO paisVO = (PaisVO) componentDependido.getObject();
	
		/*Recupera e retorna a lista de objetos DEPENDENTES do objeto DEPENDIDO ( no caso a lista de Estados de determinado País )*/
		List estados =  new ArrayList();
		estados.addAll(paisVO.getEstados());
		return estados;
	}
		
	/*Da mesma forma do código anterior filtra e retorna a lista de objetos, no caso a lista de Cidades de determinado Estado*/	
	@SuppressWarnings({ "rawtypes", "unchecked" })
	public List filtrarCidade(Bandboxbind bandboxbind){
		Bandboxbind componentDependido = (Bandboxbind)ProHelperView.recuperaBandboxParaAninhar(getWindowAtual(), bandboxbind.getDependeDoComponente());
		EstadoVO estadoVO = (EstadoVO)componentDependido.getObject();
		List cidades = new ArrayList();
		cidades.addAll(estadoVO.getCidades());
		return cidades;
	}
	/* Como queremos listar a princípio todos os países, não usaremos filtro para País */
	
