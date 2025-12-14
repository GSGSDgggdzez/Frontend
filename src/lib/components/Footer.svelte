<script lang="ts">
	import FacebookAltIcon from '$lib/assets/icons/facebook-alt.svg';
	import InstagramAltIcon from '$lib/assets/icons/instagram-alt.svg';
	import LinkedinAltIcon from '$lib/assets/icons/linkedin-alt.svg';

	import AppstoreLogo from '$lib/assets/images/appstore.png';
	import PlaystoreLogo from '$lib/assets/images/playstore.png';

	const icons = [
		{ name: 'facebook', icon: FacebookAltIcon, link: '/' },
		{ name: 'linkedin', icon: LinkedinAltIcon, link: '/' },
		{ name: 'instagram', icon: InstagramAltIcon, link: '/' }
	];

	const navs = [
		{
			title: 'Upload your first request',
			links: [
				{ name: 'Blog', link: '/' },
				{ name: 'Best Providers', link: '/' },
				{ name: 'Invite your friends', link: '/' },
				{ name: 'City Card', link: '/' }
			]
		},
		{
			title: 'Need help?',
			links: [
				{ name: 'How does it works?', link: '/' },
				{ name: 'GoWork formulas', link: '/' },
				{ name: 'GoWork, is it legal?', link: '/' },
				{ name: 'Contact Us', link: '/' },
				{ name: 'Help/FAQ', link: '/' }
			]
		},
		{
			title: 'About',
			links: [
				{ name: 'GoWork', link: '/about' },
				{ name: 'Our Team', link: '/' },
				{ name: 'Jobs/Internship', link: '/' },
				{ name: 'Press Area', link: '/' }
			]
		}
	];
</script>

<footer class="!text-base-content sm:px-30 pb-12.5 mt-14 bg-[#F2F2F280] px-6 pt-16">
	<div class="footer grid grid-cols-1 justify-between gap-2.5 lg:grid-cols-2 xl:grid-cols-4">
		{#each navs as nav}
			<nav class="gap-4">
				<h6 class="text-black! font-[Roboto] text-2xl font-medium capitalize">
					{nav.title}
				</h6>
				<div class="flex flex-col justify-center gap-3">
					{#each nav.links as link}
						<a
							href={link.link}
							class="link link-hover font-[Roboto] text-xl font-normal leading-10 text-[#333333]"
							>{link.name}</a
						>
					{/each}
				</div>
			</nav>
		{/each}
		<div class="flex flex-col gap-8">
			<div class="flex-start flex flex-col gap-4">
				<h6 class="text-black! font-[Roboto] text-2xl font-medium capitalize">Follow Us</h6>
				<div class="-ml-1.5 flex flex-row gap-6">
					{#each icons as icon}
						<a href={icon.link}><img src={icon.icon} class="size-[21px]" alt="" /></a>
					{/each}
				</div>
			</div>
			<div class="flex flex-col gap-4">
				<h6 class="text-black! font-[Roboto] text-2xl font-medium capitalize">
					Discover our mobile application
				</h6>
				<div class="flex flex-col gap-6 sm:flex-row sm:gap-6">
					<a href="/"><img class="h-[54px]" src={AppstoreLogo} alt="" /></a>
					<a href="/"><img class="h-[54px]" src={PlaystoreLogo} alt="" /></a>
				</div>
			</div>
		</div>
	</div>
	<div class="footer sm:footer-horizontal justify-center pt-20">
		<aside>
			<p class="text-black! font-[Inter] text-lg font-normal">
				Copyright © {new Date().getFullYear()} | All right reserved by GoWork
			</p>
		</aside>
	</div>
</footer>
