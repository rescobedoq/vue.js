<template>
	<div id="my-component">
		<h1 v-if="isVisible">{{ message }}</h1>
        <button v-on:click="sayHello">Toggle Visibility</button>
        <input v-model="message">
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
        },
        sayHello(){
            alert('Hello');
        }
    }
}
</script>