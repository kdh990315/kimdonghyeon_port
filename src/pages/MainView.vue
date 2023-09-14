<template>
	<HeaderView></HeaderView>
	<IntroSection></IntroSection>
	<AboutMeView></AboutMeView>
	<ProjectView></ProjectView>
	<ScriptView></ScriptView>
	<FooterView></FooterView>
</template>

<script>
import AboutMeView from '@/components/AboutMeView.vue';
import FooterView from '@/components/FooterView.vue';
import HeaderView from '@/components/HeaderView.vue';
import IntroSection from '@/components/IntroSection.vue';
import ProjectView from '@/components/ProjectView.vue';
import ScriptView from '@/components/ScriptView.vue';


export default {
	components: {
		HeaderView,
		IntroSection,
		AboutMeView,
		ProjectView,
		ScriptView,
		FooterView
	},
}
</script>