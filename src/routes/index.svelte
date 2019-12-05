<script>
	import Header from '../components/Header/header.svelte';
	import Context from '../components/Context/context.svelte';
	import { user } from '../api/user.js'
</script>
<style lang="scss">
	.body{
		max-width: 100vw;
		height: auto;
	}
	.wrap{
		width: 80%;
		margin: 10vh auto;
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
		<Context 
			title="Habilidades Técnicas"
			hasDotSkill='true'
			skillList={user.user.profile.skills}
		/>
		<Context 
			title="Experiencia"
			hasExperience={true}
			expList={user.user.experience}
		/>
	</div>
</div>


