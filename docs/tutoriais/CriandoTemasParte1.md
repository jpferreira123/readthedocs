# Criando temas

### Introdução

Este documento visa explicar como realizar a criação de temas usando o Templateprod.

### Configurações


É necessário realizar a instalação do node.js e LESS engine para a compilação dos arquivos LESS.

#### Instalando node.js

Faça o download da versão mais recente do node.js em: https://nodejs.org/en/  e realize normalmente a instalação. 

#### Instalando LESS engine

Execute os seguintes comandos no terminal para instalação da LESS ENGINE:

	npm config set proxy http://proxyint.prod.gov.br:8080

	npm install –g less

### Criando o tema

1. Importe o prodThemeTemplate como projeto maven.
2. Renomeie todas as pastas e arquivos que contenham “prodThemeTemplate” para o nome que desejar para seu tema.
3. Edite os arquivos .css e .less da maneira que preferir.
4. Clique com o botão direito em seu projeto e escolha Run As >> Maven install. Este processo poderá levar um tempo razoável.
5. Será gerado o arquivo .jar de seu tema no diretório Target do projeto.

### Habilitando o tema em projetos do prod

1. Coloque o arquivo .jar de seu tema na pasta WEB-INF/lib de seu projeto prod então seu tema personalizado se tornará padrão caso nenhum outro tema esteja habilitado.
2. Você pode fazer a troca de maneira dinâmica por cookie ou library property:
3. Usando cookie, adicione um cookie:
zktheme = NOME_DO_TEMA
4. Usando library-property

	<!--- em WEB-INF/zk.xml -->
	<library-property>
		<name>org.zkoss.theme.preferred</name>
		<value>NOME_DO_TEMA</value>
	</library-property>
