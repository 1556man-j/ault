<script>
	import { onMount } from 'svelte';
	import { browser } from '$app/environment';
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
	import PartnerImg from '$lib/assets/partner-img.jpg';
	import Gold from '$lib/assets/golden.png';
	import HowItWorksImg from '$lib/assets/how-it-works.png';
	import CardBackground from '$lib/assets/card-bg.png';
	import BenefitImg from '$lib/assets/benefit.jpg';
	import BenefitImg2 from '$lib/assets/benefit2.png';
	import AultGold from '$lib/assets/ault-gold.png';

	let isOpen = false;

	$: if (browser) {
		if (isOpen) {
			document.body.classList.add('overflow-hidden');
		} else {
			document.body.classList.remove('overflow-hidden');
		}
	}

	// =====================features===============
	export let features = [
		{
			title: 'Security',
			image: Security,
			description:
				'All Deposits Are Automatically Converted To Physical Allocated Gold Which Are Stored In LBMA-Certified Vaults In Zurich, London And Dubai.'
		},
		{
			title: 'Exclusivity',
			image: Exclusivity,
			description:
				'Our referral-only model ensures you belong to a carefully curated group of members and that we deliver a personalized service, tailored to your needs.'
		},
		{
			title: 'Liquidity',
			image: Liquidity,
			description:
				'Seamless Access To Your Funds. Withdraw, Transfer, Or Spend Your Allocated Gold Assets Wherever And Whenever Needed.'
		}
	];
	let currentIndex = 0;
	let perView = 1;
	let startX = 0;
	let slideCount = 1;

	const updatePerView = () => {
		perView = window.innerWidth >= 640 ? 2 : 1;
		slideCount = Math.ceil(features.length / perView);
	};

	const next = () => (currentIndex = (currentIndex + 1) % slideCount);
	const prev = () => (currentIndex = (currentIndex - 1 + slideCount) % slideCount);
	const goTo = (i) => (currentIndex = i);

	const handleTouchStart = (e) => (startX = e.touches[0].clientX);
	const handleTouchEnd = (e) => {
		let dx = e.changedTouches[0].clientX - startX;
		if (dx > 50) prev();
		else if (dx < -50) next();
	};

	onMount(() => {
		updatePerView();
		window.addEventListener('resize', updatePerView);

		updateStepView();
		window.addEventListener('resize', updateStepView);

		updateServiceView();
		window.addEventListener('resize', updateServiceView);

		updateBenefitView();
		window.addEventListener('resize', updateBenefitView);
	});

	// =======================step carousel ===============
	const steps = [
		{
			title: 'Step 1: Invitation & Consultation',
			dots: 1,
			description:
				'Your journey starts with an exclusive referral. Your Relationship Manager conducts a personalized consultation to understand your financial goals and preferences.'
		},
		{
			title: 'Step 2: Account Setup & Verification',
			dots: 2,
			description:
				'Our team guides you through verification and sets up your AULT account. Once funded, your gold is purchased and securely stored within three business days.'
		},
		{
			title: 'Step 3: Platform Access',
			dots: 3,
			description:
				'You receive secure access to the AULT web app. Your Relationship Manager helps you navigate the platform to manage assets and access exclusive services.'
		},
		{
			title: 'Step 4: AULT Card Issuance',
			dots: 4,
			description:
				'An exclusive AULT Mastercard is issued, providing seamless global access to your gold for spending anytime, anywhere.'
		}
	];

	let stepsIndex = 0;
	let stepPerView = 1;
	let stepSlideCount = 1;
	let stepStartX = 0;

	const updateStepView = () => {
		stepPerView = window.innerWidth >= 768 ? 2 : 1;
		stepSlideCount = Math.ceil(steps.length / stepPerView);
	};

	const goToStep = (i) => (stepsIndex = i);
	const nextStep = () => (stepsIndex = (stepsIndex + 1) % stepSlideCount);
	const prevStep = () => (stepsIndex = (stepsIndex - 1 + stepSlideCount) % stepSlideCount);

	const handleStepStart = (e) => (stepStartX = e.touches[0].clientX);
	const handleStepEnd = (e) => {
		let dx = e.changedTouches[0].clientX - stepStartX;
		if (dx > 50) prevStep();
		else if (dx < -50) nextStep();
	};

	// ======================services carousel ===================
	const services = [
		{
			title: '24/7 Concierge:',
			description: `We handle your requests on AULT services and privileges, ensuring that your needs are met whenever.`,
			image: Service1
		},
		{
			title: 'Global Support:',
			description: `AULT’s global network ensures seamless access to your gold, across borders. AULT ensures your service requirements are met wherever life takes you.`,
			image: Service2
		},
		{
			title: 'Effortless Fund Access:',
			description: `Managing your allocated gold has never been simpler. With AULT, you can access your gold effortlessly and send instructions securely via the web app.`,
			image: Service3
		}
	];
	let servicesIndex = 0;
	let perViewService = 1;
	let serviceSlideCount = 1;
	let serviceStartX = 0;

	const updateServiceView = () => {
		perViewService = window.innerWidth >= 768 ? 2 : 1;
		serviceSlideCount = Math.ceil(services.length / perViewService);
	};

	const goToService = (i) => (servicesIndex = i);
	const nextService = () => (servicesIndex = (servicesIndex + 1) % serviceSlideCount);
	const prevService = () =>
		(servicesIndex = (servicesIndex - 1 + serviceSlideCount) % serviceSlideCount);

	const handleServiceStart = (e) => (serviceStartX = e.touches[0].clientX);
	const handleServiceEnd = (e) => {
		let dx = e.changedTouches[0].clientX - serviceStartX;
		if (dx > 50) prevService();
		else if (dx < -50) nextService();
	};

	// ===============benefits carousel=====================
	const benefits = [
		{
			title: 'Concierge Services:',
			description:
				'Enjoy bespoke assistance with travel planning, dining reservations, and more — your dedicated team is here to curate seamless experiences.'
		},
		{
			title: 'Fast-Track Security & Airport Concierge:',
			description:
				'Experience hassle-free travel with priority security screening and dedicated concierge support.'
		},
		{
			title: 'Luxury Travel Discounts:',
			description:
				'Access exclusive offers at premier hotels and resorts, including renowned brands like Soneva and IHG'
		},
		{
			title: 'Visa & Booking Discounts:',
			description:
				'Take advantage of exclusive deals on flights and hotels via partners like Booking.com and Cleartrip, with expert visa support from Fulfill Visa Services.'
		},
		{
			title: 'Airport Lounge Access:',
			description:
				'Relax in luxury with complimentary entry to premium airport lounges worldwide — bring a guest along to share the experience.'
		},
		{
			title: 'Car Rental Upgrades:',
			description:
				'Travel in style with complimentary vehicle upgrades at Hertz and Avis, enhancing your journey from start to finish.'
		},
		{
			title: 'Global Blue VIP Services:',
			description:
				'Benefit from expedited VAT refunds at select international airports, making your travels smoother.'
		}
	];
	let benefitIndex = 0;
	let benefitStartX = 0;

	const nextBenefit = () => {
		benefitIndex = (benefitIndex + 1) % benefits.length;
	};

	const prevBenefit = () => {
		benefitIndex = (benefitIndex - 1 + benefits.length) % benefits.length;
	};

	const handleBenefitStart = (e) => (benefitStartX = e.touches[0].clientX);

	const handleBenefitEnd = (e) => {
		let dx = e.changedTouches[0].clientX - benefitStartX;
		if (dx > 50) prevBenefit();
		else if (dx < -50) nextBenefit();
	};

	let scrollRef;

	function scrollLeft() {
		scrollRef.scrollBy({ left: -300, behavior: 'smooth' });
	}

	function scrollRight() {
		scrollRef.scrollBy({ left: 300, behavior: 'smooth' });
	}

	let showForm = false;

	// =========insight ============
	let showInsight1 = false;
	let showInsight2 = false;
	let showInsight3 = false;
	let showInsight4 = false;
	let showInsight5 = false;
	let showInsight6 = false;
