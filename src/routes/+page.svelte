<script lang="ts">
	import { Splide, SplideTrack, SplideSlide } from '@splidejs/svelte-splide';
	import '@splidejs/svelte-splide/css';

	import Hero1 from '$lib/assets/images/hero-1.png';
	import Hero2 from '$lib/assets/images/hero-2.jpg';
	import Hero3 from '$lib/assets/images/hero-3.png';
	import Hero4 from '$lib/assets/images/hero-4.png';

	import miniCarousel1 from '$lib/assets/images/mini-carousel-1.jpg';

	import categoryImage1 from '$lib/assets/images/category-carousel-1.png';
	import categoryImage2 from '$lib/assets/images/category-carousel-2.png';
	import categoryImage3 from '$lib/assets/images/category-carousel-3.png';
	import categoryImage4 from '$lib/assets/images/category-carousel-4.png';

	import frameImage1 from '$lib/assets/images/frame-1.png';
	import frameImage2 from '$lib/assets/images/frame-2.png';

	import ProfilesIcon from '$lib/assets/icons/profiles.svg';
	import MindIcon from '$lib/assets/icons/mind.svg';
	import PlatformIcon from '$lib/assets/icons/platform.svg';
	import SupportIcon from '$lib/assets/icons/support.svg';
	import PopularSearch from '$lib/components/shared/PopularSearch.svelte';
	import Testimonials from '$lib/components/shared/Testimonials.svelte';
	import MobileAppBanner from '$lib/components/shared/MobileAppBanner.svelte';

	const categories = [
		{ title: 'Plumbing', image: categoryImage1, link: '/' },
		{ title: 'Gardening', image: categoryImage2, link: '/' },
		{ title: 'Cooking', image: categoryImage3, link: '/' },
		{ title: 'Pets', image: categoryImage4, link: '/' }
	];

	const processes = [
		{
			name: 'User Registration',
			summary:
				'Clients and service providers create accounts on the GoWork platform (mobile or web) by providing essential details—name, contact information, and role selection (client or provider).'
		},
		{
			name: 'Service Request',
			summary:
				'Clients submit service requests (e.g., plumbing, gardening, cooking) via a simple form detailing service type, description, location, and requirements.'
		},
		{
			name: 'Provider Proposals',
			summary:
				'Verified service providers receive instant notifications of new requests, review details, and submit proposals including pricing and availability.'
		},
		{
			name: 'Proposal Selection',
			summary:
				'Clients review multiple proposals, compare profiles, ratings, and prices, and select the most suitable provider. They can communicate directly through the platform for clarifications.'
		},
		{
			name: 'Job Execution & Payment',
			summary:
				'The provider completes the job as agreed. Payment is processed securely via integrated Stripe and mobile money systems.'
		},
		{
			name: 'Reviews & Ratings',
			summary:
				'Both clients and providers leave feedback to maintain transparency, quality, and trust.'
		}
	];

	const providerFeatures = [
		{ desc: 'Over 4,000 jobs every week for independent contractors and individuals' },
		{ desc: 'Set your own hours and decide how much you want to be paid.' },
		{ desc: 'Get paid within 48 hours for your services.' }
	];

	const serviceSteps = [
		{ id: 1, desc: 'Describe your need' },
		{ id: 2, desc: 'Receive offers quickly' },
		{ id: 3, desc: 'Pay & rate the service' }
	];

	const serviceFeatures = [
		{
			title: 'Verified & Qualified Profiles',
			desc: "Want to know who you're dealing with? So do we! That's why we verify the identity of our service providers.",
			icon: ProfilesIcon
		},

		{
			title: 'Freedom Of Mind',
			desc: "A guaranteed service is worth two! That's why they are all covered by personal injury & property.",
			icon: MindIcon
		},
		{
			title: 'Approved Platform',
			desc: 'Our platform is recognized by the Belgian government. All services are declared and paid online.',
			icon: PlatformIcon
		},
		{
			title: 'Support At Disposal',
			desc: 'We go beyond connecting you. Our team guides you from registration to service declaration.',
			icon: SupportIcon
		}
	];
</script>

