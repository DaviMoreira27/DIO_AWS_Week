# API para chat serverless integrado com API do OpenAI ChatGPT para a AWS Cloud Week

*Serviço AWS desenvolvido por meio da AWS Cloud Week da Digital Innovation One*

## Passos para o projeto

- Clonar o repositório
- Instalar as dependências com o comando ```npm install```
- Atualizar o arquivo ```.env``` com a sua chave do OpenAI
- Compactar o conteúdo do projeto em um arquivo ```.zip```

## Na AWS

- Acessar o console da AWS
- Criar uma função no serviço AWS Lambda
- Fazer o upload do conteúdo do arquivo ```.zip``` no código da função
- Acessar o serviço AWS API Gateway
- Criar uma API Websocket
- Criar os endpoints (obs: os três primeiros endpoints marcados com ```$``` são padrão de uma API Websocket do API Gateway):
    - ```$connect```
    - ```$disconnect```
    - ```$default```
    - ```setName```
    - ```sendPublic```
    - ```sendPrivate```
    - ```sendBot```

## Testando o Websocket

- Baixar a dependência ```wscat``` através do comando ```npm i -g wscat```. 
- Utilizar o parâmetro ```-g``` para instalar de forma global no sistema operacional, podendo chamá-la de fora do projeto.

### Utilizando o wscat

- ```wscat -c url_de_conexao_do_websocket```
- Exemplo de chamada ```{"action":"sendPublic", "message":"Hello World!"}```


- Desenvolvimento AWS Cloud*, 
- Desenvolvimento Back-end serveless chat*, 
- integração front-end react com back-end*

**Será utilizado o AWS Lambda para a lógica de negócio**

- O Amazon API Gateway será utilizado para criar o Websocket para receber conexões dos clientes e enviar mensagens. Ele dará suporte para as rotas que gerenciam a conexão dos clientes

**API REST Vs Websockets** -> Websockets tem uma baixa latência por requisição. Ideal para casos com alta frequência de comunicação. REST APIs são melhores em casos de CRUD.

**SSH** -> Secure Socket Shell, um protocolo de segurança de troca de arquivos entre cliente de servidor.

**AWS Elastic (EC2)** -> Um serviço que cria instâncias, fornece capacidade de computação escalável. podem ser conectadas via SSH ou pelo browser. *Alguel de computadores virtuais (VMs)*.

**Backend Serveless** -> A lógica de negócios é executada em serviços de computação em nuvem. Serviços serveless AWS:

-*AWS Lambda*
-*Amazon API Gateway*
-*DynamoDB*
-*S3...*

**AWS Lambda** -> Permite a execução de códigos em resposta a eventos, como uma chamada de API, upload de arquivo, etc.
É enviado por meio de funções com alguns componentes principais:

- *Eventos: Desencadeia a execução de uma função*
- *Funções: Unidade independente da implantação (código em si)*
- *Recursos: Componentes usados pela função (APIs, serviços AWS...)*

**Lambda Microservices** -> a aplicação deve ser arquitetada na forma de funções desaclopadas (sistemas independentes).

**Lambda Stateless Functions** -> Os containers são detruídos após a execução da função, não armazenam estado.

**Lambda Cold Starts** -> Latência para responder um evento quando ativado.

**Amazon API Gateway** -> Serviço de gerenciamento de APIs totalmente gerenciado. Criar, publicar, manter e monitorar APIs RESTful e Websockets; *(endpoints)*. 