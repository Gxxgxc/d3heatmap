<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <title>Biker's Den | Ride, Repair, Relish</title>
  <!-- Google Fonts & Simple CSS Reset -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
  <!-- Font Awesome 6 (free icons) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background-color: #0a0a0a;
      color: #f0f0f0;
      scroll-behavior: smooth;
    }

    /* custom scrollbar */
    ::-webkit-scrollbar {
      width: 8px;
    }
    ::-webkit-scrollbar-track {
      background: #1a1a1a;
    }
    ::-webkit-scrollbar-thumb {
      background: #e67e22;
      border-radius: 10px;
    }

    .container {
      max-width: 1300px;
      margin: 0 auto;
      padding: 0 24px;
    }

    /* header / navbar */
    .navbar {
      background: #000000dd;
      backdrop-filter: blur(12px);
      position: sticky;
      top: 0;
      z-index: 100;
      padding: 1rem 0;
      border-bottom: 1px solid #e67e2240;
    }
    .nav-wrapper {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
    }
    .logo h1 {
      font-size: 1.8rem;
      font-weight: 800;
      letter-spacing: -0.5px;
      background: linear-gradient(135deg, #f39c12, #e67e22);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }
    .logo p {
      font-size: 0.75rem;
      color: #e67e22;
      letter-spacing: 1px;
    }
    .nav-links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }
    .nav-links a {
      color: #eee;
      text-decoration: none;
      font-weight: 500;
      transition: 0.3s;
      font-size: 1rem;
    }
    .nav-links a:hover {
      color: #e67e22;
    }
    .menu-toggle {
      display: none;
      font-size: 1.8rem;
      cursor: pointer;
      color: #e67e22;
    }

    /* hero section */
    .hero {
      background: linear-gradient(107deg, #101010 0%, #1f1f1f 100%);
      padding: 4rem 0 3rem;
      border-bottom: 1px solid #e67e2230;
    }
    .hero-grid {
      display: flex;
      align-items: center;
      gap: 3rem;
      flex-wrap: wrap;
    }
    .hero-text {
      flex: 1;
    }
    .hero-text .badge {
      background: #e67e2220;
      display: inline-block;
      padding: 0.3rem 1rem;
      border-radius: 40px;
      font-size: 0.8rem;
      font-weight: 600;
      color: #f39c12;
      margin-bottom: 1rem;
    }
    .hero-text h1 {
      font-size: 3rem;
      font-weight: 800;
      line-height: 1.2;
      margin-bottom: 1.2rem;
    }
    .hero-text h1 span {
      color: #e67e22;
    }
    .hero-text p {
      color: #ccc;
      max-width: 500px;
      margin-bottom: 2rem;
      line-height: 1.5;
    }
    .btn-group {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }
    .btn-primary {
      background: #e67e22;
      border: none;
      padding: 0.9rem 2rem;
      border-radius: 40px;
      font-weight: 700;
      color: #0a0a0a;
      transition: 0.2s;
      cursor: pointer;
      text-decoration: none;
      display: inline-block;
    }
    .btn-primary:hover {
      background: #f39c12;
      transform: scale(1.02);
    }
    .btn-outline {
      background: transparent;
      border: 1.5px solid #e67e22;
      padding: 0.9rem 2rem;
      border-radius: 40px;
      font-weight: 600;
      color: #e67e22;
      transition: 0.2s;
      text-decoration: none;
    }
    .btn-outline:hover {
      background: #e67e2220;
    }
    .hero-img {
      flex: 1;
      text-align: center;
    }
    .hero-img img {
      max-width: 100%;
      border-radius: 32px;
      box-shadow: 0 25px 40px -12px black;
      border: 1px solid #e67e2250;
    }

    /* section titles */
    .section-title {
      font-size: 2.2rem;
      font-weight: 700;
      margin-bottom: 2rem;
      position: relative;
      display: inline-block;
    }
    .section-title:after {
      content: '';
      position: absolute;
      bottom: -10px;
      left: 0;
      width: 60%;
      height: 3px;
      background: #e67e22;
      border-radius: 4px;
    }
    .center-title {
      text-align: center;
    }
    .center-title:after {
      left: 20%;
      width: 60%;
    }

    /* gallery grid */
    .gallery {
      padding: 5rem 0;
      background: #0e0e0e;
    }
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 1.8rem;
      margin-top: 2rem;
    }
    .gallery-item {
      background: #1a1a1a;
      border-radius: 24px;
      overflow: hidden;
      transition: 0.3s ease;
      border: 1px solid #2c2c2c;
    }
    .gallery-item:hover {
      transform: translateY(-8px);
      border-color: #e67e22;
      box-shadow: 0 20px 25px -12px #00000080;
    }
    .gallery-item img {
      width: 100%;
      height: 220px;
      object-fit: cover;
      display: block;
      transition: 0.4s;
    }
    .gallery-item:hover img {
      transform: scale(1.02);
    }
    .img-caption {
      padding: 1rem;
      font-weight: 500;
      color: #ddd;
      background: #111;
      font-size: 0.9rem;
    }

    /* services & features */
    .services {
      padding: 5rem 0;
      background: #0a0a0a;
    }
    .cards {
      display: flex;
      flex-wrap: wrap;
      gap: 2rem;
      justify-content: center;
      margin-top: 2rem;
    }
    .card {
      background: #151515;
      border-radius: 28px;
      padding: 2rem 1.5rem;
      flex: 1 1 260px;
      text-align: center;
      transition: all 0.2s;
      border: 1px solid #2a2a2a;
    }
    .card i {
      font-size: 2.8rem;
      color: #e67e22;
      margin-bottom: 1rem;
    }
    .card h3 {
      margin-bottom: 0.8rem;
      font-size: 1.4rem;
    }
    .card p {
      color: #aaa;
      font-size: 0.9rem;
    }

    /* about / hours section */
    .info-section {
      padding: 4rem 0;
      background: #111111;
    }
    .info-flex {
      display: flex;
      flex-wrap: wrap;
      gap: 3rem;
      justify-content: space-between;
    }
    .hours-card, .contact-card {
      background: #1a1a1a;
      padding: 2rem;
      border-radius: 28px;
      flex: 1;
      border-left: 4px solid #e67e22;
    }
    .hours-card h3, .contact-card h3 {
      font-size: 1.6rem;
      margin-bottom: 1.5rem;
      display: flex;
      align-items: center;
      gap: 10px;
    }
    .hours-list {
      list-style: none;
    }
    .hours-list li {
      display: flex;
      justify-content: space-between;
      padding: 0.7rem 0;
      border-bottom: 1px dashed #333;
    }
    .open-status {
      color: #2ecc71;
      font-weight: 600;
    }
    .address {
      margin: 1.5rem 0;
      display: flex;
      gap: 12px;
      align-items: center;
    }
    .map-link {
      margin-top: 1rem;
      display: inline-block;
      color: #e67e22;
      text-decoration: none;
      font-weight: 500;
    }

    /* footer */
    footer {
      background: #030303;
      padding: 2rem 0;
      text-align: center;
      border-top: 1px solid #e67e2240;
      color: #888;
      font-size: 0.85rem;
    }

    @media (max-width: 780px) {
      .nav-links {
        display: none;
        width: 100%;
        flex-direction: column;
        align-items: center;
        gap: 1rem;
        margin-top: 1rem;
      }
      .nav-links.active {
        display: flex;
      }
      .menu-toggle {
        display: block;
      }
      .hero-text h1 {
        font-size: 2.2rem;
      }
      .section-title {
        font-size: 1.8rem;
      }
    }
  </style>
</head>
<body>

<nav class="navbar">
  <div class="container nav-wrapper">
    <div class="logo">
      <h1>Biker's Den</h1>
      <p>বাইকার্স দেন | RIDE FREE</p>
    </div>
    <div class="menu-toggle" id="mobile-menu">
      <i class="fas fa-bars"></i>
    </div>
    <ul class="nav-links" id="nav-links">
      <li><a href="#home">Home</a></li>
      <li><a href="#gallery">Gallery</a></li>
      <li><a href="#services">Services</a></li>
      <li><a href="#info">Info & Hours</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </div>
</nav>

<main>
  <!-- Hero section -->
  <section id="home" class="hero">
    <div class="container hero-grid">
      <div class="hero-text">
        <div class="badge"><i class="fas fa-motorcycle"></i> Since 2015 • Dhaka's biker hub</div>
        <h1>Fuel Your Passion, <span>Ride with Freedom</span></h1>
        <p>Premium motorcycle gear, expert repairs, and a community that lives for the open road. Biker's Den – where every ride tells a story.</p>
        <div class="btn-group">
          <a href="#gallery" class="btn-primary"><i class="fas fa-images"></i> Explore Gallery</a>
          <a href="https://maps.app.goo.gl/BgWnEWBVtK6k2PBh8" target="_blank" class="btn-outline"><i class="fas fa-map-marker-alt"></i> Get Directions</a>
        </div>
      </div>
      <div class="hero-img">
        <img src="https://picsum.photos/id/111/600/400" alt="Biker's Den hero motorcycle" onerror="this.src='https://cdn.pixabay.com/photo/2020/05/27/20/22/motorcycle-5229053_1280.jpg'">
      </div>
    </div>
  </section>

  <!-- GALLERY SECTION - high quality motorcycle & workshop images from internet (public domain / free sources) -->
  <section id="gallery" class="gallery">
    <div class="container">
      <h2 class="section-title center-title"><i class="fas fa-camera"></i> Our Den in Frames</h2>
      <div class="gallery-grid" id="galleryGrid">
        <!-- dynamic gallery will be injected via JS with high-res moto images -->
      </div>
    </div>
  </section>

  <!-- Services Section -->
  <section id="services" class="services">
    <div class="container">
      <h2 class="section-title center-title"><i class="fas fa-wrench"></i> What We Offer</h2>
      <div class="cards">
        <div class="card"><i class="fas fa-tools"></i><h3>Full Workshop</h3><p>Engine rebuilds, custom tuning, and quick pit stops.</p></div>
        <div class="card"><i class="fas fa-helmet-safety"></i><h3>Premium Gear</h3><p>Helmets, jackets, gloves – certified protection.</p></div>
        <div class="card"><i class="fas fa-hand-sparkles"></i><h3>Detailing & Ceramic</h3><p>Keep your machine looking showroom fresh.</p></div>
        <div class="card"><i class="fas fa-users"></i><h3>Rider Community</h3><p>Weekly meetups, group rides, and events.</p></div>
      </div>
    </div>
  </section>

  <!-- Info & Hours / Map embedded -->
  <section id="info" class="info-section">
    <div class="container info-flex">
      <div class="hours-card">
        <h3><i class="far fa-clock"></i> Opening Hours</h3>
        <ul class="hours-list">
          <li><span>Monday - Friday</span> <span>10:00 AM – 10:00 PM</span></li>
          <li><span>Saturday</span> <span>10:00 AM – 10:00 PM</span></li>
          <li><span>Sunday</span> <span><strong class="open-status">10:00 AM – 10:00 PM</strong></span></li>
        </ul>
        <p style="margin-top: 1rem;"><i class="fas fa-check-circle" style="color:#2ecc71"></i> Currently <strong>OPEN</strong> until 10:00 PM (local time)</p>
        <div class="address">
          <i class="fas fa-location-dot" style="color:#e67e22"></i>
          <span>Dhaka, Bangladesh – exact location: Biker's Den, (view on map)</span>
        </div>
        <a class="map-link" href="https://maps.app.goo.gl/BgWnEWBVtK6k2PBh8" target="_blank"><i class="fas fa-external-link-alt"></i> Open in Google Maps</a>
      </div>
      <div class="contact-card">
        <h3><i class="fas fa-headset"></i> Get in Touch</h3>
        <p><i class="fas fa-phone-alt"></i> +880 1XXX-XXXXXX</p>
        <p><i class="fab fa-whatsapp"></i> +880 1XXX-XXXXXX (WhatsApp)</p>
        <p><i class="fas fa-envelope"></i> hello@bikersden.com</p>
        <div style="margin: 1.5rem 0 0;">
          <i class="fab fa-instagram"></i> @bikersden_dhaka &nbsp;&nbsp; <i class="fab fa-facebook"></i> Biker's Den BD
        </div>
        <!-- simple embedded map placeholder with directions -->
        <div style="margin-top: 1.5rem; border-radius: 20px; overflow:hidden;">
          <iframe width="100%" height="180" style="border:0; border-radius: 18px;" loading="lazy" allowfullscreen src="https://www.google.com/maps/embed/v1/place?key=AIzaSyBFw0Qbyq9zTFTd-tUY6dZWTgaQzuU17R8&q=Biker's+Den+Dhaka&center=23.8103,90.4125&zoom=15"></iframe>
          <small style="color:#aaa">📍 Approximate location – click map link for accurate spot</small>
        </div>
      </div>
    </div>
  </section>
</main>

<footer>
  <div class="container">
    <p><i class="fas fa-motorcycle"></i> Biker's Den – Where rubber meets the road. © 2025 | Ride safe, ride far.</p>
    <p style="margin-top: 8px;">Data & images inspired by the biker culture | Workshop & gear specialists</p>
  </div>
</footer>

<script>
  // High-quality curated motorcycle & workshop images from free stock (Unsplash / Pexels CDN) – all public domain / high-res
  // we are using reliable image sources that represent a biker den: bikes, workshop, gear, community
  const galleryImages = [
    { url: "https://images.pexels.com/photos/1160187/pexels-photo-1160187.jpeg?auto=compress&cs=tinysrgb&w=600", caption: "Custom cruisers at Biker's Den" },
    { url: "https://images.pexels.com/photos/116675/pexels-photo-116675.jpeg?auto=compress&cs=tinysrgb&w=600", caption: "Expert engine tuning" },
    { url: "https://images.pexels.com/photos/2759612/pexels-photo-2759612.jpeg?auto=compress&cs=tinysrgb&w=600", caption: "Premium safety gear wall" },
    { url: "https://images.pexels.com/photos/3535591/pexels-photo-3535591.jpeg?auto=compress&cs=tinysrgb&w=600", caption: "Sunday group ride meetup" },
    { url: "https://images.pexels.com/photos/1344692/pexels-photo-1344692.jpeg?auto=compress&cs=tinysrgb&w=600", caption: "Workshop diagnostics & repair" },
    { url: "https://images.pexels.com/photos/1668016/pexels-photo-1668016.jpeg?auto=compress&cs=tinysrgb&w=600", caption: "Polished chrome & details" },
    { url: "https://images.pexels.com/photos/1035108/pexels-photo-1035108.jpeg?auto=compress&cs=tinysrgb&w=600", caption: "Biker's Den lounge area" },
    { url: "https://images.pexels.com/photos/1590681/pexels-photo-1590681.jpeg?auto=compress&cs=tinysrgb&w=600", caption: "New arrivals: adventure helmets" }
  ];
  
  // backup images in case of any loading issues (alternate reliable source)
  const fallbackImages = [
    "https://cdn.pixabay.com/photo/2016/04/07/18/29/motorbike-1314059_1280.jpg",
    "https://cdn.pixabay.com/photo/2017/09/07/07/38/motorcycle-2723225_1280.jpg",
    "https://cdn.pixabay.com/photo/2019/07/22/08/48/motorcycle-4354713_1280.jpg"
  ];
  
  function renderGallery() {
    const galleryGrid = document.getElementById('galleryGrid');
    if (!galleryGrid) return;
    galleryGrid.innerHTML = '';
    galleryImages.forEach((item, idx) => {
      const colDiv = document.createElement('div');
      colDiv.className = 'gallery-item';
      const img = document.createElement('img');
      img.src = item.url;
      img.alt = item.caption;
      img.loading = 'lazy';
      // fallback if image fails to load
      img.onerror = function() {
        if (!this.dataset.fallback) {
          this.dataset.fallback = 'true';
          this.src = fallbackImages[idx % fallbackImages.length];
        }
      };
      const captionDiv = document.createElement('div');
      captionDiv.className = 'img-caption';
      captionDiv.innerHTML = `<i class="fas fa-camera-retro"></i> ${item.caption}`;
      colDiv.appendChild(img);
      colDiv.appendChild(captionDiv);
      galleryGrid.appendChild(colDiv);
    });
  }
  
  // dynamic update for hero image to show relevant biker picture (not placeholder)
  function enhanceHeroImage() {
    const heroImgElement = document.querySelector('.hero-img img');
    if (heroImgElement) {
      const motoHeroSrc = "https://images.pexels.com/photos/9830606/pexels-photo-9830606.jpeg?auto=compress&cs=tinysrgb&w=800";
      heroImgElement.src = motoHeroSrc;
      heroImgElement.onerror = function() {
        this.src = "https://cdn.pixabay.com/photo/2020/07/09/13/13/motorcycle-5387136_1280.jpg";
      };
      heroImgElement.alt = "Biker's Den flagship motorcycle";
    }
  }
  
  // mobile menu toggle
  const mobileBtn = document.getElementById('mobile-menu');
  const navLinks = document.getElementById('nav-links');
  if (mobileBtn) {
    mobileBtn.addEventListener('click', () => {
      navLinks.classList.toggle('active');
    });
  }
  
  // close mobile menu after clicking a link
  document.querySelectorAll('.nav-links a').forEach(link => {
    link.addEventListener('click', () => {
      if (navLinks.classList.contains('active')) {
        navLinks.classList.remove('active');
      }
    });
  });
  
  // simple current time based status display (dynamic open/close)
  function updateOpenStatus() {
    const statusSpan = document.querySelector('.open-status');
    if (statusSpan) {
      const now = new Date();
      const hours = now.getHours();
      const day = now.getDay(); // 0 = Sunday
      // Sunday hours 10-22, Mon-Sat 10-22 as per data
      let isOpen = false;
      if (day === 0) { // Sunday
        isOpen = (hours >= 10 && hours < 22);
      } else if (day >= 1 && day <= 6) {
        isOpen = (hours >= 10 && hours < 22);
      }
      const statusText = isOpen ? "OPEN now · closes at 10:00 PM" : "CLOSED now · opens at 10:00 AM";
      statusSpan.textContent = statusText;
      const parentLi = statusSpan.closest('li');
      if (parentLi) {
        const strongElem = parentLi.querySelector('strong');
        if (strongElem) strongElem.style.color = isOpen ? '#2ecc71' : '#e67e22';
      }
    }
  }
  
  // extra images to ensure full gallery feeling + community photos
  renderGallery();
  enhanceHeroImage();
  updateOpenStatus();
  // optionally refresh status each minute
  setInterval(updateOpenStatus, 60000);
</script>

<!-- ensure that even if external images blocked, we use fallback which are public domain -->
</body>
</html>