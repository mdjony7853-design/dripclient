<!doctype html>
<html lang="bn">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>FastPixel Shop — আপনার অনলাইন শপ</title>
  <meta name="description" content="FastPixel shop demo — বিজনেস / শপ ওয়েবসাইট টেমপ্লেট" />
  <style>
    /* ===== Normalize-ish ===== */
    :root{
      --brand:#0f766e;
      --accent:#06b6d4;
      --muted:#6b7280;
      --card:#ffffff;
      --bg:#f8fafc;
      --glass: rgba(255,255,255,0.6);
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background: linear-gradient(180deg, #f8fafc 0%, #eef2f7 100%);
      color:#0f172a;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.45;
    }

    /* Container */
    .container{max-width:1100px;margin:0 auto;padding:20px;}

    /* Header */
    header{display:flex;align-items:center;justify-content:space-between;padding:12px 0}
    .brand{display:flex;gap:12px;align-items:center}
    .logo{
      width:48px;height:48px;border-radius:8px;background:var(--brand);display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:18px;
      box-shadow:0 6px 18px rgba(15,118,110,0.15);
    }
    nav{display:flex;gap:12px;align-items:center}
    nav a{color:var(--muted);text-decoration:none;padding:8px;border-radius:8px}
    nav a:hover{background:rgba(0,0,0,0.04);color:var(--brand)}

    /* Hero */
    .hero{display:flex;gap:18px;align-items:center;margin:22px 0;padding:24px;border-radius:12px;background:linear-gradient(90deg,rgba(15,118,110,0.06), rgba(6,182,212,0.02));}
    .hero-left{flex:1}
    .hero h1{margin:0;font-size:28px}
    .hero p{margin:8px 0 16px;color:var(--muted)}
    .hero .cta{background:var(--brand);color:white;padding:10px 16px;border-radius:10px;border:none;cursor:pointer;font-weight:600}
    .hero .secondary{background:transparent;border:1px solid rgba(15,118,110,0.12);padding:10px 16px;border-radius:10px;color:var(--brand);cursor:pointer}

    /* Product grid */
    .grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:18px;margin:18px 0}
    .card{background:var(--card);border-radius:12px;padding:12px;box-shadow:0 6px 18px rgba(2,6,23,0.04);display:flex;flex-direction:column;gap:8px}
    .card img{width:100%;height:160px;object-fit:cover;border-radius:8px}
    .card h3{margin:0;font-size:16px}
    .card .price{font-weight:700;color:var(--brand)}
    .card .meta{color:var(--muted);font-size:13px}

    .card .actions{margin-top:auto;display:flex;gap:8px}
    .btn{padding:8px 10px;border-radius:10px;border:none;cursor:pointer;font-weight:600}
    .btn-outline{background:transparent;border:1px solid rgba(15,118,110,0.12);color:var(--brand)}
    .btn-primary{background:var(--brand);color:white}

    /* Cart sidebar */
    .cart-toggle{position:fixed;right:18px;bottom:18px;background:var(--accent);color:white;padding:12px;border-radius:999px;box-shadow:0 8px 26px rgba(6,182,212,0.2);cursor:pointer;border:none}
    .cart-panel{position:fixed;right:18px;top:80px;width:320px;max-width:90vw;background:var(--card);border-radius:12px;box-shadow:0 12px 40px rgba(2,6,23,0.12);overflow:hidden;transform:translateX(10px);transition:transform .18s ease,opacity .18s ease;opacity:0;pointer-events:none}
    .cart-panel.open{transform:translateX(0);opacity:1;pointer-events:auto}
    .cart-head{padding:12px;border-bottom:1px solid #f1f5f9;display:flex;justify-content:space-between;align-items:center}
    .cart-list{max-height:380px;overflow:auto;padding:12px;display:flex;flex-direction:column;gap:12px}
    .cart-item{display:flex;gap:10px;align-items:center}
    .cart-item img{width:52px;height:52px;object-fit:cover;border-radius:8px}
    .cart-footer{padding:12px;border-top:1px solid #f1f5f9;display:flex;flex-direction:column;gap:8px}

    /* Modal */
    .modal-back{position:fixed;inset:0;background:rgba(2,6,23,0.5);display:none;align-items:center;justify-content:center;padding:20px}
    .modal-back.open{display:flex}
    .modal{width:100%;max-width:820px;background:var(--card);border-radius:12px;padding:18px;display:flex;gap:12px}
    .modal img{width:50%;height:320px;object-fit:cover;border-radius:8px}
    .modal .info{flex:1}

    /* Footer */
    footer{margin-top:28px;padding:18px 0;color:var(--muted);text-align:center;font-size:14px}

    /* Responsive tweaks */
    @media (max-width:720px){
      .hero{flex-direction:column;align-items:flex-start}
      .modal{flex-direction:column}
      .modal img{width:100%;height:260px}
    }

    /* small helpers */
    .muted{color:var(--muted);font-size:13px}
    input,textarea{font-family:inherit;padding:8px;border-radius:8px;border:1px solid #e6eef6}
    label{font-size:13px;color:var(--muted);display:block;margin-bottom:6px}
  </style>
</head>
<body>
  <div class="container">
    <!-- Header -->
    <header>
      <div class="brand">
        <div class="logo">FP</div>
        <div>
          <div style="font-weight:700">FastPixel Shop</div>
          <div style="font-size:12px;color:var(--muted)">Quality products • Fast delivery</div>
        </div>
      </div>

      <nav>
        <a href="#home">হোম</a>
        <a href="#products">প্রোডাক্ট</a>
        <a href="#about">অ্যাবাউট</a>
        <a href="#contact">কন্টাক্ট</a>
        <button id="openCart" class="btn" style="background:transparent;border:1px solid rgba(15,118,110,0.12);padding:8px 12px;border-radius:10px">কার্ট (<span id="cartCount">0</span>)</button>
      </nav>
    </header>

    <!-- Hero -->
    <section id="home" class="hero" role="region" aria-label="হিরো">
      <div class="hero-left">
        <h1>আপনার ব্যবসার জন্য একদম সোজা এবং সুন্দর ওয়েবশপ</h1>
        <p>FastPixel টেমপ্লেট — দ্রুত সেটআপ, মোবাইল-ফ্রেন্ডলি, এবং কাস্টমাইজযোগ্য। এখনি আপনার পণ্যগুলো আপলোড করুন ও বিক্রি শুরু করুন।</p>
        <div style="display:flex;gap:10px">
          <button id="shopNow" class="hero-cta cta btn-primary">শপ শুরু করুন</button>
          <button class="secondary btn-outline" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'})">যোগাযোগ করুন</button>
        </div>
      </div>
      <div class="hero-right" style="min-width:260px;text-align:center">
        <img src="https://images.unsplash.com/photo-1606813903046-4bca23d22f24?q=80&w=800&auto=format&fit=crop&ixlib=rb-4.0.3&s=9b2a1b6fc9a7b0a1f0e6f4a9f69d0d1b" alt="shop" style="width:100%;border-radius:10px;box-shadow:0 12px 40px rgba(2,6,23,0.06)" />
      </div>
    </section>

    <!-- Products -->
    <h2 id="products" style="margin-top:6px">পণ্যসমূহ</h2>
    <div class="grid" id="productGrid" aria-live="polite"></div>

    <!-- About -->
    <section id="about" style="margin-top:22px;padding:18px;border-radius:10px;background:linear-gradient(90deg,rgba(6,182,212,0.04),rgba(15,118,110,0.03))">
      <h3>আমাদের সম্পর্কে</h3>
      <p class="muted">FastPixel একটি ছোট বিজনেস টেমপ্লেট — আপনি চাইলে এটাকে উন্নত করে নিতে পারবেন: পেমেন্ট ইন্টিগ্রেশন, অ্যাপ ইন্টিগ্রেশন, অর্ডার ট্র্যাকিং ইত্যাদি।</p>
    </section>

    <!-- Contact -->
    <section id="contact" style="margin-top:18px">
      <h3>যোগাযোগ করুন</h3>
      <form id="contactForm" style="max-width:720px;display:grid;gap:8px">
        <div>
          <label for="name">নাম</label>
          <input id="name" required />
        </div>
        <div>
          <label for="email">ইমেইল / ফোন</label>
          <input id="email" required />
        </div>
        <div>
          <label for="message">বার্তা</label>
          <textarea id="message" rows="4" required></textarea>
        </div>
        <div>
          <button type="submit" class="btn btn-primary">পাঠান</button>
        </div>
      </form>
    </section>

    <footer>
      © <span id="year"></span> FastPixel Shop — তৈরি করেছেন আপনার জন্য। • ফোন: +880 1XXXXXXXXX
    </footer>
  </div>

  <!-- Cart toggle + panel -->
  <button id="cartToggle" class="cart-toggle" title="Open cart">🛒</button>
  <aside id="cartPanel" class="cart-panel" aria-hidden="true">
    <div class="cart-head">
      <strong>আপনার কার্ট</strong>
      <button id="closeCart" class="btn" style="background:transparent">✕</button>
    </div>
    <div class="cart-list" id="cartList">
      <!-- items -->
    </div>
    <div class="cart-footer">
      <div style="display:flex;justify-content:space-between;align-items:center">
        <div class="muted">মোট <strong id="cartTotalItems">0</strong> আইটেম</div>
        <div class="price" id="cartTotalPrice">৳0</div>
      </div>
      <div style="display:flex;gap:8px">
        <button id="checkoutBtn" class="btn btn-primary" style="flex:1">চেকআউট</button>
        <button id="clearCart" class="btn btn-outline">খালি</button>
      </div>
    </div>
  </aside>

  <!-- Modal -->
  <div id="modalBack" class="modal-back" role="dialog" aria-modal="true">
    <div class="modal" role="document" aria-label="Product detail">
      <img id="modalImg" src="" alt="product image">
      <div class="info">
        <h3 id="modalTitle"></h3>
        <div class="muted" id="modalPrice"></div>
        <p id="modalDesc" style="margin-top:8px;color:var(--muted)"></p>
        <div style="margin-top:12px;display:flex;gap:8px">
          <button id="modalAdd" class="btn btn-primary">কার্টে যোগ করুন</button>
          <button id="modalClose" class="btn btn-outline">বন্ধ</button>
        </div>
      </div>
    </div>
  </div>

  <script>
    /* ============================
       Simple product data (edit here)
       ============================ */
    const products = [
      {
        id: 'p1',
        title: 'Wireless Headphones',
        price: 1490,
        img: 'https://images.unsplash.com/photo-1518444025989-7b8d36b6b1b1?q=80&w=800&auto=format&fit=crop&ixlib=rb-4.0.3&s=8aa5a6b5e2a4b5f3f6d8a9aa2bc1a3e1',
        desc: 'আরামদায়ক হেডফোন — হাই কোয়ালিটি সাউন্ড ও লং ব্যাটারি লাইফ।'
      },
      {
        id: 'p2',
        title: 'Smart Watch',
        price: 2990,
        img: 'https://images.unsplash.com/photo-1519744792095-2f2205e87b6f?q=80&w=800&auto=format&fit=crop&ixlib=rb-4.0.3&s=8f1b5ad2d1fae3f6d8a8c9d5b6d3e2c2',
        desc: 'স্টাইলিশ স্মার্টওয়াচ — হেলথ ট্র্যাকিং ও নোটিফিকেশন।'
      },
      {
        id: 'p3',
        title: 'Gaming Mouse',
        price: 650,
        img: 'https://images.unsplash.com/photo-1585386959984-a415522c5f3c?q=80&w=800&auto=format&fit=crop&ixlib=rb-4.0.3&s=b2f4c4b3d6c2d7f9e1c2b3a4d5e6f7c8',
        desc: 'আরও ভালো কন্ট্রোল এবং আরামদায়ক গ্রিপ।'
      },
      {
        id: 'p4',
        title: 'Bluetooth Speaker',
        price: 1250,
        img: 'https://images.unsplash.com/photo-1526178613357-1e3f9d9f2f62?q=80&w=800&auto=format&fit=crop&ixlib=rb-4.0.3&s=ad6b3b4c2d9f4a1b3c4d5e6f7a8b9c0d',
        desc: 'পোর্টেবল স্পিকার — শক্তিশালী বেস ও ক্লিয়ার সাউন্ড।'
      }
    ];

    /* ================
       Render products
       ================ */
    const grid = document.getElementById('productGrid');
    function renderProducts(){
      grid.innerHTML = '';
      products.forEach(p=>{
        const div = document.createElement('div');
        div.className = 'card';
        div.innerHTML = `
          <img src="${p.img}" alt="${escapeHtml(p.title)}" loading="lazy" />
          <h3>${escapeHtml(p.title)}</h3>
          <div class="meta">${escapeHtml(p.desc)}</div>
          <div style="display:flex;justify-content:space-between;align-items:center;margin-top:8px">
            <div class="price">৳${formatNumber(p.price)}</div>
            <div style="display:flex;gap:8px">
              <button class="btn btn-outline" onclick="openModal('${p.id}')">View</button>
              <button class="btn btn-primary" onclick="addToCart('${p.id}')">Add</button>
            </div>
          </div>
        `;
        grid.appendChild(div);
      })
    }

    /* ================
       Simple modal
       ================ */
    const modalBack = document.getElementById('modalBack');
    const modalImg = document.getElementById('modalImg');
    const modalTitle = document.getElementById('modalTitle');
    const modalDesc = document.getElementById('modalDesc');
    const modalPrice = document.getElementById('modalPrice');
    const modalAdd = document.getElementById('modalAdd');
    let currentModalId = null;

    function openModal(id){
      const p = products.find(x=>x.id===id);
      if(!p) return;
      currentModalId = id;
      modalImg.src = p.img;
      modalTitle.textContent = p.title;
      modalDesc.textContent = p.desc;
      modalPrice.textContent = '৳' + formatNumber(p.price);
      modalBack.classList.add('open');
    }
    document.getElementById('modalClose').addEventListener('click', ()=>modalBack.classList.remove('open'));
    modalBack.addEventListener('click', (e)=>{ if(e.target===modalBack) modalBack.classList.remove('open') });
    modalAdd.addEventListener('click', ()=>{ if(currentModalId) addToCart(currentModalId); modalBack.classList.remove('open') });

    /* ================
       Cart logic (localStorage)
       ================ */
    const cartKey = 'fastpixel_cart_v1';
    let cart = loadCart();

    function loadCart(){
      try{
        const raw = localStorage.getItem(cartKey);
        return raw ? JSON.parse(raw) : {};
      }catch(e){ return {} }
    }
    function saveCart(){
      localStorage.setItem(cartKey, JSON.stringify(cart));
      updateCartUI();
    }

    function addToCart(id){
      cart[id] = (cart[id] || 0) + 1;
      saveCart();
      flashMsg('কার্টে যোগ করা হয়েছে');
    }

    function removeFromCart(id){
      delete cart[id];
      saveCart();
    }

    function clearCart(){
      cart = {};
      saveCart();
    }

    function updateCartUI(){
      const list = document.getElementById('cartList');
      const countSpan = document.getElementById('cartCount');
      list.innerHTML = '';
      let total = 0, items = 0;
      for(const id in cart){
        const qty = cart[id];
        const p = products.find(x=>x.id===id);
        if(!p) continue;
        const item = document.createElement('div');
        item.className = 'cart-item';
        item.innerHTML = `
          <img src="${p.img}" alt="${escapeHtml(p.title)}" />
          <div style="flex:1">
            <div style="display:flex;justify-content:space-between;align-items:center">
              <div><strong>${escapeHtml(p.title)}</strong></div>
              <div>৳${formatNumber(p.price*qty)}</div>
            </div>
            <div class="muted" style="display:flex;gap:8px;align-items:center;margin-top:6px">
              <div>Qty: ${qty}</div>
              <button class="btn" style="padding:4px 6px" onclick="decreaseQty('${id}')">−</button>
              <button class="btn" style="padding:4px 6px" onclick="increaseQty('${id}')">+</button>
              <button class="btn" style="padding:4px 6px" onclick="removeFromCart('${id}')">Remove</button>
            </div>
          </div>
        `;
        list.appendChild(item);
        total += p.price * qty;
        items += qty;
      }
      document.getElementById('cartTotalPrice').textContent = '৳' + formatNumber(total);
      document.getElementById('cartTotalItems').textContent = items;
      document.getElementById('cartCount').textContent = items;
      document.getElementById('cartTotalItems').textContent = items;
    }

    function increaseQty(id){ cart[id] = (cart[id]||0) + 1; saveCart(); }
    function decreaseQty(id){ if(!cart[id]) return; cart[id]--; if(cart[id]<=0) delete cart[id]; saveCart(); }

    document.getElementById('cartToggle').addEventListener('click', ()=>toggleCart(true));
    document.getElementById('openCart').addEventListener('click', ()=>toggleCart(true));
    document.getElementById('closeCart').addEventListener('click', ()=>toggleCart(false));
    document.getElementById('clearCart').addEventListener('click', ()=>{ if(confirm('সব আইটেম মুছে ফেলতে চান?')) clearCart(); });
    document.getElementById('checkoutBtn').addEventListener('click', ()=>{ alert('চেকআউট ডেমো: আপনি কার্টে '+document.getElementById('cartCount').textContent+' আইটেম রেখেছেন। বাস্তবে এখানে পেমেন্ট ইন্টিগ্রেশন করা হবে।'); });

    function toggleCart(open){
      const panel = document.getElementById('cartPanel');
      if(open) panel.classList.add('open'); else panel.classList.remove('open');
    }

    /* contact form demo */
    document.getElementById('contactForm').addEventListener('submit', function(e){
      e.preventDefault();
      const name = document.getElementById('name').value.trim();
      const email = document.getElementById('email').value.trim();
      const message = document.getElementById('message').value.trim();
      if(!name || !email || !message){ alert('সব ঘর পূরণ করুন'); return; }
      // Demo: just show a success msg. Integrate with backend / email service in production.
      alert('ধন্যবাদ, বার্তা পাওয়া গেছে — আমরা শিগগিরই যোগাযোগ করব।');
      this.reset();
    });

    /* small helpers */
    function formatNumber(n){ return n.toLocaleString('en-US'); }
    function escapeHtml(s){ return String(s).replace(/[&<>"']/g, function(m){return {'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[m]}); }

    function flashMsg(text){
      const el = document.createElement('div');
      el.textContent = text;
      el.style.position='fixed';
      el.style.left='50%';
      el.style.bottom='90px';
      el.style.transform='translateX(-50%)';
      el.style.background='rgba(15,118,110,0.95)';
      el.style.color='white';
      el.style.padding='10px 16px';
      el.style.borderRadius='999px';
      el.style.boxShadow='0 8px 30px rgba(2,6,23,0.12)';
      document.body.appendChild(el);
      setTimeout(()=>el.style.opacity='0',1400);
      setTimeout(()=>el.remove(),2000);
    }

    /* init */
    document.getElementById('year').textContent = new Date().getFullYear();
    document.getElementById('shopNow').addEventListener('click', ()=>document.getElementById('products').scrollIntoView({behavior:'smooth'}));
    renderProducts();
    updateCartUI();

    // Optional: populate products from server or JSON file by fetching '/products.json'
    // Fetch logic can be added here.

  </script>
</body>
</html># dripclient
