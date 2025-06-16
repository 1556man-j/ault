<script>
	import Logo from '$lib/assets/logo.png';
	import HeroBackground from '$lib/assets/herobg.jpg';
	import Security from '$lib/assets/security.png';
	import Exclusivity from '$lib/assets/exclusivity.png';
	import Liquidity from '$lib/assets/liquidity.png';
	import AboutImg from '$lib/assets/aboutimg.jpg';
	import Invitation from '$lib/assets/invitation.png';
	import Platform from '$lib/assets/platform.png';
	import Card from '$lib/assets/card.png';
	import Setup from '$lib/assets/setup.png';
	import AultOnGold from '$lib/assets/ault-on-gold.png';
	import Experience1 from '$lib/assets/experience1.jpg';
	import Experience2 from '$lib/assets/experience2.jpg';
	import Experience3 from '$lib/assets/experience3.jpg';
	import Partner1 from '$lib/assets/partner1.png';
	import Partner2 from '$lib/assets/partner2.png';
	import Partner3 from '$lib/assets/partner3.png';
	import Partner4 from '$lib/assets/partner4.png';
	import Partner5 from '$lib/assets/partner5.png';
	import FooterLogo from '$lib/assets/footer-logo.png';

	let isOpen = false;
</script>

<!-- ============================Hero section======================== -->
<section
	class="relative flex min-h-screen flex-col justify-between gap-20 overflow-x-hidden py-10 md:py-20"
	style="background-image: url({HeroBackground}); background-size: cover; background-position: center; background-repeat: no-repeat;
  background-attachment: fixed;"
>
	<!-- Gradient overlay -->
	<div class="absolute inset-0 z-0 bg-black opacity-60"></div>
	<!-- navbar -->

