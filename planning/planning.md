# PilotApp

## Requirements

- [Node.js (20.17.0)](https://nodejs.org/pt/blog/release/v20.17.0) 

## Getting Started
First, to run planning you have to add a loopback address for IPv4 `localhost.nexatlas.com` to your hosts file.

1. On `/etc/hosts` add these lines:

```bash   
127.0.0.1 localhost.nexatlas.com
::1 localhost.nexatlas.com127.0.0.1 localhost.nexatlas.com
::1 localhost.nexatlas.com
```

2. Run this command to install front-end dependencies:
```bash
npm install
```

3. Run this command to install back-end dependencies:
```bash
cd backend && npm install
```


### Running the project

Once you have the loopback address for IPv4 `localhost.nexatlas.com` added to your hosts file: 
 
- `npm run start:dev`  runs the frontend (vite) and backend (tsx watch backend/src/server.ts) simultaneously.



**Note**:
- If you get stuck on loading the page, try to login at first on [https://app.nexatlas.com](https://app.nexatlas.com/) and then access [http://localhost.nexatlas.com:3000/](http://localhost.nexatlas.com:3000/) on your browser. If you still have problems, try to clear your browser cache and check if backend is running correctly.



### Adding labels, titles and descriptions (i18n tokens)

When you need to add more labels, titles, and descriptions to the project, you can use the `backend/src/i18n/translations/source` folder to add new tokens to the `en.json`, `es.json`, and `pt-br.json` files. For each new token, you must add the same key in all three files. After that, you need to run the script:


```bash
npm run build-translation-typing-file
```


The `build-translation-typing-file` script runs a Node.js script (translationTypingFileGenerator.js) to generate a TypeScript typing file for translations. It then applies ESLint (eslint ./src/i18n/ITranslations.ts --fix) and Prettier (prettier --write ./src/i18n/ITranslations.ts) to format and fix issues in the generated file.

Once you run the script, the translation files will be updated, and you can use the new tokens in your project.

Check this [Instruções para o Processo De Tradução](https://www.notion.so/nexatlas/Instru-es-para-o-Processo-De-Tradu-o-d9c8018579404a44bb9d61c94616c8ba?pvs=4) to help you creating names for the tokens.
