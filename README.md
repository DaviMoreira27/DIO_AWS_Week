# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)

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