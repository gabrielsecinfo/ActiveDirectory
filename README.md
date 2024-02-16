# ActiveDirectory
Implementação e configuração do Active Directory

  A execução bem-sucedida da implementação e configuração do Active Directory é crucial para estabelecer um ambiente de rede eficiente. Este guia fornece um passo a passo, demonstrando como criar o primeiro usuário, grupo e pasta de rede, shadow copies e backup nativo do windows server.
  Conforme foi criado o windows server 2012 para subir o AD, então iremos continuar por ele. Link da configuração do mesmo: https://github.com/gabrielsecinfo/WindowsServerAD.git

  A criação do primeiro user é bem simples, botão direito em cima da pasta user depois ir em new>user após aparecer a tela você ira preencher 
  O primeiro nome, inicial e último nome e qual seria o logon. 




  Conforme o avançar irá solicitar uma senha pra esse usuário e vai aparecer opções como:
   Senha nunca expíra, conta desativada, user não pode mudar a senha e que vai ser alterada no próximo logon:




   O usuário como teste foi criado normalmente como a print abaixo demostra:



   A configuração do mesmo é feita em suas propriedades no qual caminho seria botão direito>propriedades



   Nessa propriedades tem diversas opções como  sessões, organizações, seu perfil, seu perfil de acesso remoto,  quais grupos você e membro e etc.



   Na guia de membros iremos adicionar um grupo, ao qual irá ser aberto um menu e um campo ser digitado o nome do grupo (Um objeto que exista), no exemplo irá ser usado grupo de administrador:



   Demostrando os grupos que faço parte:




Agora a criação do grupo que não deixa de ser nenhum pouco importante, pois o grupo fornece variações de permissões mas ele fornece uma coisa bastante importante que é a segurança, pois o mesmo consegue está controlando o acesso
a site A ou a site B, se o mesmo tem permissão de acesso a pasta de rede, vpn e etc.





Estrutura;





Agora subindo outra VM com windows 10 para ser colocada no domínio e acessar uma conta que já está criada no AD;
Ao iniciar vamos entrar no perfil do administrador e assim colocar no domínio. Quando estiver na tela de área de trabalho, usar o atalho iniciar+R e escrever ncpa.cpl e enter.
Atividar adaptadores e após ir em propriedades e dar dois cliques no IPVA4,
E nisso vamos configurá-lo podemos deixar no DHCP e configurar somente o DNS para o Windows server que acha.









Ok achando o mesmo vamos configurar o computador para o domínio:
Iniciar+r e escreva sysdm.cpl e da enter.


   


   
  
