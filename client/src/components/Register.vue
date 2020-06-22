<template>
  <div class="hello">
	  <h1>Register</h1>

	  <input
	  	type="email"
		name="email"
		v-model="email"
		placeholder="email">

	<input
		type="password"
		v-model="password"
		name="password">

	<button
		@click="register"
		>Register</button>
  </div>
</template>

<script lang="ts">
import AuthenticationService from '@/services/AuthenticationService'
export default {
	data() {
		return {
			email: '',
			password: ''
		}
	},
	methods: {
		async register () {
			const response = await AuthenticationService.register({
				email: this.email,
				password: this.password
			})
			console.log(response.data)
		}
	},
}
/*
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class HelloWorld extends Vue {
  @Prop() private msg!: string;
}
*/
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
