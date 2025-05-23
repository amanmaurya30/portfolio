<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1" />
<title>Aman Maurya - Portfolio</title>
<style>
  /* Reset & base */
  * {
    margin: 0; padding: 0; box-sizing: border-box;
  }
  body {
    font-family: 'Poppins', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: #0a192f;
    color: #ccd6f6;
    overflow-x: hidden;
    scroll-behavior: smooth;
  }
  a {
    color: #64ffda;
    text-decoration: none;
  }
  a:hover, a:focus {
    text-decoration: underline;
    outline: none;
  }
  header {
    position: fixed;
    top: 0; left: 0; width: 100%;
    background: #0a192f;
    border-bottom: 1px solid #233554;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 40px;
    z-index: 1000;
  }
  .logo {
    font-size: 1.4rem;
    font-weight: 700;
    color: #64ffda;
    user-select: none;
  }
  nav ul {
    list-style: none;
    display: flex;
    gap: 24px;
  }
  nav a {
    font-weight: 600;
    font-size: 1rem;
    color: #8892b0;
    padding: 8px;
    border-radius: 4px;
    transition: all 0.3s ease;
  }
  nav a.active,
  nav a:hover,
  nav a:focus {
    color: #64ffda;
    background: #112240;
    outline: none;
  }

  /* Sections */
  section {
    min-height: 100vh;
    padding: 120px 24px 60px;
    max-width: 1000px;
    margin: 0 auto;
  }
  h2.section-title {
    font-size: 2.5rem;
    color: #64ffda;
    margin-bottom: 20px;
    font-weight: 700;
    position: relative;
  }
  h2.section-title::after {
    content: '';
    display: block;
    width: 100px;
    height: 2px;
    background: #233554;
    margin-top: 8px;
    border-radius: 2px;
  }
  p.description {
    color: #8892b0;
    font-size: 1.1rem;
    line-height: 1.6;
    max-width: 680px;
  }
  .section-content {
    margin-top: 24px;
  }

  /* About Me flex layout with image */
  #about {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 40px;
    flex-wrap: wrap;
  }
  #about-text {
    flex: 1 1 480px;
    color: #8892b0;
    font-size: 1.1rem;
    line-height: 1.7;
  }
  #profile-image-container {
    width: 250px;
    height: 250px;
    flex-shrink: 0;
    border-radius: 50%;
    overflow: hidden;
    box-shadow: 0 0 15px 3px #64ffda80;
    position: relative;
    animation: float 4s ease-in-out infinite;
    opacity: 0;
    animation-fill-mode: forwards;
    animation-name: fadeInFloat;
    animation-delay: 0.5s;
  }
  #profile-image-container img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 50%;
    display: block;
  }

  @keyframes float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-15px); }
  }
  @keyframes fadeInFloat {
    0% {
      opacity: 0;
      transform: translateY(20px);
    }
    100% {
      opacity: 1;
      transform: translateY(0px);
    }
  }

  /* Contact info */
  #contact-info {
    margin-top: 24px;
    font-size: 1rem;
    color: #8892b0;
  }
  #contact-info a {
    color: #64ffda;
  }

  /* Experience & Other Lists */
  .job, .education, .certification {
    margin-bottom: 32px;
  }
  .job h3, .education h3, .certification h3 {
    font-weight: 700;
    color: #ccd6f6;
    font-size: 1.2rem;
    margin-bottom: 6px;
  }
  .job span, .education span, .certification span {
    font-style: italic;
    color: #8892b0;
    font-size: 0.95rem;
  }
  .job ul, .education ul, .certification ul {
    margin-top: 12px;
    list-style-type: disc;
    margin-left: 20px;
    color: #8892b0;
  }
  .job ul li, .education ul li, .certification ul li {
    margin-bottom: 8px;
  }

  /* Skills */
  .skills-list {
    list-style: none;
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
  }
  .skills-list li {
    background-color: #112240;
    color: #64ffda;
    padding: 8px 14px;
    border-radius: 20px;
    font-weight: 600;
    user-select: none;
    font-size: 0.9rem;
    box-shadow: 0 0 5px #64ffda80;
  }

  /* Footer */
  footer {
    text-align: center;
    color: #8892b0;
    padding: 24px 0;
    border-top: 1px solid #233554;
    font-size: 0.9rem;
    user-select: none;
    background: #0a192f;
  }

  /* Scroll to top button */
  #scrollToTopBtn {
    position: fixed;
    bottom: 40px;
    right: 40px;
    background: #64ffda;
    border: none;
    border-radius: 50%;
    width: 44px;
    height: 44px;
    cursor: pointer;
    box-shadow: 0 0 10px #64ffda80;
    display: none;
    align-items: center;
    justify-content: center;
    transition: background 0.3s ease;
  }
  #scrollToTopBtn:hover {
    background: #52d0bd;
  }
  #scrollToTopBtn svg {
    fill: #0a192f;
    width: 22px;
    height: 22px;
  }

  /* Responsive */
  @media (max-width: 768px) {
    header {
      padding: 14px 24px;
    }
    nav ul {
      gap: 16px;
    }
    section {
      padding: 100px 16px 40px;
    }
    #about {
      flex-direction: column;
      justify-content: center;
      align-items: center;
      gap: 25px;
      padding-top: 80px;
    }
    #profile-image-container {
      width: 180px;
      height: 180px;
      animation: float 5s ease-in-out infinite;
    }
    #about-text {
      max-width: 100%;
      text-align: center;
    }
  }
