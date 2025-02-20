# PilotApp

## Requirements

- [asdf](https://asdf-vm.com/) (Linux/Mac) - To get the same Node.js and JAVA version
- [Node.js (20.17.0)](https://nodejs.org/pt/blog/release/v20.17.0) (Windows)
- [JAVA JDK (17.0.11)](https://www.oracle.com/java/technologies/javase/17-0-11-relnotes.html) (Windows)
- [Android Studio](https://developer.android.com/studio?gad_source=1&gclid=Cj0KCQiAwtu9BhC8ARIsAI9JHakMDgxqXgZMkzwmiB8N-OhrjJjOIUgiI0VnSUhWullWMNl8fKYrljcaAihxEALw_wcB&gclsrc=aw.ds)


**Note:**: To install Node.js and Java specified for the project using asdf, just run:

```bash
asdf install
```



## Getting Started
First, to run React Native you have to add the enviroment variable to gradle file to guarantee the correct build of project and use of  [mapbox API](https://docs.mapbox.com/api/overview/). 

1. On `~/.gradle/gradle.properties` add this env:
   
`MAPBOX_DOWNLOADS_TOKEN=***********************************`


2. Run this command to install dependencies:
```bash
npm install
```


### Running the project

Once you have Android Studio Emulator running or any android device connected to your computer, open two terminals to run simultaneously:

- `npm run start` simply starts the Metro bundler, which is essential for serving your JavaScript bundle during development but doesn’t build or deploy the app itself.

- `npm run android` builds and deploys the Android app and starts logging, making it a one-stop command for running your app on Android.




### Adding labels, titles and descriptions (i18n tokens)

When you need to add more labels, titles, and descriptions to the project, you can use the `src/i18n/translations/source` folder to add new tokens to the `en.jsonc`, `es.jsonc`, and `pt-br.jsonc` files. For each new token, you must add the same key in all three files. After that, you need to run the script:


```bash
npm run build-translate-files
```


The script automates translation file management by first executing a custom Node.js script located at `./src/i18n/translations/source/process_files.js` to process raw translation data (which may include tasks such as merging files or extracting keys), then running ESLint with the auto-fix option on the translation directory to enforce coding standards, and finally applying Prettier to ensure consistent formatting and improved readability.

Once you run the script, the translation files will be updated, and you can use the new tokens in your project.
Once you run the script, the translation files will be updated and you can use the new tokens in your project.

Check this [Instruções para o Processo De Tradução](https://www.notion.so/nexatlas/Instru-es-para-o-Processo-De-Tradu-o-d9c8018579404a44bb9d61c94616c8ba?pvs=4) to help you creating names for the tokens.





