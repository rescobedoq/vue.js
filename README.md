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
```
```bash
sudo apt-get install npm
```
```bash
node --version
```
```bash
v20.13.0
```
```bash
npm --version
```
```bash
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
√ Add TypeScript? ... No
√ Add JSX Support? ... No
√ Add Vue Router for Single Page Application development? ... No 
√ Add Pinia for state management? ... No
√ Add Vitest for Unit Testing? ... No
√ Add an End-to-End Testing Solution? » No
√ Add ESLint for code quality? ... Yes
√ Add Prettier for code formatting? ... No
√ Add Vue DevTools 7 extension for debugging? (experimental) ... No

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
```
```bash
npm install
```

### Iniciar el servidor (Development)
```bash
npm run dev
```

```bash
  ➜  Local:   http://localhost:5173/
```

![vue-project-01](/images/vue-project-01.png)

### Proyecto Vue.js directamente desde una CDN (Content delivery network)
```bash
mkdir vue-project-02
```
```bash
cd vue-project-02
```
```bash
vim index.html
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
```bash
mkdir js
```
```bash
vim js/script-01.js
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

### Proyecto creado desde el CLI de Vue.js

```bash
npm install -g @vue/cli
```
```bash
vue --version
```
```bash
@vue/cli 5.0.8
```
```bash
vue create vue-project-03
```
```bash
Vue CLI v5.0.8
? Please pick a preset: Default ([Vue 3] babel, eslint)
```
```bash
cd vue-project-03
```
```bash
npm run serve
```
```bash
  DONE  Compiled successfully in 6715ms 3:23:53 p. m.

  App running at:
  - Local:   http://localhost:8080/
  - Network: http://192.168.1.18:8080/

  Note that the development build is not optimized.
  To create a production build, run npm run build.
```

![vue-project-03](/images/vue-project-03.png)

```bash
[ROOT-PROJECT]
|-- README.md
|-- babel.config.js
|-- jsconfig.json
|-- node_modules
|-- package-lock.json
|-- package.json
|-- public
|   |-- favicon.ico
|   `-- index.html
|-- src
|   |-- App.vue
|   |-- assets
|   |-- components
|   `-- main.js
`-- vue.config.js
```

### Componentes Vue
- Un componente Vue es una instancia reutilizable con un nombre que se puede usar como un elemento personalizado en el HTML. Los componentes pueden tener su propio estado, métodos, calculos, estilos, etc. Se le puede considerar un bloque de contrucción dentro de la aplicación.

```bash
vim src/components/MyComponent.vue
```

> src/components/MyComponent.vue

```js
<template>
	<div id="my-component">
		<h1>{{ message }}</h1>
	</div>
</template>

<script>
export default{
	name: 'MyComponent',
	data(){
		return{
			message: 'Hello World with Vue!'
		}
	}
}
</script>
```

```bash
vim src/App.vue
```

> src/App.vue

```js
<template>
  <img alt="Vue logo" src="./assets/logo.png">
<MyComponent />
</template>

<script>
import MyComponent from './components/MyComponent.vue'

export default {
  name: 'App',
  components: {
    MyComponent
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```

![vue-project-03_02](/images/vue-project-03_02.png)

### Directivas
- Las directivas son atributos especiales con el prefijo **'v'** que se puede aplicar a los elementos del DOM en las plantillas.

> src/componentes/MyComponent.vue

```js
<template>
	<div id="my-component">
		<h1 v-if="isVisible">{{ message }}</h1>
        <button v-on:click="event => isVisible = !isVisible">Toogle Visibility</button>
	</div>
</template>

<script>
export default{
	name: 'MyComponent',
	data(){
		return{
			message: 'Hello World with Vue!',
            isVisible: true
		}
	}
}
</script>
```

![vue-project-03_03](/images/vue-project-03_03.png)

### Métodos
- Son funciones que puedes definir dentro de tu componente y utilizar en tu plantilla

> src/componentes/MyComponent.vue

```js
<template>
	<div id="my-component">
		<h1 v-if="isVisible">{{ message }}</h1>
        <button v-on:click="toggleVisibility">Toggle Visibility</button>
	</div>
</template>

<script>
export default{
	name: 'MyComponent',
	data(){
		return{
			message: 'Hello World with Vue!',
            isVisible: true
		}
	},
    methods:{
        toggleVisibility(){
            this.isVisible = !this.isVisible;
        }
    }
}
</script>
```

![vue-project-03_03](/images/vue-project-03_03.png)



## Actividades
1. Registrese en CodePen con su cuenta google institucional o su cuenta GitHub asociada a su cuenta institucional y realice lo ejercicios del tutorial de Vue.js en https://vuejs.org/tutorial/. (El editor Vue.js en CodePen es https://codepen.io/pen/editor/vue)
Utilice el estandar **vue.js-01, vue.js-02, etc.**

![vue.js-01](/images/vue.js-01.png)

No olvide de cambiar a la versión Vue.js 3.

![codepen-js-vue3](/images/codepen-js-vue3.png)

2. Lea los estilos de la API de Vue.js en https://vuejs.org/guide/introduction.html#api-styles y responda ¿Con cuál de los estilos se siente familiarizado?
Luego, agregue cada uno de los ejemplos oficiales en https://vuejs.org/examples/ a su CodePen.
Utilice el estandar **vue.js-01, vue.js-02, etc.**

![vue.js-example-style-options-api](/images/vue.js-example-style-options-api.png)

![vue.js-example-style-options-composition](/images/vue.js-example-style-options-composition.png)

## Referencias
- [Inicio rápido](https://vuejs.org/guide/quick-start.html)
- [Introducción](https://vuejs.org/guide/introduction)
- [Ejemplos](https://vuejs.org/examples)
- [Playground](https://play.vuejs.org/)
- [CodePen Vue.js editor](https://codepen.io/pen/editor/vue)
- [CodePen Examples](https://codepen.io/vuejs-examples)
- [Vue Tutorial](https://www.w3schools.com/vue/)
- [What is Vue.js?](https://www.w3schools.com/whatis/whatis_vue.asp)
- [Tutorial de VueJS: Aprende creando un programa sencillo](https://codigonaranja.com/tutorial-de-vuejs)
- [Video tutorials on VueMastery](https://www.vuemastery.com/courses/)
- [Official Vue.js Certification](https://certificates.dev/vuejs)
- [Free Weekend](https://certificates.dev/vuejs/free-weekend)
