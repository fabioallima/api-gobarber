# api-gobarber

## Como executar o projeto?

### Docker:

#### Criar Imagem Docker do PostgresSQL (Banco Relacional):
> docker run --name database-postgres -e POSTGRES_PASSWORD=docker -p 5432:5432 -d postgres

#### Criar Imagem Docker do MongoDB (Banco não relacional):
> docker run --name mongobarber -p 27017:27017 -d -t mongo

#### Criar Imagem Docker do Redis (Banco Chave Valor):
> docker run --name redisbarber -p 6379:6379 -d -t redis:alpine

#### Listar todos os containers que estão em execução:
> docker ps

#### Listar todos os containers criados:
> docker ps -a

#### Parar container em execução:
> docker stop "nome-container" (ex: database-postgres)

#### Iniciar container novamente:
> docker start "nome-container" (ex: database-postgres)

#### Ver Logs do Container:
> docker logs "nome-container" (ex: database-postgres)

Criar diretório config dentro do diretório src e dentro de config criar os arquivos:

*`auth.js`*:

```javascript
export default {
  secret: 'configurarPalavraSecreta',
  expiresIn: 'TempoDeExpiração',
};
```

*`database.js`*:

```javascript
module.exports = {
  dialect: 'postgres',
  host: 'localhost',
  username: 'postgres',
  password: 'docker',
  database: 'gobarber',
  define: {
    timestamps: true,
    underscored: true,
    underscoredAll: true,
  },
};
```

*`mail.js`*:

```javascript
export default {
  host: '',
  port: '',
  secure: false,
  auth: {
    user: '',
    pass: '',
  },
  default: {
    from: 'Equipe GoBarber <noreply@gobarber.com>',
  },
};
```

Criado os arquivos execute *`yarn`* para baixar as dependências, *`yarn dev`* para executar o projeto e *`yarn queue`* para executar fila de jobs

## Configurar VSCode:

### Configuração *`settings.json`*:

```javascript
{
    "workbench.iconTheme": "material-icon-theme",
    //"explorer.confirmDelete": false,
    "[javascript]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "workbench.colorTheme": "Dracula",
    "emmet.includeLanguages": {
        "javascript": "javascriptreact",
        "vue-html": "html",
        "razor": "html",
        "plaintext": "jade"
    },
    "emmet.syntaxProfiles": {
        "javascript": "jsx"
    },
    "colorInfo.fields": [
        "hex"
    ],
    "colorInfo.excludedFields": [],
    "editor.renderIndentGuides": false,
    "editor.fontSize": 14,
    "editor.rulers": [
        80,
        110
    ],
    "editor.renderLineHighlight": "gutter",
    "editor.tabSize": 2,
    "terminal.integrated.fontSize": 14,
    "breadcrumbs.enabled": true,
    // ESLint settings
    "editor.formatOnSave": true,
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    },
    "eslint.validate": [
        "javascript",
        "javascriptreact",
        "typescript",
        "typescriptreact"
    ],
    "files.eol": "\n",
    "explorer.compactFolders": false,
}
```

### Extensões: 

* Auto Close Tag
* Bookmarks
* Color Info
* Debugger for Chrome
* Dracula Official
* ESLint
* Git History
* Git Lens
* Guides
* HTML Snippets
* Live Server
* Prettier - Code formatter
* Rainbow Brackets
* Rocketseat React Native
* Rocketseat ReactJS
* vscode-icons
* Color Highlight


## Node.js
### Instalação Express:
> yarn add express

### Instalação bcryptjs:
> yarn add bcryptjs

### Autenticação com JWT:
> yarn add jsonwebtoken

### YUP para fazer validações do Request:
> yarn add yup

### Multer (Node multipart/form-data):
> yarn add multer

### Instalando Biblioteca para lidar com datas:
> yarn add date-fns@next

### NodeMailer (Biblioteca para envio de email):
> yarn add nodemailer

### Configurando Template de Email:
> yarn add express-handlebars nodemailer-express-handlebars

### Controle de filas:
> yarn add bee-queue

### Instalando e configurando ESLint:
> yarn add eslint -D

### Instalação Mongoose 
* Mongoose é uma biblioteca do Nodejs que proporciona uma solução baseada em esquemas para modelar os dados da sua aplicação. Ele fornece um mapeamento de objetos do MongoDB similar ao ORM (Object Relational Mapping), ou ODM (Object Data Mapping) no caso do Mongoose. Isso significa que o Mongoose traduz os dados do banco de dados para objetos JavaScript para que possam ser utilizados por sua aplicação.
> yarn add mongoose

### Instalação Sequelize (ORM) : https://blog.rocketseat.com.br/nodejs-express-sequelize/

> yarn add sequelize
> yarn add sequelize-cli -D

#### Configuração do Sequelize para utilizar Postgres:
> yarn add pg pg-hstore

#### Utilizando o sequelize-cli para ajudar a criar as migrations:
> * yarn sequelize migration:create --name=create-users
##### ou
> * npx sequelize migration:create --name=create-users
##### ou 
> * node_modules/.bin/sequelize migration:create --name=create-users

#### Rodar Migration:
> yarn sequelize db:migrate

#### Desfazer última Migration:
> yarn sequelize db:migrate:undo

#### Desfazer última Migration:
> yarn sequelize db:migrate:undo:all


### Iniciando ESLint:
> yarn eslint --init
? How would you like to use ESLint? 
*  To check syntax only 
*  To check syntax and find problems 
* ❯ **To check syntax, find problems, and enforce code style**

? What type of modules does your project use? 
* ❯ **JavaScript modules (import/export)**
*  CommonJS (require/exports) 
*  None of these

? Which framework does your project use? (Use arrow keys)
* React
* Vue.js 
* ❯ **None of these**

? Does your project use TypeScript? (y/N) : **N**

? Where does your code run? 
*  ◯ Browser
* ❯◯ Node
 
How would you like to define a style for your project? (Use arrow keys)
* ❯ **Use a popular style guide**
*  Answer questions about your style 
*  Inspect your JavaScript file(s)

? Which style guide do you want to follow? (Use arrow keys)
* ❯ **Airbnb (https://github.com/airbnb/javascript)**
*  Standard (https://github.com/standard/standard) 
*  Google (https://github.com/google/eslint-config-google)

? What format do you want your config file to be in? (Use arrow keys)
* ❯ **JavaScript**
*  YAML 
*  JSON

> yarn add prettier eslint-config-prettier eslint-plugin-prettier babel-eslint eslint-plugin-jest -D

cria um arquivo: *`.eslintrc.js`*:

```javascript
module.exports = {
  env: {
    commonjs: true,
    es6: true,
    node: true,
    jest: true,
  },
  extends: ['airbnb-base', 'prettier'],
  globals: {
    Atomics: 'readonly',
    SharedArrayBuffer: 'readonly',
  },
  parserOptions: {
    ecmaVersion: 2018,
  },
  plugins: ['jest'],
  rules: {
    camelcase: 'off',
    'jest/no-disabled-tests': 'warn',
    'jest/no-focused-tests': 'error',
    'jest/no-identical-title': 'error',
    'jest/prefer-to-have-length': 'warn',
    'jest/valid-expect': 'error',
  },
};
```

cria um arquivo: *`.prettierrc`*:

```javascript
{
  "singleQuote": true,
  "trailingComma": "es5"
}
```