</style>
</head>
<body>

<header>
  <div class="logo" aria-label="Logo">Aman Maurya</div>
  <nav aria-label="Primary Navigation">
    <ul>
      <li><a href="#about" class="nav-link active" tabindex="0">About Me</a></li>
      <li><a href="#experience" class="nav-link" tabindex="0">Experience</a></li>
      <li><a href="#certifications" class="nav-link" tabindex="0">Certifications</a></li>
      <li><a href="#education" class="nav-link" tabindex="0">Education</a></li>
      <li><a href="#skills" class="nav-link" tabindex="0">Skills</a></li>
      <li><a href="#contact" class="nav-link" tabindex="0">Contact</a></li>
    </ul>
  </nav>
</header>

<main>
  <section id="about" tabindex="0" aria-labelledby="about-title" role="region">
    <h2 id="about-title" class="section-title">About Me</h2>
    <div id="about-text">
      <p>
        I am a passionate and motivated professional seeking a challenging role in Artificial Intelligence and Machine Learning. With a strong foundation in AI and ML concepts, I aim to leverage advanced algorithms and data-driven insights to solve complex problems. My goal is to contribute to innovative projects that push the boundaries of AI and ML technologies, driving impactful solutions across diverse industries.
      </p>
      <div id="contact-info">
        <p><strong>Mobile:</strong> <a href="tel:8924099147" aria-label="Call Aman Maurya">89240-99147</a></p>
        <p><strong>Email:</strong> <a href="mailto:amankrmaurya83@gmail.com">amankrmaurya83@gmail.com</a></p>
        <p><strong>LinkedIn:</strong> <a href="https://www.linkedin.com/in/aman-maurya-4b9563217" target="_blank" rel="noopener">aman-maurya-4b9563217</a></p>
      </div>
    </div>
    <div id="profile-image-container" aria-label="Profile picture of Aman Maurya">
      <img src="WhatsApp Image 2025-03-18 at 10.34.33_18e7092e.jpg" alt="Face photo of Aman Maurya" />
    </div>
  </section>

  <!-- ... other sections unchanged from previous version ... -->

  <section id="experience" tabindex="0" aria-labelledby="experience-title" role="region">
    <h2 id="experience-title" class="section-title">Professional Experience</h2>
    <article class="job">
      <h3>Engineer</h3>
      <span>Lohia Corp Limited | 1st Oct 2022 – 11th Aug 2023</span>
      <ul>
        <li>Reported directly to the Manufacturing Director and actively participated in strategic decision-making.</li>
        <li>Led a high-impact project aimed at reducing mould breakdowns and enhancing machine efficiency within the Mould Maintenance area.</li>
        <li>Successfully improved mould lifespan through strategic redesigns focused on durability and performance optimization.</li>
      </ul>
    </article>
    <article class="job">
      <h3>Diploma Engineer Trainee</h3>
      <span>Lohia Corp Limited | 1st Oct 2021 – 30th Sept 2022</span>
      <ul>
        <li>Collaborated with the Manufacturing Director on key projects related to Material Movement &amp; Handling and Lean Manufacturing.</li>
        <li>Designed and developed detailed drawings for mould spare parts and initiated mould design improvements for in-house production.</li>
        <li>Managed monthly consumable requirements for moulds, while actively contributing to the savings group plant for cost efficiency.</li>
      </ul>
    </article>
    <article class="job">
      <h3>Intern</h3>
      <span>Lohia Corp Limited | 2nd March 2021 – 30th Sept 2021</span>
      <ul>
        <li>Gained hands-on experience in the Moulding Shop, working closely with Injection Moulding Machines and supporting mould maintenance operations.</li>
      </ul>
    </article>
    <section id="certifications" tabindex="0" aria-labelledby="certifications-title" role="region">
        <h2 id="certifications-title" class="section-title">Certifications</h2>
        
        <article class="certification">
            <article class="certification">
              <h3>Microsoft Certified: Azure Fundamentals</h3>
              <span>Issuing Organization: 
                <svg xmlns="http://www.w3.org/2000/svg" aria-hidden="true" focusable="false" width="16" height="16" viewBox="0 0 24 24" style="vertical-align:middle; margin-right:6px;">
                  <rect width="11" height="11" fill="#F35325" x="1" y="1"/>
                  <rect width="11" height="11" fill="#81BC06" x="12" y="1"/>
                  <rect width="11" height="11" fill="#05A6F0" x="1" y="12"/>
                  <rect width="11" height="11" fill="#FFBA08" x="12" y="12"/>
                </svg>
                Microsoft
              </span><br>
              <span>Credential ID: oqmM-uSez</span><br>
              <span>Credential URL: <a href="https://www.credly.com/badges/47e8956e-628b-4372-8326-780803a83710/public_url" target="_blank" rel="noopener">View Credential</a></span><br>
              <span>Certificate Image: <a href="Screenshot 2025-04-04 224925.png" target="_blank" rel="noopener">View Certificate</a></span>
            </article>

        <article class="certification">
          <h3>Autodesk AutoCAD Certified + Siemens UG-NX (CAD)</h3>
          <span>Issuing Organization: EmaxIndia</span><br>
          <span>Credential ID: 04-EC-85232</span><br>
          <span>Credential URL: <a href="https://emaxindia.in/exampanel/student/getcertificate.php" target="_blank" rel="noopener">View Credential</a></span><br>
          <span>Certificate Image: <a href="AutoCad and UG-NX Certificate.pdf" target="_blank" rel="noopener">View Certificate</a></span>
        </article>
      </section>

  <section id="education" tabindex="0" aria-labelledby="education-title" role="region">
    <h2 id="education-title" class="section-title">Educational Qualifications</h2>
    <article class="education">
      <h3>Bachelor of Technology (CSE – Artificial Intelligence & Machine Learning)</h3>
      <span>Technocrats Institute of Technology, RGPV | 2023–2026</span>
    </article>
    <article class="education">
      <h3>Diploma in Plastic Mould Technology</h3>
      <span>CIPET, Lucknow | 2018–2021</span>
    </article>
    <article class="education">
      <h3>Higher Secondary (Math, Hindi, Physics, Chemistry, English)</h3>
      <span>U.P. Board, Allahabad | 2017–2018</span>
    </article>
    <article class="education">
      <h3>High School (Math, Science, Hindi, English, Drawing, Social Science)</h3>
      <span>U.P. Board, Allahabad | 2016–2017</span>
    </article>
  </section>

  <section id="skills" tabindex="0" aria-labelledby="skills-title" role="region">
    <h2 id="skills-title" class="section-title">Technical Skills &amp; Abilities</h2>
    <ul class="skills-list" aria-label="List of skills">
      <li>HTML</li>
      <li>CSS</li>
      <li>Basic Python</li>
      <li>AutoCAD</li>
      <li>Siemens UG-NX</li>
      <li>DraftSight</li>
      <li>SAP</li>
      <li>Power BI</li>
      <li>TABLEAU</li>
      <li>Problem Solving</li>
      <li>Team Leadership &amp; Management</li>
      <li>Data Analysis & Reporting (Excel)</li>
      <li>Technical Drawing &amp; Design</li>
    </ul>
  </section>
    <section id="contact" tabindex="0" aria-labelledby="contact-title" role="region">
      <h2 id="contact-title" class="section-title">Connect With Me</h2>
      <p style="color:#8892b0; max-width: 700px; margin-bottom: 24px;">
        I'm always open to discussing new opportunities, collaborations, or just connecting. Feel free to reach out to me through any of the methods below.
      </p>
      <div id="contact-info" style="font-size:1rem;">
        <p>📧 Email: <a href="mailto:amankrmaurya83@gmail.com">amankrmaurya83@gmail.com</a></p>
        <p>📞 Phone: <a href="tel:8924099147">89240-99147</a></p>
        <p>🔗 LinkedIn: <a href="https://www.linkedin.com/in/aman-maurya-4b9563217" target="_blank" rel="noopener">aman-maurya-4b9563217</a></p>
      </div>
    </section>
