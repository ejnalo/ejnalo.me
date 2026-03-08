<script setup lang="ts">
	import { motion } from 'motion-v';

	defineProps<{
		name: string
		icon: string
		learning?: boolean
	}>();
</script>
<template>
	<motion.button>
		<div
			class="cursor-pointer flex items-center gap-2 bg-surface border-2 border-surface-b rounded-full w-fit h-12 pl-3 pr-5 transition-all hover:scale-102"
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
		>
			<img v-if="icon.startsWith('/')" :src="icon" class="w-6 h-6 object-contain" />
			<span v-else class="w-6 h-6 flex items-center justify-center rounded-full text-xl">{{ icon }}</span>
			<div class="flex flex-col -space-y-1 text-left">
				<span class="block font-medium text-left" :class="learning ? 'text-sm' : ''">{{ name }}</span>
				<span v-if="learning" class="block text-xs text-primary italic">Débutant</span>
			</div>
		</div>
	</motion.button>
</template>