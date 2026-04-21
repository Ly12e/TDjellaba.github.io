<!doctype html>
<html lang="fr" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Djellaba Boutique</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <script src="https://cdn.jsdelivr.net/npm/lucide@0.263.0/dist/umd/lucide.min.js"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;0,700;1,400&amp;family=Outfit:wght@300;400;500;600&amp;display=swap" rel="stylesheet">
  <style>
    html, body { height: 100%; margin: 0; }
    * { box-sizing: border-box; }
    .font-heading { font-family: 'Cormorant Garamond', serif; }
    .font-body { font-family: 'Outfit', sans-serif; }
    .pattern-bg {
      background-image: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M30 0L60 30L30 60L0 30Z' fill='none' stroke='%23c4956a' stroke-width='0.4' opacity='0.15'/%3E%3C/svg%3E");
    }
    .card-hover { transition: transform 0.35s ease, box-shadow 0.35s ease; }
    .card-hover:hover { transform: translateY(-6px); box-shadow: 0 20px 40px rgba(0,0,0,0.12); }
    .fade-in { animation: fadeIn 0.7s ease both; }
    .fade-in-d1 { animation-delay: 0.1s; }
    .fade-in-d2 { animation-delay: 0.2s; }
    .fade-in-d3 { animation-delay: 0.3s; }
    .fade-in-d4 { animation-delay: 0.4s; }
    .fade-in-d5 { animation-delay: 0.5s; }
    .fade-in-d6 { animation-delay: 0.6s; }
    @keyframes fadeIn { from { opacity:0; transform: translateY(18px); } to { opacity:1; transform: translateY(0); } }
    @keyframes shimmer { 0%{background-position:-200% 0} 100%{background-position:200% 0} }
    .shimmer-btn { background-size: 200% 100%; animation: shimmer 3s linear infinite; }
    .toast-show { animation: toastIn 0.4s ease both; }
    @keyframes toastIn { from { opacity:0; transform: translateY(20px); } to { opacity:1; transform: translateY(0); } }
  </style>
  <style>body { box-sizing: border-box; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full font-body">
  <div id="app" class="w-full h-full overflow-auto" style="background-color: #faf6f1;"><!-- Toast -->
   <div id="toast" class="fixed bottom-6 right-6 z-50 hidden"></div><!-- Nav -->
   <nav id="navbar" class="sticky top-0 z-40 backdrop-blur-md border-b" style="background: rgba(250,246,241,0.92); border-color: #e0d5c7;">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 py-3 flex items-center justify-between">
     <div class="flex items-center gap-2">
      <svg width="32" height="32" viewbox="0 0 32 32" fill="none">
       <path d="M16 2C10 2 6 8 6 16c0 6 4 14 10 14s10-8 10-14C26 8 22 2 16 2z" stroke="#8b6f4e" stroke-width="1.5" fill="none" /><path d="M12 10c0 0 2 4 4 4s4-4 4-4" stroke="#8b6f4e" stroke-width="1.2" fill="none" /><circle cx="16" cy="20" r="1.5" fill="#8b6f4e" />
      </svg><span id="nav-title" class="font-heading text-xl sm:text-2xl font-bold" style="color: #8b6f4e;">TD Djellaba</span>
     </div>
     <div class="flex items-center gap-3 sm:gap-5"><button onclick="scrollToSection('collection')" class="hidden sm:block text-sm font-medium hover:opacity-70 transition" style="color: #3d3229;">Collection</button> <button onclick="scrollToSection('about')" class="hidden sm:block text-sm font-medium hover:opacity-70 transition" style="color: #3d3229;">À propos</button> <button id="cart-btn" onclick="toggleCart()" class="relative p-2 rounded-full transition hover:opacity-70" style="color: #8b6f4e;"> <i data-lucide="shopping-bag" style="width:22px;height:22px;"></i> <span id="cart-count" class="absolute -top-1 -right-1 text-white text-xs w-5 h-5 rounded-full flex items-center justify-center font-semibold hidden" style="background:#c4956a;">0</span> </button>
     </div>
    </div>
   </nav><!-- Hero -->
   <header class="pattern-bg relative overflow-hidden">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 py-16 sm:py-24 flex flex-col items-center text-center">
     <div id="promo-banner" class="fade-in mb-6 px-5 py-2 rounded-full text-sm font-medium" style="background:#8b6f4e; color:#faf6f1;">
      ✨ Livraison gratuite dès 300 DH
     </div>
     <h1 id="hero-title" class="fade-in fade-in-d1 font-heading text-4xl sm:text-6xl lg:text-7xl font-bold leading-tight" style="color: #3d3229;">Élégance<br><em class="font-normal" style="color:#8b6f4e;">Traditionnelle</em></h1>
     <p id="hero-subtitle" class="fade-in fade-in-d2 mt-5 text-base sm:text-lg max-w-xl" style="color: #6b5d50;">Djellabas raffinées pour femmes et petites filles, alliant tradition marocaine et modernité.</p><button onclick="scrollToSection('collection')" class="fade-in fade-in-d3 mt-8 shimmer-btn px-8 py-3.5 rounded-full text-sm font-semibold tracking-wide transition hover:scale-105" style="background: linear-gradient(90deg, #8b6f4e, #c4956a, #8b6f4e); color: #faf6f1;"> Découvrir la Collection </button>
    </div>
   </header><!-- Categories -->
   <section class="max-w-7xl mx-auto px-4 sm:px-6 py-12">
    <div class="grid grid-cols-2 gap-4 sm:gap-6"><button onclick="filterProducts('femme')" id="cat-femme" class="fade-in fade-in-d2 group relative overflow-hidden rounded-2xl p-8 sm:p-12 text-left transition card-hover" style="background: linear-gradient(135deg, #8b6f4e, #6b5240);"> <span class="relative z-10 font-heading text-2xl sm:text-3xl font-bold text-white">Femme</span> <p class="relative z-10 mt-1 text-sm text-white/70">Collection raffinée</p>
      <div class="absolute top-3 right-3 opacity-20 text-white">
       <i data-lucide="crown" style="width:48px;height:48px;"></i>
      </div></button> <button onclick="filterProducts('fille')" id="cat-fille" class="fade-in fade-in-d3 group relative overflow-hidden rounded-2xl p-8 sm:p-12 text-left transition card-hover" style="background: linear-gradient(135deg, #c4956a, #a87d58);"> <span class="relative z-10 font-heading text-2xl sm:text-3xl font-bold text-white">Petite Fille</span> <p class="relative z-10 mt-1 text-sm text-white/70">Adorables modèles</p>
      <div class="absolute top-3 right-3 opacity-20 text-white">
       <i data-lucide="heart" style="width:48px;height:48px;"></i>
      </div></button>
    </div>
   </section><!-- Products -->
   <section id="collection" class="max-w-7xl mx-auto px-4 sm:px-6 pb-16">
    <div class="flex items-center justify-between mb-8">
     <h2 class="font-heading text-3xl sm:text-4xl font-bold" style="color: #3d3229;">Notre Collection</h2><button onclick="filterProducts('all')" class="text-sm font-medium underline underline-offset-4 transition hover:opacity-70" style="color: #8b6f4e;">Voir tout</button>
    </div>
    <div id="filter-pills" class="flex gap-2 mb-6 flex-wrap"></div>
    <div id="products-grid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6"></div>
   </section><!-- About -->
   <section id="about" class="border-t" style="border-color: #e0d5c7;">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 py-16 grid md:grid-cols-2 gap-10 items-center">
     <div>
      <h2 class="font-heading text-3xl sm:text-4xl font-bold" style="color:#3d3229;">Savoir-faire Artisanal</h2>
      <p class="mt-4 leading-relaxed" style="color:#6b5d50;">Chaque djellaba est confectionnée à la main par nos artisans au Maroc, avec des tissus nobles et des finitions brodées minutieuses. Nous perpétuons un héritage séculaire tout en embrassant les tendances contemporaines.</p>
      <div class="mt-8 flex gap-8">
       <div class="text-center">
        <span class="block font-heading text-3xl font-bold" style="color:#8b6f4e;">100%</span><span class="text-xs" style="color:#6b5d50;">Fait main</span>
       </div>
       <div class="text-center">
        <span class="block font-heading text-3xl font-bold" style="color:#8b6f4e;">500+</span><span class="text-xs" style="color:#6b5d50;">Clientes ravies</span>
       </div>
       <div class="text-center">
        <span class="block font-heading text-3xl font-bold" style="color:#8b6f4e;">48h</span><span class="text-xs" style="color:#6b5d50;">Livraison</span>
       </div>
      </div>
     </div>
     <div class="rounded-2xl p-10 flex items-center justify-center" style="background: linear-gradient(135deg, #e0d5c7, #c4956a33);">
      <svg width="180" height="220" viewbox="0 0 180 220" fill="none"><path d="M90 10C60 10 35 50 35 110c0 45 25 100 55 100s55-55 55-100C145 50 120 10 90 10z" stroke="#8b6f4e" stroke-width="2" fill="none" /> <path d="M65 60c0 0 12 20 25 20s25-20 25-20" stroke="#8b6f4e" stroke-width="1.5" fill="none" /> <path d="M75 90l15 50 15-50" stroke="#c4956a" stroke-width="1" fill="none" stroke-dasharray="4 3" /> <circle cx="90" cy="150" r="3" fill="#8b6f4e" /> <circle cx="90" cy="165" r="3" fill="#8b6f4e" /> <circle cx="90" cy="180" r="3" fill="#8b6f4e" />
      </svg>
     </div>
    </div>
   </section><!-- Footer -->
   <footer class="border-t" style="background: #3d3229; border-color: #3d3229;">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10">
     <div class="grid sm:grid-cols-3 gap-8 text-sm" style="color: #c4b89f;">
      <div><span id="footer-brand" class="font-heading text-xl font-bold" style="color:#faf6f1;">TD Djellaba</span>
       <p id="footer-desc" class="mt-2 text-xs leading-relaxed">L'élégance traditionnelle marocaine, livrée chez vous.</p>
      </div>
      <div>
       <h4 class="font-semibold mb-3" style="color:#faf6f1;">Contact</h4>
       <p class="flex items-center gap-2"><i data-lucide="phone" style="width:14px;height:14px;"></i> +212 6 00 00 00 00</p>
       <p class="flex items-center gap-2 mt-1"><i data-lucide="mail" style="width:14px;height:14px;"></i> contact@TDdjellaba.ma</p>
       <p class="flex items-center gap-2 mt-1"><i data-lucide="map-pin" style="width:14px;height:14px;"></i> Casablanca, Maroc</p>
      </div>
      <div>
       <h4 class="font-semibold mb-3" style="color:#faf6f1;">Suivez-nous</h4>
       <div class="flex gap-3"><span class="w-9 h-9 rounded-full flex items-center justify-center" style="background:#8b6f4e;color:#faf6f1;"><i data-lucide="instagram" style="width:16px;height:16px;"></i></span> <span class="w-9 h-9 rounded-full flex items-center justify-center" style="background:#8b6f4e;color:#faf6f1;"><i data-lucide="facebook" style="width:16px;height:16px;"></i></span>
       </div>
      </div>
     </div>
     <p id="footer-copy" class="mt-8 text-center text-xs" style="color:#6b5d50;">© 2025 TD Djellaba — Tous droits réservés</p>
    </div>
   </footer><!-- Cart Drawer -->
   <div id="cart-overlay" class="fixed inset-0 z-50 hidden">
    <div class="absolute inset-0 bg-black/40" onclick="toggleCart()"></div>
    <div id="cart-drawer" class="absolute right-0 top-0 h-full w-full sm:w-96 flex flex-col" style="background:#faf6f1; transform:translateX(100%); transition:transform 0.35s ease;">
     <div class="flex items-center justify-between px-5 py-4 border-b" style="border-color:#e0d5c7;">
      <h3 class="font-heading text-xl font-bold" style="color:#3d3229;">Mon Panier</h3><button onclick="toggleCart()" class="p-1 hover:opacity-60 transition" style="color:#3d3229;"><i data-lucide="x" style="width:22px;height:22px;"></i></button>
     </div>
     <div id="cart-items" class="flex-1 overflow-auto px-5 py-4"></div>
     <div id="cart-footer" class="border-t px-5 py-4" style="border-color:#e0d5c7;">
      <div class="flex justify-between items-center mb-4"><span class="font-semibold" style="color:#3d3229;">Total</span> <span id="cart-total" class="font-heading text-2xl font-bold" style="color:#8b6f4e;">0 DH</span>
      </div><button onclick="checkout()" class="w-full py-3 rounded-full font-semibold text-sm transition hover:scale-[1.02]" style="background:#8b6f4e; color:#faf6f1;"> Commander via WhatsApp </button>
     </div>
    </div>
   </div>
  </div>
  <script>

const products = [
  { id:1, name:"Djellaba Royale", cat:"femme", price:200, color:"Blanc cassé", image:"1.jpeg", desc:"Broderie dorée, tissu soyeux" },
  { id:2, name:"Djellaba Safran", cat:"femme", price:230, color:"Safran", image:"2.jpeg", desc:"Coupe fluide, finitions perlées" },
  { id:3, name:"Djellaba Nuit", cat:"femme", price:220, color:"Bleu nuit", image:"4.jpeg", desc:"Velours premium, broderie argent" },
  { id:4, name:"Djellaba Princesse", cat:"fille", price:180, color:"Rose poudré", image:"5.jpeg", desc:"Adorable et confortable" },
  { id:5, name:"Djellaba Fleurie", cat:"fille", price:250, color:"Lilas", image:"1.jpeg", desc:"Motifs floraux délicats" },
  { id:6, name:"Djellaba Soleil", cat:"fille", price:240, color:"Doré", image:"2.jpeg", desc:"Idéale pour les fêtes" }
];

let cart = [];
let currentFilter = 'all';

function renderProducts() {
  const grid = document.getElementById('products-grid');
  const filtered = currentFilter === 'all'
    ? products
    : products.filter(p => p.cat === currentFilter);

  grid.innerHTML = '';

  filtered.forEach((p, i) => {
    const card = document.createElement('div');

    card.className =
      `card-hover rounded-2xl overflow-hidden fade-in fade-in-d${i+1}`;

    card.innerHTML = `
      <div class="h-72 bg-white overflow-hidden relative">
        <img src="${p.image}" 
             alt="${p.name}"
             class="w-full h-full object-cover">

        <span class="absolute top-3 left-3 text-xs font-medium px-3 py-1 rounded-full"
              style="background:rgba(255,255,255,0.85);color:#8b6f4e;">
          ${p.cat === 'femme' ? 'Femme' : 'Petite Fille'}
        </span>
      </div>

      <div class="p-5 bg-white">
        <h3 class="font-heading text-xl font-bold" style="color:#3d3229;">
          ${p.name}
        </h3>

        <p class="text-xs mt-1" style="color:#6b5d50;">
          ${p.desc} · ${p.color}
        </p>

        <div class="flex items-center justify-between mt-4">
          <span class="font-heading text-2xl font-bold"
                style="color:#8b6f4e;">
            ${p.price} DH
          </span>

          <button onclick="addToCart(${p.id})"
                  class="px-4 py-2 rounded-full text-xs font-semibold"
                  style="background:#8b6f4e;color:white;">
            Ajouter
          </button>
        </div>
      </div>
    `;

    grid.appendChild(card);
  });

  lucide.createIcons();
}


const gradients = {
  "Blanc cassé": "linear-gradient(135deg, #f5f0e8, #e8ddd0)",
  "Safran": "linear-gradient(135deg, #f0d9a8, #dbb878)",
  "Bleu nuit": "linear-gradient(135deg, #3d4a6b, #2a3450)",
  "Rose poudré": "linear-gradient(135deg, #f0d0d0, #e8b8b8)",
  "Lilas": "linear-gradient(135deg, #d8c8e8, #c0a8d8)",
  "Doré": "linear-gradient(135deg, #e8d8a0, #d0c080)"
};



function renderFilterPills() {
  const c = document.getElementById('filter-pills');
  const filters = [{k:'all',l:'Tout'},{k:'femme',l:'Femme'},{k:'fille',l:'Petite Fille'}];
  c.innerHTML = '';
  filters.forEach(f => {
    const btn = document.createElement('button');
    btn.className = 'px-4 py-1.5 rounded-full text-xs font-medium transition';
    const active = currentFilter === f.k;
    btn.style.background = active ? '#8b6f4e' : '#e0d5c7';
    btn.style.color = active ? '#faf6f1' : '#3d3229';
    btn.textContent = f.l;
    btn.onclick = () => filterProducts(f.k);
    c.appendChild(btn);
  });
}

function filterProducts(cat) {
  currentFilter = cat;
  renderProducts();
}

function addToCart(id) {
  const p = products.find(x => x.id === id);
  const existing = cart.find(x => x.id === id);
  if (existing) existing.qty++;
  else cart.push({...p, qty: 1});
  updateCartUI();
  showToast(`${p.name} ajouté au panier`);
}

function updateCartUI() {
  const count = cart.reduce((s,i) => s + i.qty, 0);
  const total = cart.reduce((s,i) => s + i.price * i.qty, 0);
  const badge = document.getElementById('cart-count');
  badge.textContent = count;
  badge.classList.toggle('hidden', count === 0);
  document.getElementById('cart-total').textContent = total + ' DH';

  const container = document.getElementById('cart-items');
  if (cart.length === 0) {
    container.innerHTML = '<p class="text-center py-12" style="color:#6b5d50;">Votre panier est vide</p>';
    return;
  }
  container.innerHTML = '';
  cart.forEach(item => {
    const div = document.createElement('div');
    div.className = 'flex items-center gap-3 py-3 border-b';
    div.style.borderColor = '#e0d5c7';
    div.innerHTML = `
      <div class="w-14 h-14 rounded-xl overflow-hidden flex-shrink-0">
   <img src="${item.image}" class="w-full h-full object-cover">
    </div>
      <div class="flex-1 min-w-0">
        <p class="font-semibold text-sm truncate" style="color:#3d3229;">${item.name}</p>
        <p class="text-xs" style="color:#6b5d50;">${item.price} DH × ${item.qty}</p>
      </div>
      <div class="flex items-center gap-1">
        <button onclick="changeQty(${item.id},-1)" class="w-7 h-7 rounded-full flex items-center justify-center text-xs" style="background:#e0d5c7;color:#3d3229;">−</button>
        <span class="text-sm w-6 text-center font-medium" style="color:#3d3229;">${item.qty}</span>
        <button onclick="changeQty(${item.id},1)" class="w-7 h-7 rounded-full flex items-center justify-center text-xs" style="background:#8b6f4e;color:#faf6f1;">+</button>
      </div>`;
    container.appendChild(div);
  });
}

function changeQty(id, d) {
  const item = cart.find(x => x.id === id);
  if (!item) return;
  item.qty += d;
  if (item.qty <= 0) cart = cart.filter(x => x.id !== id);
  updateCartUI();
}

function toggleCart() {
  const overlay = document.getElementById('cart-overlay');
  const drawer = document.getElementById('cart-drawer');
  const isOpen = !overlay.classList.contains('hidden');
  if (isOpen) {
    drawer.style.transform = 'translateX(100%)';
    setTimeout(() => overlay.classList.add('hidden'), 350);
  } else {
    overlay.classList.remove('hidden');
    requestAnimationFrame(() => { drawer.style.transform = 'translateX(0)'; });
  }
}

function checkout() {
  if (cart.length === 0) return;
  const msg = cart.map(i => `${i.name} ×${i.qty} — ${i.price*i.qty} DH`).join('%0A');
  const total = cart.reduce((s,i) => s + i.price*i.qty, 0);
  const url = `https://wa.me/212600000000?text=Bonjour! Je souhaite commander:%0A${msg}%0A%0ATotal: ${total} DH`;
  window.open(url, '_blank');
}

function showToast(text) {
  const t = document.getElementById('toast');
  t.innerHTML = `<div class="toast-show flex items-center gap-2 px-5 py-3 rounded-full shadow-lg text-sm font-medium" style="background:#3d3229;color:#faf6f1;"><i data-lucide="check-circle" style="width:16px;height:16px;color:#c4956a;"></i>${text}</div>`;
  t.classList.remove('hidden');
  lucide.createIcons();
  setTimeout(() => t.classList.add('hidden'), 2500);
}

function scrollToSection(id) {
  document.getElementById(id)?.scrollIntoView({ behavior:'smooth' });
}

// Element SDK
const defaultConfig = {
  background_color: '#faf6f1',
  surface_color: '#ffffff',
  text_color: '#3d3229',
  primary_action: '#8b6f4e',
  secondary_action: '#c4956a',
  font_family: 'Cormorant Garamond',
  font_size: 16,
  site_title: 'Nour Djellaba',
  hero_subtitle: 'Djellabas raffinées pour femmes et petites filles, alliant tradition marocaine et modernité.',
  promo_text: '✨ Livraison gratuite dès 500 DH',
  footer_text: '© 2025 Nour Djellaba — Tous droits réservés'
};

function applyConfig(config) {
  const bg = config.background_color || defaultConfig.background_color;
  const surface = config.surface_color || defaultConfig.surface_color;
  const txt = config.text_color || defaultConfig.text_color;
  const primary = config.primary_action || defaultConfig.primary_action;
  const secondary = config.secondary_action || defaultConfig.secondary_action;
  const font = config.font_family || defaultConfig.font_family;
  const size = config.font_size || defaultConfig.font_size;

  document.getElementById('app').style.backgroundColor = bg;
  document.querySelectorAll('.card-hover').forEach(c => { const inner = c.querySelector('.p-5')?.parentElement; if(inner) inner.style.background = surface; });

  document.getElementById('nav-title').textContent = config.site_title || defaultConfig.site_title;
  document.getElementById('nav-title').style.color = primary;
  document.getElementById('hero-title').style.color = txt;
  document.getElementById('hero-title').querySelector('em').style.color = primary;
  document.getElementById('hero-subtitle').textContent = config.hero_subtitle || defaultConfig.hero_subtitle;
  document.getElementById('hero-subtitle').style.color = txt + '99';
  document.getElementById('promo-banner').textContent = config.promo_text || defaultConfig.promo_text;
  document.getElementById('promo-banner').style.background = primary;
  document.getElementById('footer-copy').textContent = config.footer_text || defaultConfig.footer_text;
  document.getElementById('footer-brand').textContent = config.site_title || defaultConfig.site_title;

  // Font
  const bodyStack = `${font}, serif`;
  document.querySelectorAll('.font-heading').forEach(el => el.style.fontFamily = bodyStack);
  document.body.style.fontSize = size + 'px';
}

window.elementSdk.init({
  defaultConfig,
  onConfigChange: async (config) => applyConfig(config),
  mapToCapabilities: (config) => ({
    recolorables: [
      { get: () => config.background_color || defaultConfig.background_color, set: v => { config.background_color = v; window.elementSdk.setConfig({background_color:v}); }},
      { get: () => config.surface_color || defaultConfig.surface_color, set: v => { config.surface_color = v; window.elementSdk.setConfig({surface_color:v}); }},
      { get: () => config.text_color || defaultConfig.text_color, set: v => { config.text_color = v; window.elementSdk.setConfig({text_color:v}); }},
      { get: () => config.primary_action || defaultConfig.primary_action, set: v => { config.primary_action = v; window.elementSdk.setConfig({primary_action:v}); }},
      { get: () => config.secondary_action || defaultConfig.secondary_action, set: v => { config.secondary_action = v; window.elementSdk.setConfig({secondary_action:v}); }},
    ],
    borderables: [],
    fontEditable: { get: () => config.font_family || defaultConfig.font_family, set: v => { config.font_family = v; window.elementSdk.setConfig({font_family:v}); }},
    fontSizeable: { get: () => config.font_size || defaultConfig.font_size, set: v => { config.font_size = v; window.elementSdk.setConfig({font_size:v}); }},
  }),
  mapToEditPanelValues: (config) => new Map([
    ['site_title', config.site_title || defaultConfig.site_title],
    ['hero_subtitle', config.hero_subtitle || defaultConfig.hero_subtitle],
    ['promo_text', config.promo_text || defaultConfig.promo_text],
    ['footer_text', config.footer_text || defaultConfig.footer_text],
  ])
});

// Init
renderProducts();
updateCartUI();
lucide.createIcons();
</script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9ef7dca352c8d82a',t:'MTc3NjcyNzA0MC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
