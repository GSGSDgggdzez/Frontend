<script lang="ts">
	import WaitCover from '$lib/assets/images/login-cover.png';

	import UserAltIcon from '$lib/assets/icons/user-alt.svg';
	import EmailAltIcon from '$lib/assets/icons/email-alt.svg';
	import PhoneAltIcon from '$lib/assets/icons/phone-alt.svg';
	import AddressAltIcon from '$lib/assets/icons/address-alt.svg';
	import ArrowDownAltIcon from '$lib/assets/icons/arrow-down-alt.svg';
	import ArrowRightAltIcon from '$lib/assets/icons/arrow-right-alt.svg';

	import Input from '$lib/components/shared/Input.svelte';
	import Button from '$lib/components/shared/Button.svelte';
</script>

<main class="container mx-auto flex flex-col bg-white">
	<!-- Join Waiting List Section -->
	<section
		class="hero mt-39.5 sm:px-18.5 -mb-3.5 flex w-full flex-col-reverse items-start justify-between gap-8 rounded-[28px] bg-[#EAF7EF] p-10 lg:flex-row-reverse lg:items-center lg:gap-0"
	>
		<img
			src={WaitCover}
			class="xl:mr-8.5 col-span-2 w-full object-cover px-10 sm:px-0 lg:w-[468px]"
			alt="login-cover"
		/>
		<form class="flex w-full flex-col gap-5 lg:w-[40%]">
			<h2
				class="mb-1 text-center font-[Roboto] text-[28px] font-bold text-[#171128] sm:text-left sm:text-4xl"
			>
				Join Waiting List
			</h2>
			<div class="flex w-full flex-col gap-5 sm:flex-row">
				<Input name="firstname" placeholder="First Name" beforeIcon={UserAltIcon} />
				<Input name="lastname" placeholder="Last Name" beforeIcon={UserAltIcon} />
			</div>
			<Input name="email" type="email" placeholder="Email" beforeIcon={EmailAltIcon} />
			<Input name="phone" type="number" placeholder="Phone Number" beforeIcon={PhoneAltIcon} />
			<Input name="address" placeholder="Address" beforeIcon={AddressAltIcon} />
			<Input name="services" placeholder="Which service you need" afterIcon={ArrowDownAltIcon} />
			<Button
				title="Join Waiting List"
				className="!btn-xl btn-primary !py-auto mt-3.5 w-full !rounded-[10px] text-xl font-bold tracking-wide lg:h-auto lg:py-4 xl:w-[75%] 2xl:w-[50%]"
				afterIcon={ArrowRightAltIcon}
				addIconClass="size-6!"
			/>
		</form>
	</section>
</main>
