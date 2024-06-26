<template>
	<div id="my-component">
		<h1 v-if="isVisible">{{ message }}</h1>
        <button @click="sayHello">Toggle Visibility</button>
        <input v-model="message">

        <ul>
            <li v-for="item in list" :key="item.id">{{ item.text }}</li>
        </ul>

	</div>
</template>

<script>
export default{
	name: 'MyComponent',
	data(){
		return{
			message: 'Hello World with Vue!',
            isVisible: true,
            list: [
                {id:1, text: 'First item'},
                {id:2, text: 'Second item'},
                {id:3, text: 'Third item'},
                {id:4, text: 'Four item'},
            ]
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