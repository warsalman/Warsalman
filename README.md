<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>DevDesign Academy</title>
  <style>
    /* Reset & Base Styles */
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
    }

   body {
      background-color: #0f172a;
      color: #f8fafc;
      line-height: 1.6;
    }

   a {
      text-decoration: none;
      color: inherit;
    }

   /* Navigation */
    header {
      background-color: #1e293b;
      position: sticky;
      top: 0;
      z-index: 100;
      border-bottom: 1px solid #334155;
    }

   .nav-container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 1rem 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
   .logo {
      font-size: 1.5rem;
      font-weight: 700;
      color: #38bdf8;
    }

   .nav-links {
      display: flex;
      gap: 1.5rem;
      list-style: none;
    }

  .nav-links a:hover {
      color: #38bdf8;
      transition: color 0.2s;
    }

  /* Hero Section */
    .hero {
      text-align: center;
      padding: 5rem 1rem 3rem;
      background: radial-gradient(circle at top, #1e293b 0%, #0f172a 100%);
    }

  .hero h1 {
      font-size: 2.75rem;
      margin-bottom: 1rem;
    }

  .hero h1 span {
      color: #38bdf8;
    }

  .hero p {
      color: #94a3b8;
      font-size: 1.15rem;
      max-width: 600px;
      margin: 0 auto 2rem;
    }

  /* Course Filtering Tabs */
    .controls {
      max-width: 1200px;
      margin: 0 auto 2.5rem;
      padding: 0 1.5rem;
      display: flex;
      justify-content: center;
      gap: 1rem;
      flex-wrap: wrap;
    }

  .filter-btn {
      background: #1e293b;
      color: #94a3b8;
      border: 1px solid #334155;
      padding: 0.6rem 1.4rem;
      border-radius: 9999px;
      cursor: pointer;
      font-weight: 500;
      transition: all 0.2s ease;
    }

  .filter-btn:hover {
      background: #334155;
      color: #ffffff;
    }

  .filter-btn.active {
      background: #38bdf8;
      color: #0f172a;
      border-color: #38bdf8;
      font-weight: 600;
    }
  /* Course Grid */
    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 1.5rem 5rem;
    }

  .grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
      gap: 2rem;
    }

  .card {
      background: #1e293b;
      border-radius: 12px;
      padding: 1.75rem;
      border: 1px solid #334155;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      transition: transform 0.2s, border-color 0.2s;
    }

   .card:hover {
      transform: translateY(-4px);
      border-color: #38bdf8;
    }

  .badge {
      display: inline-block;
      font-size: 0.75rem;
      text-transform: uppercase;
      font-weight: 700;
      letter-spacing: 0.05em;
      padding: 0.25rem 0.6rem;
      border-radius: 6px;
      margin-bottom: 1rem;
      width: fit-content;
    }

   .badge-design {
      background: rgba(244, 63, 94, 0.15);
      color: #fb7185;
    }

  .badge-dev {
      background: rgba(56, 189, 248, 0.15);
      color: #38bdf8;
    }

  .card h3 {
      font-size: 1.3rem;
      margin-bottom: 0.5rem;
    }

  .card p {
      color: #94a3b8;
      font-size: 0.95rem;
      margin-bottom: 1.5rem;
    }

   .card-footer {
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-top: 1px solid #334155;
      padding-top: 1rem;
      margin-top: auto;
    }

   .price {
      font-weight: 700;
      font-size: 1.1rem;
    }

  .enroll-btn {
      background: #38bdf8;
      color: #0f172a;
      border: none;
      padding: 0.5rem 1rem;
      border-radius: 6px;
      font-weight: 600;
      cursor: pointer;
      transition: opacity 0.2s;
    }

  .enroll-btn:hover {
      opacity: 0.9;
    }
    
  /* Modal */
    .modal-overlay {
      position: fixed;
      inset: 0;
      background: rgba(0, 0, 0, 0.75);
      display: none;
      align-items: center;
      justify-content: center;
      z-index: 1000;
    }

   .modal {
      background: #1e293b;
      padding: 2rem;
      border-radius: 12px;
      max-width: 400px;
      width: 90%;
      border: 1px solid #475569;
      text-align: center;
    }

  .modal h2 {
      margin-bottom: 0.75rem;
      color: #38bdf8;
    }

  .modal p {
      color: #94a3b8;
      margin-bottom: 1.5rem;
    }

  .close-btn {
      background: #334155;
      color: #ffffff;
      border: none;
      padding: 0.5rem 1.25rem;
      border-radius: 6px;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <!-- Navigation -->
  <header>
    <div class="nav-container">
      <div class="logo">DevDesign Academy</div>
      <ul class="nav-links">
        <li><a href="#courses">Courses</a></li>
        <li><a href="#about">About</a></li>
      </ul>
    </div>
  </header>

  <!-- Hero -->
  <section class="hero">
    <h1>Master <span>Code</span> & <span>Aesthetics</span></h1>
    <p>Professional, project-driven curriculums in UI/UX web design and full-stack software development.</p>
  </section>

  <!-- Controls / Filter Tabs -->
  <div class="controls" id="courses">
    <button class="filter-btn active" data-filter="all">All Courses</button>
    <button class="filter-btn" data-filter="web-design">Web Designing</button>
    <button class="filter-btn" data-filter="software-dev">Software Development</button>
  </div>

  <!-- Course Directory -->
  <main class="container">
    <div class="grid" id="course-grid"></div>
  </main>

  <!-- Enrollment Modal -->
  <div class="modal-overlay" id="enrollModal">
    <div class="modal">
      <h2>Enrolled!</h2>
      <p id="modal-text">You have selected a course.</p>
      <button class="close-btn" id="closeModal">Close</button>
    </div>
  </div>

  <!-- JavaScript Logic -->
  <script>
    // Course catalog data
    const courses = [
      {
        id: 1,
        title: "UI/UX & Modern Web Layouts",
        category: "web-design",
        badge: "Web Design",
        description: "Learn color theory, responsive grid systems, Figma prototyping, and design systems for the modern web.",
        price: "$49"
      },
      {
        id: 2,
        title: "Full-Stack Web Engineering",
        category: "software-dev",
        badge: "Software Dev",
        description: "Master modern JavaScript, Node.js runtime, RESTful API design, and SQL/NoSQL database management.",
        price: "$89"
      },
      {
        id: 3,
        title: "Advanced CSS & Animations",
        category: "web-design",
        badge: "Web Design",
        description: "Deep dive into CSS Flexbox, Grid, transforms, keyframe animations, SVG integration, and micro-interactions.",
        price: "$39"
      },
      {
        id: 4,
        title: "Data Structures & Algorithms in JS",
        category: "software-dev",
        badge: "Software Dev",
        description: "Build a strong computer science foundation: binary trees, search algorithms, sorting, and Big-O efficiency.",
        price: "$69"
      },
      {
        id: 5,
        title: "Design Systems & Component Libraries",
        category: "web-design",
        badge: "Web Design",
        description: "Bridge design and code by building reusable token-based component libraries and accessible UI components.",
        price: "$59"
      },
      {
        id: 6,
        title: "Cloud & Backend Architecture",
        category: "software-dev",
        badge: "Software Dev",
        description: "Deploy scalable cloud services, write secure microservices, and configure CI/CD build pipelines using Docker.",
        price: "$99"
      }
    ];

    const courseGrid = document.getElementById("course-grid");
    const filterBtns = document.querySelectorAll(".filter-btn");
    const modal = document.getElementById("enrollModal");
    const modalText = document.getElementById("modal-text");
    const closeModal = document.getElementById("closeModal");

    // Render course cards dynamically
    function renderCourses(filteredCourses) {
      courseGrid.innerHTML = "";

      filteredCourses.forEach(course => {
        const card = document.createElement("article");
        card.className = "card";

        const badgeClass = course.category === "web-design" ? "badge-design" : "badge-dev";

        card.innerHTML = `
          <div>
            <span class="badge ${badgeClass}">${course.badge}</span>
            <h3>${course.title}</h3>
            <p>${course.description}</p>
          </div>
          <div class="card-footer">
            <span class="price">${course.price}</span>
            <button class="enroll-btn" onclick="handleEnroll('${course.title}')">Enroll Now</button>
          </div>
        `;

        courseGrid.appendChild(card);
      });
    }

    // Filter functionality
    filterBtns.forEach(btn => {
      btn.addEventListener("click", () => {
        filterBtns.forEach(b => b.classList.remove("active"));
        btn.classList.add("active");

        const filter = btn.dataset.filter;
        if (filter === "all") {
          renderCourses(courses);
        } else {
          const filtered = courses.filter(item => item.category === filter);
          renderCourses(filtered);
        }
      });
    });

    // Enrollment Modal triggers
    window.handleEnroll = function(courseTitle) {
      modalText.textContent = `You're enrolling in: ${courseTitle}`;
      modal.style.display = "flex";
    };

    closeModal.addEventListener("click", () => {
      modal.style.display = "none";
    });

    window.addEventListener("click", (e) => {
      if (e.target === modal) {
        modal.style.display = "none";
      }
    });

    // Initial render
    renderCourses(courses);
  </script>
</body>
</html>
