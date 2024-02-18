# ActiveDirectory
Implementação e configuração do Active Directory

  A execução da implementação e configuração do Active Directory é crucial para estabelecer um ambiente de rede eficiente. Este guia fornece um passo a passo, demonstrando como criar o primeiro usuário, grupo e pasta de rede, além de abordar conceitos como shadow copies e backup nativo do Windows Server. O ambiente utilizado é baseado no Windows Server 2012, e o link para a configuração está disponível em:  https://github.com/gabrielsecinfo/WindowsServerAD.git

  A criação do primeiro user é bem simples, botão direito em cima da pasta user depois ir em new>user após aparecer a tela você ira preencher 
  O primeiro nome, inicial e último nome e qual seria o logon. 
<img src="AD/image.png">

  Conforme o avançar irá solicitar uma senha pra esse usuário e vai aparecer opções como:
   Senha nunca expíra, conta desativada, user não pode mudar a senha e que vai ser alterada no próximo logon:
<img src="AD/image1.png">

   O usuário como teste foi criado normalmente como a print abaixo demostra:

<img src="AD/image2.png">

   A configuração do mesmo é feita em suas propriedades no qual caminho seria botão direito>propriedades
<img src="AD/image3.png">


   Nessa propriedades tem diversas opções como  sessões, organizações, seu perfil, seu perfil de acesso remoto,  quais grupos você e membro e etc.

<img src="AD/image3.png">

   Na guia de membros iremos adicionar um grupo, ao qual irá ser aberto um menu e um campo ser digitado o nome do grupo (Um objeto que exista), no exemplo irá ser usado grupo de administrador:

<img src="AD/image4.png">

   Demostrando os grupos que faço parte:

<img src="AD/image5.png">


Agora a criação do grupo que não deixa de ser nenhum pouco importante, pois o grupo fornece variações de permissões mas ele fornece uma coisa bastante importante que é a segurança, pois o mesmo consegue está controlando o acesso
a site A ou a site B, se o mesmo tem permissão de acesso a pasta de rede, vpn e etc.

<img src="AD/image6.png">
<img src="AD/image7.png">

obs: o tipo de grupo utilizado é de segurança porém o de distruição seria mais para e-mails.



Estrutura;


<img src="AD/image8.png">


Agora subindo outra VM com windows 10 para ser colocada no domínio e acessar uma conta que já está criada no AD;
Ao iniciar vamos entrar no perfil do administrador e assim colocar no domínio. Quando estiver na tela de área de trabalho, usar o atalho iniciar+R e escrever ncpa.cpl e enter.
Atividar adaptadores e após ir em propriedades e dar dois cliques no IPVA4,
E nisso vamos configurá-lo podemos deixar no DHCP e configurar somente o DNS para o Windows server que acha.
<img src="AD/image9.png">








Ok achando o mesmo vamos configurar o computador para o domínio:
Iniciar+r e escreva sysdm.cpl e da enter, ao entrar vai em alterar e depois selecione domínio e coloque o domínio criado anteriormente, acabando vai pedir para reiniciar.

<img src="AD/image10.png">
<img src="AD/image11.png">
Ao reiniciar você já pode colocar um usuário de rede, se você observar a print tem entrar em: GABRIELSECURITY (Domínio)

<img src="AD/image12.png">

Voltando no Windows Server 2012 R2 podemos criar uma pasta compartilhada via rede, então criamos essa *securityfile** e fomos em propriedades>compartilhamento>compartilhamento advanced sharing e nisso selecionamos a opção de compartilhar essa pasta, ao ir no permissions podemos está adicionando usuário e sua permissão como; acesso total, leitura, escrita e etc.
<img src="AD/image13.png">

e para melhoramos o ambiente para o usuário criamos uma pasta de rede para o próprio, então toda vez que o mesmo entrar vai subir uma pasta de rede do usuário dele. Vamos ir em users no AD>Propriedades>Profile e tem a opção de se conectar a uma unidade de rede e o local da pasta ao adicionar e a pessoa logar pela primeira vez deverá subir o sistema da pasta.
código: \\server\pasta$\%username%

<img src="AD/image14.png">

Agora iremos configurar Shadow Copies, vamos em este computador>seu disco>botão direito> shadow copies.

<img src="AD/image17.png">


Vamos em settings para podermos inserir a quantidade de cota da shadow copies depois de aplicar já está como enable, podemos apertar no botão de create now

<img src="AD/">


Criei um arquivo teste.txt de teste, porém o arquivo só irá ser feito o shadow copie dele ás 7horas da manhã pois o horário setado.

<img src="AD/image18.png">

   
Iremos criar de novo, após foi excluído o mesmo.
Então voltamos ao c:/ e fomos até propriedades>versões anteriores no qual mostra toda vez que a função do shadow copies foi efetuada e que possa retornar a ela.

<img src="AD/image19.png">

Selecionamos a data/hora no qual o arquivo não estava excluído e vamos em abrir/open


<img src="AD/image20.png">


   Como por redundância e questões de segurança, iremos criar um sistema de backup nativo do Windows server.
   No qual iremos criar um novo recurso a parti do wizard ao qual o caminho seria abrir o server manager>dashboard>next até features/recursos, selecionar backup do Windows server e instalar. 

<img src="AD/image22.png">
<img src="AD/image21.png">

  Ok já instalado você irá abrir ferramentas>backup do Windows server
  Agora iremos em opções de backup/backup once/ backup unico
  

<img src="AD/image23.png">
  Colocamos em opções diferente

  
<img src="AD/image24.png">



  Seleção de configuração de backup foi colocado custom/personalizado 

<img src="AD/image26.png">

  Entao na próximo etapa escolhemos o item que deverá ser feito o backup



  Agora para finalizar só avançar até confirmação e realizar o backup

  
