<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>WEB TOWN</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;800&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(120deg, #0f2027, #203a43, #2c5364);
      color: #fff;
      scroll-behavior: smooth;
    }

    nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 2rem;
      background-color: rgba(0, 0, 0, 0.8);
      position: fixed;
      width: 100%;
      top: 0;
      z-index: 1000;
      backdrop-filter: blur(10px);
      flex-wrap: wrap;
    }

    nav h1 {
      font-size: 1.8rem;
      background: linear-gradient(90deg, #00f0ff, #ff00c8);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      font-weight: 800;
    }

    .nav-links {
      display: flex;
      flex-wrap: wrap;
    }

    .nav-links a {
      margin-left: 1.5rem;
      color: #ccc;
      text-decoration: none;
      font-size: 1rem;
      transition: color 0.3s ease;
    }

    .nav-links a:hover {
      color: #00ffe7;
    }

    .logo {
      position: fixed;
      top: 100px;
      right: 30px;
      width: 80px;
      height: 80px;
      cursor: pointer;
      transition: transform 1s ease;
      z-index: 1100;
      filter: drop-shadow(0 0 8px #0ff);
    }

    .logo:hover {
      transform: rotate(360deg) scale(1.1);
    }

    header {
      height: 100vh;
      background: url('images/hero-bg.jpg') center/cover no-repeat;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 2rem;
    }

    header h2 {
      font-size: 3rem;
      background: linear-gradient(to right, #0ff, #f0f, #ff0);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    header p {
      margin-top: 1rem;
      font-size: 1.3rem;
      color: #ddd;
    }

    .section-title-wrapper {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      margin: 0 2rem;
    }

    .section-title {
      font-size: 2.2rem;
      color: #0ff;
      text-shadow: 0 0 10px #00ffe0;
    }

    .search-bar {
      margin-top: 1rem;
    }

    .search-bar input {
      padding: 0.5rem 1rem;
      border-radius: 25px;
      border: none;
      outline: none;
      font-size: 1rem;
      background-color: #111;
      color: #0ff;
      border: 1px solid #0ff;
    }

    .center-project {
      text-align: center;
      margin: 2rem 0;
    }

    .center-project a {
      font-size: 1.3rem;
      font-weight: 700;
      background: linear-gradient(145deg, rgba(255,255,255,0.1), rgba(0,255,255,0.05));
      border-radius: 20px;
      padding: 1rem 2rem;
      text-decoration: none;
      color: #00ffe7;
      border: 2px solid #00ffe7;
      display: inline-block;
      transition: all 0.3s ease;
    }

    .center-project a:hover {
      transform: rotateX(360deg);
    }

    .scroll-row-container {
      display: flex;
      flex-direction: column;
      gap: 2rem;
      overflow: hidden;
      padding: 2rem 0 5rem;
    }

    .scroll-row {
      overflow: hidden;
      white-space: nowrap;
    }

    .scroll-content {
      display: inline-flex;
      animation: scrollLeft 20s linear infinite;
    }

    .scroll-row.right .scroll-content {
      animation: scrollRight 20s linear infinite;
    }

    @keyframes scrollLeft {
      from { transform: translateX(0); }
      to { transform: translateX(-50%); }
    }

    @keyframes scrollRight {
      from { transform: translateX(-50%); }
      to { transform: translateX(0); }
    }

    .project-card {
      min-width: 200px;
      margin: 0 1rem;
      background: linear-gradient(145deg, rgba(255, 255, 255, 0.1), rgba(0, 255, 255, 0.05));
      border: 2px solid transparent;
      border-radius: 20px;
      padding: 1.5rem;
      text-align: center;
      font-weight: 600;
      font-size: 1.1rem;
      color: #00ffe7;
      transition: all 0.4s ease;
      cursor: pointer;
      position: relative;
      z-index: 1;
    }

    .project-card:hover {
      transform: scale(1.07);
      color: #fff;
      text-shadow: 0 0 10px #00ffe7;
    }

    .project-card::before {
      content: "";
      position: absolute;
      top: -2px; left: -2px; right: -2px; bottom: -2px;
      background: linear-gradient(120deg, #00f0ff, #ff00c8, #f0f, #00f0ff);
      z-index: -1;
      filter: blur(8px);
      opacity: 0;
      transition: opacity 0.3s ease;
      border-radius: 20px;
    }

    .project-card:hover::before {
      opacity: 1;
    }

    .creators {
      background: #1a1a3d;
      text-align: center;
      padding: 5rem 2rem;
    }

    .creator {
      display: inline-block;
      margin: 1.5rem;
      transition: transform 0.3s ease;
    }

    .creator:hover {
      transform: scale(1.05);
    }

    .creator img {
      width: 150px;
      height: 150px;
      border-radius: 50%;
      border: 3px solid #00f0ff;
      box-shadow: 0 0 15px #00f0ff;
      object-fit: cover;
    }

    .creator p {
      margin-top: 0.5rem;
      font-size: 1rem;
    }

    footer {
      background: #0a0a23;
      padding: 2rem 1rem;
      text-align: center;
      font-size: 1rem;
      color: #ccc;
    }

    footer a {
      color: #0ff;
      text-decoration: none;
    }

    footer a:hover {
      color: #fff;
      text-decoration: underline;
    }

    .social-links {
      margin-bottom: 1rem;
    }

    .social-links a {
      margin: 0 1rem;
      color: #0ff;
      text-decoration: none;
      font-weight: bold;
      transition: color 0.3s ease;
    }

    .social-links a:hover {
      color: #fff;
    }

    /* Responsive Design */
    @media (max-width: 1024px) {
      header h2 {
        font-size: 2.5rem;
      }

      .project-card {
        min-width: 160px;
        font-size: 1rem;
      }

      .nav-links a {
        font-size: 0.95rem;
      }

      .section-title {
        font-size: 1.8rem;
      }

      .logo {
        width: 60px;
        height: 60px;
      }
    }

    @media (max-width: 768px) {
      nav {
        flex-direction: column;
        align-items: flex-start;
      }

      .nav-links {
        margin-top: 0.5rem;
        flex-direction: column;
        width: 100%;
      }

      .nav-links a {
        margin: 0.5rem 0;
      }

      header h2 {
        font-size: 2rem;
      }

      header p {
        font-size: 1rem;
      }

      .scroll-content {
        flex-wrap: nowrap;
      }

      .project-card {
        min-width: 140px;
        font-size: 0.95rem;
        padding: 1rem;
      }

      .section-title-wrapper {
        flex-direction: column;
        align-items: flex-start;
        gap: 1rem;
      }

      .search-bar input {
        width: 100%;
      }
    } 
    .doubt-btn {
      position: fixed;
      bottom: 20px;
      left: 20px;
      background-color: #6a1b9a;
      color: white;
      border: none;
      padding: 12px 16px;
      border-radius: 8px;
      font-weight: bold;
      cursor: pointer;
      z-index: 1000;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }

    .doubt-form {
      display: none;
      position: fixed;
      bottom: 80px;
      right: 20px;
      background: white;
      border: 2px solid #6a1b9a;
      border-radius: 12px;
      padding: 16px;
      width: 280px;
      z-index: 1000;
      box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
    }

    .doubt-form textarea {
      width: 100%;
      height: 100px;
      margin-bottom: 10px;
      padding: 8px;
      border-radius: 6px;
      border: 1px solid #ccc;
      font-family: 'Poppins', sans-serif;
    }

    .doubt-form button {
      background-color: #6a1b9a;
      color: white;
      border: none;
      padding: 8px 12px;
      border-radius: 6px;
      cursor: pointer;
    }

    .close-btn {
      background: none;
      color: #6a1b9a;
      border: none;
      float: right;
      font-size: 18px;
      cursor: pointer;
    }
    .robot-container {
  position: fixed;
  bottom: 20px;
  right: 20px; 
  width: 200px; 
  height: 60px;
  z-index: 999;
  cursor: pointer;
  border-radius: 12px;
  overflow: hidden;
  transition: all 0.5s ease;
  background-color: #6a1b9a;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
  font-family: 'Poppins', sans-serif;
  box-shadow: 0 0 10px rgba(106, 27, 154, 0.6);
}

.robot-container:hover {
  background-color: #7c2ccf;
}

.robot-container.expanded {
  width: 66vw;
  height: 66vh;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  position: fixed;
  border-radius: 16px;
  box-shadow: 0 0 20px rgba(0,255,255,0.3);

}

    .robot-container spline-viewer {
      width: 100%;
      height: 100%;
      pointer-events: auto;
      display: none;
    }
    .robot-container spline-viewer {
  display: none;
}

.robot-container.expanded spline-viewer {
  display: block;
}
.robot-label {
  font-size: 1rem;
}

.robot-container.expanded .robot-label {
  display: none;
}
.robot-label {
  font-size: 1rem;
}

.robot-container.expanded .robot-label {
  display: none;
}




  
  </style>
</head>
<body>

<!-- NAVIGATION + LOGO -->
<nav>
  <h1>WEB TOWN</h1>
  <div class="nav-links">
    <a href="#projects">Projects</a>
    <a href="#creators">Creators</a>
    <a href="#contact">Contact</a>
  </div>
</nav>
<img src="logo.jpg" alt="Logo" class="logo" onclick="window.scrollTo({ top: 0, behavior: 'smooth' })" />

<!-- HEADER -->
<header>
  <h2 id="typed-text"></h2>
  <p>Creative Developer • Customise the design</p>
</header>

<!-- PROJECTS SECTION -->
<section id="projects">
    <div class="section-title-wrapper">
    <h2 class="section-title">Projects</h2>
    <div class="search-bar">
      <input type="text" id="searchInput" onkeyup="searchProjects()" placeholder="Search projects..." />
    </div>
  </div>

  <div class="center-project">
    <a href="https://svu-webpage.netlify.app/" target="_blank">SVU Webpage</a>
    <a href="https://curser-follow-robot.netlify.app/" target="_blank" style="margin-left: 1rem;">Curser Follow Robot</a>

  </div>

  <div class="scroll-row-container" id="projectContainer">
    <div class="scroll-row left">
      <div class="scroll-content">
        <a href="https://snake-game-slowed.netlify.app/" class="project-card" target="_blank">Snake Game</a>
        <a href="https://marks-sheet-calculation.netlify.app/" class="project-card" target="_blank">Marksheet Calculator</a>
        <a href="https://attendence-sheet-with-print.netlify.app/" class="project-card" target="_blank">Attendance Sheet</a>
        <a href="https://ai-prime-number-generator.netlify.app/" class="project-card" target="_blank">AI Prime Generator</a>
        <a href="https://to-do-list-maker-webpage.netlify.app/" class="project-card" target="_blank">To-Do List Maker</a>
      </div>
    </div>
    <div class="scroll-row right">
      <div class="scroll-content">
        <a href="https://bg-colour-change.netlify.app/" class="project-card" target="_blank">BG Color Changer</a>
        <a href="https://horizonta-scrolling-page.netlify.app/" class="project-card" target="_blank">Horizontal Scroll Page</a>
        <a href="https://vertical-scrolling.netlify.app/" class="project-card" target="_blank">Vertical Scroll Page</a>
        <a href="https://live-date-time.netlify.app/" class="project-card" target="_blank">Live Clock</a>
        <a href="https://moving-gif.netlify.app/" class="project-card" target="_blank">GIF Mover</a>
      </div>
    </div>
  </div>
<section id="creators" class="creators">
  <h2 class="section-title">Creators</h2>
  <div class="creator">
    <img src="img1.jpg" alt="Harsha" />
    <p>G Harsha Vardhan Reddy</p>
  </div>
  <div class="creator">
    <img src="img2.jpg" alt="Thanush" />
    <p>C Thanush</p>
  </div>
</section>

<!-- DOUBT FORM -->
<button class="doubt-btn" onclick="toggleDoubtForm()">Ask a Doubt</button>
<div class="doubt-form" id="doubtForm">
  <button class="close-btn" onclick="toggleDoubtForm()">×</button>
  <h4>Submit your doubt</h4>
  <textarea id="doubtText" placeholder="Type your doubt here..."></textarea>
  <button onclick="submitDoubt()">Submit</button>
</div>

<!-- FOOTER -->
<footer id="contact">
  <div class="social-links">
    <h4 style="color:blueviolet;">Follow us on</h4>
    <a href="https://www.instagram.com/webtown_design_the_furure/?igsh=MW91YTdwYzV3d3BzZA%3D%3D#" target="_blank">Instagram</a>
    <a href="https://www.youtube.com/@Webtown-2006-b3m" target="_blank">YouTube</a>
  </div>
  <h3>Contact Us</h3>
  <p>Mail To: <a href="mailto:webtown2006@gmail.com">webtown2006@gmail.com</a> | To Clarify Doubts</p>
  <p>Harsha: <a href="mailto:harshagundre2006@gmail.com">harshagundre2006@gmail.com</a> | 9032102806</p>
  <p>Thanush: <a href="mailto:thanushch06@gmail.com">thanushch06@gmail.com</a> | 7893475910</p>
  <p>© Web Town | Build With TH</p>
</footer>

<!-- SCRIPT -->
<script>
  const text = "Welcome to our website";
  const typedText = document.getElementById("typed-text");
  let i = 0;
  function typeWriter() {
    if (i < text.length) {
      typedText.innerHTML += text.charAt(i);
      i++;
      setTimeout(typeWriter, 80);
    }
  }
  typeWriter();

  function searchProjects() {
    const input = document.getElementById("searchInput").value.toLowerCase();
    const cards = document.querySelectorAll(".project-card");
    cards.forEach(card => {
      const text = card.textContent.toLowerCase();
      card.style.display = text.includes(input) ? "inline-block" : "none";
    });
  }

  function toggleDoubtForm() {
    const form = document.getElementById("doubtForm");
    form.style.display = form.style.display === "block" ? "none" : "block";
  }

  function submitDoubt() {
    const doubt = document.getElementById("doubtText").value.trim();
    if (doubt) {
      const mailtoLink = `mailto:webtown2006@gmail.com?subject=User Doubt from Website&body=${encodeURIComponent(doubt)}`;
      window.location.href = mailtoLink;
      document.getElementById("doubtText").value = "";
      toggleDoubtForm();
    } else {
      alert("Please type a doubt before submitting.");
    }
  }

  function toggleRobotSize() {
    const robot = document.getElementById('robotContainer');
    robot.classList.toggle('expanded');
  }
  function shiftRobotContent() {
  const robot = document.getElementById('robotContainer');
  robot.classList.toggle('shift-right');
  
}

</script>

<!-- ROBOT VIEWER: Spline.js -->
<script type="module" src="https://unpkg.com/@splinetool/viewer/build/spline-viewer.js"></script>
<div class="robot-wrapper">
    <div class="robot-container" id="robotContainer" onclick="toggleRobotSize()">
      <spline-viewer url="https://prod.spline.design/X4RFgK9vqUDZdQ75/scene.splinecode"></spline-viewer>
      <p class="robot-label">Click here<br>to view robot</p>

    </div>



</body>
</html>
