# Alterando tema pelo Eclipse:

Obs.: É necessário possuir o projeto do tema e um projeto prod abertos em sua workspace.

![](imagens/alterando_tema_pelo_eclipse_1.png)


### Altere os arquivos .less da maneira que preferir.

![](imagens/alterando_tema_pelo_eclipse_2.png)
 
### Após realizar as alterações clique com o botão direito do mouse sobre o projeto do tema e escolha a opção Run As>>Maven Install

![](imagens/alterando_tema_pelo_eclipse_3.png)
 
### Feche o projeto do tema

![](imagens/alterando_tema_pelo_eclipse_4.png)
 
# Alterando tema em outros editores 

### Feche o projeto do tema no Eclipse

![](imagens/alterando_tema_pelo_eclipse_5.png)
 
### Acesse os arquivos do projeto (possivelmente: C:\prod\workspace\prodtema\prodtema\src\archive\web\zul\less)

![](imagens/alterando_tema_pelo_eclipse_6.png)
 
### Edite os arquivos com o editor de sua escolha.

### Acesse o diretório do projeto pelo prompt e execute os seguintes comandos para compilar os arquivos less e gerar o jar de seu tema:

	set PATH=%PATH%;c:\prod\maven\apache-maven-3.0.5\bin

	mvn install -DgroupId=org.zkoss.theme -DartifactId=nomedotema -Dversion=1.0.0 -Dpackaging=jar

# Aplicando o Tema

### Adicione a dependência do tema no pom.xml do projeto web:
 
![](imagens/alterando_tema_pelo_eclipse_7.png)

![](imagens/alterando_tema_pelo_eclipse_8.png)

### Realize um Maven Update(Alt+F5) em todo seu projeto

![](imagens/alterando_tema_pelo_eclipse_9.png)

### Executando aplicação
Basta adicionar sua aplicação ao servidor e inicializa-lo.

![](imagens/alterando_tema_pelo_eclipse_10.png)

![](imagens/alterando_tema_pelo_eclipse_11.png)
 
Sua aplicação poderá ser acessada pelo navegador através da URL: 

	http://localhost:8080/nomeDoProjeto-web/

### Limpe o cache do navegador para visualizar as alterações.