<main class="container mx-auto flex flex-col gap-20 bg-white">
	<!-- Hero Section -->
	<section
		class="hero mt-18 sm:mt-34 flex w-full flex-col items-start justify-between gap-8 rounded-[20px] bg-[#EAF7EF] px-10 py-10 lg:flex-row-reverse lg:items-center lg:gap-0"
	>
		<div class="grid w-full grid-cols-3 grid-rows-2 gap-5 lg:w-[50%]">
			<img
				src={Hero1}
				class="col-span-2 h-full w-full object-cover shadow-xl sm:h-[250px]"
				alt=""
			/>
			<img
				src={Hero2}
				class="col-span-1 h-full w-full object-cover shadow-xl sm:h-[250px]"
				alt=""
			/>
			<img
				src={Hero3}
				class="col-span-1 h-full w-full object-cover shadow-xl sm:h-[250px]"
				alt=""
			/>
			<img
				src={Hero4}
				class="col-span-2 h-full w-full object-cover shadow-xl sm:h-[250px]"
				alt=""
			/>
		</div>
		<div class="w-full lg:w-[40%]">
			<h1
				class="md:leading-14 font-[Roboto] text-4xl font-bold leading-10 text-[#333333] sm:text-[42px] md:text-5xl lg:text-[52px]"
			>
				Neighbors with <span class="text-primary">Talent</span>, right next door!
			</h1>
			<p class="pt-5.5 pb-11 font-[Roboto] text-[22px] font-normal leading-9 text-[#666666]">
				Choose the best deal among 50,000 people and pros by requesting a service!
			</p>
			<a
				href="/"
				class="btn btn-primary btn-lg sm:px-7.5 rounded-xl px-4 py-4 font-[Roboto] text-lg font-medium tracking-wide md:text-xl"
				>Get a Service</a
			>
			<div class="flex flex-row gap-14 pt-11">
				<div class="flex flex-col">
					<span class="font-[Inter] text-lg font-extrabold tracking-wide text-black">50,000</span>
					<p class="font-[Inter] text-lg font-normal tracking-wide text-black">Clients</p>
				</div>
				<div class="flex flex-col">
					<span class="font-[Inter] text-lg font-extrabold tracking-wide text-black">15,000</span>
					<p class="font-[Inter] text-lg font-normal tracking-wide text-black">Reviews</p>
				</div>
			</div>
		</div>
	</section>

	<!-- Categories With Carousel Section -->
	<section class="w-full bg-white px-10 sm:px-0">
		<Splide
			options={{
				rewind: true,
				autoplay: false,
				type: 'loop',
				pagination: false,
				perPage: 4,
				perMove: 1,
				breakpoints: {
					1280: {
						perPage: 4,
						perMove: 1
					},
					1024: {
						perPage: 3,
						perMove: 1
					},
					768: {
						perPage: 2,
						perMove: 1,
						gap: '24px'
					},
					640: {
						perPage: 1,
						perMove: 1
					}
				},
				speed: 1200,
				flickMaxPages: 1,
				arrows: true,
				gap: '36px'
			}}
			hasTrack={false}
		>
			<div class="flex w-full flex-col justify-between gap-5 pb-9 md:flex-row md:gap-0">
				<h3 class="font-[Roboto] text-3xl font-semibold text-[#333333] sm:text-4xl md:text-[44px]">
					What are you <span class="!text-primary">looking</span> for?
					<svg
						width="172"
						height="10"
						viewBox="0 0 172 10"
						fill="#2AAE5C"
						xmlns="http://www.w3.org/2000/svg"
						class="md:ml-62 ml-42 w-31 -mt-px md:w-auto"
					>
						<path
							d="M170.134 6.62944C170.498 6.66194 170.832 6.83775 171.064 7.11991C171.296 7.40197 171.406 7.76727 171.371 8.13374C171.335 8.50021 171.156 8.83733 170.874 9.06923C170.592 9.30123 170.229 9.409 169.866 9.37056C167.058 9.07343 164.221 8.76061 161.372 8.44146C110.645 2.35913 59.0664 -2.30387 8.40001 6.44899C5.58345 6.92888 2.80367 7.44147 0 8C2.79433 7.39653 5.56607 6.83873 8.37579 6.31343C58.9029 -3.26775 110.831 0.57188 161.643 5.83904C164.493 6.11221 167.329 6.37882 170.134 6.62944Z"
							fill="#2AAE5C"
						/>
					</svg>
				</h3>
				<div class="splide__arrows flex flex-row items-center justify-between md:justify-end">
					<a
						href="/"
						class="btn btn-primary btn-md sm:px-7.5 mr-3.5 rounded-xl px-4 py-4 font-[Roboto] text-lg font-normal tracking-wide md:text-xl"
						>See All</a
					>
					<div class="relative flex flex-row items-center justify-center">
						<button
							class="btn btn-circle splide__arrow splide__arrow--prev hover:!bg-primary group/service-arrow-1 !relative !-bottom-5 !left-0 ml-2.5 !size-10 !bg-[#E6E6E6] !opacity-100"
							aria-label="control-left"
						>
							<svg
								width="24"
								height="24"
								viewBox="0 0 24 24"
								fill="currentColor"
								xmlns="http://www.w3.org/2000/svg"
								class="!size-6 rotate-180 text-black group-hover/service-arrow-1:text-white"
							>
								<path
									d="M7.82484 13L12.7248 17.9C12.9248 18.1 13.0208 18.3334 13.0128 18.6C13.0048 18.8667 12.9005 19.1 12.6998 19.3C12.4998 19.4834 12.2665 19.5794 11.9998 19.588C11.7332 19.5967 11.4998 19.5007 11.2998 19.3L4.69984 12.7C4.59984 12.6 4.52884 12.4917 4.48684 12.375C4.44484 12.2584 4.42451 12.1334 4.42584 12C4.42718 11.8667 4.44818 11.7417 4.48884 11.625C4.52951 11.5084 4.60018 11.4 4.70084 11.3L11.3008 4.70005C11.4842 4.51672 11.7135 4.42505 11.9888 4.42505C12.2642 4.42505 12.5015 4.51672 12.7008 4.70005C12.9008 4.90005 13.0008 5.13772 13.0008 5.41305C13.0008 5.68838 12.9008 5.92572 12.7008 6.12505L7.82484 11H18.9998C19.2832 11 19.5208 11.096 19.7128 11.288C19.9048 11.48 20.0005 11.7174 19.9998 12C19.9992 12.2827 19.9032 12.5204 19.7118 12.713C19.5205 12.9057 19.2832 13.0014 18.9998 13H7.82484Z"
									fill="currentColor"
								/>
							</svg>
						</button>
						<button
							class="btn btn-circle splide__arrow splide__arrow--next hover:!bg-primary group/service-arrow-2 !relative !-bottom-5 !left-0 ml-2.5 !size-10 !bg-[#E6E6E6] !opacity-100"
							aria-label="control-right"
						>
							<svg
								width="24"
								height="24"
								viewBox="0 0 24 24"
								fill="currentColor"
								xmlns="http://www.w3.org/2000/svg"
								class="!size-6 -rotate-180 text-black group-hover/service-arrow-2:text-white"
							>
								<path
									d="M7.82484 13L12.7248 17.9C12.9248 18.1 13.0208 18.3334 13.0128 18.6C13.0048 18.8667 12.9005 19.1 12.6998 19.3C12.4998 19.4834 12.2665 19.5794 11.9998 19.588C11.7332 19.5967 11.4998 19.5007 11.2998 19.3L4.69984 12.7C4.59984 12.6 4.52884 12.4917 4.48684 12.375C4.44484 12.2584 4.42451 12.1334 4.42584 12C4.42718 11.8667 4.44818 11.7417 4.48884 11.625C4.52951 11.5084 4.60018 11.4 4.70084 11.3L11.3008 4.70005C11.4842 4.51672 11.7135 4.42505 11.9888 4.42505C12.2642 4.42505 12.5015 4.51672 12.7008 4.70005C12.9008 4.90005 13.0008 5.13772 13.0008 5.41305C13.0008 5.68838 12.9008 5.92572 12.7008 6.12505L7.82484 11H18.9998C19.2832 11 19.5208 11.096 19.7128 11.288C19.9048 11.48 20.0005 11.7174 19.9998 12C19.9992 12.2827 19.9032 12.5204 19.7118 12.713C19.5205 12.9057 19.2832 13.0014 18.9998 13H7.82484Z"
									fill="currentColor"
								/>
							</svg>
						</button>
					</div>
				</div>
			</div>
			<SplideTrack>
				{#each categories as category}
					<SplideSlide>
						<div class="flex flex-col gap-5">
							<img
								src={category.image}
								alt=""
								class="h-[357px] w-full rounded-[20px] object-cover object-center shadow-xl"
							/>
							<div
								class="absolute bottom-0 left-0 right-0 mx-3 mb-[17px] flex flex-row items-center justify-between rounded-xl bg-[#FFFFFFE5] px-5 py-3"
							>
								<h6 class="relative text-center font-[Roboto] text-[22px] font-medium text-black">
									{category.title}
								</h6>
								<a
									href={category.link}
									class="btn btn-circle hover:bg-primary! group/service !size-11 !bg-[#BFE7CE]"
									aria-label="control-left"
								>
									<svg
										width="28"
										height="29"
										viewBox="0 0 28 29"
										fill="currentColor"
										xmlns="http://www.w3.org/2000/svg"
										class="group-hover/service:text-white! !size-7 !text-black"
									>
										<g clip-path="url(#clip0_82_158)">
											<path
												d="M6.99967 7.25V9.66667H17.0213L5.83301 21.2546L7.47801 22.9583L18.6663 11.3704V21.75H20.9997V7.25H6.99967Z"
												fill="currentColor"
											/>
										</g>
										<defs>
											<clipPath id="clip0_82_158">
												<rect width="28" height="29" rx="14" fill="white" />
											</clipPath>
										</defs>
									</svg>
								</a>
							</div>
						</div>
					</SplideSlide>
				{/each}
			</SplideTrack>
		</Splide>
	</section>

	<!-- Request Service With Carousel Section -->
	<section
		class="flex w-full flex-col-reverse items-start justify-between gap-8 rounded-[20px] bg-[#FEFAEE] px-10 py-14 lg:flex-row lg:items-center lg:gap-0"
	>
		<div class="relative w-full lg:w-[40%]">
			<h2
				class="leading-12 font-[Roboto] text-3xl font-bold text-[#333333] md:text-4xl lg:text-5xl"
			>
				Upload your <span class="text-primary">first request.</span>
			</h2>
			<p
				class="py-4.5 font-[Roboto] text-lg font-normal leading-8 text-[#666666] md:text-xl lg:text-2xl"
			>
				Over 50,000 private and professional service providers throughout Africa!
			</p>
			<div class="relative">
				<hr
					class="absolute left-[19px] top-5 z-10 flex h-[80%] scale-x-[0.25] justify-center border border-dashed border-black"
				/>
				<ul class="mb-11.5 flex flex-col gap-3 py-[11px]">
					{#each serviceSteps as feature}
						<li class="flex flex-row items-center gap-[13px]">
							<span
								class="bg-primary z-20 size-10 rounded-full py-0.5 text-center align-middle font-[Roboto] text-lg font-normal leading-9 text-white sm:text-xl lg:text-2xl"
								>{feature.id}</span
							><span
								class="align-middle font-[Roboto] text-base font-normal leading-7 text-[#333333] sm:text-lg sm:leading-8 lg:text-xl lg:leading-10"
								>{feature.desc}</span
							>
						</li>
					{/each}
				</ul>
			</div>

			<a
				href="/"
				class="btn btn-primary btn-lg sm:px-7.5 rounded-xl px-4 py-4 font-[Roboto] text-lg font-normal tracking-wide md:text-xl"
				>Request a Service</a
			>
		</div>
		<div
			class="border-1 border-primary flex w-full flex-col gap-7 rounded-[20px] bg-white p-10 lg:w-[50%]"
		>
			<Splide
				options={{
					rewind: true,
					autoplay: false,
					type: 'loop',
					pagination: false,
					perPage: 2,
					perMove: 1,
					breakpoints: {
						1280: {
							perPage: 2,
							perMove: 1
						},
						1024: {
							perPage: 2,
							perMove: 1
						},
						767: {
							perPage: 1,
							perMove: 1
						}
					},
					speed: 1200,
					flickMaxPages: 1,
					arrows: true,
					gap: '24px'
				}}
				hasTrack={false}
			>
				<div class="flex flex-row justify-between pb-6">
					<h3 class="font-[Roboto] text-[22px] font-bold text-black md:text-2xl lg:text-[32px]">
						Most Popular Requests
					</h3>
					<div class="splide__arrows right-0 flex flex-row">
						<button
							class="btn btn-circle splide__arrow splide__arrow--prev hover:!bg-primary group/request-arrow-1 md:mb-0! !relative !left-0 ml-2.5 !size-10 !bg-[#E6E6E6] !opacity-100"
							aria-label="control-left"
						>
							<svg
								width="24"
								height="24"
								viewBox="0 0 24 24"
								fill="currentColor"
								xmlns="http://www.w3.org/2000/svg"
								class="!size-6 rotate-180 text-black group-hover/request-arrow-1:text-white"
							>
								<path
									d="M7.82484 13L12.7248 17.9C12.9248 18.1 13.0208 18.3334 13.0128 18.6C13.0048 18.8667 12.9005 19.1 12.6998 19.3C12.4998 19.4834 12.2665 19.5794 11.9998 19.588C11.7332 19.5967 11.4998 19.5007 11.2998 19.3L4.69984 12.7C4.59984 12.6 4.52884 12.4917 4.48684 12.375C4.44484 12.2584 4.42451 12.1334 4.42584 12C4.42718 11.8667 4.44818 11.7417 4.48884 11.625C4.52951 11.5084 4.60018 11.4 4.70084 11.3L11.3008 4.70005C11.4842 4.51672 11.7135 4.42505 11.9888 4.42505C12.2642 4.42505 12.5015 4.51672 12.7008 4.70005C12.9008 4.90005 13.0008 5.13772 13.0008 5.41305C13.0008 5.68838 12.9008 5.92572 12.7008 6.12505L7.82484 11H18.9998C19.2832 11 19.5208 11.096 19.7128 11.288C19.9048 11.48 20.0005 11.7174 19.9998 12C19.9992 12.2827 19.9032 12.5204 19.7118 12.713C19.5205 12.9057 19.2832 13.0014 18.9998 13H7.82484Z"
									fill="currentColor"
								/>
							</svg>
						</button>
						<button
							class="btn btn-circle splide__arrow splide__arrow--next hover:!bg-primary group/request-arrow-2 !relative !left-0 ml-2.5 !size-10 !bg-[#E6E6E6] !opacity-100"
							aria-label="control-right"
						>
							<svg
								width="24"
								height="24"
								viewBox="0 0 24 24"
								fill="currentColor"
								xmlns="http://www.w3.org/2000/svg"
								class="!size-6 -rotate-180 text-black group-hover/request-arrow-2:text-white"
							>
								<path
									d="M7.82484 13L12.7248 17.9C12.9248 18.1 13.0208 18.3334 13.0128 18.6C13.0048 18.8667 12.9005 19.1 12.6998 19.3C12.4998 19.4834 12.2665 19.5794 11.9998 19.588C11.7332 19.5967 11.4998 19.5007 11.2998 19.3L4.69984 12.7C4.59984 12.6 4.52884 12.4917 4.48684 12.375C4.44484 12.2584 4.42451 12.1334 4.42584 12C4.42718 11.8667 4.44818 11.7417 4.48884 11.625C4.52951 11.5084 4.60018 11.4 4.70084 11.3L11.3008 4.70005C11.4842 4.51672 11.7135 4.42505 11.9888 4.42505C12.2642 4.42505 12.5015 4.51672 12.7008 4.70005C12.9008 4.90005 13.0008 5.13772 13.0008 5.41305C13.0008 5.68838 12.9008 5.92572 12.7008 6.12505L7.82484 11H18.9998C19.2832 11 19.5208 11.096 19.7128 11.288C19.9048 11.48 20.0005 11.7174 19.9998 12C19.9992 12.2827 19.9032 12.5204 19.7118 12.713C19.5205 12.9057 19.2832 13.0014 18.9998 13H7.82484Z"
									fill="currentColor"
								/>
							</svg>
						</button>
					</div>
				</div>
				<SplideTrack>
					<SplideSlide>
						<div class="flex flex-col gap-5">
							<img src={miniCarousel1} alt="" class="w-full rounded-2xl object-cover shadow-xl" />
							<div class="flex flex-col items-center gap-2 px-1 text-center align-middle">
								<h5 class="text-center font-[Roboto] text-2xl font-medium text-black">
									Small Job Work
								</h5>
								<p class="text-center font-[Roboto] text-xl font-normal leading-7 text-[#666666]">
									Repair water leakage & Leaf collection
								</p>
								<span class="text-center font-[Roboto] text-xl font-medium text-black">$ 50</span>
							</div>
						</div>
					</SplideSlide>
				</SplideTrack>
			</Splide>
		</div>
	</section>

	<!-- Service Feature Section -->
	<section class="-mt-4.5 w-full bg-white">
		<div
			class="border-primary pt-14.5 flex w-full flex-row justify-between rounded-[20px] border-2 px-14 pb-16 lg:flex-row-reverse"
		>
			<div class="grid grid-cols-1 justify-between gap-12 px-6 md:grid-cols-2 lg:grid-cols-4">
				{#each serviceFeatures as feature}
					<div class="flex flex-col items-center gap-4">
						<span
							class="bg-primary flex size-[84px] items-center justify-center rounded-full md:size-[100px] lg:size-[124px]"
						>
							<img src={feature.icon} class="size-[42px] md:size-[64px] lg:size-[75px]" alt="" />
						</span>
						<h5
							class="text-primary text-center font-[Roboto] text-lg font-medium md:text-xl lg:text-2xl"
						>
							{feature.title}
						</h5>
						<p class="text-center font-[Roboto] text-lg font-normal text-[#666666]">
							{feature.desc}
						</p>
					</div>
				{/each}
			</div>
		</div>
		<div class="-mt-6.5 container mx-auto flex w-full items-center justify-center">
			<a
				href="/"
				class="btn btn-primary btn-lg sm:px-7.5 flex-none rounded-xl px-4 py-4 font-[Roboto] text-lg font-normal tracking-wide md:text-xl"
				>Request a Service</a
			>
		</div>
	</section>

	<!-- Service Provider Section -->
	<section
		class="-mt-[13px] flex w-full flex-col-reverse items-center justify-between gap-9 lg:flex-row"
	>
		<div
			class="flex h-auto w-full flex-col justify-center gap-4 rounded-[20px] bg-[#EAF7EF] px-10 py-14 lg:h-[600px] lg:w-[50%]"
		>
			<h6 class="leading-12 font-[Roboto] text-[32px] font-bold text-[#1A1A1A]">
				Use your skills to make money, whether you're a professional or an individual!
			</h6>
			<p class="font-[Roboto] text-2xl font-normal leading-9 text-[#666666]">
				Do like Alain and register:
			</p>
			<ul class="flex flex-col gap-3 pb-6">
				{#each providerFeatures as feature}
					<li class="flex flex-row items-start gap-3.5">
						<span class="flex size-10 items-center rounded-full bg-[#6AC68D] p-1.5">
							<svg
								width="24"
								height="24"
								viewBox="0 0 24 24"
								fill="currentColor"
								xmlns="http://www.w3.org/2000/svg"
								class="size-7 text-[#6AC68D]"
							>
								<path
									d="M5 12.5L9.667 17L19 8"
									stroke="white"
									stroke-width="1.5"
									stroke-linecap="round"
									stroke-linejoin="round"
								/>
							</svg>
						</span>
						<span class="font-[Roboto] text-xl font-normal leading-10 text-[#333333]"
							>{feature.desc}</span
						>
					</li>
				{/each}
			</ul>
			<div>
				<a
					href="/"
					class="btn btn-primary btn-lg sm:px-7.5 rounded-xl px-4 py-4 font-[Roboto] text-lg font-medium tracking-wide md:text-xl"
					>Become a service provider</a
				>
			</div>
		</div>
		<div class="flex w-full justify-center lg:w-[50%] lg:justify-end">
			<img src={frameImage1} class="h-auto w-full lg:w-[702px]" alt="" />
		</div>
	</section>

	<!-- How It Works Section -->
	<section
		class="flex w-full flex-col items-center justify-between gap-14 rounded-[20px] bg-[#FEFAEE] p-10 lg:flex-row"
	>
		<div class="w-full lg:w-[32%]">
			<img src={frameImage2} class="w-full" alt="" />
		</div>
		<div class="gap-4.5 flex w-full flex-col justify-center lg:w-[68%]">
			<h6 class="leading-12 font-[Roboto] text-[32px] font-bold text-[#1A1A1A]">How It Works</h6>
			<div class="relative flex flex-row gap-7">
				<div class="absolute bottom-1.5 left-[6px] top-1.5 z-10 flex justify-center">
					<hr class="h-full scale-x-[0.25] border-[0.5px] border-dashed border-black" />
				</div>
				<div class="flex flex-col gap-7">
					{#each processes as process}
						<div class="gap-4.5 flex flex-row">
							<!-- <span class="size-3.5! z-20 mt-1.5 rounded-full bg-[#F4C952]"></span> -->
							<span class="z-20 mt-1.5 size-3.5 flex-shrink-0 rounded-full bg-[#F4C952]"></span>
							<p class="font-[Roboto] text-lg font-light text-black">
								<span class="text-primary font-medium">{process.name}:</span><br />{process.summary}
							</p>
						</div>
					{/each}
				</div>
			</div>
		</div>
	</section>

	<!-- Testemonials Section -->
	<Testimonials />

	<!-- Mobile App Download Section -->
	<MobileAppBanner />

	<!-- Popular Search Section -->
	<PopularSearch />
</main>
