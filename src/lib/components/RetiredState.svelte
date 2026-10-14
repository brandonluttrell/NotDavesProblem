<script lang="ts">
	import { BRAND_NAME, RETIREE_NAME } from '#lib/retirement';
</script>

<section
	class="flex max-w-xl flex-col items-center gap-4 px-6 text-center"
	aria-live="polite"
>
	<p
		class="font-display text-4xl font-bold leading-none tracking-tight text-primary sm:text-5xl md:text-6xl"
	>
		{BRAND_NAME}
	</p>
	<h1 class="text-2xl font-bold leading-tight sm:text-3xl md:text-4xl">He's retired.</h1>
	<p class="text-base leading-relaxed text-base-content/80 sm:text-lg md:text-xl">
		{RETIREE_NAME} has crossed the finish line. The countdown is over — celebrate accordingly.
	</p>
</section>
