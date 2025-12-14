<script lang="ts">
	import TalentSeeker from '$lib/assets/images/signup-talent-seeker.png';

	import UserAltIcon from '$lib/assets/icons/user-alt.svg';
	import EmailAltIcon from '$lib/assets/icons/email-alt.svg';
	import ArrowRightAltIcon from '$lib/assets/icons/arrow-right-alt.svg';
	import LockAltIcon from '$lib/assets/icons/lock-alt.svg';
	import IdCardAltIcon from '$lib/assets/icons/id-card-alt.svg';

	import Input from '$lib/components/shared/Input.svelte';
	import Button from '$lib/components/shared/Button.svelte';
</script>

<main class="container mx-auto flex flex-col bg-white">
	<!-- Join Waiting List Section -->
	<section
		class="hero mt-34 mb-25 sm:px-18.5 flex w-full flex-col-reverse items-start justify-between gap-8 overflow-hidden rounded-[28px] bg-[#EAF7EF] p-10 sm:py-14 lg:flex-row-reverse lg:items-center lg:gap-0"
	>
		<img
			src={TalentSeeker}
			class="col-span-2 -mb-64 w-full object-cover px-10 sm:px-0 md:w-[480px] lg:w-[600px]"
			alt="signup-seeker"
		/>
		<form class="flex w-full flex-col gap-5 lg:w-[40%]">
			<h2
				class="text-center font-[Roboto] text-[28px] font-bold text-[#171128] sm:text-left sm:text-4xl lg:text-[45px]"
			>
				I'm looking for talent
			</h2>
			<div class="mt-4.5 flex w-full flex-col gap-5 sm:flex-row">
				<Input name="firstname" placeholder="First Name" beforeIcon={UserAltIcon} />
				<Input name="lastname" placeholder="Last Name" beforeIcon={UserAltIcon} />
			</div>
			<Input name="email" type="email" placeholder="Email" beforeIcon={EmailAltIcon} />
			<Input name="password" type="password" placeholder="Password" beforeIcon={LockAltIcon} />
			<Input name="id" placeholder="Government ID" beforeIcon={IdCardAltIcon} />
			<div class="mt-3 flex flex-col gap-7">
				<label
					class="label gap-5 text-wrap font-[Roboto] text-base font-normal leading-[120%] text-black"
				>
					<input
						type="checkbox"
						checked={false}
						class="checkbox checkbox-md checkbox-primary checked:border-primary rounded-md border-[#D2D2D2]"
					/>
					I am registering as a company, Work with providers with a VAT number.
				</label>
				<label
					class="label gap-5 text-wrap font-[Roboto] text-base font-normal leading-[120%] text-black"
				>
					<input
						type="checkbox"
						checked={false}
						class="checkbox checkbox-md checkbox-primary checked:border-primary rounded-md border-[#D2D2D2]"
					/>
					I would like to receive information and promotions.
				</label>
			</div>
			<Button
				title="Register"
				className="!btn-xl btn-primary !py-auto mt-4.5 !rounded-[10px] text-xl font-bold tracking-wide lg:h-auto lg:py-4"
				afterIcon={ArrowRightAltIcon}
				addIconClass="size-6!"
			/>
		</form>
	</section>
</main>
