<script setup lang="ts">
	import { AcademicCapIcon, BeakerIcon, DocumentArrowDownIcon, MapPinIcon } from '@heroicons/vue/24/solid';

	import Project from '~/components/layout/Project.vue';
	import Skill from '~/components/Skill.vue';

	import { motion } from 'motion-v';

	import { tools } from '~/data/tools';

	const profile = ref<string>('creation');

	const isAboutImageHovered = ref<boolean>(false);
</script>
<template>
	<header
		id="header"
		class="flex flex-col gap-8 items-center justify-center bg-[url('/bg-header.png')] bg-cover bg-center bg-no-repeat h-screen pt-16 xl:bg-contain"
	>
		<div class="grid grid-rows-6 justify-end items-end bg-primary rounded-full w-64 h-64">
			<div class="row-start-2 row-span-6  justify-start w-64 h-80 rounded-b-full overflow-hidden">
				<motion.img
					id="moi"
					src="/moi.png"
					class="w-64 h-80 object-cover"
					:initial="{
						transform: 'translateY(140px) scale(25%)'
					}"
					:whileInView="{
						transform: 'translateY(0) scale(100%)'
					}"
				/>
			</div>
		</div>
		<h1 class="text-primary text-6xl font-display">Loan</h1>
		<div class="flex gap-2 justify-center items-center max-xs:flex-col">
			<a href="#footer" class="cursor-pointer flex justify-center items-center gap-1 bg-primary text-white font-medium rounded-full w-fit px-5 py-3 hover:scale-105 transition-all duration-200 not-[&:hover]:animate-debounce">Me contacter</a>
			<a href="https://portfolio.ejnalo.me/" class="cursor-pointer flex justify-center items-center gap-1 bg-navbar text-primary font-medium rounded-full w-fit px-5 py-3 hover:scale-105 transition-all duration-200 not-[&:hover]:animate-debounce"><DocumentArrowDownIcon class="w-5 h-5" /> Portfolio</a>
		</div>
	</header>
	<main class="p-8 space-y-6 sm:p-12 sm:space-y-12 md:px-32 lg:px-48 xl:px-72 2xl:px-96">
		<section
			id="about"
			class="grid grid-cols-1 gap-8 items-center max-lg:text-center lg:grid-cols-5"
		>
			<article class="space-y-2 sm:space-y-4 max-lg:row-start-2 lg:col-span-3">
				<motion.h2
					class="text-primary text-4xl font-bold font-title"
					:initial="{
						transform: 'translateY(32px)',
						opacity: 0
					}"
					:whileInView="{
						transform: 'translateY(0)',
						opacity: 1
					}"
					:transition="{
						duration: 0.5,
						delay: 0.1,
						ease: 'easeOut'
					}"
				>
					À propos de moi
				</motion.h2>
				<motion.p
					:initial="{
						transform: 'translateY(32px)',
						opacity: 0
					}"
					:whileInView="{
						transform: 'translateY(0)',
						opacity: 1
					}"
					:transition="{
						duration: 0.5,
						delay: 0.25,
						ease: 'easeOut'
					}"
				>
					J'ai 17 ans et je suis actuellement en 1ère année de <span class="bg-linear-to-r from-primary to-primary bg-size-[0%_3px] bg-no-repeat bg-bottom duration-200 hover:bg-size-[100%_3px]">BUT MMI</span> (Métiers du Multimédia et de l'Internet) à l'IUT de Vélizy. Passionné par la programmation, la musique et la photographie, je consacre mon temps libre à marier esthétique et fonctionnalité. Mon objectif ? Rendre le monde agréable à regarder.
				</motion.p>
			</article>
			<motion.aside
				class="cursor-pointer space-y-2 lg:col-span-2"
				@hoverStart="() => { isAboutImageHovered = true }"
				@hoverEnd="() => { isAboutImageHovered = false }"
				:initial="{
					opacity: 0,
					x: 360,
					y: 120,
					rotate: '30deg'
				}"
				:whileInView="{
					opacity: 1,
					x: 0,
					y: 0,
					rotate: '0deg'
				}"
				:transition="{
					duration: 0.5,
					ease: 'easeOut'
				}"
			>
				<motion.img
					src="/mmi.png"
					class="z-50 rounded-2xl w-full aspect-4/3 object-cover"
					:whileInView="{
						rotate: '2.5deg'
					}"
					:transition="{
						type: 'tween',
						duration: 0.4,
						ease: 'easeOut'
					}"
					:animate="{
						y: isAboutImageHovered ? -4 : 32,
						scale: isAboutImageHovered ? 1.05 : 1,
					}"
				/>
				<motion.legend
					:animate="{
						color: isAboutImageHovered ? 'inherit' : '#ffffff',
						y: isAboutImageHovered ? 4 : -32,
						scale: isAboutImageHovered ? 1 : .85,
						rotate: isAboutImageHovered ? 0 : 2.5
					}"
					:transition="{
						type: 'tween',
						duration: 0.3,
						ease: 'easeOut'
					}"
					class="z-0 text-sm"
				>
					Là, on relève la température en Kelvin de la lumière de la Tour Eiffel.
				</motion.legend>
			</motion.aside>
		</section>
		<section
			id="formation"
			class="flex flex-col items-center justify-center w-full space-y-6 sm:space-y-12"
		>
			<h2 class="text-center text-primary text-4xl font-bold font-title">Formation</h2>
			<div
				class="grid gap-2 w-full sm:grid-cols-2"
			>
				<motion.div
					class="bg-surface border-2 border-surface-b rounded-3xl p-6 space-y-2 cursor-pointer"
					:initial="{
						opacity: 0,
						scale: .5
					}"
					:whileInView="{
						opacity: 1,
						scale: 1,
						transition: {
							type: 'spring',
							duration: 0.25,
							delay: 0
						}
					}"
					:whileHover="{
						scale: 1.02,
						transition: {
							delay: 0
						}
					}"
				>
					<div class="flex items-center bg-primary text-white text-sm font-medium border-2 border-surface-b rounded-full w-fit px-3 h-8 mx-auto -mb-8 -translate-y-10">2025 - Aujourd'hui</div>
					<h3 class="text-xl font-semibold"><a class="decoration-2 underline-offset-1 duration-200 hover:underline" href="https://www.uvsq.fr/but-metiers-du-multimedia-et-de-linternet-mmi">BUT Métiers du Multimedia et d'Internet</a></h3>
					<ul class="list-none">
						<li class="flex items-center gap-1 font-medium"><MapPinIcon class="w-5 h-5"/> IUT de Vélizy, Vélizy-Villacoublay (78140)</li>
						<li class="flex items-center gap-1 font-medium"><BeakerIcon class="w-5 h-5 mt-0.5"/> Principaux axes:</li>
						<ul class="list-disc ml-10">
							<li>Création graphique, audiovisuel</li>
							<li>Dév. Web, intégration, ergonomie</li>
							<li>Communication, gestion de projet</li>
						</ul>
					</ul>
				</motion.div>
				<motion.div
					class="bg-surface border-2 border-surface-b rounded-3xl p-6 space-y-2 cursor-pointer"
					:initial="{
						opacity: 0,
						scale: .5
					}"
					:whileInView="{
						opacity: 1,
						scale: 1,
						transition: {
							type: 'spring',
							duration: 0.25,
							delay: 0.025
						}
					}"
					:whileHover="{
						scale: 1.02,
						transition: {
							delay: 0
						}
					}"
				>
					<div class="flex items-center bg-primary text-white text-sm font-medium border-2 border-surface-b rounded-full w-fit px-3 h-8 mx-auto -mb-8 -translate-y-10">2022 - 2025</div>
					<h3 class="text-xl font-semibold">Baccalauréat Général</h3>
					<ul class="list-none">
						<li class="flex items-center gap-1 font-medium"><MapPinIcon class="w-5 h-5"/> Lycée La Source, Meudon (92190)</li>
						<li class="flex items-center gap-1 font-medium"><AcademicCapIcon class="w-5 h-5"/> Avec mention</li>
						<li class="flex items-center gap-1 font-medium"><BeakerIcon class="w-5 h-5"/> Spécialités:</li>
						<ul class="list-disc ml-10">
							<li>Numérique & Sciences Informatiques</li>
							<li>Cinéma, Audiovisuel</li>
							<li class="opacity-50">Mathématiques</li>
						</ul>
					</ul>
				</motion.div>
			</div>
			<div
				class="grid gap-2 w-full sm:grid-cols-2"
			>
				<motion.div
					class="bg-surface border-2 border-surface-b rounded-3xl p-6 space-y-2 cursor-pointer"
					:initial="{
						opacity: 0,
						scale: .5
					}"
					:whileInView="{
						opacity: 1,
						scale: 1,
						transition: {
							type: 'spring',
							duration: 0.25,
							delay: 0.05
						}
					}"
					:whileHover="{
						scale: 1.02,
						transition: {
							delay: 0
						}
					}"
				>
					<div class="flex items-center bg-primary text-white text-sm font-medium border-2 border-surface-b rounded-full w-fit px-3 h-8 mx-auto -mb-8 -translate-y-10">2023 - Aujourd'hui</div>
					<h3 class="text-xl font-semibold">Percussions - 1er Cycle</h3>
					<ul class="list-none">
						<li class="flex items-center gap-1 font-medium"><MapPinIcon class="w-5 h-5"/> Atrium de Chaville</li>
						<li class="flex items-center gap-1 font-medium"><AcademicCapIcon class="w-5 h-5"/> Batterie, timbales, claviers</li>
					</ul>
				</motion.div>
				<motion.div
					class="bg-surface border-2 border-surface-b rounded-3xl p-6 space-y-2 cursor-pointer"
					:initial="{
						opacity: 0,
						scale: .5
					}"
					:whileInView="{
						opacity: 1,
						scale: 1,
						transition: {
							type: 'spring',
							duration: 0.25,
							delay: 0.075
						}
					}"
					:whileHover="{
						scale: 1.02,
						transition: {
							delay: 0
						}
					}"
				>
					<div class="flex items-center bg-primary text-white text-sm font-medium border-2 border-surface-b rounded-full w-fit px-3 h-8 mx-auto -mb-8 -translate-y-10">2019 - Aujourd'hui</div>
					<h3 class="text-xl font-semibold">Piano - 2nd Cycle</h3>
					<ul class="list-none">
						<li class="flex items-center gap-1 font-medium"><MapPinIcon class="w-5 h-5"/> Atrium de Chaville</li>
						<li class="flex items-center gap-1 font-medium"><AcademicCapIcon class="w-5 h-5"/> Cursus classique (2019) puis Jazz (2025)</li>
					</ul>
				</motion.div>
			</div>
		</section>
		<section
			id="skills"
			class="flex flex-col items-center justify-center w-full space-y-6"
		>
			<h2 class="text-center text-primary text-4xl font-bold font-title">Outils & compétences</h2>
			<nav class="flex gap-2 bg-surface border-2 border-surface-b rounded-full p-1 mx-auto">
				<button
					class="cursor-pointer font-medium rounded-full py-3 transition-all duration-200"
					:class="profile == 'creation' ? 'bg-primary text-white px-5 ml-0' : 'px-2 ml-3'"
					@click="profile = 'creation'"
				>
					Création graphique
				</button>
				<button
					class="cursor-pointer font-medium rounded-full py-3 transition-all duration-200"
					:class="profile == 'dev' ? 'bg-primary text-white px-5' : 'px-2'"
					@click="profile = 'dev'"
				>
					Développement
				</button>
				<button
					class="cursor-pointer font-medium rounded-full py-3 transition-all duration-200"
					:class="profile == 'music' ? 'bg-primary text-white px-5' : 'px-2'"
					@click="profile = 'music'"
				>
					Musique
				</button>
				<button
					class="cursor-pointer font-medium rounded-full py-3 transition-all duration-200"
					:class="profile == 'soft' ? 'bg-primary text-white px-5 mr-0' : 'px-2 mr-3'"
					@click="profile = 'soft'"
				>
					Soft Skills
				</button>
			</nav>
			<div v-if="profile == 'creation'" class="grid grid-cols-1 gap-6 w-full md:grid-cols-2">
				<div class="flex flex-wrap justify-center gap-1 h-fit">
					<h3 class="text-3xl text-center font-semibold w-full pb-2">Outils</h3>
					<Skill
						v-for="tool in tools.creation.tools"
						:key="tool.name"
						:name="tool.name"
						:icon="tool.icon"
						:learning="tool.learning"
					/>
				</div>
				<div class="flex flex-wrap justify-center gap-1 h-fit">
					<h3 class="text-3xl text-center font-semibold w-full pb-2">Compétences</h3>
					<Skill
						v-for="skill in tools.creation.skills"
						:key="skill.name"
						:name="skill.name"
						:icon="skill.icon"
						:learning="skill.learning"
					/>
				</div>
			</div>
			<div v-else-if="profile == 'dev'" class="grid grid-cols-1 gap-6 w-full md:grid-cols-2">
				<div class="flex flex-wrap justify-center gap-1 h-fit">
					<h3 class="text-3xl text-center font-semibold w-full pb-2">Langages</h3>
					<Skill
						v-for="tool in tools.dev.languages"
						:key="tool.name"
						:name="tool.name"
						:icon="tool.icon"
						:learning="tool.learning"
					/>
				</div>
				<div class="flex flex-wrap justify-center gap-1 h-fit">
					<h3 class="text-3xl text-center font-semibold w-full pb-2">Outils</h3>
					<Skill
						v-for="tool in tools.dev.tools"
						:key="tool.name"
						:name="tool.name"
						:icon="tool.icon"
						:learning="tool.learning"
					/>
				</div>
				<div class="col-span-2 flex flex-wrap justify-center gap-1 h-fit">
					<h3 class="text-3xl text-center font-semibold w-full pb-2">Compétences</h3>
					<Skill
						v-for="skill in tools.dev.skills"
						:key="skill.name"
						:name="skill.name"
						:icon="skill.icon"
						:learning="skill.learning"
					/>
				</div>
			</div>
			<div v-else-if="profile == 'music'" class="grid grid-cols-1 gap-6 w-full md:grid-cols-1">
				<div class="flex flex-wrap justify-center gap-1 h-fit">
					<h3 class="text-3xl text-center font-semibold w-full pb-2">Instruments</h3>
					<Skill
						v-for="instrument in tools.music.instruments"
						:key="instrument.name"
						:name="instrument.name"
						:icon="instrument.icon"
						:learning="instrument.learning"
					/>
				</div>
				<div class="flex flex-wrap justify-center gap-1 h-fit">
					<h3 class="text-3xl text-center font-semibold w-full pb-2">Compétences</h3>
					<Skill
						v-for="skill in tools.music.skills"
						:key="skill.name"
						:name="skill.name"
						:icon="skill.icon"
						:learning="skill.learning"
					/>
				</div>
			</div>
			<div v-else-if="profile == 'soft'" class="grid grid-cols-1 gap-2 w-full md:grid-cols-1">
				<div class="flex flex-wrap justify-center gap-1 h-fit">
					<h3 class="text-3xl text-center font-semibold w-full pb-2">Soft Skills</h3>
					<Skill
						v-for="skill in tools.soft.skills"
						:key="skill.name"
						:name="skill.name"
						:icon="skill.icon"
						:learning="skill.learning"
					/>
				</div>
			</div>
		</section>
		<section
			id="projets"
			class="flex flex-col items-center justify-center w-full space-y-6 sm:space-y-12"
		>
			<h2 class="text-center text-primary text-4xl font-bold font-title">Projets</h2>
			<div
				class="grid gap-2 w-full sm:grid-cols-2"
			>
				<Project
					name="Beam"
					desc="Petit réseau social Twitter-like pour moi et quelques amis, disopnible uniquement sur demande. Il compte actuellement une dizaine de membres dont moi."
					th="/banner_beam.png"
					role="Dev. solo"
					:start="new Date('2026-01-06')"
				/>
				<Project
					name="MMI.codes"
					desc="Portail d'outils complémentaires à ceux de l'UVSQ, permettant de visualiser les données publiques uniquement de manière plus ergonomique."
					href="https://github.com/MMI-CODES"
					th="/vencat.png"
					role="Dev. solo"
					:start="new Date('2025-03-23')"
				/>
				<Project
					name="Nation"
					desc="Serveur Discord censé représenter une démocratie, assistée par des bots et des services entièrement développés par mon coéquipier et moi."
					href="https://github.com/1nserv"
					th="/nation.png"
					role="Co-fondateur & Lead dev."
					:start="new Date('2024-06-17')"
					:end="new Date('2025-11-02')"
				/>
				<Project
					name="Bow / Arrowbit"
					desc="Langage de programmation écrit en Python, ayant pour but initial d'être intégré sur un projet que j'ai créé sur Scratch."
					href="https://github.com/ejnalo/arrowbit"
					th="/arrowbit.png"
					role="Dev. solo"
					:start="new Date('2023-11-01')"
					:end="new Date('2026-03-05')"
				/>
			</div>
		</section>
	</main>
	<footer
		id="footer"
		class="bg-surface rounded-t-4xl border-t-2 border-x-2 border-surface-b p-8 space-y-4 xs:mx-8 sm:p-12 sm:mx-12 sm:text-center md:mx-32 lg:mx-48 xl:mx-72 2xl:mx-96"
	>
		<h2 class="text-3xl font-medium -mb-2">Contact</h2>
		<p><a href="mailto:contact@ejnalo.me" class="font-medium">contact@ejnalo.me</a></p>
		<div class="flex justify-start gap-2 sm:justify-center">
			<a href="https://instagram.com/ejnalo" target="_blank" rel="noopener noreferrer" class="text-primary hover:text-primary-dark">
				<img src="@/assets/instagram.svg" alt="Instagram" class="w-6 h-6"/>
			</a>
			<a href="https://github.com/ejnalo" target="_blank" rel="noopener noreferrer" class="text-primary hover:text-primary-dark">
				<img src="@/assets/github.svg" alt="Github" class="w-6 h-6"/>
			</a>
			<a href="https://flickr.com/photos/ejnalo" target="_blank" rel="noopener noreferrer" class="text-primary hover:text-primary-dark">
				<img src="@/assets/flickr.svg" alt="Flickr" class="w-6 h-6"/>
			</a>
		</div>
	</footer>
</template>