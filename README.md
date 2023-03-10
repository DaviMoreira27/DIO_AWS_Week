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

*Servi??o AWS desenvolvido por meio da AWS Cloud Week da Digital Innovation One*

## Passos para o projeto

- Clonar o reposit??rio
- Instalar as depend??ncias com o comando ```npm install```
- Atualizar o arquivo ```.env``` com a sua chave do OpenAI
- Compactar o conte??do do projeto em um arquivo ```.zip```

## Na AWS

- Acessar o console da AWS
- Criar uma fun????o no servi??o AWS Lambda
- Fazer o upload do conte??do do arquivo ```.zip``` no c??digo da fun????o
- Acessar o servi??o AWS API Gateway
- Criar uma API Websocket
- Criar os endpoints (obs: os tr??s primeiros endpoints marcados com ```$``` s??o padr??o de uma API Websocket do API Gateway):
    - ```$connect```
    - ```$disconnect```
    - ```$default```
    - ```setName```
    - ```sendPublic```
    - ```sendPrivate```
    - ```sendBot```

## Testando o Websocket

- Baixar a depend??ncia ```wscat``` atrav??s do comando ```npm i -g wscat```. 
- Utilizar o par??metro ```-g``` para instalar de forma global no sistema operacional, podendo cham??-la de fora do projeto.

### Utilizando o wscat

- ```wscat -c url_de_conexao_do_websocket```
- Exemplo de chamada ```{"action":"sendPublic", "message":"Hello World!"}```


- Desenvolvimento AWS Cloud*, 
- Desenvolvimento Back-end serveless chat*, 
- integra????o front-end react com back-end*

**Ser?? utilizado o AWS Lambda para a l??gica de neg??cio**

- O Amazon API Gateway ser?? utilizado para criar o Websocket para receber conex??es dos clientes e enviar mensagens. Ele dar?? suporte para as rotas que gerenciam a conex??o dos clientes

**API REST Vs Websockets** -> Websockets tem uma baixa lat??ncia por requisi????o. Ideal para casos com alta frequ??ncia de comunica????o. REST APIs s??o melhores em casos de CRUD.

**SSH** -> Secure Socket Shell, um protocolo de seguran??a de troca de arquivos entre cliente de servidor.

**AWS Elastic (EC2)** -> Um servi??o que cria inst??ncias, fornece capacidade de computa????o escal??vel. podem ser conectadas via SSH ou pelo browser. *Alguel de computadores virtuais (VMs)*.

**Backend Serveless** -> A l??gica de neg??cios ?? executada em servi??os de computa????o em nuvem. Servi??os serveless AWS:

-*AWS Lambda*
-*Amazon API Gateway*
-*DynamoDB*
-*S3...*

**AWS Lambda** -> Permite a execu????o de c??digos em resposta a eventos, como uma chamada de API, upload de arquivo, etc.
?? enviado por meio de fun????es com alguns componentes principais:

- *Eventos: Desencadeia a execu????o de uma fun????o*
- *Fun????es: Unidade independente da implanta????o (c??digo em si)*
- *Recursos: Componentes usados pela fun????o (APIs, servi??os AWS...)*

**Lambda Microservices** -> a aplica????o deve ser arquitetada na forma de fun????es desaclopadas (sistemas independentes).

**Lambda Stateless Functions** -> Os containers s??o detru??dos ap??s a execu????o da fun????o, n??o armazenam estado.

**Lambda Cold Starts** -> Lat??ncia para responder um evento quando ativado.

**Amazon API Gateway** -> Servi??o de gerenciamento de APIs totalmente gerenciado. Criar, publicar, manter e monitorar APIs RESTful e Websockets; *(endpoints)*. 