# Configurações para Projeto prod sem SSC

Requisitos: possuir ambiente configurado e projeto criado via archetype com SSC desabilitado na properties ‘includeSSC’ durante a criação do projeto.

## Introdução

Este documento visa explicar as configurações necessárias em um projeto prod sem SSC.

## Alterando a index.zul

Abra o arquivo index.zul que se encontra no projeto frontend dentro da pasta visão.

![](imagens/projeto_sem_ssc_1.png)

O arquivo deve estar parecido com o a seguir:

![](imagens/projeto_sem_ssc_2.png)

Altere o caminho da classe controle, no atributo apply da tag window para a classe br.gov.prod.controle.WindowPrincipalUnsecured da seguinte maneira:

![](imagens/projeto_sem_ssc_3.png)
 
Agora substitua a tag <div id="introducao"></div>
pela tag <include id="include_introducao" src="introducao.zul" />

Antes:

![](imagens/projeto_sem_ssc_4.png)

Depois:

![](imagens/projeto_sem_ssc_5.png)


Adicione o atributo onCreate="classecontrole.configuraUsuarioUnidadeLogada()" na tag window.

![](imagens/projeto_sem_ssc_6.png)

## Alterando a introducao.zul

Abra o arquivo introducao.zul que se encontra no projeto frontend dentro da pasta visão.

![](imagens/projeto_sem_ssc_7.png)

O arquivo deve estar semelhante ao a seguir:

![](imagens/projeto_sem_ssc_8.png)

Na tag <nav label="Menu" visible="true" onCreate="classecontrole.insereMenuPopUp(self)" />   
remova o atributo onCreate="classecontrole.insereMenuPopUp(self)".

![](imagens/projeto_sem_ssc_9.png)

Adicione agora os itens do menu como a seguir:

![](imagens/projeto_sem_ssc_10.png)

Observe bem a estrutura do menu e da tag custom-attributes.
Por último, no atributo apply da tag Window substitua “br.gov.prod.controle.WindowIntroducao” por “br.gov.prod.controle.WindowPrincipalUnsecured”.
<window id="principal" apply="br.gov.prod.controle.WindowPrincipalUnsecured">	


