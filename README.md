<!DOCTYPE html>
<html lang="cs" class="scroll-smooth">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Coffee Spot | Výběrová káva a útulná atmosféra</title>
<!-- Tailwind CSS CDN -->
<script src="https://cdn.tailwindcss.com"></script>
<!-- Font Awesome Icons -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<!-- Google Fonts (Playfair Display & Plus Jakarta Sans) -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,500;0,600;0,700;1,400&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<script>
tailwind.config = {
theme: {
extend: {
colors: {
coffee: {
50: '#fdfbf7',
100: '#f7f2e8',
200: '#eee3d0',
300: '#e0ccaf',
400: '#cbab84',
500: '#b88b5d',
600: '#9e6e44',
700: '#7e5338',
800: '#644231',
900: '#4e3328',
950: '#2b1a14',
},
cream: '#FAF6f0',
},
fontFamily: {
serif: ['Playfair Display', 'serif'],
sans: ['Plus Jakarta Sans', 'sans-serif'],
}
}
}
}
</script>
<style>
.page-section {
display: none;
opacity: 0;
transition: opacity 0.3s ease-in-out;
}
.page-section.active {
display: block;
opacity: 1;
}
</style>
</head>
<body class="font-sans bg-cream text-coffee-950 antialiased flex flex-col min-h-screen selection:bg-coffee-500 selection:text-white">
<!-- TOP ANNOUNCEMENT BAR -->
<div class="bg-coffee-900 text-coffee-200 text-xs sm:text-sm py-2 px-4 text-center font-medium tracking-wide flex justify-between items-center px-6 md:px-12">
<div class="hidden sm:flex items-center space-x-4">
<span><i class="fa-regular font-bold fa-clock text-coffee-400 mr-1"></i> Po-Pá: 7:30 - 19:00 | So-Ne: 8:30 - 18:00</span>
</div>
<div class="mx-auto sm:mx-0">
<span class="bg-coffee-700/60 text-amber-200 text-xs px-2 py-0.5 rounded-full mr-2 font-semibold">Tip dne</span>
Čerstvě upražená Etiopie Yirgacheffe na filtru! ☕
</div>
<div class="hidden md:flex items-center space-x-3">
<a href="tel:+420777123456" class="hover:text-white transition-colors"><i class="fa-solid fa-phone text-xs mr-1"></i> +420 777 123 456</a>
</div>
</div>
<!-- MAIN HEADER / NAVIGATION -->
<header class="sticky top-0 z-40 bg-cream/95 backdrop-blur-md border-b border-coffee-200/60 shadow-sm transition-all duration-200">
<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
<div class="flex justify-between items-center h-20">
<!-- LOGO -->
<a href="#home" onclick="navigateTo('home'); return false;" class="flex items-center space-x-3 group">
<div class="w-11 h-11 rounded-full bg-coffee-800 flex items-center justify-center text-amber-100 shadow-md group-hover:bg-coffee-700 transition-colors">
<i class="fa-solid fa-mug-hot text-xl"></i>
</div>
<div>
<span class="font-serif text-2xl font-bold tracking-tight text-coffee-900 block leading-none">Coffee Spot</span>
<span class="text-[10px] tracking-widest uppercase font-semibold text-coffee-600 block mt-1">Artisan Café & Bakery</span>
</div>
</a>
<!-- DESKTOP NAVIGATION LINKS -->
<nav class="hidden md:flex items-center space-x-1 lg:space-x-2">
<a href="#home" onclick="navigateTo('home'); return false;" id="nav-home" class="nav-link px-3 py-2 rounded-lg text-sm font-semibold text-coffee-800 hover:text-coffee-600 hover:bg-coffee-100/60 transition-all">Úvod</a>
<a href="#menu" onclick="navigateTo('menu'); return false;" id="nav-menu" class="nav-link px-3 py-2 rounded-lg text-sm font-semibold text-coffee-800 hover:text-coffee-600 hover:bg-coffee-100/60 transition-all">Menu & Ceník</a>
<a href="#hours" onclick="navigateTo('hours'); return false;" id="nav-hours" class="nav-link px-3 py-2 rounded-lg text-sm font-semibold text-coffee-800 hover:text-coffee-600 hover:bg-coffee-100/60 transition-all">Otevírací doba</a>
<a href="#about" onclick="navigateTo('about'); return false;" id="nav-about" class="nav-link px-3 py-2 rounded-lg text-sm font-semibold text-coffee-800 hover:text-coffee-600 hover:bg-coffee-100/60 transition-all">Náš příběh</a>
<a href="#gallery" onclick="navigateTo('gallery'); return false;" id="nav-gallery" class="nav-link px-3 py-2 rounded-lg text-sm font-semibold text-coffee-800 hover:text-coffee-600 hover:bg-coffee-100/60 transition-all">Galerie</a>
<a href="#contact" onclick="navigateTo('contact'); return false;" id="nav-contact" class="nav-link px-3 py-2 rounded-lg text-sm font-semibold text-coffee-800 hover:text-coffee-600 hover:bg-coffee-100/60 transition-all">Kontakt & Recenze</a>
</nav>
<!-- HEADER ACTION BUTTON -->
<div class="hidden md:flex items-center space-x-3">
<a href="#contact" onclick="navigateTo('contact'); return false;" class="bg-coffee-800 text-cream px-4 py-2.5 rounded-xl font-medium text-sm hover:bg-coffee-700 shadow-sm transition-all hover:shadow flex items-center gap-2">
<i class="fa-regular fa-calendar-check text-amber-300"></i> Rezervace
</a>
</div>
<!-- MOBILE MENU BUTTON -->
<button id="mobile-menu-btn" onclick="toggleMobileMenu()" class="md:hidden p-2 rounded-lg text-coffee-800 hover:bg-coffee-100 focus:outline-none" aria-label="Menu">
<i class="fa-solid fa-bars text-xl" id="menu-icon"></i>
</button>
</div>
</div>
<!-- MOBILE NAVIGATION DROPDOWN -->
<div id="mobile-menu" class="hidden md:hidden bg-cream border-b border-coffee-200 px-4 pt-2 pb-6 space-y-2">
<a href="#home" onclick="navigateTo('home'); toggleMobileMenu(); return false;" class="block px-4 py-3 rounded-xl text-base font-medium text-coffee-900 hover:bg-coffee-100">Úvod</a>
<a href="#menu" onclick="navigateTo('menu'); toggleMobileMenu(); return false;" class="block px-4 py-3 rounded-xl text-base font-medium text-coffee-900 hover:bg-coffee-100">Menu & Ceník</a>
<a href="#hours" onclick="navigateTo('hours'); toggleMobileMenu(); return false;" class="block px-4 py-3 rounded-xl text-base font-medium text-coffee-900 hover:bg-coffee-100">Otevírací doba</a>
<a href="#about" onclick="navigateTo('about'); toggleMobileMenu(); return false;" class="block px-4 py-3 rounded-xl text-base font-medium text-coffee-900 hover:bg-coffee-100">Náš příběh</a>
<a href="#gallery" onclick="navigateTo('gallery'); toggleMobileMenu(); return false;" class="block px-4 py-3 rounded-xl text-base font-medium text-coffee-900 hover:bg-coffee-100">Galerie</a>
<a href="#contact" onclick="navigateTo('contact'); toggleMobileMenu(); return false;" class="block px-4 py-3 rounded-xl text-base font-medium text-coffee-900 hover:bg-coffee-100">Kontakt & Recenze</a>
</div>
</header>
<main class="flex-grow">
<!-- PAGE 1: HOME -->
<section id="page-home" class="page-section active">
<div class="relative bg-coffee-950 text-white min-h-[500px] flex items-center overflow-hidden">
<div class="absolute inset-0 z-0 opacity-40 bg-cover bg-center" style="background-image: url('https://images.unsplash.com/photo-1501339847302-ac426a4a7cbb?auto=format&fit=crop&w=1920&q=80');"></div>
<div class="absolute inset-0 bg-gradient-to-r from-coffee-950 via-coffee-950/80 to-transparent z-10"></div>
<div class="relative z-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
<div class="max-w-2xl">
<span class="inline-block px-3 py-1 rounded-full bg-coffee-800/80 text-amber-200 text-xs font-medium mb-4">Vaše oblíbená kavárna</span>
<h1 class="font-serif text-4xl sm:text-6xl font-bold text-cream mb-6">Místo, kde káva voní <span class="text-amber-300 italic font-normal">domovem.</span></h1>
<p class="text-coffee-200 text-base sm:text-lg mb-8 font-light">Vítáme vás v Coffee Spot. Připravujeme pro vás výběrovou kávu od nejlepších evropských pražíren a čerstvé pečené croissanty každý den.</p>
<div class="flex flex-wrap gap-4">
<a href="#menu" onclick="navigateTo('menu'); return false;" class="bg-amber-500 hover:bg-amber-600 text-coffee-950 font-bold px-7 py-3.5 rounded-xl transition-all">Prohlédnout Nabídku →</a>
<a href="#hours" onclick="navigateTo('hours'); return false;" class="bg-white/10 hover:bg-white/20 text-cream px-6 py-3.5 rounded-xl border border-white/20 transition-all">Otevírací doba</a>
</div>
</div>
</div>
</div>
<!-- BESTSELLERS PREVIEW -->
<div class="py-16 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
<div class="text-center max-w-xl mx-auto mb-10">
<h2 class="font-serif text-3xl font-bold text-coffee-900">Oblíbené bestsellery</h2>
</div>
<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
<div class="bg-white p-5 rounded-2xl border border-coffee-200 shadow-sm">
<img src="https://images.unsplash.com/photo-1534778101976-62847782c213?auto=format&fit=crop&w=500&q=80" alt="Flat White" class="w-full h-40 object-cover rounded-xl mb-3">
<div class="flex justify-between items-center mb-1">
<h3 class="font-bold text-coffee-900">Flat White</h3>
<span class="font-bold text-coffee-800">85 Kč</span>
</div>
<p class="text-xs text-coffee-600">Dvojité espresso s jemnou mikropěnou.</p>
</div>
<div class="bg-white p-5 rounded-2xl border border-coffee-200 shadow-sm">
<img src="https://images.unsplash.com/photo-1517701604599-bb29b565090c?auto=format&fit=crop&w=500&q=80" alt="Batch Brew" class="w-full h-40 object-cover rounded-xl mb-3">
<div class="flex justify-between items-center mb-1">
<h3 class="font-bold text-coffee-900">Batch Brew</h3>
<span class="font-bold text-coffee-800">75 Kč</span>
</div>
<p class="text-xs text-coffee-600">Čerstvá filtrovaná káva výběrového původu.</p>
</div>
<div class="bg-white p-5 rounded-2xl border border-coffee-200 shadow-sm">
<img src="https://images.unsplash.com/photo-1550617931-e17a7b70dce2?auto=format&fit=crop&w=500&q=80" alt="Cheesecake" class="w-full h-40 object-cover rounded-xl mb-3">
<div class="flex justify-between items-center mb-1">
<h3 class="font-bold text-coffee-900">Pistáciový Cheesecake</h3>
<span class="font-bold text-coffee-800">95 Kč</span>
</div>
<p class="text-xs text-coffee-600">Pečený dort s pravými pistáciemi.</p>
</div>
<div class="bg-white p-5 rounded-2xl border border-coffee-200 shadow-sm">
<img src="https://images.unsplash.com/photo-1525351484163-7529414344d8?auto=format&fit=crop&w=500&q=80" alt="Avokádový Toast" class="w-full h-40 object-cover rounded-xl mb-3">
<div class="flex justify-between items-center mb-1">
<h3 class="font-bold text-coffee-900">Avokádový Toast</h3>
<span class="font-bold text-coffee-800">145 Kč</span>
</div>
<p class="text-xs text-coffee-600">Kvasový chléb, avokádo a pošírované vejce.</p>
</div>
</div>
</div>
</section>
<!-- PAGE 2: MENU -->
<section id="page-menu" class="page-section">
<div class="bg-coffee-900 text-cream py-10 text-center">
<h1 class="font-serif text-3xl sm:text-4xl font-bold">Naše Nabídka & Ceník</h1>
</div>
<div class="max-w-6xl mx-auto px-4 py-10">
<div class="flex flex-wrap justify-center gap-3 mb-8">
<button onclick="filterMenu('all')" class="menu-tab-btn px-4 py-2 rounded-xl font-bold text-sm bg-coffee-800 text-white" data-category="all">Všechno</button>
<button onclick="filterMenu('hot')" class="menu-tab-btn px-4 py-2 rounded-xl font-medium text-sm bg-white text-coffee-800 border" data-category="hot">Teplá káva ☕</button>
<button onclick="filterMenu('cold')" class="menu-tab-btn px-4 py-2 rounded-xl font-medium text-sm bg-white text-coffee-800 border" data-category="cold">Ledové nápoje 🧊</button>
<button onclick="filterMenu('food')" class="menu-tab-btn px-4 py-2 rounded-xl font-medium text-sm bg-white text-coffee-800 border" data-category="food">Jídlo & Sladké 🥐</button>
</div>
<div class="grid grid-cols-1 md:grid-cols-2 gap-6" id="menu-container">
<div class="menu-item bg-white p-5 rounded-2xl border flex justify-between" data-category="hot">
<div><h3 class="font-bold text-coffee-900">Espresso / Ristretto</h3><p class="text-xs text-coffee-600">Intenzivní shot 100% Arabika.</p></div>
<span class="font-bold text-coffee-800">55 Kč</span>
</div>
<div class="menu-item bg-white p-5 rounded-2xl border flex justify-between" data-category="hot">
<div><h3 class="font-bold text-coffee-900">Cappuccino</h3><p class="text-xs text-coffee-600">Espresso s nadýchanou pěnou.</p></div>
<span class="font-bold text-coffee-800">75 Kč</span>
</div>
<div class="menu-item bg-white p-5 rounded-2xl border flex justify-between" data-category="hot">
<div><h3 class="font-bold text-coffee-900">Flat White</h3><p class="text-xs text-coffee-600">Dvojitý shot a mikropěna.</p></div>
<span class="font-bold text-coffee-800">85 Kč</span>
</div>
<div class="menu-item bg-white p-5 rounded-2xl border flex justify-between" data-category="cold">
<div><h3 class="font-bold text-coffee-900">Espresso Tonic</h3><p class="text-xs text-coffee-600">Tonic, led, limetka a espresso.</p></div>
<span class="font-bold text-coffee-800">95 Kč</span>
</div>
<div class="menu-item bg-white p-5 rounded-2xl border flex justify-between" data-category="cold">
<div><h3 class="font-bold text-coffee-900">Iced Latte</h3><p class="text-xs text-coffee-600">Espresso, studené mléko a led.</p></div>
<span class="font-bold text-coffee-800">85 Kč</span>
</div>
<div class="menu-item bg-white p-5 rounded-2xl border flex justify-between" data-category="food">
<div><h3 class="font-bold text-coffee-900">Máslový Croissant</h3><p class="text-xs text-coffee-600">Pečený denně čerstvý.</p></div>
<span class="font-bold text-coffee-800">50 Kč</span>
</div>
<div class="menu-item bg-white p-5 rounded-2xl border flex justify-between" data-category="food">
<div><h3 class="font-bold text-coffee-900">Pistáciový Cheesecake</h3><p class="text-xs text-coffee-600">Krémový pečený cheesecake.</p></div>
<span class="font-bold text-coffee-800">95 Kč</span>
</div>
</div>
</div>
</section>
<!-- PAGE 3: HOURS -->
<section id="page-hours" class="page-section">
<div class="bg-coffee-900 text-cream py-10 text-center">
<h1 class="font-serif text-3xl font-bold">Otevírací Doba</h1>
</div>
<div class="max-w-3xl mx-auto px-4 py-12">
<div class="bg-white p-8 rounded-3xl border border-coffee-200 shadow-sm space-y-4">
<div class="flex justify-between border-b pb-3"><span class="font-semibold">Pondělí – Pátek</span><span class="font-bold bg-coffee-100 px-3 py-1 rounded-lg">7:30 – 19:00</span></div>
<div class="flex justify-between border-b pb-3"><span class="font-semibold">Sobota</span><span class="font-bold bg-coffee-100 px-3 py-1 rounded-lg">8:30 – 18:00</span></div>
<div class="flex justify-between"><span class="font-semibold">Neděle & Sváteční dny</span><span class="font-bold bg-coffee-100 px-3 py-1 rounded-lg">8:30 – 18:00</span></div>
</div>
</div>
</section>
<!-- PAGE 4: ABOUT -->
<section id="page-about" class="page-section">
<div class="bg-coffee-900 text-cream py-10 text-center"><h1 class="font-serif text-3xl font-bold">Náš Příběh</h1></div>
<div class="max-w-4xl mx-auto px-4 py-12">
<p class="text-coffee-700 leading-relaxed mb-4">Příběh Coffee Spot začal cestováním po malých farmách v Jižní Americe a Africe. Chtěli jsme vytvořit komunitní prostor bez spěchu, kde se potkává vynikající káva s rodinnou atmosférou.</p>
<div class="mt-8 bg-white p-6 rounded-2xl border flex gap-4 items-center">
<img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&w=200&q=80" alt="Majda a Alice" class="w-16 h-16 rounded-full object-cover">
<div>
<h3 class="font-bold text-coffee-900">Majda & Alice</h3>
<p class="text-xs text-coffee-600">Zakladatelky kavárny Coffee Spot</p>
</div>
</div>
</div>
</section>
<!-- PAGE 5: GALLERY -->
<section id="page-gallery" class="page-section">
<div class="bg-coffee-900 text-cream py-10 text-center"><h1 class="font-serif text-3xl font-bold">Galerie</h1></div>
<div class="max-w-6xl mx-auto px-4 py-10">
<div class="grid grid-cols-1 sm:grid-cols-3 gap-4">
<img src="https://images.unsplash.com/photo-1554118811-1e0d58224f24?auto=format&fit=crop&w=600&q=80" class="rounded-2xl h-60 w-full object-cover shadow-sm">
<img src="https://images.unsplash.com/photo-1511920170033-f8396924c348?auto=format&fit=crop&w=600&q=80" class="rounded-2xl h-60 w-full object-cover shadow-sm">
<img src="https://images.unsplash.com/photo-1509042239860-f550ce710b93?auto=format&fit=crop&w=600&q=80" class="rounded-2xl h-60 w-full object-cover shadow-sm">
</div>
</div>
</section>
<!-- PAGE 6: CONTACT -->
<section id="page-contact" class="page-section">
<div class="bg-coffee-900 text-cream py-10 text-center"><h1 class="font-serif text-3xl font-bold">Kontakt & Recenze</h1></div>
<div class="max-w-4xl mx-auto px-4 py-10">
<form onsubmit="alert('Děkujeme za zprávu!'); return false;" class="bg-white p-6 rounded-3xl border space-y-4">
<div><label class="block text-xs font-bold mb-1">Jméno</label><input type="text" required class="w-full border p-3 rounded-xl text-sm"></div>
<div><label class="block text-xs font-bold mb-1">Zpráva / Recenze</label><textarea required rows="4" class="w-full border p-3 rounded-xl text-sm"></textarea></div>
<button type="submit" class="w-full bg-coffee-800 text-cream font-bold py-3 rounded-xl">Odeslat</button>
</form>
</div>
</section>
</main>
<footer class="bg-coffee-950 text-coffee-300 py-6 text-center text-xs">
<p>© 2026 Coffee Spot. Všechna práva vyhrazena.</p>
</footer>
<script>
function navigateTo(pageId) {
document.querySelectorAll('.page-section').forEach(p => p.classList.remove('active'));
const target = document.getElementById('page-' + pageId);
if (target) target.classList.add('active');
window.scrollTo({ top: 0, behavior: 'smooth' });
}
function toggleMobileMenu() {
document.getElementById('mobile-menu').classList.toggle('hidden');
}
function filterMenu(category) {
document.querySelectorAll('.menu-item').forEach(item => {
if (category === 'all' || item.getAttribute('data-category') === category) {
item.style.display = 'flex';
} else {
item.style.display = 'none';
}
});
}
</script>
</body>
</html>
