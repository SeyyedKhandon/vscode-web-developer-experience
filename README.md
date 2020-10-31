# Web Developer Experience Pack

### vscode-web-developer-experience

A collection/pack of extensions for Web Developers in VS Code

These are some of my favorite extensions to make web development easier.

### Pre-defined settings which you maybe want to use:

1. press `ctrl+shift+p`
2. type `settings`
3. click on `Prefrences: Open settings (JSON)` to open your settings.json file
4. add these lines of settings:

```json
  "workbench.iconTheme": "material-icon-theme",
  "workbench.colorTheme": "Atom One Dark",
  "files.autoSave": "afterDelay",
  "editor.fontFamily": "Fira Code",
  "editor.fontLigatures": "",
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.fontSize": 16,
  "window.zoomLevel": 1,
  "sync.gist": "70a5fe700fe4e46aebdf678a5c1db398",
  "typescript.preferences.importModuleSpecifier": "non-relative",
  "local-history.exclude": [
    "**/.history/**",
    "**/.vscode/**",
    "**/node_modules/**",
    "**/typings/**",
    "**/out/**",
    "**/Code/User/**"
  ]
```

5. add below lines to your `compilerOptions` in `tsconfig.json`:
   **Note** If you are using `tsnd` or what ever server which maybe cannt work with es module like `import {foo} from "@/fooModule";` or if you had problem like with this, you can skip this step.

```json
  "baseUrl": ".",
  "paths": {
    "@/*": ["src/*"]
  }
```

6. add `.history` to your `.gitignore`

