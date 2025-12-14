<script lang="ts">
	/*
	interface PopularListItem {
		keyword: string;
		link: string;
	}

	let { popularList }: { popularList?: PopularListItem[] } = $props();

	if (!popularList) {
		popularList = [];
	}
    */

	const popularList = [
		{ keyword: 'Carpenter Brussels', link: '/' },
		{ keyword: 'Handyman Bussels', link: '/' },
		{ keyword: 'Painter Liege', link: '/' },
		{ keyword: 'Plumber Namur', link: '/' },
		{ keyword: 'Message Cork', link: '/' },
		{ keyword: 'Moving to Brussels', link: '/' },
		{ keyword: 'Electrician Charleroi', link: '/' }
	];

	// Shuffle helper
	function shuffle<T>(arr: T[]): T[] {
		const a = [...arr];
		for (let i = a.length - 1; i > 0; i--) {
			const j = Math.floor(Math.random() * (i + 1));
			[a[i], a[j]] = [a[j], a[i]];
		}
		return a;
	}
</script>

<!-- Popular Search Section -->
<section class="relative flex w-full flex-col items-center justify-between gap-10 bg-white px-10">
	<h2 class="leading-12 text-center font-[Roboto] text-5xl font-bold text-[#1A1A1A]">
		Popular Search in <span class="text-primary">Africa</span>
	</h2>
	{#each Array.from({ length: 4 }) as _, i}
		<!-- Shuffle on each iteration -->
		{@const shuffledList = shuffle(popularList)}
		<div class="flex flex-row gap-10">
			{#each shuffledList as search}
				<a
					href={search.link}
					class="link link-hover font-[Roboto] text-xl font-normal text-[#333333]"
					>{search.keyword}</a
				>
			{/each}
		</div>
	{/each}
</section>
