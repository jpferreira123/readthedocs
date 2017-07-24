# Configurando o ambiente

## Introdução
Este documento visa explicar como realizar as configurações necessárias no Postgre, Maven e jBoss para utilização do framework Proddígio.

## Configurando o Postgre
### Inicializando o Banco

Na pasta de instalação do Proddígio acesse o diretório databases\postgre_portable e execute o PortablePostgreSQL.
Acesse o Postgre nos ícones ocultos, clique com o botão direito do mouse e selecione Progs>>Start PostgreSQL.

![](imagens/configurando_o_ambiente_1.png)

A seguinte janela deverá ser aberta com a mensagem SERVER STARTING e não poderá ser fechada durante toda utilização do banco.

![](imagens/configurando_o_ambiente_2.png)

### Configurando e conectando ao servidor
Acesse o Postgre nos ícones ocultos, clique com o botão direito do mouse e selecione Progs>>Start pgAdminIII

![](imagens/configurando_o_ambiente_3.png)

No pgAdminIII clique em Adicionar conexão a um servidor

![](imagens/configurando_o_ambiente_4.png)

Configure o novo registro da seguinte maneira e clique em OK:

![](imagens/configurando_o_ambiente_5.png)

Conecte-se ao servidor

![](imagens/configurando_o_ambiente_6.png)

### Criando banco de dados
Clique com o botão direito em Banco de Dados e escolha a opção Novo Banco de Dados...

![](imagens/configurando_o_ambiente_7.png)

Defina o nome do banco e selecione Proddígio como Dono

![](imagens/configurando_o_ambiente_8.png)

Clique em OK para finalizar e em seguida clique uma vez no banco criado.

### Encerrando conexão

Importante: não encerre a conexão com servidor durante a utilização de sua aplicação.

Acesse o Postgre nos ícones ocultos, clique com o botão direito do mouse e selecione Progs>>Start pgAdminIII

![](imagens/configurando_o_ambiente_9.png)

Clique com o botão direito do mouse em sua conexão e selecione a opção Desconectar.

![](imagens/configurando_o_ambiente_10.png)


Acesse o Postgre nos ícones ocultos, clique com o botão direito do mouse e selecione Progs>>Stop PostgreSQL.

![](imagens/configurando_o_ambiente_11.png)


## Maven

Abra o Eclipse Luna, no menu superior selecione WINDOW >> PREFERENCES

![](imagens/configurando_o_ambiente_12.png)

No campo superior esquerdo procure por ‘maven’

![](imagens/configurando_o_ambiente_13.png)

Acesse a propriedade ‘User Settings’:

![](imagens/configurando_o_ambiente_14.png)

No campo ‘User settings’ selecione o arquivo settings.xml que se encontra na pasta maven\apache-maven-3.0.5\conf localizada na pasta de instalação do Proddígio e clique em APPLY. 

![](imagens/configurando_o_ambiente_15.png)

Agora vá para a opção MAVEN >> INSTALLATIONS 

![](imagens/configurando_o_ambiente_16.png)

Clique no botão ‘Add...’ adicione e o diretório de instalação maven do Proddígio 

![](imagens/configurando_o_ambiente_17.png)
![](imagens/configurando_o_ambiente_18.png)

Clique em FINISH.
Certifique-se de habilitar o maven Proddígio, clique em APPLY e em seguida em OK.

![](imagens/configurando_o_ambiente_19.png)