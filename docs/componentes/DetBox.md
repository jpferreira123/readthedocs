# Componente DetBox

## Introdução
Esta seção visa explicar o funcionamento do componente ``detbox`` do Framework Prodígio.

Requisitos: Possuir as classes de domínio já modeladas e página .zul já configurada.

## Estrutura do componente detbox

O elemento ``detbox`` possui a seguinte estrutura:

	<detbox id="listaDeObjetosDet" nomeDoObjeto="classecontrole.objetoAtual.listaDeObjetos">
		<listboxdet id="listaDeObjetos">
				
			<listhead>
				<listheader label="LabelAtributo1" value="atributo1" />
				<listheader label="LabelAtributo2" value="atributo2 " />
			</listhead>
				
			<listitem>
				<listcell>
					<label value="atributo1"></label>
					<textboxbind nomeDoObjeto="objeto.atributo1"/>
				</listcell>
				<listcell>
					<label value="atributo2"></label>
					<textboxbind nomeDoObjeto="objeto.atributo2"/>
				</listcell>
			</listitem>
		</listboxdet>
	</detbox>
	
### A tag <detbox> deve conter os seguintes atributos:

* ``id`` -> contém o nome da lista de objetos seguido pelo prefixo Det. Exemplo: Um detbox que atribui valores a uma lista de objetos chamado ``HistoricoProfissional`` receberia o id ``historicoProfissionalDet``.
* ``nomeDoObjeto`` -> lista de objetos.

Existem também atributos opcionais como o mais utilizado label que atribuí uma label título para o detbox.

Dentro de ``detbox`` possuímos a tag ``<listboxdet>`` que representa o corpo do componente, no atributo id setamos o objeto definido em ``nomeDoObjeto`` do detbox.

### Dentro de ``<LISTBOXDET>`` possuímos as Tags:

* ``<listheader></listheader>`` -> que define o cabeçalho da listagem e dentro de ``listheader`` temos ``<listhead></listhead>``   que representa o cabeçalho de cada coluna.
* ``<listitem></listitem>`` -> onde serão listados e atribuídos os valores dos atributos do objeto. Apresenta a tag  ``<listcell></listcell>``  e dentro de cada ``listcell`` definimos os componentes de cada propriedade.
