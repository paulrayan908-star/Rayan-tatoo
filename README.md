<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>SecureHire · HR platform</title>
  <!-- Font & icons -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: #f8faff;
      color: #0b1b32;
      line-height: 1.5;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 24px;
    }

    /* HEADER / NAV */
    .navbar {
      background: white;
      box-shadow: 0 4px 20px rgba(0, 20, 50, 0.04);
      position: sticky;
      top: 0;
      z-index: 50;
      backdrop-filter: blur(8px);
      background: rgba(255, 255, 255, 0.92);
    }

    .nav-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 16px 0;
    }

    .logo {
      font-size: 1.7rem;
      font-weight: 700;
      letter-spacing: -0.02em;
      color: #0b1b32;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .logo i {
      color: #2563eb;
      font-size: 1.8rem;
    }

    .nav-links {
      display: flex;
      gap: 32px;
      align-items: center;
    }

    .nav-links a {
      text-decoration: none;
      color: #1e293b;
      font-weight: 500;
      font-size: 0.95rem;
      transition: color 0.2s;
    }

    .nav-links a:hover {
      color: #2563eb;
    }

    .btn-outline {
      border: 1.5px solid #2563eb;
      background: transparent;
      color: #2563eb;
      padding: 8px 18px;
      border-radius: 40px;
      font-weight: 600;
      font-size: 0.9rem;
      cursor: pointer;
      transition: background 0.2s, color 0.2s;
    }

    .btn-outline:hover {
      background: #2563eb;
      color: white;
    }

    .btn-primary {
      background: #2563eb;
      border: none;
      color: white;
      padding: 10px 24px;
      border-radius: 40px;
      font-weight: 600;
      font-size: 0.95rem;
      cursor: pointer;
      transition: background 0.2s, transform 0.1s;
      box-shadow: 0 8px 18px -6px rgba(37, 99, 235, 0.35);
    }

    .btn-primary:hover {
      background: #1d4ed8;
    }

    .btn-primary:active {
      transform: scale(0.97);
    }

    /* HERO */
    .hero {
      padding: 48px 0 32px;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 48px;
      align-items: center;
    }

    .hero-badge {
      background: #e0e9ff;
      color: #1d4ed8;
      font-weight: 600;
      font-size: 0.8rem;
      padding: 6px 16px;
      border-radius: 40px;
      display: inline-block;
      margin-bottom: 20px;
      letter-spacing: 0.3px;
      text-transform: uppercase;
    }

    .hero h1 {
      font-size: 3.1rem;
      font-weight: 700;
      line-height: 1.2;
      letter-spacing: -0.03em;
      color: #0b1b32;
      margin-bottom: 18px;
    }

    .hero h1 span {
      color: #2563eb;
    }

    .hero p {
      font-size: 1.1rem;
      color: #475569;
      margin-bottom: 32px;
      max-width: 90%;
    }

    .fee-highlight {
      background: #f0f5ff;
      border-left: 5px solid #2563eb;
      padding: 16px 20px;
      border-radius: 12px;
      margin: 24px 0 32px;
      font-size: 0.98rem;
      color: #1e293b;
      display: flex;
      gap: 14px;
      align-items: center;
      box-shadow: 0 2px 12px rgba(0,0,0,0.02);
    }

    .fee-highlight i {
      color: #2563eb;
      font-size: 1.8rem;
    }

    .fee-highlight strong {
      font-weight: 700;
      color: #0b1b32;
    }

    .hero-stats {
      display: flex;
      gap: 32px;
      margin-top: 32px;
    }

    .stat-item h3 {
      font-size: 1.7rem;
      font-weight: 700;
      color: #0b1b32;
    }

    .stat-item p {
      font-size: 0.85rem;
      color: #64748b;
      margin-bottom: 0;
    }

    .hero-visual {
      background: linear-gradient(145deg, #eef4ff, #ffffff);
      border-radius: 32px;
      padding: 28px 24px;
      box-shadow: 0 30px 40px -20px rgba(0, 30, 80, 0.15);
      border: 1px solid rgba(37, 99, 235, 0.08);
    }

    .job-card-mini {
      background: white;
      border-radius: 18px;
      padding: 18px;
      box-shadow: 0 8px 24px -8px rgba(0,0,0,0.06);
      margin-bottom: 16px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      transition: transform 0.15s;
    }

    .job-card-mini:hover {
      transform: translateY(-2px);
    }

    .job-info {
      display: flex;
      align-items: center;
      gap: 14px;
    }

    .job-icon {
      width: 44px;
      height: 44px;
      background: #dbeafe;
      border-radius: 12px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #2563eb;
      font-size: 1.3rem;
    }

    .job-text h4 {
      font-weight: 600;
      font-size: 0.95rem;
      color: #0b1b32;
    }

    .job-text p {
      font-size: 0.8rem;
      color: #64748b;
      margin-bottom: 0;
    }

    .badge-secured {
      background: #dcfce7;
      color: #166534;
      font-size: 0.7rem;
      font-weight: 600;
      padding: 4px 10px;
      border-radius: 20px;
      display: flex;
      align-items: center;
      gap: 4px;
    }

    /* SECTION TITLES */
    .section-title {
      text-align: center;
      font-size: 2rem;
      font-weight: 700;
      color: #0b1b32;
      letter-spacing: -0.02em;
      margin-bottom: 12px;
    }

    .section-sub {
      text-align: center;
      color: #64748b;
      max-width: 600px;
      margin: 0 auto 48px;
      font-size: 1rem;
    }

    /* HOW IT WORKS */
    .how {
      padding: 72px 0 48px;
    }

    .steps-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 28px;
    }

    .step-card {
      background: white;
      border-radius: 24px;
      padding: 32px 24px;
      text-align: center;
      box-shadow: 0 8px 28px -8px rgba(0, 0, 0, 0.04);
      border: 1px solid #eef2f6;
      transition: box-shadow 0.2s, transform 0.2s;
    }

    .step-card:hover {
      box-shadow: 0 20px 30px -12px rgba(37, 99, 235, 0.12);
      transform: translateY(-4px);
    }

    .step-icon {
      width: 64px;
      height: 64px;
      background: #e0e9ff;
      border-radius: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0 auto 20px;
      color: #2563eb;
      font-size: 1.8rem;
    }

    .step-card h3 {
      font-size: 1.2rem;
      font-weight: 700;
      margin-bottom: 10px;
    }

    .step-card p {
      color: #475569;
      font-size: 0.92rem;
    }

    .step-fee {
      margin-top: 18px;
      background: #f1f6ff;
      border-radius: 40px;
      padding: 6px 12px;
      font-size: 0.8rem;
      font-weight: 600;
      color: #1d4ed8;
      display: inline-block;
    }

    /* JOB LISTINGS */
    .jobs-section {
      padding: 48px 0 64px;
    }

    .job-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 24px;
    }

    .job-card {
      background: white;
      border-radius: 24px;
      padding: 24px;
      box-shadow: 0 5px 18px rgba(0, 0, 0, 0.02);
      border: 1px solid #edf2f7;
      transition: all 0.25s;
      display: flex;
      flex-direction: column;
    }

    .job-card:hover {
      border-color: #bdd3ff;
      box-shadow: 0 20px 30px -12px rgba(37, 99, 235, 0.12);
    }

    .job-card-header {
      display: flex;
      align-items: center;
      gap: 14px;
      margin-bottom: 16px;
    }

    .company-logo {
      width: 48px;
      height: 48px;
      background: #f1f5fe;
      border-radius: 14px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.5rem;
      color: #2563eb;
    }

    .job-title {
      font-weight: 700;
      font-size: 1.1rem;
      color: #0b1b32;
    }

    .company-name {
      font-size: 0.8rem;
      color: #64748b;
      display: flex;
      align-items: center;
      gap: 4px;
    }

    .job-desc {
      color: #475569;
      font-size: 0.9rem;
      margin: 12px 0 16px;
      flex: 1;
    }

    .job-meta {
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-top: 1px solid #eef2f6;
      padding-top: 16px;
      margin-top: 8px;
    }

    .fee-tag {
      background: #fef9e7;
      color: #b45309;
      font-weight: 600;
      font-size: 0.8rem;
      padding: 4px 10px;
      border-radius: 20px;
      display: flex;
      align-items: center;
      gap: 5px;
    }

    .btn-small {
      background: #2563eb;
      color: white;
      border: none;
      border-radius: 30px;
      padding: 8px 16px;
      font-weight: 600;
      font-size: 0.8rem;
      cursor: pointer;
      transition: background 0.2s;
    }

    .btn-small:hover {
      background: #1d4ed8;
    }

    /* PAYMENT / FEE CTA */
    .fee-cta {
      background: linear-gradient(135deg, #0b1b32 0%, #152a4a 100%);
      color: white;
      border-radius: 32px;
      padding: 48px 40px;
      margin: 32px 0 64px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 28px;
    }

    .fee-cta h2 {
      font-size: 1.9rem;
      font-weight: 700;
      letter-spacing: -0.02em;
      max-width: 60%;
    }

    .fee-cta .btn-primary {
      background: white;
      color: #0b1b32;
      box-shadow: none;
      font-size: 1rem;
      padding: 14px 32px;
    }

    .fee-cta .btn-primary:hover {
      background: #eef4ff;
    }

    /* MODAL (simulated secure flow) */
    .modal-overlay {
      display: none;
      position: fixed;
      top: 0; left: 0; width: 100%; height: 100%;
      background: rgba(0, 0, 0, 0.4);
      backdrop-filter: blur(4px);
      z-index: 1000;
      align-items: center;
      justify-content: center;
      padding: 16px;
    }

    .modal-overlay.active {
      display: flex;
    }

    .modal-box {
      background: white;
      max-width: 420px;
      width: 100%;
      border-radius: 32px;
      padding: 32px 28px;
      text-align: center;
      box-shadow: 0 40px 60px -16px rgba(0,0,0,0.3);
      animation: pop 0.2s ease;
    }

    @keyframes pop {
      0% { transform: scale(0.92); opacity: 0; }
      100% { transform: scale(1); opacity: 1; }
    }

    .modal-icon {
      width: 64px;
      height: 64px;
      background: #dcfce7;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0 auto 18px;
      color: #16a34a;
      font-size: 2rem;
    }

    .modal-box h3 {
      font-size: 1.7rem;
      font-weight: 700;
      margin-bottom: 8px;
    }

    .modal-box p {
      color: #475569;
      margin-bottom: 24px;
    }

    .modal-box .btn-primary {
      width: 100%;
      padding: 14px;
    }

    /* FOOTER */
    footer {
      background: white;
      border-top: 1px solid #eef2f6;
      padding: 32px 0;
      text-align: center;
      color: #64748b;
      font-size: 0.9rem;
    }

    footer i {
      color: #2563eb;
      margin-right: 6px;
    }

    /* RESPONSIVE */
    @media (max-width: 992px) {
      .hero-grid {
        grid-template-columns: 1fr;
        gap: 32px;
      }
      .hero h1 {
        font-size: 2.6rem;
      }
      .steps-grid {
        grid-template-columns: 1fr 1fr;
      }
      .job-grid {
        grid-template-columns: 1fr 1fr;
      }
      .fee-cta h2 {
        max-width: 100%;
        font-size: 1.7rem;
      }
    }

    @media (max-width: 768px) {
      .nav-inner {
        flex-wrap: wrap;
        gap: 12px;
      }
      .nav-links {
        gap: 18px;
        flex-wrap: wrap;
      }
      .hero h1 {
        font-size: 2.2rem;
      }
      .steps-grid {
        grid-template-columns: 1fr;
      }
      .job-grid {
        grid-template-columns: 1fr;
      }
      .hero-stats {
        flex-wrap: wrap;
        gap: 20px;
      }
      .fee-cta {
        flex-direction: column;
        text-align: center;
        padding: 32px 24px;
      }
      .fee-cta h2 {
        max-width: 100%;
        font-size: 1.5rem;
      }
      .section-title {
        font-size: 1.8rem;
      }
    }

    @media (max-width: 480px) {
      .container {
        padding: 0 18px;
      }
      .logo {
        font-size: 1.3rem;
      }
      .hero h1 {
        font-size: 1.9rem;
      }
      .hero p {
        max-width: 100%;
        font-size: 1rem;
      }
      .hero-badge {
        font-size: 0.7rem;
      }
      .fee-highlight {
        flex-direction: column;
        text-align: center;
      }
      .job-meta {
        flex-direction: column;
        align-items: flex-start;
        gap: 12px;
      }
    }
  </style>
</head>
<body>
  <!-- NAVBAR -->
  <nav class="navbar">
    <div class="container nav-inner">
      <div class="logo">
        <i class="fas fa-shield-alt"></i>
        <span>SecureHire</span>
      </div>
      <div class="nav-links">
        <a href="#">Jobs</a>
        <a href="#">How it works</a>
        <a href="#">Pricing</a>
        <a href="#">For employers</a>
        <button class="btn-outline" id="navSignIn">Sign in</button>
        <button class="btn-primary" id="navGetStarted">Get started</button>
      </div>
    </div>
  </nav>

  <!-- HERO -->
  <section class="hero">
    <div class="container hero-grid">
      <div>
        <div class="hero-badge"><i class="fas fa-lock" style="margin-right:6px;"></i> Secure placement</div>
        <h1>Get hired faster with <span>guaranteed</span> job placement.</h1>
        <p>We bridge candidates and companies — pay a small fee to secure your job, breeze through interviews, and get documentation handled end‑to‑end.</p>
        <div class="fee-highlight">
          <i class="fas fa-hand-holding-usd"></i>
          <div><strong>One‑time fee $79</strong> — covers interview coaching, document verification & job securing. Only pay when you’re placed.</div>
        </div>
        <div style="display: flex; gap: 16px; flex-wrap: wrap;">
          <button class="btn-primary" id="heroSecureBtn" style="padding: 14px 36px; font-size: 1rem;">Secure a job now</button>
          <button class="btn-outline" id="heroBrowseBtn" style="padding: 14px 28px;">Browse jobs</button>
        </div>
        <div class="hero-stats">
          <div class="stat-item">
            <h3>2,400+</h3>
            <p>Placements secured</p>
          </div>
          <div class="stat-item">
            <h3>94%</h3>
            <p>Interview success</p>
          </div>
          <div class="stat-item">
            <h3>48h</h3>
            <p>Avg. documentation</p>
          </div>
        </div>
      </div>
      <div class="hero-visual">
        <div class="job-card-mini">
          <div class="job-info">
            <div class="job-icon"><i class="fas fa-code"></i></div>
            <div class="job-text">
              <h4>Frontend Developer</h4>
              <p>TechNova · Remote</p>
            </div>
          </div>
          <div class="badge-secured"><i class="fas fa-check-circle"></i> Secured</div>
        </div>
        <div class="job-card-mini">
          <div class="job-info">
            <div class="job-icon"><i class="fas fa-chart-line"></i></div>
            <div class="job-text">
              <h4>Data Analyst</h4>
              <p>FinScale · Hybrid</p>
            </div>
          </div>
          <div class="badge-secured"><i class="fas fa-check-circle"></i> Secured</div>
        </div>
        <div class="job-card-mini" style="margin-bottom:0;">
          <div class="job-info">
            <div class="job-icon"><i class="fas fa-paint-brush"></i></div>
            <div class="job-text">
              <h4>UI/UX Designer</h4>
              <p>CreativePulse · Remote</p>
            </div>
          </div>
          <div class="badge-secured"><i class="fas fa-check-circle"></i> Secured</div>
        </div>
        <div style="text-align: center; margin-top: 20px; color: #2563eb; font-weight: 500; font-size: 0.9rem;">
          <i class="fas fa-arrow-right"></i> 150+ new jobs secured this week
        </div>
      </div>
    </div>
  </section>

  <!-- HOW IT WORKS -->
  <section class="how">
    <div class="container">
      <h2 class="section-title">How SecureHire works</h2>
      <p class="section-sub">Three steps to land your next role with full support.</p>
      <div class="steps-grid">
        <div class="step-card">
          <div class="step-icon"><i class="fas fa-search"></i></div>
          <h3>1. Choose a job</h3>
          <p>Browse verified job listings from companies that are actively hiring through our platform.</p>
          <div class="step-fee">No fee to browse</div>
        </div>
        <div class="step-card">
          <div class="step-icon"><i class="fas fa-credit-card"></i></div>
          <h3>2. Pay securing fee</h3>
          <p>Pay a one‑time fee of $79 to secure the position. This unlocks interview coaching & documentation.</p>
          <div class="step-fee">$79 one‑time</div>
        </div>
        <div class="step-card">
          <div class="step-icon"><i class="fas fa-handshake"></i></div>
          <h3>3. Get placed</h3>
          <p>We fast‑track your interview and handle all documentation. You start your new job with confidence.</p>
          <div class="step-fee">Guaranteed placement</div>
        </div>
      </div>
    </div>
  </section>

  <!-- JOB LISTINGS -->
  <section class="jobs-section" id="jobListings">
    <div class="container">
      <h2 class="section-title">Featured job openings</h2>
      <p class="section-sub">Secure any of these roles — fee includes interview & documentation support.</p>
      <div class="job-grid" id="jobGrid">
        <!-- dynamically populated via JS (static fallback) -->
      </div>
    </div>
  </section>

  <!-- FEE CTA -->
  <div class="container">
    <div class="fee-cta">
      <h2>Ready to secure your next job?</h2>
      <button class="btn-primary" id="ctaSecureBtn">Secure a position · $79</button>
    </div>
  </div>

  <!-- FOOTER -->
  <footer>
    <div class="container">
      <p><i class="fas fa-shield-alt"></i> SecureHire — placement made simple. © 2025</p>
    </div>
  </footer>

  <!-- MODAL (confirmation) -->
  <div class="modal-overlay" id="modalOverlay">
    <div class="modal-box" id="modalBox">
      <div class="modal-icon" id="modalIcon"><i class="fas fa-check"></i></div>
      <h3 id="modalTitle">Job secured!</h3>
      <p id="modalMessage">Our team will contact you within 24h to start interview prep and documentation.</p>
      <button class="btn-primary" id="modalCloseBtn">Great, thanks!</button>
    </div>
  </div>

  <script>
    (function() {
      // ----- JOB DATA (static + dynamic) -----
      const jobs = [
        { title: "Frontend Developer", company: "TechNova", location: "Remote", fee: "$79", icon: "fa-code", desc: "React, TypeScript, and modern UI." },
        { title: "Data Analyst", company: "FinScale", location: "Hybrid · NY", fee: "$79", icon: "fa-chart-line", desc: "SQL, Python, dashboards." },
        { title: "UI/UX Designer", company: "CreativePulse", location: "Remote", fee: "$79", icon: "fa-paint-brush", desc: "Figma, user research, design systems." },
        { title: "DevOps Engineer", company: "CloudMatrix", location: "Remote", fee: "$79", icon: "fa-cloud", desc: "AWS, Kubernetes, CI/CD." },
        { title: "Product Manager", company: "InnovateLabs", location: "San Francisco", fee: "$79", icon: "fa-product-hunt", desc: "Roadmaps, agile, stakeholder." },
        { title: "Sales Executive", company: "GrowthPeak", location: "London", fee: "$79", icon: "fa-chart-simple", desc: "B2B sales, negotiation." }
      ];

      const jobGrid = document.getElementById('jobGrid');

      function renderJobs() {
        jobGrid.innerHTML = jobs.map(job => `
          <div class="job-card">
            <div class="job-card-header">
              <div class="company-logo"><i class="fas ${job.icon}"></i></div>
              <div>
                <div class="job-title">${job.title}</div>
                <div class="company-name"><i class="fas fa-building"></i> ${job.company} · ${job.location}</div>
              </div>
            </div>
            <p class="job-desc">${job.desc}</p>
            <div class="job-meta">
              <div class="fee-tag"><i class="fas fa-lock"></i> Secure fee ${job.fee}</div>
              <button class="btn-small secure-job-btn" data-job="${job.title}">Secure now</button>
            </div>
          </div>
        `).join('');

        // attach listeners to secure buttons
        document.querySelectorAll('.secure-job-btn').forEach(btn => {
          btn.addEventListener('click', function(e) {
            e.preventDefault();
            const jobTitle = this.getAttribute('data-job') || 'this position';
            showModal('Job secured!', `You've secured the ${jobTitle} position. Our team will email you within 24h to begin interview prep and document handling.`);
          });
        });
      }

      // ----- MODAL logic -----
      const modalOverlay = document.getElementById('modalOverlay');
      const modalTitle = document.getElementById('modalTitle');
      const modalMessage = document.getElementById('modalMessage');
      const modalIcon = document.getElementById('modalIcon');
      const modalCloseBtn = document.getElementById('modalCloseBtn');

      function showModal(title, message, isSuccess = true) {
        modalTitle.textContent = title;
        modalMessage.textContent = message;
        modalIcon.innerHTML = isSuccess ? '<i class="fas fa-check"></i>' : '<i class="fas fa-info-circle"></i>';
        modalOverlay.classList.add('active');
      }

      function hideModal() {
        modalOverlay.classList.remove('active');
      }

      modalCloseBtn.addEventListener('click', hideModal);
      modalOverlay.addEventListener('click', function(e) {
        if (e.target === modalOverlay) hideModal();
      });

      // ----- BUTTON INTERACTIONS -----
      // Hero secure button
      document.getElementById('heroSecureBtn').addEventListener('click', () => {
        showModal('Secure a job now', 'Browse jobs below and click "Secure now" on any listing. The $79 fee covers interview coaching & documentation.');
      });

      // Hero browse button -> scroll to jobs
      document.getElementById('heroBrowseBtn').addEventListener('click', () => {
        document.getElementById('jobListings').scrollIntoView({ behavior: 'smooth' });
      });

      // CTA secure button
      document.getElementById('ctaSecureBtn').addEventListener('click', () => {
        showModal('Ready to secure?', 'Choose any job from the listings and click "Secure now". Your placement fee is $79 — includes everything.');
      });

      // Nav sign in
      document.getElementById('navSignIn').addEventListener('click', () => {
        showModal('Sign in', 'Demo mode: sign‑in flow will be available soon. For now, explore jobs and secure a position.', false);
      });

      // Nav get started
      document.getElementById('navGetStarted').addEventListener('click', () => {
        document.getElementById('jobListings').scrollIntoView({ behavior: 'smooth' });
        showModal('Welcome to SecureHire', 'Pick a job below, pay the $79 fee, and we\'ll fast‑track your interview & documents.', false);
      });

      // render jobs on load
      renderJobs();

      // small extra: make all job card secure buttons visible
    })();
  </script>
</body>
</html>
