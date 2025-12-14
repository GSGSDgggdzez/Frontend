<script lang="ts">
	import { Splide, SplideTrack, SplideSlide } from '@splidejs/svelte-splide';
	import '@splidejs/svelte-splide/css';

	import AboutHero from '$lib/assets/images/about-cover.png';
	import WhyImage from '$lib/assets/images/why-gowork.png';
	import WhoImage from '$lib/assets/images/who-gowork.png';

	import CatImage1 from '$lib/assets/images/cat-image-1.jpg';
	import CatImage2 from '$lib/assets/images/cat-image-2.jpg';
	import CatImage3 from '$lib/assets/images/cat-image-3.jpg';
	import CatImage4 from '$lib/assets/images/cat-image-4.jpg';
	import CatImage5 from '$lib/assets/images/cat-image-5.jpg';
	import CatImage6 from '$lib/assets/images/cat-image-6.jpg';

	const categories = [
		{ title: 'Home Clean', figures: '35K', image: CatImage1 },
		{ title: 'Personal Care', figures: '658 Hrs', image: CatImage2 },
		{ title: 'Furniture Moved', figures: '45,000', image: CatImage3 },
		{ title: 'Pampered Animals', figures: '5,500', image: CatImage4 },
		{ title: 'Freshly Painted', figures: '3,500', image: CatImage5 },
		{ title: 'Plumbing Work', figures: '3,500 Hrs', image: CatImage6 }
	];
</script>

<main class="mb-38 mt-24 w-full bg-white">
	<!-- About Hero Section class="hero bg-linear-to-r flex h-[1000px] w-screen flex-col items-start justify-center gap-8 from-white to-transparent bg-cover bg-center px-6 sm:h-[800px] sm:px-12 md:px-20 lg:px-32 xl:px-40"
		style="background-image: url({AboutHero});"-->
	<section
		class="hero bg-linear-to-r lg:px-45 flex h-[1000px] w-full flex-col items-start justify-center gap-8 from-white to-transparent bg-cover bg-center px-10 py-10 sm:h-[799px] sm:px-20 md:px-[161px]"
		style="background-image: url({AboutHero});"
	>
		<div class="flex w-full flex-col gap-5 sm:w-[80%] md:w-[65%] lg:w-[45%]">
			<h1 class="font-[Roboto] text-4xl font-bold text-[#333333] sm:text-[42px] md:text-[52px]">
				A Community of More<br /> Than <span class="text-primary">500,000 Users</span>
			</h1>
			<div class="flex flex-1 flex-col flex-wrap">
				<span class="font-[Roboto] text-2xl font-extrabold leading-9 text-black"
					>What is GoWork?</span
				>
				<p
					class="text-wrap font-[Roboto] text-[22px] font-normal leading-9 tracking-tight text-[#666666]"
				>
					At GoWork, our mission is to connect people who are looking for help with others who
					can—and most importantly, love to—help. We believe in wholeheartedly sharing talent. And
					if our community is any guide, neighborhoods are full of hidden talent! <br /><br />You'd
					be surprised how good your neighbor is at playing the piano, how much of an animal lover
					she is, or even how fluent in Japanese they are! Imagine how amazing it would be to learn
					a few words for your next trip to Japan, wouldn't it?
				</p>
			</div>
		</div>
	</section>

	<!-- Why and Who GoWork Section -->
	<section class="my-11.5 container mx-auto flex flex-col">
		<div
			class="rounded-t-4xl flex flex-col items-center gap-10 bg-[#EAF7EF] px-6 pb-5 pt-14 lg:flex-row lg:px-20"
		>
			<img src={WhyImage} class="w-full lg:w-[50%]" alt="why" />
			<div class="flex flex-col gap-5">
				<h3
					class="font-[Roboto] text-4xl font-bold text-[#333333] sm:text-[42px] md:text-5xl lg:text-[52px]"
				>
					Why <span class="text-primary">GoWork?</span>
				</h3>
				<p class="py-4.5 leading-7.5 font-[Roboto] text-xl font-normal text-black">
					GoWork is all about creating that little sign of trust between people—just like the
					feeling of familiarity when someone rings twice at your door. Amazing things happen when
					two people come together. Whether you're looking for help or offering your talents,
					joining GoWork means becoming part of a community and experiencing incredible things.
				</p>
			</div>
		</div>
		<div
			class="rounded-4xl -mt-5 flex flex-col items-center gap-10 bg-[#FEFAEE] px-6 pb-12 pt-8 lg:flex-row-reverse lg:px-20"
		>
			<img src={WhoImage} class="rounded-4xl w-full lg:w-[50%]" alt="why" />
			<div class="flex flex-col gap-3">
				<h3
					class="font-[Roboto] text-4xl font-bold text-[#333333] sm:text-[42px] md:text-5xl lg:text-[52px]"
				>
					Who is <span class="text-primary">GoWork?</span>
				</h3>
				<p class="py-4.5 leading-7.5 font-[Roboto] text-xl font-normal text-black">
					Founded in 2013, GoWork (formerly ListMinut) is a 100% Belgian web startup operating
					nationwide. What started as a graduation project has grown into a platform where more than
					500,000 users have found help nearby, thanks to over 36,000 talented service providers.
					Today, the GoWork family (yes, we like to call ourselves a small family) is made up of 27
					motivated, enthusiastic, and ambitious people—and we're only growing!
				</p>
			</div>
		</div>
	</section>

	<!-- GoWork Work Categories Section -->
	<section class="flex w-full flex-col items-center justify-center gap-11 bg-white">
		<h3
			class="text-center font-[Roboto] text-4xl font-bold text-[#333333] sm:text-[42px] md:text-5xl lg:text-[52px]"
		>
			GoWork is also...
		</h3>
		<Splide
			options={{
				rewind: true,
				autoplay: true,
				type: 'loop',
				pagination: false,
				perPage: 6,
				perMove: 1,
				breakpoints: {
					1280: {
						perPage: 4
					},
					1024: {
						perPage: 3
					},
					768: {
						perPage: 2
					},
					640: {
						perPage: 1,
						gap: '0px'
					}
				},
				speed: 1200,
				flickMaxPages: 1,
				arrows: false,
				gap: '8px',
				width: '100%'
				//class: 'relative'
			}}
			hasTrack={false}
		>
			<SplideTrack>
				{#each categories as category}
					<SplideSlide>
						<div
							class="relative flex h-[582px] w-full flex-col justify-end gap-10 overflow-hidden bg-cover bg-center object-center"
							style="background-image: url({category.image});"
						>
							<div
								class="pb-10.5 bg-linear-to-b flex w-full flex-col from-[#D9D9D900] to-[#000000] px-9"
							>
								<h4 class="leading-9.5 font-[Roboto] text-[38px] font-bold text-white">
									{category.figures}
								</h4>
								<span class="font-[Roboto] text-[28px] font-bold text-white">{category.title}</span>
							</div>
						</div>
					</SplideSlide>
				{/each}
			</SplideTrack>
		</Splide>
		<div class="mt-7.5 flex flex-col gap-12 px-6">
			<p class="font-[Roboto] text-xl font-normal leading-[27px] text-black">
				Discover what GoWork can do for you and how it can make a difference in your everyday life.
			</p>
			<div class="flex flex-row justify-center">
				<a
					href="/"
					class="btn btn-primary btn-lg sm:px-7.5 rounded-xl px-4 py-4 font-[Roboto] text-lg font-medium tracking-wide md:text-xl"
					>Discover GoWork</a
				>
			</div>
		</div>
	</section>
</main>
