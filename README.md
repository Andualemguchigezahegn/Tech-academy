<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>EduForge · Online Course App</title>
  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet" />
  <style>
    /* ---------- RESET & BASE ---------- */
    *,
    *::before,
    *::after {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: #f6f8fc;
      color: #1a1a2e;
      line-height: 1.5;
    }

    .container {
      max-width: 1280px;
      margin: 0 auto;
      padding: 0 1.8rem;
    }

    img {
      max-width: 100%;
      display: block;
    }

    /* ---------- TYPOGRAPHY & UTILITY ---------- */
    .section-title {
      font-size: 2.2rem;
      font-weight: 700;
      letter-spacing: -0.02em;
      margin-bottom: 0.5rem;
    }

    .section-sub {
      color: #4a4a6a;
      max-width: 620px;
      margin: 0 auto 2.5rem auto;
    }

    .text-center {
      text-align: center;
    }

    .badge {
      background: #6c5ce7;
      color: #fff;
      font-size: 0.75rem;
      font-weight: 600;
      padding: 0.2rem 1rem;
      border-radius: 40px;
      display: inline-block;
      letter-spacing: 0.3px;
    }

    /* ---------- BUTTONS ---------- */
    .btn {
      display: inline-block;
      font-weight: 600;
      font-size: 1rem;
      padding: 0.7rem 1.8rem;
      border-radius: 60px;
      text-decoration: none;
      transition: all 0.2s ease;
      border: none;
      cursor: pointer;
    }

    .btn-primary {
      background: #6c5ce7;
      color: #fff;
      box-shadow: 0 6px 16px rgba(108, 92, 231, 0.25);
    }

    .btn-primary:hover {
      background: #5a4bd1;
      transform: translateY(-2px);
      box-shadow: 0 10px 24px rgba(108, 92, 231, 0.35);
    }

    .btn-outline {
      background: transparent;
      color: #1e1e2f;
      border: 2px solid #d0d0dd;
    }

    .btn-outline:hover {
      border-color: #6c5ce7;
      color: #6c5ce7;
      background: rgba(108, 92, 231, 0.04);
    }

    .btn-small {
      padding: 0.4rem 1.2rem;
      font-size: 0.85rem;
    }

    /* ---------- NAVBAR ---------- */
    .navbar {
      padding: 1rem 0;
      background: rgba(255, 255, 255, 0.85);
      backdrop-filter: blur(8px);
      border-bottom: 1px solid rgba(0, 0, 0, 0.04);
      position: sticky;
      top: 0;
      z-index: 50;
    }

    .navbar .container {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      font-size: 1.7rem;
      font-weight: 800;
      letter-spacing: -0.02em;
      color: #1a1a2e;
    }

    .logo span {
      color: #6c5ce7;
    }

    .nav-menu {
      display: flex;
      gap: 2rem;
      list-style: none;
      font-weight: 500;
    }

    .nav-menu a {
      text-decoration: none;
      color: #2d2d44;
      transition: color 0.2s;
      font-size: 0.95rem;
    }

    .nav-menu a:hover {
      color: #6c5ce7;
    }

    .nav-cta {
      background: #6c5ce7;
      color: #fff !important;
      padding: 0.5rem 1.5rem;
      border-radius: 40px;
      font-weight: 600;
      transition: background 0.2s, transform 0.15s;
    }

    .nav-cta:hover {
      background: #5a4bd1 !important;
      transform: scale(1.02);
    }

    .menu-toggle {
      display: none;
      flex-direction: column;
      gap: 6px;
      background: transparent;
      border: none;
      cursor: pointer;
    }

    .menu-toggle span {
      width: 28px;
      height: 3px;
      background: #1a1a2e;
      border-radius: 4px;
      transition: 0.2s;
    }

    /* ---------- HERO ---------- */
    .hero {
      padding: 3.5rem 0 2.5rem 0;
    }

    .hero-grid {
      display: flex;
      align-items: center;
      gap: 3rem;
      flex-wrap: wrap;
    }

    .hero-content {
      flex: 1 1 48%;
    }

    .hero-content h1 {
      font-size: 3.2rem;
      font-weight: 800;
      letter-spacing: -0.03em;
      line-height: 1.15;
      margin-bottom: 1.2rem;
    }

    .hero-content h1 .highlight {
      background: linear-gradient(145deg, #6c5ce7, #a29bfe);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .hero-content p {
      font-size: 1.2rem;
      color: #4a4a6a;
      max-width: 480px;
      margin-bottom: 2rem;
    }

    .hero-buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
    }

    .hero-image {
      flex: 1 1 44%;
      background: linear-gradient(135deg, #e8e4f8, #d5cff0);
      border-radius: 40px;
      padding: 1.8rem;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 240px;
      box-shadow: 0 20px 40px -12px rgba(0, 0, 0, 0.06);
    }

    .hero-image svg {
      width: 100%;
      max-width: 400px;
      height: auto;
    }

    /* ---------- COURSES SECTION ---------- */
    .courses {
      padding: 3.5rem 0 4.5rem 0;
      background: #ffffff;
    }

    .course-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 2.5rem;
      margin-top: 1.5rem;
    }

    .course-card {
      background: #f6f5fc;
      border-radius: 32px;
      padding: 1.8rem 1.8rem 2rem;
      transition: all 0.25s ease;
      border: 1px solid transparent;
      display: flex;
      flex-direction: column;
    }

    .course-card:hover {
      background: #ffffff;
      border-color: #d5cff0;
      transform: translateY(-6px);
      box-shadow: 0 16px 32px -12px rgba(108, 92, 231, 0.14);
    }

    .course-icon {
      font-size: 2.6rem;
      margin-bottom: 0.4rem;
    }

    .course-card h3 {
      font-weight: 700;
      font-size: 1.5rem;
      margin-bottom: 0.25rem;
    }

    .course-card .meta {
      display: flex;
      gap: 1rem;
      font-size: 0.85rem;
      color: #4a4a6a;
      margin: 0.5rem 0 0.8rem 0;
      flex-wrap: wrap;
    }

    .course-card .meta span {
      background: #eae6f7;
      padding: 0.15rem 0.8rem;
      border-radius: 40px;
    }

    .course-card p {
      color: #3d3d5c;
      margin-bottom: 1.2rem;
      flex: 1;
    }

    .course-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 0.6rem;
      margin-top: 0.2rem;
    }

    .course-actions .btn {
      font-size: 0.85rem;
      padding: 0.45rem 1.2rem;
    }

    .exam-tag {
      background: #ffd966;
      color: #1e1e2f;
      font-weight: 600;
      font-size: 0.7rem;
      padding: 0.2rem 0.9rem;
      border-radius: 30px;
      display: inline-block;
      margin-right: 0.3rem;
    }

    .video-badge {
      background: #d4d0f0;
      color: #1e1e2f;
      font-weight: 600;
      font-size: 0.7rem;
      padding: 0.2rem 0.9rem;
      border-radius: 30px;
      display: inline-block;
    }

    /* ---------- TESTIMONIALS ---------- */
    .testimonials {
      padding: 4rem 0 5rem 0;
      background: #f6f8fc;
    }

    .testimonial-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 2rem;
    }

    .testimonial-card {
      background: #ffffff;
      padding: 1.8rem 1.8rem;
      border-radius: 28px;
      box-shadow: 0 8px 24px rgba(0, 0, 0, 0.02);
      transition: all 0.2s ease;
      border: 1px solid #efedf9;
    }

    .testimonial-card:hover {
      border-color: #c8bff0;
      box-shadow: 0 12px 32px rgba(108, 92, 231, 0.08);
    }

    .testimonial-card .stars {
      color: #f1c40f;
      letter-spacing: 2px;
      font-size: 1.1rem;
      margin-bottom: 0.5rem;
    }

    .testimonial-card blockquote {
      font-style: italic;
      color: #2d2d44;
      margin-bottom: 1rem;
    }

    .testimonial-card .author {
      display: flex;
      align-items: center;
      gap: 0.8rem;
    }

    .testimonial-card .avatar {
      width: 44px;
      height: 44px;
      background: #6c5ce7;
      border-radius: 50%;
      color: #fff;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 700;
    }

    .testimonial-card .author-info strong {
      display: block;
      font-weight: 700;
    }

    .testimonial-card .author-info span {
      font-size: 0.8rem;
      color: #5f5f7a;
    }

    /* ---------- FOOTER ---------- */
    .footer {
      background: #1a1a2e;
      color: #cdcde0;
      padding: 3rem 0 2rem 0;
    }

    .footer .container {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      gap: 2rem;
    }

    .footer-brand .logo {
      color: #fff;
      margin-bottom: 0.3rem;
    }

    .footer-brand p {
      font-size: 0.95rem;
      max-width: 280px;
      color: #a5a5bf;
    }

    .footer-links {
      display: flex;
      gap: 3rem;
      flex-wrap: wrap;
    }

    .footer-links h4 {
      color: #fff;
      font-weight: 600;
      margin-bottom: 0.8rem;
    }

    .footer-links ul {
      list-style: none;
    }

    .footer-links li {
      margin-bottom: 0.3rem;
    }

    .footer-links a {
      color: #b0b0cc;
      text-decoration: none;
      transition: color 0.2s;
      font-size: 0.95rem;
    }

    .footer-links a:hover {
      color: #b8abff;
    }

    .footer-bottom {
      border-top: 1px solid #2b2b44;
      padding-top: 2rem;
      margin-top: 2.5rem;
      text-align: center;
      font-size: 0.9rem;
      color: #7a7a9a;
      flex-basis: 100%;
    }

    /* ---------- RESPONSIVE ---------- */
    @media screen and (max-width: 768px) {
      .menu-toggle {
        display: flex;
      }

      .nav-menu {
        position: absolute;
        top: 100%;
        left: 0;
        right: 0;
        background: rgba(255, 255, 255, 0.98);
        backdrop-filter: blur(8px);
        flex-direction: column;
        padding: 1.8rem 1.5rem;
        gap: 1.2rem;
        display: none;
        border-bottom: 1px solid #eaeaf2;
        box-shadow: 0 16px 32px -8px rgba(0, 0, 0, 0.04);
        text-align: center;
      }

      .nav-menu.open {
        display: flex;
      }

      .nav-cta {
        align-self: center;
      }

      .hero-grid {
        flex-direction: column;
        text-align: center;
      }

      .hero-content h1 {
        font-size: 2.5rem;
      }

      .hero-content p {
        margin-left: auto;
        margin-right: auto;
      }

      .hero-buttons {
        justify-content: center;
      }

      .hero-image {
        min-height: 180px;
      }

      .section-title {
        font-size: 1.9rem;
      }

      .course-grid {
        grid-template-columns: 1fr;
      }

      .testimonial-grid {
        grid-template-columns: 1fr;
      }

      .footer .container {
        flex-direction: column;
        align-items: center;
        text-align: center;
      }

      .footer-links {
        justify-content: center;
      }
    }

    @media screen and (max-width: 480px) {
      .hero-content h1 {
        font-size: 2rem;
      }

      .btn {
        width: 100%;
        text-align: center;
      }

      .hero-buttons {
        flex-direction: column;
        align-items: center;
      }

      .course-actions .btn {
        width: auto;
      }
    }

    /* mobile toggle animation */
    .menu-toggle.active span:nth-child(1) {
      transform: rotate(45deg) translate(5px, 5px);
    }
    .menu-toggle.active span:nth-child(2) {
      opacity: 0;
    }
    .menu-toggle.active span:nth-child(3) {
      transform: rotate(-45deg) translate(5px, -5px);
    }
  </style>
