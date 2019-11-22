<script>
	import Header from '../components/Header/header.svelte';
	import Context from '../components/Context/context.svelte';
	import { experience } from '../api/experience.js'
	import { user } from '../api/user.js'
</script>
<style>
	.body{
		width: 100vw;
		height: 100vh;
	}
	.wrap{
		position: fixed;
		top: 12.5%;
		left: 15%;
	}
</style>

<svelte:head>
	<title>White4aPapers</title>
</svelte:head>

<div class="body">
	<div class="wrap">
		<Header
			src={user.avatar}
			name={user.name}
			surname={user.surname}
			ocupation={user.ocupation}
		/>
		<Context 
			title="Contatos" 
			hasInfo='true'
			infoList={user.user.profile.contacts}
		/>
		<Context 
			title="perfil" 
			hasTextField='true'
			textField={user.user.profile.about}
		/>
		<Context 
			title="Educação"
			hasDotList='true'
			doList={user.user.profile.academic}
		/>
	</div>
</div>


