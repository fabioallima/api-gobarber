# api-gobarber
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

### Instalando e configurando ESLint:
> yarn add eslint -D

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