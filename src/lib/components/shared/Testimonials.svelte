<script lang="ts">
	import { page } from '$app/state';
	import { Splide, SplideTrack, SplideSlide } from '@splidejs/svelte-splide';
	import '@splidejs/svelte-splide/css';

	import TestBg from '$lib/assets/images/bg-1.png';
</script>

<!-- Testemonials Section -->
<section
	class="relative flex w-full flex-row items-center gap-0 rounded-none bg-[white] py-[79px] lg:overflow-hidden lg:rounded-[44px] {page
		.url.pathname === '/' && '-mt-5'}"
>
	<div
		class="z-10 ml-0 flex w-full flex-row items-center justify-center bg-white lg:justify-normal"
	>
		<div
			class="absolute hidden size-[482px] bg-cover bg-right lg:flex"
			style="background-image: url({TestBg});"
		></div>
		<div class="z-100 w-full">
			<Splide
				options={{
					rewind: true,
					autoplay: true,
					type: 'loop',
					pagination: false,
					perPage: 1,
					perMove: 1,
					speed: 1200,
					flickMaxPages: 1,
					arrows: true,
					gap: '30px',
					width: '100%'
				}}
				hasTrack={false}
			>
				<div
					class="lg:pl-74 flex w-full flex-col-reverse justify-center gap-0 px-0 lg:w-[95%] lg:flex-row lg:justify-between lg:gap-0"
				>
					<SplideTrack>
						<SplideSlide>
							<div
								class="flex w-full flex-col flex-wrap gap-6 rounded-none bg-white p-10 shadow-[rgba(0,0,0,0.05)] lg:w-[600px] lg:rounded-xl"
							>
								<div class="flex flex-row items-center justify-center gap-[15px] lg:justify-normal">
									<div class="avatar">
										<div class="w-20 rounded-full">
											<img
												src="https://img.daisyui.com/images/profile/demo/superperson@192.webp"
												alt="Tailwind-CSS-Avatar-component"
											/>
										</div>
									</div>
									<div class="flex flex-col gap-1">
										<h6 class="font-[Roboto] text-2xl font-extrabold text-[#2AAE5C]">
											John Anderson
										</h6>
										<span class="font-[Roboto] text-base font-medium text-[#555555]">
											CEO at Innovate Solutions
										</span>
									</div>
								</div>
								<p
									class="text-center font-[Roboto] text-lg font-normal leading-7 text-[#1E1E1E] lg:text-left"
								>
									"Their attention to detail and creative design approach transformed our website
									into a visually stunning and highly functional platform. We've seen a 30% increase
									in traffic since the relaunch. I highly recommend them to anyone seeking
									professional web design services!"
								</p>
							</div>
						</SplideSlide>
					</SplideTrack>
					<div
						class="z-100 flex w-full flex-col justify-center gap-8 pl-0 lg:justify-normal lg:pl-10"
					>
						<div class="flex flex-col gap-4">
							<span
								class="text-primary text-center font-[Roboto] text-base font-medium uppercase leading-5 tracking-wider lg:text-left"
							>
								Testimonial
							</span>
							<h5
								class="leading-15 text-center font-[Roboto] text-[40px] font-bold text-[#1E1E1E] lg:text-left"
							>
								Client's Success Stories
							</h5>
						</div>
						<div
							class="splide__arrows bottom-0 right-0 flex flex-row justify-center lg:justify-normal"
						>
							<button
								class="btn btn-circle splide__arrow splide__arrow--prev !relative !left-0 -mb-4 !size-10 !bg-[#E6E6E6] !opacity-100 hover:!bg-[#F4C952] md:!mb-0"
								aria-label="control-left"
							>
								<svg
									width="24"
									height="24"
									viewBox="0 0 24 24"
									fill="currentColor"
									xmlns="http://www.w3.org/2000/svg"
									class="!size-6 rotate-180 text-black"
								>
									<path
										d="M7.82484 13L12.7248 17.9C12.9248 18.1 13.0208 18.3334 13.0128 18.6C13.0048 18.8667 12.9005 19.1 12.6998 19.3C12.4998 19.4834 12.2665 19.5794 11.9998 19.588C11.7332 19.5967 11.4998 19.5007 11.2998 19.3L4.69984 12.7C4.59984 12.6 4.52884 12.4917 4.48684 12.375C4.44484 12.2584 4.42451 12.1334 4.42584 12C4.42718 11.8667 4.44818 11.7417 4.48884 11.625C4.52951 11.5084 4.60018 11.4 4.70084 11.3L11.3008 4.70005C11.4842 4.51672 11.7135 4.42505 11.9888 4.42505C12.2642 4.42505 12.5015 4.51672 12.7008 4.70005C12.9008 4.90005 13.0008 5.13772 13.0008 5.41305C13.0008 5.68838 12.9008 5.92572 12.7008 6.12505L7.82484 11H18.9998C19.2832 11 19.5208 11.096 19.7128 11.288C19.9048 11.48 20.0005 11.7174 19.9998 12C19.9992 12.2827 19.9032 12.5204 19.7118 12.713C19.5205 12.9057 19.2832 13.0014 18.9998 13H7.82484Z"
										fill="currentColor"
									/>
								</svg>
							</button>
							<button
								class="btn btn-circle splide__arrow splide__arrow--next !relative !left-0 ml-2.5 !size-10 !bg-[#E6E6E6] !opacity-100 hover:!bg-[#F4C952]"
								aria-label="control-right"
							>
								<svg
									width="24"
									height="24"
									viewBox="0 0 24 24"
									fill="currentColor"
									xmlns="http://www.w3.org/2000/svg"
									class="!size-6 -rotate-180 text-black"
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
			</Splide>
		</div>
	</div>
</section>
