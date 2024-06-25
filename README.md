# Vue.js

![vue.js-logo](/images/vue.js-logo.png)

- Es un marco de trabajo (framework) en JavaScript.
- Es Software de código abierto (freesoftware) bajo la licencia MIT.
- Sirve para la construcción de Interfaces de Usuario.
- Fué creado por Evan You (Febrero, 2014).
- Evan trabajó para Google utilizando AngularJS
- Su última versión es 3.0.1 (Octubre, 2020).
- Esta basado en componentes.
- Extiende el HTML con directivas.
- Cuenta con un sistema de reactividad (Presición para renderizar).
- Posee varias formas de aplicar efectos de transicion (CSS, Hooks JS).
- Proporciona un Routing mapeando componentes de acuerdo a la ruta a la que pertenecen.
- Su sitio oficial es https://vuejs.org/

## Inicio rápido

### Instalar Node.js >= 18.3
```bash
sudo apt-get install nodejs
sudo apt-get install npm
node --version
v20.13.0
npm --version
10.5.2
```

### Crear un nuevo proyecto Vue.js
```bash
npm create vue@latest
```
```bash
Ok to proceed? (y) y

Vue.js - The Progressive JavaScript Framework

√ Project name: ... vue-project-01
√ Add TypeScript? ... No / Yes
√ Add JSX Support? ... No / Yes
√ Add Vue Router for Single Page Application development? ... No / Yes
√ Add Pinia for state management? ... No / Yes
√ Add Vitest for Unit Testing? ... No / Yes
√ Add an End-to-End Testing Solution? » No
√ Add ESLint for code quality? ... No / Yes
√ Add Prettier for code formatting? ... No / Yes
√ Add Vue DevTools 7 extension for debugging? (experimental) ... No / Yes

Scaffolding project in C:\Development\vue.js\vue-project-01...

Done. Now run:

  cd vue-project-01
  npm install
  npm run dev

npm notice
npm notice New minor version of npm available! 10.5.2 -> 10.8.1
npm notice Changelog: https://github.com/npm/cli/releases/tag/v10.8.1
npm notice Run npm install -g npm@10.8.1 to update!
npm notice
```

### Estructura inicial de un proyecto Vue.js
```bash
[ROOT-PROJECT]
│   .eslintrc.cjs
│   .gitignore
│   index.html
│   jsconfig.json
│   package.json
│   README.md
│   vite.config.js
│
├───.vscode
│       extensions.json
│       settings.json
│
├───public
│       favicon.ico
│
└───src
    │   App.vue
    │   main.js
    │
    ├───assets
    │       base.css
    │       logo.svg
    │       main.css
    │
    └───components
        │   HelloWorld.vue
        │   TheWelcome.vue
        │   WelcomeItem.vue
        │
        └───icons
                IconCommunity.vue
                IconDocumentation.vue
                IconEcosystem.vue
                IconSupport.vue
                IconTooling.vue
```

### Instalar dependencias (package.json)
```bash
cd vue-project-01
npm install
```

```bash
npm WARN deprecated inflight@1.0.6: This module is not supported, and leaks memory. Do not use it. Check out lru-cache if you want a good and tested way to coalesce async requests by a key value, which is much more comprehensive and powerful.
npm WARN deprecated glob@7.2.3: Glob versions prior to v9 are no longer supported
npm WARN deprecated rimraf@3.0.2: Rimraf versions prior to v4 are no longer supported
npm WARN deprecated @humanwhocodes/object-schema@2.0.3: Use @eslint/object-schema instead
npm WARN deprecated @humanwhocodes/config-array@0.11.14: Use @eslint/config-array instead

added 136 packages, and audited 137 packages in 18s

29 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
```

### Iniciar el servidor (Development)
```bash
npm run dev
```

```bash
> vue-project-01@0.0.0 dev
> vite


  VITE v5.3.1  ready in 543 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
  ➜  press h + enter to show help
```

![vue-project-01](/images/vue-project-01.png)

### Crear otro proyecto Vue directamente desde una CDN (Content delivery network)
```bash
mkdir vue-project-02
cd vue-project-02
vim index.html
mkdir js
vim js/script-01.js
```
> index.html
```html
<!DOCTYPE html>
<html>
<head>
<title>Vue project</title>
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
</head>
<body>

<div id="app">{{ message }}</div>

<script src="js/script-01.js"></script>
</body>
</html>
```
> js/script-01.js
```js
const { createApp, ref } = Vue

createApp({
setup() {
    const message = ref('Hello vue!')
    return {
    message
    }
}
}).mount('#app')
```

![vue-project-02](/images/vue-project-02.png)



## Actividades
1. Registrese en CodePen con su cuenta google institucional o su cuenta GitHub asociada a su cuenta institucional y realice el tutorial de Vue.js en https://vuejs.org/tutorial/. (El editor Vue.js en CodePen es https://codepen.io/pen/editor/vue)

![vue.js-01](/images/vue.js-01.png)

No olvide de cambiar a la versión Vue.js 3.

![codepen-js-vue3](/images/codepen-js-vue3.png)

2. Lea los estilos de la API de Vue.js en https://vuejs.org/guide/introduction.html#api-styles y responda ¿Con cuál de los estilos se siente familiarizado?

![vue.js-example-style-options-api](/images/vue.js-example-style-options-api.png)

![vue.js-example-style-options-composition](/images/vue.js-example-style-options-composition.png)

## Referencias
- Inicio rápido - https://vuejs.org/guide/quick-start.html
- https://vuejs.org/guide/introduction
- https://vuejs.org/examples
- https://play.vuejs.org/
- https://codepen.io/pen/editor/vue
- https://codepen.io/vuejs-examples
- https://www.w3schools.com/vue/
- https://www.w3schools.com/whatis/whatis_vue.asp
- https://codigonaranja.com/tutorial-de-vuejs#version-en-video
- https://www.vuemastery.com/courses/
- https://certificates.dev/vuejs
