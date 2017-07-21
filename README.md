# Teste

O **Soft** é um framework provido pela **Empresa**

  - Agilidade no desenvolvimento

## Download

  - Realize o download do instalador em ????.

## Instalação

Execute o arquivo **.exe** , clique na opção Avançar, direcione a instalação para raiz de C: , clique em avançar. Aguarde a instalação ser concluída. A instalação irá configurar o seguinte ambiente:

  - Archetypes
  - Databases (Postgre)
  - Ide (Eclipse Luna)
  - Jkds (1.7.0 e 1.8.0)
  - Maven
  - Servers (jBoss)
  - Workspaces

Ao final da instalação, o ambiente estará completamente configurado com uma aplicação de exemplo.


## Configurando o ambiente

### Introdução
Este documento visa explicar como realizar as configurações necessárias no Postgre, Maven e jBoss para utilização do framework Proddígio.

### Configurando o Postgre
#### Inicializando o Banco

A seguinte janela deverá ser aberta com a mensagem SERVER STARTING e não poderá ser fechada durante toda utilização do banco.

(imagem)

#### Configurando e conectando ao servidor
Acesse o Postgre nos ícones ocultos, clique com o botão direito do mouse e selecione Progs>>Start pgAdminIII

(imagem)

No pgAdminIII clique em Adicionar conexão a um servidor

(imagem)

Configure o novo registro da seguinte maneira e clique em OK:

(imagem)

Conecte-se ao servidor

(imagem)

#### Criando banco de dados
Clique com o botão direito em Banco de Dados e escolha a opção Novo Banco de Dados...

(imagem)

Defina o nome do banco e selecione prodigio como Dono

(imagem)

Clique em OK para finalizar e em seguida clique uma vez no banco criado.

#### Encerrando conexão

Importante: não encerre a conexão com servidor durante a utilização de sua aplicação.

Acesse o Postgre nos ícones ocultos, clique com o botão direito do mouse e selecione Progs>>Start pgAdminIII

(imagem)

Clique com o botão direito do mouse em sua conexão e selecione a opção Desconectar.

(imagem)

Acesse o Postgre nos ícones ocultos, clique com o botão direito do mouse e selecione Progs>>Stop PostgreSQL.

(imagem)


### Maven

Abra o Eclipse Luna, no menu superior selecione WINDOW >> PREFERENCES

(imagem)

No campo superior esquerdo procure por ‘maven’

(imagem)

## PROJETO VIA ARCHETYPE

### Introdução
Este documento visa explicar como configurar o archetype e realizar a criação de um projeto seguindo o padrão arquitetural.

Obs. 1 : Neste tutorial o Archetype se encontrava na versão 2.5, a possível evolução do Archetype não altera os procedimentos de criação de projetos descritos neste documento, sendo necessário apenas a substituição do arquivo archetype-catalog para a versão mais recente.



### Configurando Archetype

Abra o Eclipse Luna. No menu superior selecione WINDOW >> PREFERENCES e acesse a opção MAVEN >> ARCHETYPES 

(imagem)
(imagem)

Aplique as modificações na janela Preferences clicando em Apply e em seguida clique em OK.

(imagem)

### Criando Projeto

No menu superior selecione FILE>> NEW>> Maven Project.

(imagem)

Utilizaremos o workspace padrão mas caso deseje alterar sua workspace selecione o diretório no Location clicando em ‘Browse...’ . 
Clique em Next.

(imagem)

Especifique os parâmetros GroupId com o grupo do projeto, ArtifactId com o nome do projeto e Package com a estrutura de pacotes do projeto. 
Configure também as properties:


(imagem)

Na properties baseClassname coloque o nome do projeto com a primeira letra maiúscula.

### Executando a aplicação

####  Adicionando  server

Na view SERVERS do Eclipse, clique na opção para adicionar um novo server. 

(imagem)

Escolha a versão mais recente do jBoss Enterprise Application Platform e clique em NEXT

(imagem)

Selecione a opção “Create new runtime” e clique novamente em Next

#### Configurando standalone

Abra o arquivo standalone.xml do jBoss

(imagem)

Configure o datasource de acordo com o seu banco de dados seguindo o modelo substituindo os campos nomeDaAplicacao e nomeDoBanco.

(imagem)
(imagem)

*Ferramenta Find/Replace(atalho ctrl+F)*

#### Executando aplicação
Basta adicionar sua aplicação ao servidor e inicializa-lo.

(imagem)
(imagem)
(imagem)
(imagem)

Sua aplicação poderá ser acessada pelo navegador através da URL: 
```sh
http://localhost:8080/nomeDaAplicacao-frontend/
```