7. `FiraCode Font` <img src="https://raw.githubusercontent.com/SeyyedKhandon/vscode-web-developer-experience/main/firacode.png" width="100"/>

   https://github.com/tonsky/FiraCode
   7.1 download zip file [FiraCode](https://github.com/tonsky/FiraCode/releases/download/5.2/Fira_Code_v5.2.zip)
   7.2. install `ttf` fonts in your OS
   7.3. add these two lines of settings to your vscode `settings.json` (which you did above)

```json
   "editor.fontFamily": "Fira Code",
   "editor.fontLigatures": ""
```

`More Fonts` check this https://www.programmingfonts.org/#cascadia-code

8. `sync settings` Global Settings:
   You may want to ignore some folder and files from being uploaded to your gist,
   you can add them in extention's config file which are present in `syncLocalSettings.json` inside `User` folder. e.g. in windows: `C:\Users\you_user_name\AppData\Roaming\Code\User`, add `Users` to `ignoreUploadFolders` like below:

```json
 "ignoreUploadFolders": [
    "workspaceStorage",
    "Users"
  ]
```

9.`key bindings`
As you may encounter shortcut-keys conflicts between extensions(e.g. bookmark, turboConsole, deploy has conflict on `ctrl+alt+l`). to avoid that, you can add these keybindings to your `keybindings.json` which is inside `C:\Users\you_user_name\AppData\Roaming\Code\User\keybindings.json`

```json
[
  {
    "key": "ctrl+shift+alt+l",
    "command": "bookmarks.jumpToNext",
    "when": "editorTextFocus"
  },
  {
    "key": "ctrl+alt+l",
    "command": "-bookmarks.jumpToNext",
    "when": "editorTextFocus"
  },
  {
    "key": "ctrl+shift+alt+k",
    "command": "extension.deploy.listen"
  },
  {
    "key": "ctrl+alt+l",
    "command": "-extension.deploy.listen"
  }
]
```

**Extension usage hints**

1. `deploy`
   To use this plugin, it is better to put your config files at the root of your project `.vscode/settings.json`, to make it local and prevent `sync settings` uploading it to your gist.github.com, because most of the time it includes username/password of your deploy server which is like below:

```json
{
  "deploy": {
    "targets": [
      {
        "type": "sftp",
        "name": "my files",
        "description": "deploy file/folder to remote server",
        "dir": "remote folder",
        "host": "your remote address",
        "port": 22,
        "user": "your username here",
        "password": "your password here"
      }
    ]
  }
}
```

`Note:` Also you maybe want to put `.vscode` or `.vscode/settings.json` into your `.gitignore` to prevent commit and push it to your git server.

Now you can rightclick on your file/folder and click `depoly` to safly deploy your desired files/folders.

## Extensions Included

- 1- [Better Comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments) - Improve your code commenting by annotating with alert, informational, TODOs, and more!

- 2- [Atom One Dark Theme](https://marketplace.visualstudio.com/items?itemName=akamud.vscode-theme-onedark) - One Dark Theme based on Atom

- 3- [open native terminal](https://marketplace.visualstudio.com/items?itemName=alexeyvax.vscode-open-native-terminal) - Open native terminal for vscode

- 4- [Static server](https://marketplace.visualstudio.com/items?itemName=axetroy.vscode-static-server) - Serve your static directory

- 5- [node-readme](https://marketplace.visualstudio.com/items?itemName=bengreenier.vscode-node-readme) - A vscode extension to view javascript module documentation in editor.

- 6- [Color Info](https://marketplace.visualstudio.com/items?itemName=bierner.color-info) - Provides quick information about css colors

- 7- [Turbo Console Log](https://marketplace.visualstudio.com/items?itemName=ChakrounAnas.turbo-console-log) - Automating the process of writing meaningful log messages.

- 8- [npm Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.npm-intellisense) - Visual Studio Code plugin that autocompletes npm modules in import statements

- 9- [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense) - Visual Studio Code plugin that autocompletes filenames

- 10- [gitignore](https://marketplace.visualstudio.com/items?itemName=codezombiech.gitignore) - Language support for .gitignore files. Lets you pull .gitignore files from the https://github.com/github/gitignore repository.

- 11- [Bracket Pair Colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer) - A customizable extension for colorizing matching brackets

- 12- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) - Integrates ESLint JavaScript into VS Code.

- 13- [NPM Browser](https://marketplace.visualstudio.com/items?itemName=dennisvhest.npm-browser) - Easily search, install and keep track of NPM packages from within Visual Studio Code.

- 14- [Git History](https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory) - View git log, file history, compare branches or commits

- 15- [GitLens — Git supercharged](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens) - Supercharge the Git capabilities built into Visual Studio Code — Visualize code authorship at a glance via Git blame annotations and code lens, seamlessly navigate and explore Git repositories, gain valuable insights via powerful comparison commands, and so much more

- 16- [HTML CSS Support](https://marketplace.visualstudio.com/items?itemName=ecmel.vscode-html-css) - CSS support for HTML documents

- 17- [npm](https://marketplace.visualstudio.com/items?itemName=eg2.vscode-npm-script) - npm support for VS Code

- 18- [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) - Code formatter using prettier

- 19- [Auto Close Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag) - Automatically add HTML/XML close tag, same as Visual Studio IDE or Sublime Text

- 20- [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag) - Auto rename paired HTML/XML tag

- 21- [Git History Diff](https://marketplace.visualstudio.com/items?itemName=huizhou.githd) - View git history. View diff of committed files. View git blame info. View stash details.

- 22- [CodeMetrics](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-codemetrics) - Computes complexity in TypeScript / JavaScript files.

- 23- [Image preview](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-gutter-preview) - Shows image preview in the gutter and on hover

- 24- [Diff Folders](https://marketplace.visualstudio.com/items?itemName=L13RARY.l13-diff) - Compare two folders in Visual Studio Code

- 25- [vuex peek](https://marketplace.visualstudio.com/items?itemName=Mcbai.vscode-vuex-peek) - Allows peek and goto vuex definition for Vue components

- 26- [Git Graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph) - View a Git Graph of your repository, and perform Git actions from the graph.

- 27- [Sort Typescript Imports](https://marketplace.visualstudio.com/items?itemName=miclo.sort-typescript-imports) - Sorts import statements in Typescript code

- 28- [DotENV](https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv) - Support for dotenv file syntax

- 29- [HTMLHint](https://marketplace.visualstudio.com/items?itemName=mkaufman.HTMLHint) - VS Code integration for HTMLHint - A Static Code Analysis Tool for HTML

- 30- [Deploy](https://marketplace.visualstudio.com/items?itemName=mkloubert.vs-deploy) - Commands for deploying files of your workspace to a destination.

- 31- [SCSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=mrmlnc.vscode-scss) - Advanced autocompletion and refactoring support for SCSS

- 32- [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker) - Makes it easy to create, manage, and debug containerized applications.

- 33- [Abracadabra, refactor this!](https://marketplace.visualstudio.com/items?itemName=nicoespeon.abracadabra) - Automated refactorings for VS Code, in JavaScript and TypeScript.

- 34- [Hocus Pocus](https://marketplace.visualstudio.com/items?itemName=nicoespeon.hocus-pocus) - Make useful things appear out of the void, in JavaScript and TypeScript.

- 35- [Vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur) - Vue tooling for VS Code

- 36- [Material Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme) - Material Design Icons for Visual Studio Code

- 37- [VSCode React Refactor](https://marketplace.visualstudio.com/items?itemName=planbcoding.vscode-react-refactor) - Recompose your overgrown JSX without worrying about the given data.

- 38- [Git File History](https://marketplace.visualstudio.com/items?itemName=pomber.git-file-history) - Modern, fast and intuitive tool for browsing the history and files in any git repository

- 39- [CSS Peek](https://marketplace.visualstudio.com/items?itemName=pranaygp.vscode-css-peek) - Allow peeking to css ID and class strings as definitions from html files to respective CSS. Allows peek and goto definition.

- 40- [CSS Navigation](https://marketplace.visualstudio.com/items?itemName=pucelle.vscode-css-navigation) - Allows Go to Definition from HTML to CSS; provides Completion and Workspace Symbols for class & id name; supports CSS, Sass, Less languages.

- 41- [Paste JSON as Code](https://marketplace.visualstudio.com/items?itemName=quicktype.quicktype) - Copy JSON, paste as Go, TypeScript, C#, C++ and more.

- 42- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) - Launch a development local Server with live reload feature for static & dynamic pages

- 43- [Partial Diff](https://marketplace.visualstudio.com/items?itemName=ryu1kn.partial-diff) - Compare (diff) text selections within a file, across files, or to the clipboard

- 44- [JavaScript Booster](https://marketplace.visualstudio.com/items?itemName=sburg.vscode-javascript-booster) - Boost your productivity with advanced JavaScript/TypeScript refactorings and commands

- 45- [Vue VSCode Snippets](https://marketplace.visualstudio.com/items?itemName=sdras.vue-vscode-snippets) - Snippets that will supercharge your Vue workflow

- 46- [Settings Sync](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync) - Synchronize Settings, Snippets, Themes, File Icons, Launch, Keybindings, Workspaces and Extensions Across Multiple Machines Using GitHub Gist.

- 47- [Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced) - Markdown Preview Enhanced ported to vscode

- 48- [SonarLint](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarlint-vscode) - SonarLint is an IDE extension that helps you detect and fix quality issues as you write code in JavaScript, TypeScript, Python, Java, HTML and PHP.

- 49- [React PropTypes Generate](https://marketplace.visualstudio.com/items?itemName=suming.react-proptypes-generate) - Auto generate react's propTypes

- 50- [Formatting Toggle](https://marketplace.visualstudio.com/items?itemName=tombonnike.vscode-status-bar-format-toggle) - A VS Code extension that allows you to toggle the formatter (Prettier, Beautify, …) ON and OFF with a simple click.

- 51- [Sort lines](https://marketplace.visualstudio.com/items?itemName=Tyriar.sort-lines) - Sorts lines of text

- 52- [Sort package.json](https://marketplace.visualstudio.com/items?itemName=unional.vscode-sort-package-json) - Sort package.json

- 53- [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens) - Improve highlighting of errors, warnings and other language diagnostics.

- 54- [Reopen Closed Tab](https://marketplace.visualstudio.com/items?itemName=uyiosa-enabulele.reopenclosedtab) - A very light-weight extension that simply adds the classic 'Reopen Closed Editor' item to the Title Tab menu

- 55- [Conventional Commits](https://marketplace.visualstudio.com/items?itemName=vivaxy.vscode-conventional-commits) - 💬Conventional Commits for VSCode.

- 56- [Import Cost](https://marketplace.visualstudio.com/items?itemName=wix.vscode-import-cost) - Display import/require package size in the editor

- 57- [Local History](https://marketplace.visualstudio.com/items?itemName=xyz.local-history) - Save files into local history

- 58- [Sort JS object keys](https://marketplace.visualstudio.com/items?itemName=zengxingxin.sort-js-object-keys) - An extension to sort the js object keys

## Relevant Links

- [Github](https://github.com/SeyyedKhandon/vscode-web-developer-experience)
- [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=SeyyedKhandon.vscode-web-developer-experience)

**Enjoy!**
