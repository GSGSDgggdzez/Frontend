<script lang="ts">
	import AppPhoneMockup from '$lib/assets/images/app-phone-mockup.png';
	import AppstoreLogo from '$lib/assets/images/appstore.png';
	import PlaystoreLogo from '$lib/assets/images/playstore.png';
</script>

<!-- Mobile App Download Section -->
<section
	class="pt-25.5 gap-18 container relative mx-auto flex w-full flex-col justify-between rounded-[20px] bg-[#2AAE5C] px-10 lg:flex-row lg:gap-0"
>
	<div class="flex flex-col justify-start gap-9">
		<h2 class="leading-12.5 text-left font-[Roboto] text-5xl font-bold text-white">
			Download our mobile app
		</h2>
		<div class="gap-6.5 flex flex-col justify-center sm:flex-row sm:justify-normal sm:gap-6">
			<a href="/"><img class="h-[54px]" src={AppstoreLogo} alt="" /></a>
			<a href="/"><img class="h-[54px]" src={PlaystoreLogo} alt="" /></a>
		</div>
	</div>

	<div
		class="relative bottom-0 mr-5 flex h-[142px] w-full justify-center rounded-t-[200px] bg-[#F4C952] lg:h-[204px] lg:w-[703px]"
	>
		<img
			src={AppPhoneMockup}
			class="-mt-20 h-24 md:-mt-28 md:h-[248px] lg:-mt-36 lg:h-[349px]"
			alt="App Phone Mockup"
		/>
	</div>
</section>
