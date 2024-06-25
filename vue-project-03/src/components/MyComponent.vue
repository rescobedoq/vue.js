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