</script>

<!-- ============================Hero section======================== -->
<section
	class="relative flex min-h-screen flex-col gap-20 overflow-x-hidden py-0 lg:py-10"
	style="background-image: url({HeroBackground}); background-size: cover; background-position: center; background-repeat: no-repeat;"
>
	<!-- Gradient overlay -->
	<div class="absolute inset-0 z-0 bg-black opacity-20"></div>
	<!-- navbar -->

	<nav
		class="relative z-10 flex items-center justify-between bg-[#181818] px-5 py-4 lg:bg-transparent lg:py-0"
	>
		<!-- Logo -->
		<div class="cursor-pointer">
			<a href="#"><img src={Logo} alt="logo" class="w-28 md:w-32" /></a>
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
					on:click={() => (showForm = true)}
					class="group grid h-[55px] w-[189px] place-items-center rounded-[10px] bg-[#D9D9D9] text-center text-[14px] font-[700] uppercase text-black transition-all duration-300 hover:scale-105 hover:opacity-95 hover:shadow-lg"
					><span class="transition-all duration-300 group-hover:tracking-wider">LOG-IN</span></a
				>
				<a
					on:click={() => (showForm = true)}
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
			<!-- Backdrop -->
			<!-- <div
				in:fade
				out:fade
				class="fixed inset-0 z-[80] bg-black lg:hidden touch-none"
				on:click={() => (isOpen = false)}
			></div> -->

			<!-- Sidebar -->
			<div
				class="max-w-screen fixed left-0 top-0 z-[90] h-full w-full translate-x-0 transform overflow-y-auto bg-black pt-0 shadow-lg transition-transform duration-300 lg:hidden"
			>
				<div class="flex items-center justify-between bg-[#181818] px-5 py-4">
					<!-- Logo -->
					<div class="cursor-pointer">
						<a href="#"><img src={Logo} alt="logo" class="w-28 md:w-32" /></a>
					</div>
					<button class="block focus:outline-none lg:hidden" on:click={() => (isOpen = false)}>
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
				</div>

				<!-- Nav Items -->
				<ul class="space-y-10 px-4 py-6 text-left text-[16px] font-medium text-white">
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
							on:click={() => (showForm = true)}
							class="group mx-auto block w-full max-w-[100%] border border-[#D9D9D9] px-4 py-2 text-center font-bold uppercase text-white transition-all duration-300 hover:scale-105 hover:opacity-95 hover:shadow-lg"
							><span class="transition-all duration-300 group-hover:tracking-wider">LOG-IN</span></a
						>
					</li>
					<li>
						<a
							on:click={() => (showForm = true)}
							class="group mx-auto block w-full max-w-[100%] bg-[#D9D9D9] px-4 py-2 text-center font-bold uppercase text-black transition-all duration-300 hover:scale-105 hover:opacity-95 hover:shadow-lg"
							><span class="transition-all duration-300 group-hover:tracking-wider"
								>Get Started</span
							></a
						>
					</li>
				</ul>
			</div>
		{/if}
	</nav>

	<!-- =====================form section================================= -->
	{#if showForm}
		<div
			class="max-w-screen no-scrollbar fixed left-0 top-0 z-[90] h-full w-full translate-x-0 transform overflow-y-auto bg-black px-8 py-10 shadow-lg transition-transform duration-300 lg:px-[20%]"
		>
			<!-- Close Button -->
			<div class="mb-4 flex justify-end">
				<button
					on:click={() => (showForm = false)}
					class="rounded-full border border-[#7C7C7C] p-3 text-[#7C7C7C] hover:border-white hover:text-white"
				>
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="h-6 w-6"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M6 18L18 6M6 6l12 12"
						/>
					</svg>
				</button>
			</div>
			<div class="leading-none">
				<h1 class="text-[64px] font-[316px] capitalize tracking-tight">Join ault</h1>
				<p class="text-[16px] font-[442] capitalize text-[#A5A5A5]">
					The journey to more start here
				</p>
			</div>

			<div class="mt-10 grid grid-cols-1 gap-5 lg:grid-cols-2">
				<div class="flex flex-col gap-2">
					<label class="font-[442]" for="name">Full name</label>
					<input
						type="text"
						placeholder="Gabriel onanosanya"
						required
						class="boder-[#FFFFFF2E] border bg-[#0B0C0E] text-[#FFFFFF75]"
					/>
				</div>
				<div class="flex flex-col gap-2">
					<label class="font-[442]" for="email">Email Address</label>
					<input
						type="text"
						placeholder="david@blank.design"
						required
						class="boder-[#FFFFFF2E] border bg-[#0B0C0E] text-[#FFFFFF75]"
					/>
				</div>
				<div class="flex flex-col gap-2">
					<label class="font-[442]" for="number">Phone Number</label>
					<input
						type="text"
						placeholder="0123456789"
						required
						class="boder-[#FFFFFF2E] border bg-[#0B0C0E] text-[#FFFFFF75]"
					/>
				</div>
			</div>

			<div class="flex flex-col gap-8 py-8">
				<div class="flex flex-col gap-5">
					<div class="flex gap-3 text-[14px] font-[442] capitalize tracking-tight">
						<div>what are you interested in ?</div>
						<div class="text-[#E9E9E9CC]">(Select all that apply)</div>
					</div>
					<div class="ml-3 space-y-3">
						<div class="flex items-center gap-2">
							<input
								type="checkbox"
								class="rounded-[4px] bg-transparent outline-black transition-all duration-300 checked:border-transparent checked:bg-[#FFCC00] checked:text-black focus:ring-0"
							/>
							<div class="text-[14px] font-[316] text-[#E9E9E9CC]">Buying and Holding Gold</div>
						</div>
						<div class="flex items-center gap-2">
							<input
								type="checkbox"
								class="rounded-[4px] bg-transparent outline-black transition-all duration-300 checked:border-transparent checked:bg-[#FFCC00] checked:text-black focus:ring-0"
							/>
							<div class="text-[14px] font-[316] text-[#E9E9E9CC]">Leasing Gold</div>
						</div>
						<div class="flex items-center gap-2">
							<input
								type="checkbox"
								class="rounded-[4px] bg-transparent outline-black transition-all duration-300 checked:border-transparent checked:bg-[#FFCC00] checked:text-black focus:ring-0"
							/>
							<div class="text-[14px] font-[316] text-[#E9E9E9CC]">Credit Solutions</div>
						</div>
						<div class="flex items-center gap-2">
							<input
								type="checkbox"
								class="rounded-[4px] bg-transparent outline-black transition-all duration-300 checked:border-transparent checked:bg-[#FFCC00] checked:text-black focus:ring-0"
							/>
							<div class="text-[14px] font-[316] text-[#E9E9E9CC]">AULT Mastercard</div>
						</div>
					</div>
				</div>
				<div class="flex flex-col gap-5">
					<div class="text-[14px] font-[442] capitalize tracking-tight">
						Do You Already Own Physical or Tokenized Gold?
					</div>
					<div class="ml-3 flex gap-10">
						<div class="flex items-center gap-2">
							<input
								type="radio"
								name="own_gold"
								value="yes"
								class="rounded-[4px] bg-transparent outline-black transition-all duration-300 checked:border-transparent checked:bg-[#FFCC00] checked:text-black focus:ring-0"
							/>
							<div class="text-[14px] font-[316] text-[#E9E9E9CC]">Yes</div>
						</div>
						<div class="flex items-center gap-2">
							<input
								type="radio"
								name="own_gold"
								value="no"
								class="rounded-[4px] bg-transparent outline-black transition-all duration-300 checked:border-transparent checked:bg-[#FFCC00] checked:text-black focus:ring-0"
							/>
							<div class="text-[14px] font-[316] text-[#E9E9E9CC]">No</div>
						</div>
					</div>
				</div>

				<div class="flex flex-col gap-5">
					<div class="text-[14px] font-[442] capitalize tracking-tight">
						Do You Have A ProvidusBank Account?
					</div>
					<div class="ml-3 flex gap-10">
						<div class="flex items-center gap-2">
							<input
								type="radio"
								name="providus_account"
								value="yes"
								class="rounded-[4px] bg-transparent outline-black transition-all duration-300 checked:border-transparent checked:bg-[#FFCC00] checked:text-black focus:ring-0"
							/>
							<div class="text-[14px] font-[316] text-[#E9E9E9CC]">Yes</div>
						</div>
						<div class="flex items-center gap-2">
							<input
								type="radio"
								name="providus_account"
								value="no"
								class="rounded-[4px] bg-transparent outline-black transition-all duration-300 checked:border-transparent checked:bg-[#FFCC00] checked:text-black focus:ring-0"
							/>
							<div class="text-[14px] font-[316] text-[#E9E9E9CC]">No</div>
						</div>
					</div>
				</div>
			</div>
			<button
				class="mx-auto h-[40px] w-full max-w-[350px] bg-white text-center font-bold uppercase text-black"
				on:click={() => (showForm = false)}>REQUEST YOUR INVITATION</button
			>
		</div>
	{/if}

	<!-- hero content -->
	<div class="relative z-[1] mx-5 flex flex-col gap-5 text-center">
		<div
			class="3xl:text-[96px] text-[40px] font-[200] uppercase leading-none tracking-tighter sm:text-[45px] lg:text-[60px] xl:text-[70px]"
		>
			timeless security,<br />modern convenience
		</div>
		<p class="text-[14px] font-[316] lg:text-[20px] xl:text-[27px]">
			Gold made Flexible and Tailored For You
		</p>
	</div>
</section>

<!-- ============================About section======================== -->
<section
	id="about"
	class="item-center relative mx-5 flex min-h-screen flex-col justify-center gap-40 py-10 text-center md:mx-20 md:py-20"
>
	<div class="mx-auto flex flex-col justify-center gap-5">
		<div
			class="lg:text[42px] 3xl:text-[64px] mx-auto flex gap-3 text-[30px] uppercase tracking-tighter sm:text-[37px] md:leading-none"
		>
			<span>BUY.</span>
			<span class="text-[#686868]">SPEND.</span>
			<span class="text-[#686868]"> MORE.</span>
		</div>
		<div class="mx-auto flex flex-col gap-2 font-[442] md:w-[400px]">
			<h2 class="text-[20px] capitalize lg:text-[36px]">Own With Confidence</h2>
			<p class="textx-[14px] text-[#FFFFFFCC] lg:text-[20px]">
				Securely purchase and hold physical allocated gold, safely stored in LBMA-certified vaults.
			</p>
		</div>
		<div>
			<div class="mx-auto mt-3 flex w-full max-w-[80px] justify-center lg:max-w-[131px]">
				<img src={Gold} alt="gold" class="w-full" />
			</div>
		</div>
		<div class="text-[20px] font-[316] capitalize text-[#E4E4E4] lg:w-[787px] lg:text-[36px]">
			AULT Is A Concierge Service That Transforms Physical Allocated Gold Into A Liquid Financial
			Asset. Through Advance Tokenization And Trusted Institutional Partnerships, We Empower You To
			Buy, Hold, Spend, Lease, And Borrow-Against Gold With Unmatched Freedom And Confidence.
		</div>
		<button
			class="mx-auto block h-[45px] w-[144px] cursor-pointer rounded-[10px] bg-[#D9D9D9] text-[15px] font-[442] uppercase text-black md:text-[20px] lg:hidden lg:h-[55px] lg:w-[211px]"
			>JOIN AULT</button
		>
	</div>

	<div class="mx-auto flex flex-col gap-20">
		<h1
			class="lg:text[37px] 3xl:text-[64px] mx-auto text-[32px] font-[316] uppercase sm:text-[37px]"
		>
			BEYOND WEALTH. BEYOND GOLD.
		</h1>

		<div>
		<!-- Carousel for small screens only -->
		<div class="relative w-full overflow-hidden md:block lg:hidden">
			<!-- Slider wrapper -->
			<div
				class="flex transition-transform duration-500 ease-in-out"
				style="transform: translateX({-currentIndex * 100}%);"
				on:touchstart={handleTouchStart}
				on:touchend={handleTouchEnd}
			>
				{#each features as feature}
					<div class="w-full flex-shrink-0 px-2 md:w-1/2" style="width: calc(100% / {perView})">
						<div class="h-[305px] rounded-[4px] bg-[#181818] p-4 flex flex-col justify-between">
							<img src={feature.image} alt={feature.title} class="mx-auto mb-4 w-[165px]" />
							<h3 class="text-[25px] font-bold text-white">{feature.title}</h3>
							<p class="text-sm text-white/80">{feature.description}</p>
						</div>
					</div>
				{/each}
			</div>

			<!-- Pagination Dots -->
			<div class="mt-4 flex justify-center gap-2">
				{#each Array(slideCount) as _, i}
					<button
						on:click={() => goTo(i)}
						class="h-2 w-2 rounded-full transition-all duration-300"
						class:bg-white={i === currentIndex}
						class:bg-gray-500={i !== currentIndex}
					></button>
				{/each}
			</div>
		</div>

		<!-- Grid layout for desktop -->
		<div class="hidden grid-cols-2 gap-8 lg:grid lg:grid-cols-3">
			{#each features as feature (feature.title)}
				<div class="space-y-4 rounded-[4px] bg-[#181818] p-4">
					<div class="mx-auto max-w-[152px]">
						<img src={feature.image} alt={feature.title} class="w-full" />
					</div>
					<div>
						<h3 class="text-[25px] font-bold text-white">{feature.title}</h3>
						<p class="text-[15px] text-white/80">{feature.description}</p>
					</div>
				</div>
			{/each}
		</div>
		</div>
	</div>
</section>

<!-- ============================How It Works section======================== -->
<section
	id="how-it-works"
	class="item-center relative flex min-h-screen flex-col justify-center gap-20 overflow-x-hidden bg-[#181818] px-5 py-10 md:px-20 md:py-20"
>
	<div class="flex flex-col gap-8 font-[316] lg:flex-row lg:justify-between">
		<h1
			class="lg:text[42px] text-[32px] uppercase tracking-tighter sm:text-[37px] md:w-[282px] md:leading-none xl:text-[60px]"
		>
			How It Works
		</h1>
		<p class="text-[24px] font-[300] capitalize text-[#FFFFFFCC] lg:w-[1006px] lg:text-[36px]">
			Exceptional service begins with a personal connection. As a member, you are paired with a
			dedicated Relationship Manager who acts as your trusted advisor — available around the clock
			to handle your requests with precision and confidentiality.
		</p>
	</div>
	<div class="flex flex-col justify-between gap-[76px] lg:flex-row">
		<div class="hidden lg:block">
			<img src={HowItWorksImg} alt="how-it-works-img" />
		</div>
		<div class="flex flex-col gap-10">
			<!-- Desktop Grid -->
			<div class="hidden grid-cols-2 gap-[41px] lg:grid">
				{#each steps as step, i}
					<div
						class="flex max-w-[316px] flex-col gap-9 rounded-[4px] bg-[#000000] p-4 lg:bg-transparent"
					>
						<div class="flex gap-1">
							{#each Array(step.dots) as _}
								<div class="-mt-1 h-3 w-3 rounded-full bg-[#7D7D7D]"></div>
							{/each}
						</div>
						<div class="grid gap-2">
							<h3 class="text-[16px] font-semibold capitalize lg:text-[20px]">{step.title}</h3>
							<p class="text-[14px] font-light lg:text-[20px]">{step.description}</p>
						</div>
					</div>
				{/each}
			</div>

			<!-- Mobile Carousel -->
			<div class="relative w-full overflow-hidden lg:hidden">
				<!-- Swipeable Steps Wrapper -->
				<div
					class="flex transition-transform duration-500 ease-in-out"
					style="transform: translateX({-stepsIndex * 100}%);"
					on:touchstart={handleStepStart}
					on:touchend={handleStepEnd}
				>
					{#each steps as step (step.title)}
						<div
							class="w-full flex-shrink-0 px-2 md:w-1/2"
							style="width: calc(100% / {stepPerView})"
						>
							<div
								class="flex h-[240px] flex-col justify-center gap-9 rounded-[16px] bg-[#000000] p-4"
							>
								<div class="flex gap-1">
									{#each Array(step.dots) as _}
										<div class="-mt-1 h-3 w-3 rounded-full bg-[#7D7D7D]"></div>
									{/each}
								</div>
								<div class="grid gap-2">
									<h3 class="text-[16px] font-semibold capitalize">{step.title}</h3>
									<p class="text-[14px] font-light">{step.description}</p>
								</div>
							</div>
						</div>
					{/each}
				</div>

				<!-- Pagination Dots -->
				<div class="mt-4 flex justify-center gap-2">
					{#each Array(stepSlideCount) as _, i}
						<button
							on:click={() => goToStep(i)}
							class="h-2 w-2 rounded-full transition-all duration-300"
							class:bg-white={i === stepsIndex}
							class:bg-gray-500={i !== stepsIndex}
						></button>
					{/each}
				</div>
			</div>

			<button
				class="mx-auto hidden h-[45px] w-[144px] cursor-pointer rounded-[10px] bg-[#D9D9D9] text-[15px] font-[442] uppercase text-black md:text-[20px] lg:block lg:h-[55px] lg:w-[211px]"
				>JOIN AULT</button
			>
		</div>
	</div>
</section>

<!-- ============================Your Card section======================== -->
<section
	id="your-card"
	class="item-center relative flex min-h-[664px] flex-col justify-center gap-20 overflow-hidden px-5 py-10 md:px-20 md:py-0 lg:min-h-screen"
	style="background-image: url({CardBackground}); background-size: cover; background-position: center; background-repeat: no-repeat;"
>
	<div
		class="absolute bottom-[-1rem] left-0 right-0 z-10 mx-auto max-w-[276px] gap-9 object-contain lg:bottom-[1rem] lg:left-auto lg:right-[1rem] lg:mx-0 xl:max-w-[522.2px]"
	>
		<img src={AultOnGold} alt="ault-on-gold" class="w-full" />
	</div>
	<div
		class="uppecase relative z-0 hidden text-[18vw] font-[200] tracking-[0.03em] text-[#181818] lg:block"
	>
		LIMITLESS
	</div>
	<div class="relative mx-auto mb-auto lg:mx-0">
		<div
			class="lg:pb-50 relative z-20 mb-auto flex flex-col gap-8 p-5 pt-10 text-center capitalize lg:mt-auto lg:p-20 lg:pt-5 lg:text-left"
		>
			<h1
				class="5xl:text-[64px] text-center text-[25px] font-[200] uppercase leading-tight tracking-tight lg:text-left lg:text-[50px] lg:leading-none"
			>
				Gold In Your Hands, <br /> Anytime, Anywhere.
			</h1>
			<p class="w-[272px] text-sm font-[200] capitalize md:w-[572px] lg:text-[20px] lg:font-[300]">
				Experience True Freedom. With Your AULT Mastercard, You Can Spend Your Gold as Currency
				Anywhere in the World.
			</p>
			<button
				class="mx-auto h-[45px] w-[160px] cursor-pointer rounded-[10px] bg-[#D9D9D9] text-[15px] font-[442] uppercase text-black md:text-[20px] lg:mx-0 lg:h-[55px] lg:w-[211px]"
				>Get your card</button
			>
		</div>
	</div>
</section>

<!-- ============================Services section======================== -->
<section
	class="item-center relative flex min-h-screen flex-col justify-center gap-20 overflow-x-hidden bg-[#181818] px-5 py-10 md:py-20"
>
	<div class="flex flex-col gap-20 lg:px-20 xl:px-60">
		<h1
			class="lg:text[37px] 3xl:w-[1138px] 3xl:text-[48px] w-full text-[32px] font-[200] capitalize sm:text-[37px] lg:w-[809px]"
		>
			Unparalleled service that combines security, flexibility, and exclusivity tailored for you.
		</h1>
		<!-- Carousel (small screens only) -->
		<div class="relative w-full overflow-hidden lg:hidden">
			<!-- Services swipeable wrapper -->
			<div
				class="flex transition-transform duration-500 ease-in-out"
				style="transform: translateX({-servicesIndex * 100}%);"
				on:touchstart={handleServiceStart}
				on:touchend={handleServiceEnd}
			>
				{#each services as service}
					<div
						class="w-full flex-shrink-0 px-2 md:w-1/2"
						style="width: calc(100% / {perViewService})"
					>
						<div class="flex max-h-[448px] flex-col gap-5 rounded-[4px] bg-[#181818] p-4">
							<div class="h-[280px] w-full overflow-hidden rounded">
								<img
									src={service.image}
									alt="service"
									class="h-full w-full object-cover object-center"
								/>
							</div>
							<div class="max-w-[320px] text-[14px] text-white md:w-auto lg:text-[20px]">
								<h3 class="font-semibold capitalize tracking-normal">{service.title}</h3>
								<p class="font-light capitalize leading-relaxed tracking-normal text-white/80">
									{service.description}
								</p>
							</div>
						</div>
					</div>
				{/each}
			</div>

			<!-- Pagination Dots -->
			<div class="mt-4 flex justify-center gap-2">
				{#each Array(serviceSlideCount) as _, i}
					<button
						on:click={() => goToService(i)}
						class="h-2 w-2 rounded-full transition-all duration-300"
						class:bg-white={i === servicesIndex}
						class:bg-gray-500={i !== servicesIndex}
					></button>
				{/each}
			</div>
		</div>

		<!-- for desktop -->
		<div class="hidden grid-cols-1 gap-20 lg:grid lg:grid-cols-3">
			{#each services as item}
				<div class="flex h-full w-full flex-col gap-5 overflow-hidden">
					<div class="h-full max-h-[286px] w-full overflow-hidden">
						<img src={item.image} alt="service" class="h-full w-full object-cover object-center" />
					</div>
					<div class="text-[14px] lg:text-[20px]">
						<h3 class="font-semibold capitalize tracking-normal">{item.title}</h3>
						<p class="font-light capitalize leading-relaxed tracking-normal">{item.description}</p>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>

<!-- ============================Benefit section======================== -->
<section
	id="benefits"
	class="item-center relative mx-5 flex min-h-full flex-col justify-center gap-20 overflow-x-hidden py-10 md:mx-20 md:py-20"
>
	<div class="grid place-items-center gap-10 lg:grid-cols-2">
		<!-- IMAGE SECTION -->
		<div class="order-2 lg:order-1">
			<div class="relative hidden max-h-[470px] w-full lg:flex lg:h-auto lg:w-[496px]">
				<img src={BenefitImg} alt="benefit-img" class="w-full lg:w-[367px]" />
				<img
					src={BenefitImg2}
					alt="benefit-img"
					class="absolute bottom-[-15rem] left-[-5rem] z-10 hidden max-w-[254px] lg:block"
				/>
			</div>
		</div>

		<!-- TEXT + BENEFITS SECTION -->
		<div class="order-1 flex w-full flex-col gap-10 md:order-2">
			<h1 class="3xl:text-[64px] text-[24px] font-[316] capitalize lg:text-[37px] xl:text-[45px]">
				As a valued member, you unlock a world of personalized travel, lifestyle, and financial
				privileges, powered by our trusted partnership with Mastercard World Elite.
			</h1>
			<div class="ml-auto block gap-2 text-right lg:hidden">
				<!-- Left Arrow -->
				<button
					on:click={prevBenefit}
					class="cursor-pointer rounded-full bg-white p-2 text-black backdrop-blur-md lg:hidden"
					aria-label="Scroll Left"
				>
					<svg
						xmlns="http://www.w3.org/2000/svg"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
						class="h-5 w-5"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M15 19l-7-7 7-7"
						/>
					</svg>
				</button>

				<!-- Right Arrow -->
				<button
					on:click={nextBenefit}
					class="cursor-pointer rounded-full bg-white p-2 text-black backdrop-blur-md lg:hidden"
					aria-label="Scroll Right"
				>
					<svg
						xmlns="http://www.w3.org/2000/svg"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
						class="h-5 w-5"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M9 5l7 7-7 7"
						/>
					</svg>
				</button>
			</div>

			<!-- Carousel for small screens -->
			<div class="relative h-[130px] lg:hidden">
				<div
					class="duration-600 flex transition-transform ease-in-out"
					style="transform: translateX(-{benefitIndex * 100}%);"
					on:touchstart={handleBenefitStart}
					on:touchend={handleBenefitEnd}
				>
					{#each benefits as benefit}
						<div class="w-full flex-shrink-0 px-4" style="width: 100%">
							<div
								class="flex h-full w-[288px] flex-col space-y-[4px] rounded-[6px] bg-[#000000] p-4 text-[14px] font-[571] capitalize"
							>
								<p>{benefit.title}</p>
								<span class="font-[200] normal-case">{benefit.description}</span>
							</div>
						</div>
					{/each}
				</div>
			</div>

			<!-- Grid for large screens -->
			<div class="hidden grid-cols-2 gap-10 lg:grid">
				{#each benefits as benefit}
					<div class="flex flex-col space-y-[4px] text-[14px] font-[571] capitalize lg:text-[20px]">
						{benefit.title}
						<span class="font-[200] normal-case">{benefit.description}</span>
					</div>
				{/each}
			</div>
		</div>
	</div>
</section>

<!-- ============================Our Patner section======================== -->
<section
	id="partner"
	class="item-center relative flex min-h-screen flex-col justify-center gap-20 overflow-x-hidden bg-[#181818] px-5 py-10 md:px-20 md:py-20"
>
	<div
		class="flex min-h-[284px] flex-col justify-between gap-5 px-0 py-10 lg:flex-row lg:gap-20 lg:px-0"
	>
		<div class="flex flex-col justify-between gap-7">
			<p class="3xl:text-[36px] text-[24px] font-[316] lg:max-w-[907px] lg:text-[25px]">
				Our commitment to you is founded on trusted partnerships and a shared dedication to managing
				your assets with the highest standards of security, transparency, and personalized
				flexibility.
			</p>
			<div class="hidden max-h-[294px] max-w-[908px] lg:block">
				<img src={PartnerImg} alt="Partner-img" class="h-full w-full" />
			</div>
		</div>
		<div
			class="ml-5 mt-10 flex flex-col justify-between gap-10 md:flex-row lg:ml-0 lg:mt-0 lg:flex-col lg:gap-2"
		>
			<div class="flex max-w-[378px] flex-col gap-5 text-[20px] font-[571]">
				<div class="max-w-[159px]">
					<img src={Partner4} alt="partner" class="w-full" />
				</div>
				<h3>
					Emerging Africa
					<span class="ml-1 text-[16px] font-[316] text-[#FFFFFFCC] lg:w-[312px]">
						Oversees fiduciary responsibilities, safeguarding your gold assets with exceptional care
						and strict regulatory compliance.
					</span>
				</h3>
			</div>
			<div class="flex max-w-[378px] flex-col gap-5 text-[20px] font-[571]">
				<div class="max-w-[132px] opacity-[60%]">
					<img src={Partner1} alt="partner" class="w-full" />
				</div>
				<h3>
					Providus Bank
					<span class="ml-1 text-[16px] font-[316] text-[#FFFFFFCC] lg:w-[312px]">
						Provides reliable and efficient card solutions, ensuring your funds remain secure,
						accessible, and available whenever you need them.
					</span>
				</h3>
			</div>
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
		class="absolute left-1/2 top-1/2 z-0 h-40 w-40 -translate-y-1/2 rounded-full bg-[#C686014D] blur-[130px] md:left-0 md:h-96 md:w-96"
	></div>

	<!-- Right Glow -->
	<div
		class="absolute right-0 top-1/3 z-0 hidden h-96 w-96 -translate-y-1/2 rounded-full bg-[#C686014D] blur-[130px] md:block"
	></div>

	<div class="relative z-10 flex flex-col gap-10">
		<h1 class="lg:text[37px] 3xl:text-[64px] text-[37px] font-[316] uppercase sm:text-[37px]">
			Insight
		</h1>

		<div class="flex flex-col gap-3 text-[16px] lg:text-[20px]">
			<div
				class="cursor-pointer rounded-[8px] border-[3px] border-[#FFFFFF24]"
				on:click={() => (showInsight1 = !showInsight1)}
			>
				<p class="p-3 font-[442]">What is AULT?</p>
				{#if showInsight1}
					<p class="p-3 font-[442]">
						AULT is an exclusive concierge service designed to provide seamless access to
						gold-backed financial services, allowing the purchase, management, and spend of gold
						assets securely, with flexibility and ease.
					</p>
				{/if}
			</div>

			<div
				class="cursor-pointer rounded-[8px] border-[3px] border-[#FFFFFF24]"
				on:click={() => (showInsight6 = !showInsight6)}
			>
				<p class="p-3 font-[442]">Why Gold?</p>
				{#if showInsight6}
					<p class="p-3 font-[442]">
						Gold is a stable, long-term asset with a proven track record of preserving value across
						economic fluctuations. Unlike traditional currencies or investments, gold offers a
						tangible hedge against uncertainty and market volatility, providing security and
						liquidity.
					</p>
				{/if}
			</div>
			<div
				class="cursor-pointer rounded-[8px] border-[3px] border-[#FFFFFF24]"
				on:click={() => (showInsight2 = !showInsight2)}
			>
				<p class="p-3 font-[442]">How Do I Fund My AULT Account?</p>
				{#if showInsight2}
					<p class="p-3 font-[442]">
						You can fund your AULT account by transferring fiat currency (USD, EUR, NGN) through our
						secure platform. Once the funds are received, we will purchase the gold on your behalf.
						All gold purchased is securely stored in LBMA-certified vaults in London, Zurich, or the
						UAE.
					</p>
				{/if}
			</div>
			<div
				class="cursor-pointer rounded-[8px] border-[3px] border-[#FFFFFF24]"
				on:click={() => (showInsight3 = !showInsight3)}
			>
				<p class="p-3 font-[442]">How Do I Access My Gold?</p>
				{#if showInsight3}
					<p class="p-3 font-[442]">
						Once your account is active, access your gold via the AULT web app, liquidate it, and
						spend it using your AULT Mastercard. The entire process of liquidating your allocated
						gold is supported by robust technology infrastructure and is audited by KPMG LLP for
						added assurance.
					</p>
				{/if}
			</div>
			<div
				class="cursor-pointer rounded-[8px] border-[3px] border-[#FFFFFF24]"
				on:click={() => (showInsight4 = !showInsight4)}
			>
				<p class="p-3 font-[442]">How Is My Gold Stored?</p>
				{#if showInsight4}
					<p class="p-3 font-[442]">
						Your gold is securely stored in insured vaults in London, Zurich, and the UAE. These
						vaults meet international standards of security and compliance, ensuring your assets are
						safe and protected.
					</p>
				{/if}
			</div>
			<div
				class="cursor-pointer rounded-[8px] border-[3px] border-[#FFFFFF24]"
				on:click={() => (showInsight5 = !showInsight5)}
			>
				<p class="p-3 font-[442]">Do I Need To Sell My Gold To Spend It?</p>
				{#if showInsight5}
					<p class="p-3 font-[442]">
						No, you don’t need to sell your gold. AULT has partnered with regulated financial
						entities, allowing you to spend your gold directly anywhere in the world using the AULT
						Mastercard.
					</p>
				{/if}
			</div>
		</div>
		<div
			class="ml-auto flex cursor-pointer items-center gap-3 text-[14px] font-[200] tracking-tight lg:text-[32px] lg:font-[316]"
		>
			Learn more
			<svg
				viewBox="0 0 20 12"
				fill="currentColor"
				xmlns="http://www.w3.org/2000/svg"
				class="h-2 w-8 rotate-180 text-white lg:h-5 lg:w-10"
			>
				<path
					d="M9.84281 11.9019C10.1028 11.7642 10.2649 11.5023 10.2649 11.2175V6.7825H19.1841C19.6345 6.7825 20 6.43195 20 6.00003C20 5.56811 19.6345 5.21756 19.1841 5.21756H10.2649V0.782525C10.2649 0.496663 10.1028 0.234796 9.84281 0.0981252C9.58281 -0.0406327 9.26516 -0.0312431 9.01387 0.120034L0.380745 5.33754C0.143595 5.48151 0 5.73086 0 6.00003C0 6.2692 0.143595 6.51854 0.380745 6.66252L9.01387 11.88C9.14659 11.9593 9.2978 12 9.44901 12C9.5839 12 9.71988 11.9666 9.84281 11.9019Z"
					class="icon-path"
				/>
			</svg>
		</div>
	</div>
</section>

<!-- ============================Footer section======================== -->
<footer
	class="item-center relative mx-5 flex flex-col gap-3 overflow-x-hidden py-10 md:mx-20 md:gap-10 md:py-10"
>
	<div class="flex justify-between gap-8 text-[10px] font-[200] uppercase lg:text-[18px]">
		<div>
			AULT 2024.<br />
			27 OLD GLOUCESTER STREET, LONDON, UNITED KINGDOM, WC1N 3AX
		</div>
		<div class="flex flex-col gap-3 lg:flex-row">
			<div>
				<p>
					your Journey to more <br />
					begins here.
				</p>
			</div>
			<p class="uppercase">Partnerships@goAULT.COM</p>
		</div>
	</div>
	<div class="w-full">
		<img src={FooterLogo} alt="footer-logo" class="w-full" />
	</div>
</footer>
