<script>
	import Logo from '$lib/assets/logo.png';
	import HeroBackground from '$lib/assets/herobg.jpg';
	import Security from '$lib/assets/security.png';
	import Exclusivity from '$lib/assets/exclusivity.png';
	import Liquidity from '$lib/assets/liquidity.png';
</script>

<!-- ============================Hero section======================== -->
<section
	class="relative flex min-h-screen flex-col justify-between gap-20 overflow-x-hidden py-20"
	style="background-image: url({HeroBackground}); background-size: cover; background-position: center; background-repeat: no-repeat;
  background-attachment: fixed;"
>
	<!-- Gradient overlay -->
	<div class="absolute inset-0 z-0 bg-black opacity-60"></div>
	<!-- navbar -->
	<nav class="relative z-10 mx-5 flex cursor-pointer justify-between md:mx-20">
		<div>
			<img src={Logo} alt="logo" />
		</div>
		<div class="hidden items-center gap-20 font-[200] lg:flex">
			<ul class="flex gap-20 text-[15px]">
				<li>How It Works</li>
				<li>Your Card</li>
				<li>Benefits</li>
			</ul>
			<button
				class="cursor-pointer rounded-[10px] bg-[#FFEFC2] px-7 py-3 text-[20px] font-[700] uppercase text-black"
				>GET STARTED</button
			>
		</div>
	</nav>

	<!-- hero content -->
	<div
		class="relative z-10 mx-5 mb-20 flex flex-col text-center font-[400] md:mx-20 md:mb-0 md:text-left"
	>
		<div
			class="lg:text[60px] text-[27px] uppercase tracking-tighter sm:text-[45px] md:leading-none xl:text-[96px]"
		>
			timeless security,<br />modern convenience
		</div>
		<p class=" text-[15px] sm:text-[25px] lg:text-[30px] xl:text-[40px]">
			Buy, save and spend allocated gold with confidence.
		</p>
	</div>
</section>

<section
	class="item-center relative mx-5 flex min-h-screen flex-col justify-center gap-20 overflow-x-hidden py-20 md:mx-20"
>
	<div class="flex flex-col gap-8">
		<div
			class="lg:text[60px] w-[300px] text-[37px] uppercase tracking-tighter sm:text-[45px] md:leading-none lg:w-[1009px] xl:text-[96px]"
		>
			BUY, SAVE, SPEND GOLD. SEAMLESSLY
		</div>
		<p class="text-[20px] font-[200] sm:text-[30px] lg:text-[38px] xl:text-[48px]">
			AULT Is An Exclusive Concierge Service Designed For High Net-Worth Individuals. To Provide A
			Seamless Experience In The Purchase And Management Of Allocated Gold. Created For Those Who
			Demand Security, Wealth Preservation, And At The Same Time, Instant Access To Traditional Gold
			Ownership By Enabling Real Time Spending Of Gold Assets.
		</p>
		<button
			class="h-[30px] w-[100px] cursor-pointer rounded-[10px] bg-[#FFEFC2] text-[15px] font-[400] uppercase text-black md:text-[20px] lg:h-[88px] lg:w-[374px]"
			>JOIN AULT</button
		>
	</div>

	<div class="flex flex-col md:flex-row gap-8">
		<div class="flex h-[416px] flex-col justify-between rounded-[24px] bg-[#212121] p-5">
			<div class="flex max-w-[165px]">
				<img src={Security} alt="security" class="w-full" />
			</div>
			<div>
				<h3 class="font-[700] text-[25px]">Security</h3>
				<p>
					All Deposits Are Automatically Converted To Physical Allocated Gold Which Are Stored In
					LBMA-Certified Vaults In Zurich, London And Dubai.
				</p>
			</div>
		</div>
		<div class="flex h-[416px] flex-col justify-between rounded-[24px] bg-[#212121] p-5">
			<div class="flex max-w-[165px]">
				<img src={Exclusivity} alt="security" class="w-full" />
			</div>
			<div>
				<h3>Exclusivity</h3>
				<p>
					Our referral-only model ensures you belong to a carefully curated group of members and
					that we deliver a personalized service, tailored to your needs.
				</p>
			</div>
		</div>
		<div class="flex h-[416px] flex-col justify-between rounded-[24px] bg-[#212121] p-5">
			<div class="flex max-w-[165px]">
				<img src={Liquidity} alt="security" class="w-full" />
			</div>
			<div>
				<h3>Liquidity</h3>
				<p>
					Seamless Access To Your Funds. Withdraw, Transfer, Or Spend Your Allocated Gold Assets
					Wherever And Whenever Needed.
				</p>
			</div>
		</div>
	</div>
</section>
