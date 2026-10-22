CSS

/* ==========================================================================
   1. CSS Variables & Design Tokens (:root)
   ========================================================================== */
:root {
  /* Brand Palette */
  --primary: #1e3a8a;          /* Deep Navy */
  --primary-hover: #172554;
  --accent: #2563eb;           /* Royal Blue */
  --accent-light: #eff6ff;
  --secondary: #0d9488;        /* Teal */
  
  /* Neutral Palette */
  --bg-page: #f8fafc;
  --surface: #ffffff;
  --text-main: #0f172a;
  --text-muted: #64748b;
  --border: #e2e8f0;

  /* Spacing Tokens */
  --space-xs: 4px;
  --space-sm: 8px;
  --space-md: 16px;
  --space-lg: 24px;
  --space-xl: 40px;

  /* Typography Tokens */
  --font-stack: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  --font-size-sm: 0.875rem;
  --font-size-base: 1rem;
  --font-size-md: 1.25rem;
  --font-size-lg: 1.75rem;
  --font-size-xl: 2.25rem;

  /* Design Assets */
  --radius: 8px;
  --shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
  --transition: 0.2s ease;
}

/* ==========================================================================
   2. Global Reset & Base Typography
   ========================================================================== */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: var(--font-stack);
  background-color: var(--bg-page);
  color: var(--text-main);
  line-height: 1.6;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

/* Grouping Selectors for Headings */
h1, h2, h3 {
  color: var(--primary);
  line-height: 1.25;
  letter-spacing: -0.02em;
}

h1 { font-size: var(--font-size-xl); margin-bottom: var(--space-md); }
h2 { font-size: var(--font-size-lg); margin-bottom: var(--space-sm); }
h3 { font-size: var(--font-size-md); margin-bottom: var(--space-xs); }

p {
  color: var(--text-muted);
  font-size: var(--font-size-base);
  margin-bottom: var(--space-md);
}

/* ==========================================================================
   3. Navigation Bar
   ========================================================================== */
header {
  background-color: var(--surface);
  border-bottom: 1px solid var(--border);
  position: sticky;
  top: 0;
  z-index: 100;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.04);
}

.nav-container {
  max-width: 1080px;
  margin: 0 auto;
  padding: var(--space-md) var(--space-lg);
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.brand-logo {
  font-size: 1.2rem;
  font-weight: 700;
  color: var(--primary);
  text-decoration: none;
}

.nav-menu {
  list-style: none;
  display: flex;
  gap: var(--space-md);
  align-items: center;
}

.nav-menu a {
  text-decoration: none;
  font-weight: 500;
  font-size: var(--font-size-sm);
  color: var(--text-muted);
  padding: var(--space-sm) var(--space-md);
  border-radius: var(--radius);
  transition: color var(--transition), background-color var(--transition);
}

.nav-menu a:hover {
  color: var(--accent);
  background-color: var(--accent-light);
}

.nav-menu a.active {
  color: var(--accent);
  font-weight: 600;
  background-color: var(--accent-light);
}

/* ==========================================================================
   4. Layout Containers, Cards & Buttons
   ========================================================================== */
.main-wrapper {
  max-width: 1080px;
  margin: var(--space-xl) auto;
  padding: 0 var(--space-lg);
  flex: 1;
  width: 100%;
}

.hero-banner {
  background: linear-gradient(135deg, #eff6ff 0%, #dbeafe 100%);
  border: 1px solid #bfdbfe;
  padding: var(--space-xl) var(--space-lg);
  border-radius: var(--radius);
  text-align: center;
  margin-bottom: var(--space-xl);
}

.lead-text {
  font-size: 1.15rem;
  color: var(--text-main);
  max-width: 650px;
  margin: 0 auto var(--space-lg) auto;
}

.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: var(--space-lg);
  margin-bottom: var(--space-xl);
}

.card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: var(--space-lg);
  box-shadow: var(--shadow);
}