</head>
<body>

  <!-- ========== NAVBAR ========== -->
  <nav class="navbar">
    <div class="container">
      <div class="logo">Edu<span>Forge</span></div>
      <button class="menu-toggle" id="menuToggle" aria-label="Toggle menu">
        <span></span><span></span><span></span>
      </button>
      <ul class="nav-menu" id="navMenu">
        <li><a href="#courses">Courses</a></li>
        <li><a href="#testimonials">Testimonials</a></li>
        <li><a href="#" class="nav-cta">Enroll Now</a></li>
      </ul>
    </div>
  </nav>

  <!-- ========== HERO ========== -->
  <section class="hero">
    <div class="container hero-grid">
      <div class="hero-content">
        <h1>Level up with <span class="highlight">expert-led</span> courses</h1>
        <p>Python, C++, OOP — each course includes video lessons, practice exams, and real projects.</p>
        <div class="hero-buttons">
          <a href="#courses" class="btn btn-primary">Browse Courses</a>
          <a href="#" class="btn btn-outline">Learn More</a>
        </div>
      </div>
      <div class="hero-image">
        <svg viewBox="0 0 400 240" fill="none" xmlns="http://www.w3.org/2000/svg">
          <rect x="30" y="20" width="340" height="200" rx="36" fill="#E0D9F5" />
          <circle cx="120" cy="100" r="44" fill="#6C5CE7" opacity="0.12" />
          <circle cx="120" cy="100" r="28" fill="#6C5CE7" opacity="0.25" />
          <circle cx="120" cy="100" r="14" fill="#6C5CE7" />
          <rect x="180" y="70" width="150" height="16" rx="8" fill="#6C5CE7" opacity="0.3" />
          <rect x="180" y="100" width="120" height="14" rx="7" fill="#6C5CE7" opacity="0.2" />
          <rect x="180" y="130" width="140" height="14" rx="7" fill="#6C5CE7" opacity="0.2" />
          <path d="M70 190 L330 190 L310 210 L90 210 L70 190Z" fill="#6C5CE7" opacity="0.2" />
          <text x="100" y="180" font-size="18" font-weight="600" fill="#1e1e2f" opacity="0.7">📘 3 courses</text>
          <text x="230" y="180" font-size="16" fill="#4a4a6a">+ exams</text>
        </svg>
      </div>
    </div>
  </section>

  <!-- ========== COURSES ========== -->
  <section class="courses" id="courses">
    <div class="container">
      <div class="text-center">
        <h2 class="section-title">🎓 Our course collection</h2>
        <p class="section-sub">Pick your track — each course includes video modules, practice exams, and a certificate.</p>
      </div>
      <div class="course-grid">
        <!-- Course 1: Python -->
        <div class="course-card">
          <div class="course-icon">🐍</div>
          <h3>Python Training</h3>
          <div class="meta">
            <span>📹 12 videos</span>
            <span>⏳ 8h 20m</span>
          </div>
          <p>From syntax to data science — build real‑world projects with Python.</p>
          <div style="margin-bottom: 0.8rem;">
            <span class="exam-tag">📝 Exam included</span>
            <span class="video-badge">▶️ Video lessons</span>
          </div>
          <div class="course-actions">
            <a href="#" class="btn btn-primary btn-small">Start Course</a>
            <a href="#" class="btn btn-outline btn-small">Exam</a>
          </div>
        </div>

        <!-- Course 2: C++ -->
        <div class="course-card">
          <div class="course-icon">⚙️</div>
          <h3>C++ Programming</h3>
          <div class="meta">
            <span>📹 14 videos</span>
            <span>⏳ 10h 15m</span>
          </div>
          <p>Master pointers, memory management, and STL — write high‑performance code.</p>
          <div style="margin-bottom: 0.8rem;">
            <span class="exam-tag">📝 Exam included</span>
            <span class="video-badge">▶️ Video lessons</span>
          </div>
          <div class="course-actions">
            <a href="#" class="btn btn-primary btn-small">Start Course</a>
            <a href="#" class="btn btn-outline btn-small">Exam</a>
          </div>
        </div>

        <!-- Course 3: OOP -->
        <div class="course-card">
          <div class="course-icon">🧩</div>
          <h3>Object‑Oriented Programming</h3>
          <div class="meta">
            <span>📹 10 videos</span>
            <span>⏳ 7h 45m</span>
          </div>
          <p>Encapsulation, inheritance, polymorphism — design robust systems with OOP.</p>
          <div style="margin-bottom: 0.8rem;">
            <span class="exam-tag">📝 Exam included</span>
            <span class="video-badge">▶️ Video lessons</span>
          </div>
          <div class="course-actions">
            <a href="#" class="btn btn-primary btn-small">Start Course</a>
            <a href="#" class="btn btn-outline btn-small">Exam</a>
          </div>
        </div>
      </div>
      <!-- extra note: all courses have video + exam -->
      <div style="text-align: center; margin-top: 2.5rem; font-size: 0.95rem; color: #4a4a6a;">
        ⚡ Each course includes <strong>video modules</strong> and a <strong>final exam</strong> to test your skills.
      </div>
    </div>
  </section>

  <!-- ========== TESTIMONIALS ========== -->
  <section class="testimonials" id="testimonials">
    <div class="container">
      <div class="text-center">
        <h2 class="section-title">What learners say</h2>
        <p class="section-sub">Real feedback from students who took our courses.</p>
      </div>
      <div class="testimonial-grid">
        <div class="testimonial-card">
          <div class="stars">⭐⭐⭐⭐⭐</div>
          <blockquote>“The Python course gave me the confidence to build my own apps. Exam was challenging but fair.”</blockquote>
          <div class="author">
            <div class="avatar">AK</div>
            <div class="author-info"><strong>Alex K.</strong><span>Python Dev</span></div>
          </div>
        </div>
        <div class="testimonial-card">
          <div class="stars">⭐⭐⭐⭐⭐</div>
          <blockquote>“C++ was tough but the video breakdowns made it click. I aced the exam!”</blockquote>
          <div class="author">
            <div class="avatar">SR</div>
            <div class="author-info"><strong>Sam R.</strong><span>Game dev</span></div>
          </div>
        </div>
        <div class="testimonial-card">
          <div class="stars">⭐⭐⭐⭐⭐</div>
          <blockquote>“OOP finally makes sense. The real‑world examples and exam prep were top‑notch.”</blockquote>
          <div class="author">
            <div class="avatar">LM</div>
            <div class="author-info"><strong>Lin M.</strong><span>Software Eng.</span></div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ========== FOOTER ========== -->
  <footer class="footer">
    <div class="container">
      <div class="footer-brand">
        <div class="logo">Edu<span>Forge</span></div>
        <p>Learn anytime, anywhere. Courses with video, exams, and certificates.</p>
      </div>
      <div class="footer-links">
        <div>
          <h4>Courses</h4>
          <ul>
            <li><a href="#">Python</a></li>
            <li><a href="#">C++</a></li>
            <li><a href="#">OOP</a></li>
          </ul>
        </div>
        <div>
          <h4>Company</h4>
          <ul>
            <li><a href="#">About</a></li>
            <li><a href="#">Blog</a></li>
            <li><a href="#">Careers</a></li>
          </ul>
        </div>
        <div>
          <h4>Support</h4>
          <ul>
            <li><a href="#">Help Center</a></li>
            <li><a href="#">Terms</a></li>
            <li><a href="#">Privacy</a></li>
          </ul>
        </div>
      </div>
      <div class="footer-bottom">
        &copy; 2026 EduForge. All rights reserved.
      </div>
    </div>
  </footer>

  <!-- mobile menu toggle -->
  <script>
    (function() {
      const toggle = document.getElementById('menuToggle');
      const menu = document.getElementById('navMenu');

      toggle.addEventListener('click', function() {
        menu.classList.toggle('open');
        toggle.classList.toggle('active');
      });

      menu.querySelectorAll('a').forEach(link => {
        link.addEventListener('click', () => {
          menu.classList.remove('open');
          toggle.classList.remove('active');
        });
      });
    })();
  </script>
</body>
</html>
