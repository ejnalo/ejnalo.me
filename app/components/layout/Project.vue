<script setup lang="ts">
import { motion } from 'motion-v';

	defineProps<{
		name: string
		desc: string
		th: string
		start?: Date
		end?: Date
		role?: string
		href?: string
	}>();
</script>
<template>
	<motion.a
		:href=href
		class="bg-surface border-2 border-surface-b rounded-3xl space-y-2 overflow-hidden cursor-pointer"
		:initial="{
			opacity: 0,
			scale: .5
		}"
		:whileInView="{
			opacity: 1,
			scale: 1,
			transition: {
				type: 'spring',
				duration: 0.25
			}
		}"
		:whileHover="{
			scale: 1.02
		}"
	>
		<img :src="th" class="w-full aspect-video object-cover" />
		<div class="p-6 pt-2 space-y-2">
			<div v-if="start" class="flex items-center bg-primary text-white text-sm font-medium rounded-full w-fit px-3 h-8">{{ end ? `${start.getFullYear()} - ${end.getFullYear()}` : start.getFullYear() }}</div>
			<h3 class="text-xl font-semibold">{{ role ? `${role} - ` : '' }} {{ name }}</h3>
			<p class="text-sm opacity-75">{{ desc }}</p>
		</div>
	</motion.a>
</template>