/* Buttons */
.btn {
  display: inline-block;
  padding: 10px 20px;
  font-size: var(--font-size-base);
  font-weight: 600;
  border-radius: var(--radius);
  border: none;
  cursor: pointer;
  text-decoration: none;
  transition: background-color var(--transition), transform 0.1s ease;
}

.btn-primary {
  background-color: var(--accent);
  color: #ffffff;
}

.btn-primary:hover {
  background-color: var(--primary-hover);
}

/* ==========================================================================
   5. Tables Styling (Events & Leaderboard)
   ========================================================================== */
.table-card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: var(--space-lg);
  box-shadow: var(--shadow);
  overflow-x: auto;
}

table {
  width: 100%;
  border-collapse: collapse;
  text-align: left;
}

caption {
  font-size: 1.1rem;
  font-weight: 700;
  color: var(--primary);
  margin-bottom: var(--space-md);
  text-align: left;
}

th, td {
  padding: 12px 16px;
  border-bottom: 1px solid var(--border);
}

thead th {
  background-color: var(--accent-light);
  color: var(--primary);
  font-weight: 600;
}

tbody tr:hover {
  background-color: #f1f5f9;
}

tfoot td {
  font-weight: 700;
  color: var(--text-main);
  background-color: #f8fafc;
}

/* ==========================================================================
   6. Forms Styling (Registration Page)
   ========================================================================== */
.form-container {
  max-width: 580px;
  margin: 0 auto;
  background: var(--surface);
  padding: var(--space-xl) var(--space-lg);
  border-radius: var(--radius);
  border: 1px solid var(--border);
  box-shadow: var(--shadow);
}

.form-group {
  margin-bottom: var(--space-md);
}

.form-group label {
  display: block;
  font-size: var(--font-size-sm);
  font-weight: 600;
  margin-bottom: var(--space-xs);
  color: var(--text-main);
}

.form-group input,
.form-group select,
.form-group textarea {
  width: 100%;
  padding: 10px 14px;
  font-size: var(--font-size-base);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  outline: none;
  transition: border-color var(--transition), box-shadow var(--transition);
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
  border-color: var(--accent);
  box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.15);
}

/* ==========================================================================
   7. Footer
   ========================================================================== */
footer {
  background: var(--surface);
  border-top: 1px solid var(--border);
  text-align: center;
  padding: var(--space-lg);
  color: var(--text-muted);
  font-size: var(--font-size-sm);
  margin-top: auto;
}

HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Apex Coding Club — Home</title>
  <meta name="description" content="Welcome to the Apex Coding Club, fostering software engineering, hackathons, and open source collaboration.">
  <link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>💻</text></svg>">
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <header>
    <div class="nav-container">
      <a href="index.html" class="brand-logo">&lt;ApexCodingClub /&gt;</a>
      <ul class="nav-menu">
        <li><a href="index.html" class="active">Home</a></li>
        <li><a href="events.html">Events &amp; Schedule</a></li>
        <li><a href="join.html">Join Us</a></li>
      </ul>
    </div>
  </header>

  <main class="main-wrapper">
    <section class="hero-banner">
      <h1>Code, Build &amp; Innovate Together</h1>
      <p class="lead-text">
        The official student chapter for software developers, competitive coders, and open-source contributors on campus.
      </p>
      <a href="join.html" class="btn btn-primary">Become a Member</a>
    </section>

    <h2>What We Do</h2>
    <p>Explore our core club pillars focused on building industry-ready engineering skills:</p>

    <div class="card-grid">
      <article class="card">
        <h3>Weekly Hack Sessions</h3>
        <p>Collaborative coding jams solving algorithmic problems, web projects, and building real-world software together.</p>
      </article>

      <article class="card">
        <h3>Guest Tech Talks</h3>
        <p>Engineers and alumni from top tech firms share architecture practices, system designs, and career insights.</p>
      </article>

      <article class="card">
        <h3>Open Source Guild</h3>
        <p>Mentored contributions to active open-source repositories to boost portfolios and practical engineering chops.</p>
      </article>
    </div>
  </main>

  <footer>
    <p>&copy; 2026 Apex Coding Club &middot; Campus Student Organization</p>
  </footer>

</body>
</html>