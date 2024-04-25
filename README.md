
# MQTT: Conectando Dispositivos para a Era da Internet das Coisas

Este projeto documenta a criação e configuração de uma conexão entre um dispositivo móvel e um servidor MQTT. Para este propósito, usaremos o [HiveMQ](https://www.hivemq.com/) omo servidor. Aqui estão as etapas para configurar seu próprio ambiente MQTT usando o HiveMQ.




## Início Rápido com o HiveMQ

Para usar o HiveMQ como servidor MQTT, é necessário criar uma conta e configurar um servidor. Veja a seguir os passos para configurar sua conta e seu servidor.

### criação de conta 

-  Visite o site do HiveMQ.

- Se você não tiver uma conta, clique em "Criar Conta" ou "Sign Up" para se registrar.

- Complete o formulário de registro com suas informações. Um e-mail de confirmação será enviado para você.

![Pagina inicial](/imgs/Home.png)


###  Configurar o Servidor

- Após criar a conta e fazer login, você verá uma interface com um menu lateral.

- No menu lateral, clique no símbolo de + para criar um novo servidor.

  ![Menu](/imgs/Menu.png)

- Selecione o plano "Livre" (Free). Não se preocupe com as opções pagas, pois para este projeto o plano gratuito é suficiente.

- Aparecera para selecionar o serviço em nuvem, pode deixar sendo AWS
  
   ![Servidor](/imgs/Servidor.png)
  
- Após criar o servidor, ele aparecerá na lista de "clusters".


### Gerenciando o Cluster 

- Para acessar o servidor recém-criado, selecione-o na lista de clusters.

![clusters](/imgs/clusters.png)


- Você verá informações importantes, como o URL do servidor, que será usado para conectar seus dispositivos.

- Anote ou copie o URL do servidor para uso posterior.
  

![clusters_Config](/imgs/clusters_Config.png)

### Configurar Acesso ao Cluster

Antes de conectar dispositivos ao servidor, você precisa configurar as permissões de acesso.

-Dentro do servidor, configure as permissões e usuários conforme necessário

- Dependendo do uso, você pode precisar criar regras específicas para dispositivos ou tópicos.

  ![Credenciais](/imgs/Credenciais.png)

  ### Próximos Passos

  - Apos essa configuração voce pode ir no cliente web
 
  - passe as credenciais que foram criadas, e conecte ao server (Atenção com o nome do topico)
 
   ![ClienteWeb](/imgs/ClienteWeb.png)

  
