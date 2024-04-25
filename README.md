
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

  ## Projeto Android

### Dependências Necessárias

Para utilizar o protocolo MQTT neste projeto, você precisará instalar algumas dependências e ajustar a configuração do build.gradle. Aqui estão as etapas para adicionar as dependências corretas e modificar a configuração de embalagem (packaging):

#### 1. Adicionar Dependências do HiveMQ

Para incluir o cliente MQTT do HiveMQ no seu projeto, adicione a seguinte linha à seção dependencies do seu arquivo build.gradle:

```
dependencies {
    implementation("com.hivemq:hivemq-mqtt-client:1.2.1")
    // Outras dependências necessárias...
}
```

#### 2. Modificar a Configuração de Embalagem (Packaging)

 O protocolo MQTT pode trazer alguns recursos que precisam ser excluídos para evitar conflitos ou problemas de compilação. Para ajustar a seção de embalagem, use a seguinte configuração
```
android {
    // Outras configurações do projeto...

    packaging {
        resources {
            val exclusions = mutableListOf(
                "META-INF/INDEX.LIST",
                "META-INF/io.netty.versions.properties"
            )
            excludes.addAll(exclusions)
        }
    }
}
```

### MainActivity 

Nesse ponto podemos passar as informaçoes de configuração que conseguimos anteriomente,  para ocorrer a conexão ao server 
```
        String host = "1e09ce88868d412f98954e54496fb...";
        String username = "User";
        String password = "password!";
```

### Projeto em Funcionamento
Após completar todas as etapas de configuração, conseguimos estabelecer uma comunicação entre o aplicativo e o servidor MQTT. Veja como a troca de mensagens acontece:

#### Do Aplicativo para o Servidor
Ao enviar uma mensagem do aplicativo para o servidor, ela é exibida assim:
 
   ![App](/imgs/App.png)

O servidor recebe a mensagem e a processa como esperado:

  ![mensagemrecebida](/imgs/mensagemrecebida.png)
  
#### Do Servidor para o Aplicativo
Também é possível enviar uma mensagem do servidor para o aplicativo. Veja como o servidor envia a mensagem:

  ![Mensagemenviadadoserver ](/imgs/Mensagemenviadadoserver.png)

E aqui está como a mensagem é recebida no aplicativo:

  ![App2](/imgs/App2.png)

  ## Como Contribuir 
Sinta-se à vontade para contribuir para o desenvolvimento do SIAS! Você pode clonar o repositório, abrir issues ou enviar pull requests. Certifique-se de seguir as diretrizes de contribuição.

## Instalação e Configuração
Para configurar e executar o projeto localmente, siga estas etapas:

1. Clone o repositório: `git clone https://github.com/seu-usuario/MQTT.git`
2. Navegue até o diretório do projeto
3. Configure o ambiente (certifique-se de ter as tecnologias mencionadas instaladas)
4. Execute o aplicativo
  