<nav class="relative z-10 mx-5 flex justify-between items-center py-4 md:py-0 md:mx-20">
	<!-- Logo -->
	<div>
		<img src={Logo} alt="logo" class="w-28 md:w-32" />
	</div>

	<!-- Desktop Links -->
	<div class="hidden items-center gap-20 font-[200] lg:flex">
		<ul class="flex gap-10 text-[15px]">
			<li><a href="#how-it-works"class="relative  after:absolute after:left-0 after:-bottom-1 after:h-[2px] after:w-0 after:bg-[#FFEFC2] after:transition-all after:duration-300 hover:after:w-full hover:text-white/80">How It Works</a></li>
			<li><a href="#your-card" class="relative  after:absolute after:left-0 after:-bottom-1 after:h-[2px] after:w-0 after:bg-[#FFEFC2] after:transition-all after:duration-300 hover:after:w-full hover:text-white/80">Your Card</a></li>
			<li><a href="#benefits" class="relative  after:absolute after:left-0 after:-bottom-1 after:h-[2px] after:w-0 after:bg-[#FFEFC2] after:transition-all after:duration-300 hover:after:w-full hover:text-white/80">Benefits</a></li>
		</ul>
		<a
			href="#about"
			class="group inline-block rounded-[10px] bg-[#FFEFC2] px-7 py-3 text-[14px] font-[700] uppercase text-black transition-all duration-300 hover:scale-105 hover:shadow-lg hover:opacity-95"
			><span class="group-hover:tracking-wider transition-all duration-300">Get Started</span></a
		>
	</div>

	<!-- Mobile Hamburger -->
	<button
		class="block lg:hidden focus:outline-none"
		on:click={() => (isOpen = !isOpen)}
	>
		<svg
			xmlns="http://www.w3.org/2000/svg"
			fill="none"
			viewBox="0 0 24 24"
			stroke="currentColor"
			class="w-8 h-8 text-white cursor-pointer"
		>
			{#if isOpen}
				<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
			{:else}
				<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
			{/if}
		</svg>
	</button>

	<!-- Mobile Menu -->
	{#if isOpen}
		<div class="absolute top-full left-0 w-full bg-black/15 p-5 shadow-lg lg:hidden">
			<ul class="space-y-4 text-[16px] font-medium text-white">
				<li><a href="#how-it-works" class="relative  after:absolute after:left-0 after:-bottom-1 after:h-[2px] after:w-0 after:bg-[#FFEFC2] after:transition-all after:duration-300 hover:after:w-full hover:text-white/80" on:click={() => (isOpen = false)}>How It Works</a></li>
				<li><a href="#your-card" class="relative  after:absolute after:left-0 after:-bottom-1 after:h-[2px] after:w-0 after:bg-[#FFEFC2] after:transition-all after:duration-300 hover:after:w-full hover:text-white/80" on:click={() => (isOpen = false)}>Your Card</a></li>
				<li><a href="#benefits" class="relative  after:absolute after:left-0 after:-bottom-1 after:h-[2px] after:w-0 after:bg-[#FFEFC2] after:transition-all after:duration-300 hover:after:w-full hover:text-white/80" on:click={() => (isOpen = false)}>Benefits</a></li>
				<li>
					<a
						href="#about"
						class="max-w-[300px] w-full block rounded-[10px] bg-[#FFEFC2] px-4 py-2 text-center text-black font-bold uppercase mx-auto group transition-all duration-300 hover:scale-105 hover:shadow-lg hover:opacity-95"
						on:click={() => (isOpen = false)}
					><span class="group-hover:tracking-wider transition-all duration-300">Get Started</span></a>
				</li>
			</ul>
		</div>
	{/if}
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

<!-- ============================About section======================== -->
<section
id="about"
	class="item-center relative mx-5 flex min-h-screen flex-col justify-center gap-20 overflow-x-hidden py-10 md:py-20 md:mx-20"
>
	<div class="gap-18 flex flex-col xl:flex-row">
		<div class="flex flex-col gap-8">
			<div
				class="lg:text[37px] w-[350px] text-[37px] uppercase tracking-tighter sm:text-[37px] md:leading-none lg:w-[609px] xl:text-[64px]"
			>
				BUY, SAVE, SPEND GOLD. <span class="italic">SEAMLESSLY</span>
			</div>
			<p
				class="lg:ml-50 text-[20px] font-[200] lowercase sm:text-[20px] lg:w-[679px] lg:text-[25px] xl:text-[32px]"
			>
				ault Is An Exclusive Concierge Service Designed For High Net-Worth Individuals. To Provide A
				Seamless Experience In The Purchase And Management Of Allocated Gold. Created For Those Who
				Demand Security, Wealth Preservation, And At The Same Time, Instant Access To Traditional
				Gold Ownership By Enabling Real Time Spending Of Gold Assets.
			</p>
			<button
				class="lg:ml-50 h-[45px] w-[200px] cursor-pointer rounded-[10px] bg-[#FFEFC2] text-[15px] font-[400] uppercase text-black md:text-[20px] lg:h-[88px] lg:w-[374px]"
				>JOIN AULT</button
			>
		</div>
		<div class="w-full h-[500px] sm:w-[400px] lg:h-[740px] lg:w-[587px] mx-auto items-center flex overflow-hidden">
			<img src={AboutImg} alt="about-img" class="w-full" />
		</div>
	</div>

	<div class="grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-3">
		<div class="flex h-[416px] flex-col justify-between rounded-[24px] bg-[#212121] p-7">
			<div class="flex max-w-[165px]">
				<img src={Security} alt="security" class="w-full" />
			</div>
			<div>
				<h3 class="text-[25px] font-[700]">Security</h3>
				<p class="mb-7 text-[15px] font-[200] md:text-[18px] md:w-full max-w-[300px]">
					All Deposits Are Automatically Converted To Physical Allocated Gold Which Are Stored In
					LBMA-Certified Vaults In Zurich, London And Dubai.
				</p>
			</div>
		</div>
		<div class="flex h-[416px] flex-col justify-between rounded-[24px] bg-[#212121] p-7">
			<div class="flex max-w-[165px]">
				<img src={Exclusivity} alt="security" class="w-full" />
			</div>
			<div>
				<h3 class="text-[25px] font-[700]">Exclusivity</h3>
				<p class="mb-7 text-[15px] font-[200] md:text-[18px] md:w-full max-w-[300px]">
					Our referral-only model ensures you belong to a carefully curated group of members and
					that we deliver a personalized service, tailored to your needs.
				</p>
			</div>
		</div>
		<div class="flex h-[416px] flex-col justify-between rounded-[24px] bg-[#212121] p-7">
			<div class="flex max-w-[165px]">
				<img src={Liquidity} alt="security" class="w-full" />
			</div>
			<div>
				<h3 class="text-[25px] font-[700]">Liquidity</h3>
				<p class="mb-7 text-[15px] font-[200] md:text-[18px] md:w-full max-w-[300px]">
					Seamless Access To Your Funds. Withdraw, Transfer, Or Spend Your Allocated Gold Assets
					Wherever And Whenever Needed.
				</p>
			</div>
		</div>
	</div>
</section>

<!-- ============================Historical Performance section======================== -->

<!-- ============================How It Works section======================== -->
<section
	id="how-it-works"
	class="item-center relative mx-5 flex min-h-screen flex-col justify-center gap-20 overflow-x-hidden py-10 md:py-20 md:mx-20"
>
	<div class="flex flex-col gap-6">
		<h1
			class="lg:text[37px] w-[350px] text-[37px] uppercase tracking-tighter sm:text-[37px] md:leading-none lg:w-[609px] xl:text-[64px]"
		>
			How It Works
		</h1>
		<div class="grid grid-cols-1 gap-10 md:grid-cols-2 md:gap-3 xl:grid-cols-4">
			<div class="flex max-h-[598px] justify-center h-auto flex-col gap-5 rounded-[24px] bg-[#212121] p-7">
				<div class="mx-auto flex max-w-[165px]">
					<img src={Invitation} alt="invitation" class="w-full" />
				</div>
				<div>
					<p class="text-[20px] font-[300]">Step 1:</p>
					<h3 class="text-[25px] font-[500]">Invitation & Consultation</h3>
					<p class="mb-7 text-[15px] font-[200] capitalize md:text-[18px] mt-3">
						Your onboarding begins with an exclusive referral. A dedicated Relationship Manager will
						conduct a personalized consultation to understand your financial goals and preferences.
					</p>
				</div>
			</div>
			<div class="flex max-h-[598px] justify-center h-auto flex-col gap-5 rounded-[24px] bg-[#212121] p-7">
				<div class="mx-auto flex max-w-[165px]">
					<img src={Setup} alt="setup" class="w-full" />
				</div>
				<div>
					<p class="text-[20px] font-[300]">Step 2:</p>
					<h3 class="text-[25px] font-[500]">Account Setup & Verification</h3>
					<p class="mb-7 text-[15px] font-[200] capitalize md:text-[18px] mt-3">
						Our team will guide you through verification and set up your AULT account. Once funded,
						gold is purchased within three business days, ensuring wealth protection.
					</p>
				</div>
			</div>
			<div class="flex max-h-[598px] justify-center h-auto flex-col gap-5 rounded-[24px] bg-[#212121] p-7">
				<div class="mx-auto flex max-w-[165px]">
					<img src={Platform} alt="platform" class="w-full" />
				</div>
				<div>
					<p class="text-[20px] font-[300]">Step 3:</p>
					<h3 class="text-[25px] font-[500]">Platform Access</h3>
					<p class="mb-7 text-[15px] font-[200] capitalize md:text-[18px] mt-3">
						You’ll receive access to AULT’s secure web app. Your Relationship Manager will assist in
						navigating the platform for managing assets and accessing exclusive services.
					</p>
				</div>
			</div>
			<div class="flex max-h-[598px] justify-center flex-col gap-5 rounded-[24px] bg-[#212121] p-7">
				<div class="mx-auto flex max-w-[165px]">
					<img src={Card} alt="card" class="w-full" />
				</div>
				<div>
					<p class="text-[20px] font-[300]">Step 4:</p>
					<h3 class="text-[25px] font-[500]">Ault Card Issuance</h3>
					<p class="mb-7 text-[15px] font-[200] capitalize md:text-[18px] mt-3">
						An exclusive AULT Card will be issued, providing global access to your gold for seamless
						spending.
					</p>
				</div>
			</div>
		</div>
		<p class="font-[400] lg:text-[25px] 3xl:text-[42px]">
			Exceptional service begins with a personal connection. As a member, you are paired with a
			dedicated Relationship Manager who acts as your trusted advisor, available round the clock to
			handle your requests and enquiries. From managing your assets to offering personalized
			experiences, your Relationship Manager ensures that every detail is addressed with precision
			and confidentiality.
		</p>
		<button
			class="h-[45px] w-[200px] cursor-pointer rounded-[10px] bg-[#FFEFC2] text-[15px] font-[400] uppercase text-black md:text-[20px] lg:h-[88px] lg:w-[374px]"
			>JOIN AULT</button
		>
	</div>
</section>

<!-- ============================Your Card section======================== -->
<section
	id="your-card"
	class="item-center relative mx-5 flex min-h-[50%] flex-col justify-center gap-20 overflow-x-hidden py-10 md:py-20 md:mx-20"
>
	<div
		class="relative z-0 mx-auto overflow-hidden rounded-[26px] bg-[#212121] lg:min-w-[1001px] lg:rounded-[76px]"
	>
		<div class="h-[809px]">
			<div class="absolute bottom-[-30%] right-[-200px] object-contain lg:w-[1651px]">
				<img src={AultOnGold} alt="ault-on-gold" class="w-full" />
			</div>
			<div class="pb-50 relative z-10 flex flex-col gap-3 p-5 capitalize lg:p-20">
				<h1 class="5xl:text-[96px] text-xl uppercase sm:text-[45px]">
					Gold In Your Hands, <br /> Anytime, Anywhere.
				</h1>
				<p class="text-sm md:w-[572px] lg:text-[18px]">
					Experience True Freedom. With Your AULT Mastercard, You Can Spend Your Gold as Currency
					Anywhere in the World, take credit against your gold or spend your returns from leasing
					your gold.
				</p>
				<button
					class="h-[45px] w-[200px] cursor-pointer rounded-[10px] bg-[#FFEFC2] text-[15px] font-[400] capitalize text-black md:text-[20px] lg:h-[88px] lg:w-[374px]"
					>Get your card</button
				>
			</div>
		</div>
	</div>
</section>

<!-- ============================Experience section======================== -->
<section
	class="item-center relative mx-5 flex min-h-full flex-col justify-center gap-20 overflow-x-hidden py-10 md:py-20 md:mx-20"
>
	<div class="flex flex-col gap-5">
		<h1
			class="lg:text[37px] w-[350px] text-[37px] uppercase tracking-tighter sm:text-[37px] md:leading-none lg:w-[609px] xl:text-[64px]"
		>
			The ault experiences
		</h1>
		<p class="font-[400] lg:text-[25px] 3xl:text-[42px]">
			An Experience That Blends Security, Flexibility And Exclusivity -Delivering True Freedom.
		</p>
		<div class="grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-3">
			<div class="flex h-full w-full flex-col gap-5 overflow-hidden">
				<div class="h-full max-h-[286px] w-full overflow-hidden">
					<img
						src={Experience1}
						alt="experience"
						class="h-full w-full object-cover object-center"
					/>
				</div>
				<div>
					<h3 class="lg:text-32px font-[500] tracking-normal">24/7 Concierge:</h3>
					<p class="lg:tex-[20px] text-[12px] md:text-[15px] font-[200] tracking-normal">
						We handle your requests on AULT services and privileges, ensuring that your needs are
						met whenever.
					</p>
				</div>
			</div>
			<div class="flex h-full w-full flex-col gap-5 overflow-hidden">
				<div class="h-full max-h-[286px] w-full overflow-hidden">
					<img
						src={Experience2}
						alt="experience"
						class="h-full w-full object-cover object-center"
					/>
				</div>
				<div>
					<h3 class="lg:text-32px font-[500] tracking-normal">Global Support:</h3>
					<p class="lg:tex-[20px] text-[12px] md:text-[15px] font-[200] tracking-normal">
						AULT’s global network ensures seamless access to your gold, across borders. AULT ensures
						your service requirements are met wherever life takes you.
					</p>
				</div>
			</div>
			<div class="flex h-full w-full flex-col gap-5 overflow-hidden">
				<div class="h-full max-h-[286px] w-full overflow-hidden">
					<img
						src={Experience3}
						alt="experience"
						class="h-full w-full object-cover object-center"
					/>
				</div>
				<div>
					<h3 class="lg:text-32px font-[500] tracking-normal">Effortless Fund Access:</h3>
					<p class="lg:tex-[20px] text-[12px] md:text-[15px] font-[200] tracking-normal">
						Managing your allocated gold has never been simpler. With AULT, you can access your gold
						effortlessly and send instructions securely via  the web app.
					</p>
				</div>
			</div>
		</div>
	</div>
</section>

<!-- ============================Benefit section======================== -->
<section
	id="benefits"
	class="item-center relative mx-5 flex min-h-full flex-col justify-center gap-20 overflow-x-hidden py-10 md:py-20 md:mx-20"
>
	<div class="flex flex-col gap-5">
		<h1
			class="lg:text[37px] w-[350px] text-[37px] uppercase tracking-tighter sm:text-[37px] md:leading-none lg:w-[609px] xl:text-[64px]"
		>
			Benefits
		</h1>
		<p class="font-[400] lg:text-[25px] 3xl:text-[42px]">
			As a member, you gain access to exclusive travel, lifestyle, and financial perks through our 
			partnerships with Providus Bank and Mastercard World Elite.
		</p>
		<div class="grid grid-cols-2 space-x-3 space-y-8 sm:space-x-8 lg:ml-[150px] md:grid-cols-3 lg:grid-cols-4">
			<div class="rounded-2xl border border-white sm:px-5 py-5 pb-10 px-2">
				<h3 class="lg:text-32px font-[500] tracking-normal">Concierge Services:</h3>
				<p class="lg:tex-[20px] text-[12px] md:text-[15px] font-[200] tracking-normal">
					Personalized assistance for travel planning, dining reservations, and more.
				</p>
			</div>
			<div class="rounded-2xl border border-white sm:px-5 py-5 pb-10 px-2">
				<h3 class="lg:text-32px font-[500] tracking-normal">Concierge Services:</h3>
				<p class="lg:tex-[20px] text-[12px] md:text-[15px] font-[200] tracking-normal">
					Personalized assistance for travel planning, dining reservations, and more.
				</p>
			</div>
			<div class="rounded-2xl border border-white sm:px-5 py-5 pb-10 px-2">
				<h3 class="lg:text-32px font-[500] tracking-normal">Concierge Services:</h3>
				<p class="lg:tex-[20px] text-[12px] md:text-[15px] font-[200] tracking-normal">
					Personalized assistance for travel planning, dining reservations, and more.
				</p>
			</div>
			<div class="rounded-2xl border border-white sm:px-5 py-5 pb-10 px-2">
				<h3 class="lg:text-32px font-[500] tracking-normal">Concierge Services:</h3>
				<p class="lg:tex-[20px] text-[12px] md:text-[15px] font-[200] tracking-normal">
					Personalized assistance for travel planning, dining reservations, and more.
				</p>
			</div>
			<div class="rounded-2xl border border-white sm:px-5 py-5 pb-10 px-2">
				<h3 class="lg:text-32px font-[500] tracking-normal">Concierge Services:</h3>
				<p class="lg:tex-[20px] text-[12px] md:text-[15px] font-[200] tracking-normal">
					Personalized assistance for travel planning, dining reservations, and more.
				</p>
			</div>
			<div class="rounded-2xl border border-white sm:px-5 py-5 pb-10 px-2">
				<h3 class="lg:text-32px font-[500] tracking-normal">Concierge Services:</h3>
				<p class="lg:tex-[20px] text-[12px] md:text-[15px] font-[200] tracking-normal">
					Personalized assistance for travel planning, dining reservations, and more.
				</p>
			</div>
			<div class="rounded-2xl border border-white sm:px-5 py-5 pb-10 px-2">
				<h3 class="lg:text-32px font-[500] tracking-normal">Concierge Services:</h3>
				<p class="lg:tex-[20px] text-[12px] md:text-[15px] font-[200] tracking-normal">
					Personalized assistance for travel planning, dining reservations, and more.
				</p>
			</div>
			<div class="rounded-2xl border border-white sm:px-5 py-5 pb-10 px-2">
				<h3 class="lg:text-32px font-[500] tracking-normal">Concierge Services:</h3>
				<p class="lg:tex-[20px] text-[12px] md:text-[15px] font-[200] tracking-normal">
					Personalized assistance for travel planning, dining reservations, and more.
				</p>
			</div>
		</div>
	</div>
</section>

<!-- ============================Our Patner section======================== -->
<section
	id="partner"
	class="item-center relative mx-5 flex min-h-[50%] flex-col justify-center gap-20 overflow-x-hidden py-10 md:py-20 md:mx-20"
>
	<div
		class="mx-auto flex min-h-[284px] max-w-[1016px] flex-col justify-center gap-10 rounded-[46px] bg-[#1C1C1C] px-20 py-10 text-center"
	>
		<h1 class="text-[20px] font-[200] uppercase lg:text-[64px]">OUR PARTNERS</h1>
		<div class="flex flex-col justify-center">
			<div class="grid grid-cols-3 items-center justify-center gap-8 lg:grid-cols-5">
				<img src={Partner1} alt="partner" class="w-[120px] opacity-[60%]" />
				<img src={Partner2} alt="partner" class="w-[68px] opacity-[60%]" />
				<img src={Partner3} alt="partner" class="w-[204px] opacity-[60%]" />
				<img src={Partner4} alt="partner" class="w-[152px] opacity-[60%]" />
				<img src={Partner5} alt="partner" class="w-[115px] opacity-[60%]" />
			</div>
		</div>
	</div>
</section>

<!-- ============================Footer section======================== -->
<footer
	class="item-center relative mx-5 flex  flex-col gap-3 md:gap-10 overflow-x-hidden py-10 md:py-20 md:mx-20"
>
	<div class="font-[200] lg:text-[18px] text-[12px] flex justify-between gap-8 uppercase">
		<div class="w-[238px]">
			AULT 2024.<br />
			27 OLD GLOUCESTER STREET, LONDON, UNITED KINGDOM, WC1N 3AX
		</div>
		<div class="w-[238px]">
			your Journey to more <br />
			begins here.
		</div>
	</div>
	<div class="w-full">
		<img src={FooterLogo} alt="footer-logo" class="w-full">
	</div>
</footer>
