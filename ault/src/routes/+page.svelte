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
	import Service1 from '$lib/assets/service1.jpg';
	import Service2 from '$lib/assets/service2.png';
	import Service3 from '$lib/assets/service3.png';
	import Partner1 from '$lib/assets/partner1.png';
	import Partner2 from '$lib/assets/partner2.png';
	import Partner3 from '$lib/assets/partner3.png';
	import Partner4 from '$lib/assets/partner4.png';
	import Partner5 from '$lib/assets/partner5.png';
	import FooterLogo from '$lib/assets/footer-logo.png';
	import Gold from '$lib/assets/golden.png';
	import HowItWorksImg from '$lib/assets/how-it-works.png';
	import CardBackground from '$lib/assets/card-bg.png';
	import BenefitImg from '$lib/assets/benefit.jpg';
	import BenefitImg2 from '$lib/assets/benefit2.png';
	import AultGold from '$lib/assets/ault-gold.png';

	let isOpen = false;
</script>

<!-- ============================Hero section======================== -->
<section
	class="relative flex min-h-screen flex-col gap-20 overflow-x-hidden py-10"
	style="background-image: url({HeroBackground}); background-size: cover; background-position: center; background-repeat: no-repeat;"
>
	<!-- Gradient overlay -->
	<div class="absolute inset-0 z-0 bg-black opacity-60"></div>
	<!-- navbar -->

	<nav class="relative z-10 mx-5 flex items-center justify-between py-4 md:py-0">
		<!-- Logo -->
		<div>
			<img src={Logo} alt="logo" class="w-28 md:w-32" />
		</div>

		<!-- Desktop Links -->
		<div class="hidden items-center gap-20 font-[442] lg:flex">
			<ul class="flex gap-10 text-[15px]">
				<li>
					<a
						href="#how-it-works"
						class="relative after:absolute after:-bottom-1 after:left-0 after:h-[2px] after:w-0 after:bg-[#D9D9D9] after:transition-all after:duration-300 hover:text-white/80 hover:after:w-full"
						>Discover</a
					>
				</li>
				<li>
					<a
						href="#your-card"
						class="relative after:absolute after:-bottom-1 after:left-0 after:h-[2px] after:w-0 after:bg-[#D9D9D9] after:transition-all after:duration-300 hover:text-white/80 hover:after:w-full"
						>Your Card</a
					>
				</li>
				<li>
					<a
						href="#benefits"
						class="relative after:absolute after:-bottom-1 after:left-0 after:h-[2px] after:w-0 after:bg-[#D9D9D9] after:transition-all after:duration-300 hover:text-white/80 hover:after:w-full"
						>Benefits</a
					>
				</li>
				<li>
					<a
						href="#insight"
						class="relative after:absolute after:-bottom-1 after:left-0 after:h-[2px] after:w-0 after:bg-[#D9D9D9] after:transition-all after:duration-300 hover:text-white/80 hover:after:w-full"
						>Insight</a
					>
				</li>
			</ul>
			<div class="flex gap-5">
				<a
					href="#log-in"
					class="group grid h-[55px] w-[189px] place-items-center rounded-[10px] bg-[#D9D9D9] text-center text-[14px] font-[700] uppercase text-black transition-all duration-300 hover:scale-105 hover:opacity-95 hover:shadow-lg"
					><span class="transition-all duration-300 group-hover:tracking-wider">LOG-IN</span></a
				>
				<a
					href="#about"
					class="group grid h-[55px] w-[189px] place-items-center rounded-[10px] bg-[#D9D9D9] text-center text-[14px] font-[700] uppercase text-black transition-all duration-300 hover:scale-105 hover:opacity-95 hover:shadow-lg"
					><span class="transition-all duration-300 group-hover:tracking-wider">Get Started</span
					></a
				>
			</div>
		</div>

		<!-- Mobile Hamburger -->
		<button class="block focus:outline-none lg:hidden" on:click={() => (isOpen = !isOpen)}>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				fill="none"
				viewBox="0 0 24 24"
				stroke="currentColor"
				class="h-8 w-8 cursor-pointer text-white"
			>
				{#if isOpen}
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M6 18L18 6M6 6l12 12"
					/>
				{:else}
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M4 6h16M4 12h16M4 18h16"
					/>
				{/if}
			</svg>
		</button>

		<!-- Mobile Menu -->
		{#if isOpen}
			<div class="absolute left-0 top-full w-full bg-black/15 p-5 shadow-lg lg:hidden">
				<ul class="space-y-4 text-center text-[16px] font-medium text-white">
					<li>
						<a
							href="#how-it-works"
							class="relative after:absolute after:-bottom-1 after:left-0 after:h-[2px] after:w-0 after:bg-[#D9D9D9] after:transition-all after:duration-300 hover:text-white/80 hover:after:w-full"
							on:click={() => (isOpen = false)}>Discover</a
						>
					</li>
					<li>
						<a
							href="#your-card"
							class="relative after:absolute after:-bottom-1 after:left-0 after:h-[2px] after:w-0 after:bg-[#D9D9D9] after:transition-all after:duration-300 hover:text-white/80 hover:after:w-full"
							on:click={() => (isOpen = false)}>Your Card</a
						>
					</li>
					<li>
						<a
							href="#benefits"
							class="relative after:absolute after:-bottom-1 after:left-0 after:h-[2px] after:w-0 after:bg-[#D9D9D9] after:transition-all after:duration-300 hover:text-white/80 hover:after:w-full"
							on:click={() => (isOpen = false)}>Benefits</a
						>
					</li>
					<li>
						<a
							href="#insight"
							class="relative after:absolute after:-bottom-1 after:left-0 after:h-[2px] after:w-0 after:bg-[#D9D9D9] after:transition-all after:duration-300 hover:text-white/80 hover:after:w-full"
							on:click={() => (isOpen = false)}>Insight</a
						>
					</li>
					<li>
						<a
							href="#log-in"
							class="group mx-auto block w-full max-w-[300px] rounded-[10px] bg-[#D9D9D9] px-4 py-2 text-center font-bold uppercase text-black transition-all duration-300 hover:scale-105 hover:opacity-95 hover:shadow-lg"
							on:click={() => (isOpen = false)}
							><span class="transition-all duration-300 group-hover:tracking-wider">LOG-IN</span></a
						>
					</li>
					<li>
						<a
							href="#about"
							class="group mx-auto block w-full max-w-[300px] rounded-[10px] bg-[#D9D9D9] px-4 py-2 text-center font-bold uppercase text-black transition-all duration-300 hover:scale-105 hover:opacity-95 hover:shadow-lg"
							on:click={() => (isOpen = false)}
							><span class="transition-all duration-300 group-hover:tracking-wider"
								>Get Started</span
							></a
						>
					</li>
				</ul>
			</div>
		{/if}
	</nav>

	<!-- hero content -->
	<div class="relative z-10 mx-5 flex flex-col text-center">
		<div
			class="lg:text[60px] 3xl:text-[96px] text-[27px] font-[200] uppercase tracking-tighter sm:text-[45px] md:leading-none xl:text-[70px]"
		>
			timeless security,<br />modern convenience
		</div>
		<p class="text-[13px] font-[316] lg:text-[20px] xl:text-[27px]">
			Gold made Flexible and Tailored For You
		</p>
	</div>
</section>

<!-- ============================About section======================== -->
<section
	id="about"
	class="item-center relative mx-5 flex min-h-screen flex-col justify-center gap-40 overflow-x-hidden py-10 text-center md:mx-20 md:py-20"
>
	<div class="mx-auto flex flex-col justify-center gap-5">
		<div
			class="lg:text[37px] 3xl:text-[64px] mx-auto flex gap-3 text-[37px] uppercase tracking-tighter sm:text-[37px] md:leading-none"
		>
			<span>BUY.</span>
			<span class="text-[#686868]">SPEND.</span>
			<span class="text-[#686868]"> MORE.</span>
		</div>
		<div class="mx-auto flex flex-col gap-2 font-[442] md:w-[400px]">
			<h2 class="text-[36px] capitalize">Own With Confidence</h2>
			<p class="text-[20px] text-[#FFFFFFCC]">
				Securely purchase and hold physical allocated gold, safely stored in LBMA-certified vaults.
			</p>
		</div>
		<div>
			<div class="mx-auto mt-3 flex w-[131px] justify-center">
				<img src={Gold} alt="gold" class="w-full" />
			</div>
		</div>
		<div class="text-[36px] font-[316] capitalize text-[#E4E4E4] lg:w-[787px]">
			AULT Is A Concierge Service That Transforms Physical Allocated Gold Into A Liquid Financial
			Asset. Through Advance Tokenization And Trusted Institutional Partnerships, We Empower You To
			Buy, Hold, Spend, Lease, And Borrow-Against Gold With Unmatched Freedom And Confidence.
		</div>
	</div>

	<div class="mx-auto flex flex-col gap-20">
		<h1
			class="lg:text[37px] 3xl:text-[64px] mx-auto text-[37px] font-[316] uppercase sm:text-[37px]"
		>
			BEYOND WEALTH. BEYOND GOLD.
		</h1>

		<div class="grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-3">
			<div class="flex h-[333px] flex-col gap-5">
				<div class="mx-auto flex max-w-[165px]">
					<img src={Security} alt="security" class="w-full" />
				</div>
				<div>
					<h3 class="text-[25px] font-[700]">Security</h3>
					<p class="mb-7 max-w-[300px] text-[15px] font-[200] md:w-full md:text-[18px]">
						All Deposits Are Automatically Converted To Physical Allocated Gold Which Are Stored In
						LBMA-Certified Vaults In Zurich, London And Dubai.
					</p>
				</div>
			</div>
			<div class="flex h-[333px] flex-col gap-5">
				<div class="mx-auto flex max-w-[165px]">
					<img src={Exclusivity} alt="security" class="w-full" />
				</div>
				<div>
					<h3 class="text-[25px] font-[700]">Exclusivity</h3>
					<p class="mb-7 max-w-[300px] text-[15px] font-[200] md:w-full md:text-[18px]">
						Our referral-only model ensures you belong to a carefully curated group of members and
						that we deliver a personalized service, tailored to your needs.
					</p>
				</div>
			</div>
			<div class="flex h-[333px] flex-col gap-5">
				<div class="mx-auto flex max-w-[165px]">
					<img src={Liquidity} alt="security" class="w-full" />
				</div>
				<div>
					<h3 class="text-[25px] font-[700]">Liquidity</h3>
					<p class="mb-7 max-w-[300px] text-[15px] font-[200] md:w-full md:text-[18px]">
						Seamless Access To Your Funds. Withdraw, Transfer, Or Spend Your Allocated Gold Assets
						Wherever And Whenever Needed.
					</p>
				</div>
			</div>
		</div>
	</div>
</section>

<!-- ============================How It Works section======================== -->
<section
	id="how-it-works"
	class="item-center relative flex min-h-screen flex-col justify-center gap-20 overflow-x-hidden bg-[#181818] px-5 py-10 md:px-20 md:py-20"
>
	<div class="flex flex-col font-[316] lg:flex-row lg:justify-between">
		<h1
			class="lg:text[37px] text-[37px] uppercase tracking-tighter sm:text-[37px] md:w-[282px] md:leading-none xl:text-[60px]"
		>
			How It Works
		</h1>
		<p class="text-[36px] capitalize text-[#FFFFFFCC] lg:w-[1006px]">
			Exceptional service begins with a personal connection. As a member, you are paired with a
			dedicated Relationship Manager who acts as your trusted advisor — available around the clock
			to handle your requests with precision and confidentiality.
		</p>
	</div>
	<div class="flex flex-col justify-between gap-[76px] lg:flex-row">
		<div>
			<img src={HowItWorksImg} alt="how-it-works-img" />
		</div>
		<div class="flex flex-col gap-10">
			<div class="grid grid-cols-1 gap-[41px] lg:grid-cols-2">
				<div class="flex max-w-[316px] flex-col gap-9">
					<div>
						<div class="h-3 w-3 rounded-full bg-[#7D7D7D]"></div>
					</div>
					<div class="grid gap-2">
						<h3 class="text-[20px] font-[571] capitalize">Step 1: Invitation & Consultation</h3>
						<p class="captalize text-[20px] font-[200]">
							Your journey starts with an exclusive referral. Your Relationship Manager conducts a
							personalized consultation to understand your financial goals and preferences.
						</p>
					</div>
				</div>
				<div class="flex max-w-[316px] flex-col gap-9">
					<div class="flex gap-1">
						<div class="-mt-1 h-3 w-3 rounded-full bg-[#7D7D7D]"></div>
						<div class="h-3 w-3 rounded-full bg-[#7D7D7D]"></div>
					</div>
					<div class="grid gap-2">
						<h3 class="text-[20px] font-[571] capitalize">Step 2: Account Setup & Verification</h3>
						<p class="captalize text-[20px] font-[200]">
							Our team guides you through verification and sets up your AULT account. Once funded,
							your gold is purchased and securely stored within three business days.
						</p>
					</div>
				</div>
				<div class="flex max-w-[316px] flex-col gap-9">
					<div class="flex gap-1">
						<div class="-mt-1 h-3 w-3 rounded-full bg-[#7D7D7D]"></div>
						<div class="h-3 w-3 rounded-full bg-[#7D7D7D]"></div>
						<div class="-mt-1 h-3 w-3 rounded-full bg-[#7D7D7D]"></div>
					</div>
					<div class="grid gap-2">
						<h3 class="text-[20px] font-[571] capitalize">Step 3: Platform Access</h3>
						<p class="captalize text-[20px] font-[200]">
							You receive secure access to the AULT web app. Your Relationship Manager helps you
							navigate the platform to manage assets and access exclusive services.
						</p>
					</div>
				</div>
				<div class="flex max-w-[316px] flex-col gap-9">
					<div class="flex gap-1">
						<div class="-mt-1 h-3 w-3 rounded-full bg-[#7D7D7D]"></div>
						<div class="h-3 w-3 rounded-full bg-[#7D7D7D]"></div>
						<div class="-mt-1 h-3 w-3 rounded-full bg-[#7D7D7D]"></div>
						<div class="h-3 w-3 rounded-full bg-[#7D7D7D]"></div>
					</div>
					<div class="grid gap-2">
						<h3 class="text-[20px] font-[571] capitalize">Step 4: AuLT Card Issuance</h3>
						<p class="captalize text-[20px] font-[200]">
							An exclusive AULT Mastercard is issued, providing seamless global access to your gold
							for spending anytime, anywhere.
						</p>
					</div>
				</div>
			</div>
			<button
				class="h-[45px] w-[200px] cursor-pointer rounded-[10px] bg-[#D9D9D9] text-[15px] font-[442] uppercase text-black md:text-[20px] lg:h-[55px] lg:w-[211px]"
				>JOIN AULT</button
			>
		</div>
	</div>
</section>

<!-- ============================Your Card section======================== -->
<section
	id="your-card"
	class="item-center relative flex min-h-screen flex-col justify-center gap-20 overflow-hidden px-5 py-10 md:px-20 md:py-0"
	style="background-image: url({CardBackground}); background-size: cover; background-position: center; background-repeat: no-repeat;"
>
	<div class="uppecase relative z-0 text-[18vw] font-[200] tracking-[0.03em] text-[#181818]">
		LIMITLESS
	</div>
	<div class="relative mt-auto">
		<div class="pb-50 relative z-20 flex flex-col gap-8 p-5 capitalize lg:p-20">
			<h1
				class="5xl:text-[64px] text-xl font-[200] uppercase tracking-tight sm:text-[30px] lg:text-5xl"
			>
				Gold In Your Hands, <br /> Anytime, Anywhere.
			</h1>
			<p class="w-[272px] text-sm font-[442] capitalize md:w-[572px] lg:text-[20px]">
				Experience True Freedom. With Your AULT Mastercard, You Can Spend Your Gold as Currency
				Anywhere in the World.
			</p>
			<button
				class="h-[45px] w-[200px] cursor-pointer rounded-[10px] bg-[#D9D9D9] text-[15px] font-[442] uppercase text-black md:text-[20px] lg:h-[55px] lg:w-[211px]"
				>Get your card</button
			>
		</div>
		<div class="absolute bottom-[3rem] right-[6rem] z-10 gap-9 object-contain xl:w-[522.2px]">
			<img src={AultOnGold} alt="ault-on-gold" class="w-full" />
		</div>
	</div>
</section>

<!-- ============================Services section======================== -->
<section
	class="item-center relative flex min-h-screen flex-col justify-center gap-20 overflow-x-hidden bg-[#181818] px-5 py-10 md:px-60 md:py-20"
>
	<div class="flex flex-col gap-20">
		<h1
			class="lg:text[37px] 3xl:w-[1138px] 3xl:text-[48px] w-[350px] text-[37px] font-[200] capitalize sm:text-[37px] lg:w-[809px]"
		>
			Unparalleled service that combines security, flexibility, and exclusivity tailored for you.
		</h1>
		<div class="grid grid-cols-1 gap-20 md:grid-cols-2 lg:grid-cols-3">
			<div class="flex h-full w-full flex-col gap-5 overflow-hidden">
				<div class="h-full max-h-[286px] w-full overflow-hidden">
					<img src={Service1} alt="service" class="h-full w-full object-cover object-center" />
				</div>
				<div>
					<h3 class="capitallize font-[571] tracking-normal lg:text-[20px]">24/7 Concierge:</h3>
					<p
						class="lg:tex-[20px] capitallize text-[12px] font-[200] tracking-normal md:text-[15px]"
					>
						We handle your requests on AULT services and privileges, ensuring that your needs are
						met whenever.
					</p>
				</div>
			</div>
			<div class="flex h-full w-full flex-col gap-5 overflow-hidden">
				<div class="h-full max-h-[286px] w-full overflow-hidden">
					<img src={Service2} alt="service" class="h-full w-full object-cover object-center" />
				</div>
				<div>
					<h3 class="capitallize font-[571] tracking-normal lg:text-[20px]">Global Support:</h3>
					<p
						class="lg:tex-[20px] capitallize text-[12px] font-[200] tracking-normal md:text-[15px]"
					>
						AULT’s global network ensures seamless access to your gold, across borders. AULT ensures
						your service requirements are met wherever life takes you.
					</p>
				</div>
			</div>
			<div class="flex h-full w-full flex-col gap-5 overflow-hidden">
				<div class="h-full max-h-[286px] w-full overflow-hidden">
					<img src={Service3} alt="service" class="h-full w-full object-cover object-center" />
				</div>
				<div>
					<h3 class="capitallize font-[571] tracking-normal lg:text-[20px]">
						Effortless Fund Access:
					</h3>
					<p
						class="lg:tex-[20px] capitallize text-[12px] font-[200] tracking-normal md:text-[15px]"
					>
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
	class="item-center relative mx-5 flex min-h-full flex-col justify-center gap-20 overflow-x-hidden py-10 md:mx-20 md:py-20"
>
	<div class="grid place-items-center lg:grid-cols-2">
		<div>
			<div class="relative flex w-[496px]">
				<img src={BenefitImg} alt="benefit-img" class="w-[367px]" />
				<img
					src={BenefitImg2}
					alt="benefit-img"
					class="absolute bottom-[-15rem] left-[-5rem] z-10 hidden max-w-[254px] lg:block"
				/>
			</div>
		</div>
		<div class="flex flex-col gap-10">
			<h1
				class="3xl:text-[64px] text-[20px] font-[316] capitalize leading-none sm:text-[25px] lg:text-[37px] xl:text-[45px]"
			>
				As a valued member, you unlock a world of personalized travel, lifestyle, and financial
				privileges, powered by our trusted partnership with Mastercard World Elite.
			</h1>
			<div class="grid gap-10 lg:grid-cols-2">
				<div class="flex flex-col space-y-[4px] text-[20px] font-[571] capitalize">
					Concierge Services: <span class="font-[200]"
						>Enjoy bespoke assistance with travel planning, dining reservations, and more — your
						dedicated team is here to curate seamless experiences.</span
					>
				</div>
				<div class="flex flex-col space-y-[4px] text-[20px] font-[571] capitalize">
					Fast-Track Security & Airport Concierge: <span class="font-[200]">
						Experience hassle-free travel with priority security screening and dedicated concierge
						support.</span
					>
				</div>
				<div class="flex flex-col space-y-[4px] text-[20px] font-[571] capitalize">
					Luxury Travel Discounts: <span class="font-[200]">
						Access exclusive offers at premier hotels and resorts, including renowned brands like
						Soneva and IHG</span
					>
				</div>
				<div class="flex flex-col space-y-[4px] text-[20px] font-[571] capitalize">
					Visa & Booking Discounts: <span class="font-[200]">
						Take advantage of exclusive deals on flights and hotels via partners like Booking.com
						and Cleartrip, with expert visa support from Fulfill Visa Services.</span
					>
				</div>
				<div class="flex flex-col space-y-[4px] text-[20px] font-[571] capitalize">
					Airport Lounge Access: <span class="font-[200]">
						Relax in luxury with complimentary entry to premium airport lounges worldwide — bring a
						guest along to share the experience.
					</span>
				</div>

				<div class="flex flex-col space-y-[4px] text-[20px] font-[571] capitalize">
					Car Rental Upgrades: <span class="font-[200]">
						Travel in style with complimentary vehicle upgrades at Hertz and Avis, enhancing your
						journey from start to finish.
					</span>
				</div>
				<div class="flex flex-col space-y-[4px] text-[20px] font-[571] capitalize">
					Global Blue VIP Services: <span class="font-[200]">
						Benefit from expedited VAT refunds at select international airports, making your travels
						smoother.</span
					>
				</div>
			</div>
		</div>
	</div>
</section>

<!-- ============================Our Patner section======================== -->
<section
	id="partner"
	class="item-center relative flex min-h-screen flex-col justify-center gap-20 overflow-x-hidden bg-[#181818] px-5 py-10 md:px-20 md:py-20"
>
	<div class="flex min-h-[284px] flex-col justify-center gap-10 rounded-[46px] px-20 py-10">
		<h1 class="3xl:text-[60px] text-[20px] font-[316] uppercase lg:text-[35px] xl:text-[50px]">
			OUR PARTNERS
		</h1>
		<p class="3xl:text-[36px] text-[18px] font-[316] lg:w-[907px] lg:text-[25px]">
			Our commitment to you is founded on trusted partnerships and a shared dedication to managing
			your assets with the highest standards of security, transparency, and personalized
			flexibility.
		</p>
		<div class="ml-55 flex flex-row gap-20">
			<div class="text-[20px] font-[571]">
				<h3>Emerging Africa</h3>
				<p class="font-[316] lg:w-[312px]">
					Oversees fiduciary responsibilities, safeguarding your gold assets with exceptional care
					and strict regulatory compliance.
				</p>
			</div>
			<div class="text-[20px] font-[571]">
				<h3>Providus Bank</h3>
				<p class="font-[316] lg:w-[312px]">
					Provides reliable and efficient card solutions, ensuring your funds remain secure,
					accessible, and available whenever you need them.
				</p>
			</div>
		</div>
		<div class="ml-auto max-w-[677px]">
			<img src={AultGold} alt="ault-gold" class="w-full" />
		</div>
	</div>
</section>

<!-- ============================Insight section======================== -->
<section
	id="insight"
	class="item-center md:px-50 relative mx-auto flex min-h-screen flex-col justify-center gap-20 overflow-hidden px-5 py-10 md:py-20"
>
	<!-- Left Glow -->
	<div
		class="absolute left-0 top-1/2 z-0 h-96 w-96 -translate-y-1/2 rounded-full bg-[#C686014D] blur-[130px]"
	></div>

	<!-- Right Glow -->
	<div
		class="absolute right-0 top-1/3 z-0 h-96 w-96 -translate-y-1/2 rounded-full bg-[#C686014D] blur-[130px]"
	></div>

	<div class="relative z-10 flex flex-col gap-10">
		<h1 class="lg:text[37px] 3xl:text-[64px] text-[37px] font-[316] uppercase sm:text-[37px]">
			Insight
		</h1>

		<div class="flex flex-col gap-3 text-[16px] lg:text-[20px]">
			<div class="rounded-[8px] border border-white cursor-pointer">
				<p class="p-3 font-[442]">What is AULT?</p>
			</div>
			<div class="rounded-[8px] border border-white cursor-pointer">
				<p class="p-3  font-[442]">What do I need to get started?</p>
			</div>
			<div class="rounded-[8px] border border-white cursor-pointer">
				<p class="p-3 font-[442]">Do I need to sell my gold to spend it?</p>
			</div>
			<div class="rounded-[8px] border border-white cursor-pointer">
				<p class="p-3 font-[442]">What are the benefits of the AULT Mastercard?</p>
			</div>
			<div class="rounded-[8px] border border-white cursor-pointer">
				<p class="p-3  font-[442]">What are the benefits of the AULT Mastercard?</p>
			</div>
			<div class="rounded-[8px] border border-white cursor-pointer">
				<p class="p-3 font-[442]">What are the benefits of the AULT Mastercard?</p>
			</div>
		</div>
	</div>
</section>

<!-- ============================Footer section======================== -->
<footer
	class="item-center relative mx-5 flex flex-col gap-3 overflow-x-hidden py-10 md:mx-20 md:gap-10 md:py-20"
>
	<div class="flex justify-between gap-8 text-[10px] font-[200] uppercase lg:text-[18px]">
		<div class="">
			AULT 2024.<br />
			27 OLD GLOUCESTER STREET, LONDON, UNITED KINGDOM, WC1N 3AX
		</div>
		<div class="flex gap-3 flex-col lg:flex-row">
			<div class="">
				<p>
					your Journey to more <br />
					begins here.
				</p>
			</div>
			<p class="uppercase">BUSINESs@goAULT.COM</p>
		</div>
	</div>
	<div class="w-full">
		<img src={FooterLogo} alt="footer-logo" class="w-full" />
	</div>
</footer>