</main>

<button aria-label="Scroll to top" id="scrollToTopBtn" title="Scroll to top">
  <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" >
    <path d="M12 4l-8 8h6v8h4v-8h6z"/>
  </svg>
</button>

<script>
  // Navigation highlight on scroll and smooth scroll
  const sections = document.querySelectorAll('main section');
  const navLinks = document.querySelectorAll('nav a');
  const scrollToTopBtn = document.getElementById('scrollToTopBtn');

  function debounce(fn, delay) {
    let timer = null;
    return function(...args) {
      clearTimeout(timer);
      timer = setTimeout(() => fn.apply(this, args), delay);
    };
  }

  window.addEventListener('scroll', debounce(() => {
    const scrollY = window.pageYOffset;

    // Show scroll to top button after scrolling down 400px
    if (scrollY > 400) {
      scrollToTopBtn.style.display = 'flex';
    } else {
      scrollToTopBtn.style.display = 'none';
    }

    sections.forEach(section => {
      const sectionTop = section.offsetTop - 100;
      const sectionHeight = section.offsetHeight;
      const id = section.getAttribute('id');

      if (scrollY >= sectionTop && scrollY < sectionTop + sectionHeight) {
        navLinks.forEach(link => {
          link.classList.remove('active');
          if (link.getAttribute('href').substring(1) === id) {
            link.classList.add('active');
          }
        });
      }
    });
  }, 100));

  // Smooth scroll for navigation links
  navLinks.forEach(link => {
    link.addEventListener('click', e => {
      e.preventDefault();
      const targetId = link.getAttribute('href').substring(1);
      const targetSection = document.getElementById(targetId);
      if (targetSection) {
        window.scrollTo({
          top: targetSection.offsetTop - 70,
          behavior: 'smooth'
        });
      }
    });
  });

  // Scroll to top button event
  scrollToTopBtn.addEventListener('click', () => {
    window.scrollTo({top: 0, behavior: 'smooth'});
  });
</script>

</body>
</html>
