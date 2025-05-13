# Final Project and Deployment

## Objectives
Build a fully functional web application.
Apply HTML, CSS, and JavaScript concepts learned.
Deploy the project using GitHub Pages, Netlify, or Vercel.

## Instructions
Choose one of the following project ideas:
Blog Website: Implement a multi-page site with navigation.
Ecommerce Website: Implement a multi-page site with navigation.

>[!NOTE]
> - Include at least:
> - A responsive design.
> - JavaScript interactivity.
> - A deployment link.

## Tasks

Create a well-structured HTML5 document.
Use at least 5 different HTML elements.
Ensure semantic correctness.

Good luck and happy coding! 🚀💻
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TechInsights Blog</title>
    <style>
        /* CSS Reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* Variables */
        :root {
            --primary-color: #3498db;
            --secondary-color: #2c3e50;
            --text-color: #333;
            --bg-color: #f9f9f9;
            --card-bg: #ffffff;
            --header-bg: #ffffff;
            --footer-bg: #2c3e50;
            --footer-text: #ecf0f1;
        }

        /* Dark Mode Variables */
        .dark-mode {
            --primary-color: #3498db;
            --secondary-color: #34495e;
            --text-color: #ecf0f1;
            --bg-color: #1a1a1a;
            --card-bg: #2c2c2c;
            --header-bg: #2c2c2c;
            --footer-bg: #34495e;
            --footer-text: #ecf0f1;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            background-color: var(--bg-color);
            transition: background-color 0.3s ease, color 0.3s ease;
        }

        a {
            text-decoration: none;
            color: var(--primary-color);
        }

        /* Header Styles */
        header {
            background-color: var(--header-bg);
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
            transition: background-color 0.3s ease;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 5%;
            max-width: 1200px;
            margin: 0 auto;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-color);
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 2rem;
        }

        .nav-links a {
            color: var(--text-color);
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--primary-color);
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--text-color);
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
            padding: 5rem 5%;
            text-align: center;
        }

        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
        }

        .search-container {
            max-width: 500px;
            margin: 0 auto;
            position: relative;
        }

        .search-input {
            width: 100%;
            padding: 0.8rem 1rem;
            border-radius: 30px;
            border: none;
            font-size: 1rem;
        }

        .search-results {
            position: absolute;
            top: 100%;
            left: 0;
            right: 0;
            background: var(--card-bg);
            border-radius: 5px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            margin-top: 0.5rem;
            display: none;
            max-height: 300px;
            overflow-y: auto;
            z-index: 10;
        }

        .search-results.active {
            display: block;
        }

        .search-result-item {
            padding: 0.8rem 1rem;
            cursor: pointer;
            transition: background-color 0.2s ease;
        }

        .search-result-item:hover {
            background-color: rgba(0, 0, 0, 0.05);
        }

        /* Main Content */
        main {
            max-width: 1200px;
            margin: 3rem auto;
            padding: 0 5%;
        }

        .section-title {
            font-size: 2rem;
            margin-bottom: 2rem;
            color: var(--text-color);
            position: relative;
            padding-bottom: 0.5rem;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100px;
            height: 3px;
            background-color: var(--primary-color);
        }

        /* Featured Posts */
        .featured-posts {
            margin-bottom: 4rem;
        }

        .featured-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .featured-card {
            background-color: var(--card-bg);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .featured-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        }

        .card-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .card-content {
            padding: 1.5rem;
        }

        .post-category {
            display: inline-block;
            background-color: var(--primary-color);
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 30px;
            font-size: 0.8rem;
            margin-bottom: 1rem;
        }

        .post-title {
            font-size: 1.5rem;
            margin-bottom: 0.8rem;
            color: var(--text-color);
        }

        .post-excerpt {
            margin-bottom: 1.5rem;
            color: var(--text-color);
        }

        .post-meta {
            font-size: 0.9rem;
            color: #777;
            display: flex;
            align-items: center;
        }

        .post-date {
            margin-right: 1rem;
        }

        /* Recent Posts */
        .recent-posts {
            margin-bottom: 4rem;
        }

        .post-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .post-card {
            background-color: var(--card-bg);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .post-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        }

        /* Newsletter */
        .newsletter {
            background-color: var(--card-bg);
            padding: 3rem;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }

        .newsletter h2 {
            margin-bottom: 1rem;
            color: var(--text-color);
        }

        .newsletter p {
            margin-bottom: 2rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            color: var(--text-color);
        }

        .newsletter-form {
            display: flex;
            max-width: 500px;
            margin: 0 auto;
        }

        .newsletter-input {
            flex: 1;
            padding: 0.8rem 1rem;
            border: 1px solid #ddd;
            border-radius: 5px 0 0 5px;
            font-size: 1rem;
        }

        .newsletter-btn {
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 0 1.5rem;
            border-radius: 0 5px 5px 0;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        .newsletter-btn:hover {
            background-color: #2980b9;
        }

        /* Footer */
        footer {
            background-color: var(--footer-bg);
            color: var(--footer-text);
            padding: 3rem 5%;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
        }

        .footer-logo {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
        }

        .footer-links h3 {
            margin-bottom: 1.5rem;
            font-size: 1.2rem;
        }

        .footer-links ul {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 0.8rem;
        }

        .footer-links a {
            color: var(--footer-text);
            transition: color 0.3s ease;
        }

        .footer-links a:hover {
            color: var(--primary-color);
        }

        .social-links {
            display: flex;
            gap: 1rem;
        }

        .social-links a {
            color: var(--footer-text);
            font-size: 1.5rem;
            transition: color 0.3s ease;
        }

        .social-links a:hover {
            color: var(--primary-color);
        }

        .footer-bottom {
            max-width: 1200px;
            margin: 2rem auto 0;
            padding-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            text-align: center;
        }

        /* Theme Toggle */
        .theme-toggle {
            background: none;
            border: none;
            color: var(--text-color);
            font-size: 1.2rem;
            cursor: pointer;
            margin-left: 1.5rem;
            display: flex;
            align-items: center;
        }

        /* Responsive Styles */
        @media (max-width: 768px) {
            .nav-links {
                position: fixed;
                top: 70px;
                left: 0;
                right: 0;
                background-color: var(--header-bg);
                flex-direction: column;
                align-items: center;
                padding: 2rem;
                clip-path: circle(0% at 100% 0);
                transition: clip-path 0.5s ease;
            }

            .nav-links.active {
                clip-path: circle(150% at 100% 0);
            }

            .nav-links li {
                margin: 1rem 0;
            }

            .mobile-menu-btn {
                display: block;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .newsletter {
                padding: 2rem 1rem;
            }

            .newsletter-form {
                flex-direction: column;
            }

            .newsletter-input {
                border-radius: 5px;
                margin-bottom: 1rem;
            }

            .newsletter-btn {
                border-radius: 5px;
                padding: 0.8rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <nav class="navbar">
            <a href="index.html" class="logo">TechInsights</a>
            <ul class="nav-links">
                <li><a href="index.html" class="active">Home</a></li>
                <li><a href="blog.html">Blog</a></li>
                <li><a href="about.html">About</a></li>
                <li><a href="contact.html">Contact</a></li>
            </ul>
            <button class="theme-toggle" aria-label="Toggle Dark Mode">
                🌙
            </button>
            <button class="mobile-menu-btn" aria-label="Toggle Menu">
                ☰
            </button>
        </nav>
    </header>

    <section class="hero">
        <h1>TechInsights Blog</h1>
        <p>Stay updated with the latest in technology, programming, and digital innovation</p>
        <div class="search-container">
            <input type="text" class="search-input" placeholder="Search for articles...">
            <div class="search-results">
                <!-- Search results will appear here -->
            </div>
        </div>
    </section>

    <main>
        <section class="featured-posts">
            <h2 class="section-title">Featured Posts</h2>
            <div class="featured-grid">
                <article class="featured-card">
                    <img src="/api/placeholder/800/500" alt="Web Development" class="card-img">
                    <div class="card-content">
                        <span class="post-category">Web Development</span>
                        <h3 class="post-title">The Future of Front-End Development in 2025</h3>
                        <p class="post-excerpt">Explore the latest trends and technologies shaping the future of front-end development in 2025.</p>
                        <div class="post-meta">
                            <span class="post-date">May 10, 2025</span>
                            <span class="post-author">By Alex Johnson</span>
                        </div>
                    </div>
                </article>
                <article class="featured-card">
                    <img src="/api/placeholder/800/500" alt="Artificial Intelligence" class="card-img">
                    <div class="card-content">
                        <span class="post-category">AI</span>
                        <h3 class="post-title">How AI is Transforming Software Development</h3>
                        <p class="post-excerpt">Discover how artificial intelligence is revolutionizing the way we build and maintain software applications.</p>
                        <div class="post-meta">
                            <span class="post-date">May 8, 2025</span>
                            <span class="post-author">By Sarah Chen</span>
                        </div>
                    </div>
                </article>
                <article class="featured-card">
                    <img src="/api/placeholder/800/500" alt="Cybersecurity" class="card-img">
                    <div class="card-content">
                        <span class="post-category">Security</span>
                        <h3 class="post-title">Essential Cybersecurity Practices for Developers</h3>
                        <p class="post-excerpt">Learn the most important security practices every developer should implement in their projects.</p>
                        <div class="post-meta">
                            <span class="post-date">May 5, 2025</span>
                            <span class="post-author">By Michael Roberts</span>
                        </div>
                    </div>
                </article>
            </div>
        </section>

        <section class="recent-posts">
            <h2 class="section-title">Recent Posts</h2>
            <div class="post-grid">
                <article class="post-card">
                    <img src="/api/placeholder/800/500" alt="Cloud Computing" class="card-img">
                    <div class="card-content">
                        <span class="post-category">Cloud</span>
                        <h3 class="post-title">Optimizing Cloud Infrastructure for Performance</h3>
                        <p class="post-excerpt">Tips and strategies for improving the performance of your cloud infrastructure.</p>
                        <div class="post-meta">
                            <span class="post-date">May 3, 2025</span>
                            <span class="post-author">By David Kim</span>
                        </div>
                    </div>
                </article>
                <article class="post-card">
                    <img src="/api/placeholder/800/500" alt="Mobile Development" class="card-img">
                    <div class="card-content">
                        <span class="post-category">Mobile</span>
                        <h3 class="post-title">Cross-Platform vs. Native Mobile Development</h3>
                        <p class="post-excerpt">Analyzing the pros and cons of cross-platform and native mobile development approaches.</p>
                        <div class="post-meta">
                            <span class="post-date">April 30, 2025</span>
                            <span class="post-author">By Emily Wilson</span>
                        </div>
                    </div>
                </article>
                <article class="post-card">
                    <img src="/api/placeholder/800/500" alt="DevOps" class="card-img">
                    <div class="card-content">
                        <span class="post-category">DevOps</span>
                        <h3 class="post-title">Implementing CI/CD Pipelines for Small Teams</h3>
                        <p class="post-excerpt">How small development teams can benefit from continuous integration and deployment practices.</p>
                        <div class="post-meta">
                            <span class="post-date">April 28, 2025</span>
                            <span class="post-author">By Jake Martinez</span>
                        </div>
                    </div>
                </article>
            </div>
        </section>

        <section class="newsletter">
            <h2>Subscribe to Our Newsletter</h2>
            <p>Get the latest tech insights, tutorials, and news delivered directly to your inbox.</p>
            <form class="newsletter-form" id="newsletter-form">
                <input type="email" class="newsletter-input" placeholder="Enter your email address" required>
                <button type="submit" class="newsletter-btn">Subscribe</button>
            </form>
        </section>
    </main>

    <footer>
        <div class="footer-content">
            <div class="footer-links">
                <h3 class="footer-logo">TechInsights</h3>
                <p>Delivering high-quality content on technology, programming, and digital transformation.</p>
                <div class="social-links">
                    <a href="#" aria-label="Twitter">T</a>
                    <a href="#" aria-label="Facebook">F</a>
                    <a href="#" aria-label="LinkedIn">L</a>
                    <a href="#" aria-label="GitHub">G</a>
                </div>
            </div>
            <div class="footer-links">
                <h3>Navigation</h3>
                <ul>
                    <li><a href="index.html">Home</a></li>
                    <li><a href="blog.html">Blog</a></li>
                    <li><a href="about.html">About</a></li>
                    <li><a href="contact.html">Contact</a></li>
                </ul>
            </div>
            <div class="footer-links">
                <h3>Categories</h3>
                <ul>
                    <li><a href="#">Web Development</a></li>
                    <li><a href="#">Artificial Intelligence</a></li>
                    <li><a href="#">Cybersecurity</a></li>
                    <li><a href="#">Cloud Computing</a></li>
                </ul>
            </div>
            <div class="footer-links">
                <h3>Legal</h3>
                <ul>
                    <li><a href="#">Privacy Policy</a></li>
                    <li><a href="#">Terms of Service</a></li>
                    <li><a href="#">Cookie Policy</a></li>
                </ul>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2025 TechInsights Blog. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Theme Toggle Functionality
        const themeToggle = document.querySelector('.theme-toggle');
        const body = document.body;

        // Check for saved theme preference
        if (localStorage.getItem('theme') === 'dark') {
            body.classList.add('dark-mode');
            themeToggle.textContent = '☀️';
        }

        themeToggle.addEventListener('click', () => {
            body.classList.toggle('dark-mode');
            
            if (body.classList.contains('dark-mode')) {
                localStorage.setItem('theme', 'dark');
                themeToggle.textContent = '☀️';
            } else {
                localStorage.setItem('theme', 'light');
                themeToggle.textContent = '🌙';
            }
        });

        // Mobile Menu Toggle
        const mobileMenuBtn = document.querySelector('.mobile-menu-btn');
        const navLinks = document.querySelector('.nav-links');

        mobileMenuBtn.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            mobileMenuBtn.textContent = navLinks.classList.contains('active') ? '✕' : '☰';
        });

        // Search Functionality
        const searchInput = document.querySelector('.search-input');
        const searchResults = document.querySelector('.search-results');

        // Sample blog posts data
        const blogPosts = [
            { title: 'The Future of Front-End Development in 2025', category: 'Web Development' },
            { title: 'How AI is Transforming Software Development', category: 'AI' },
            { title: 'Essential Cybersecurity Practices for Developers', category: 'Security' },
            { title: 'Optimizing Cloud Infrastructure for Performance', category: 'Cloud' },
            { title: 'Cross-Platform vs. Native Mobile Development', category: 'Mobile' },
            { title: 'Implementing CI/CD Pipelines for Small Teams', category: 'DevOps' },
            { title: 'JavaScript Frameworks Comparison 2025', category: 'Web Development' },
            { title: 'Database Selection Guide for Modern Applications', category: 'Backend' }
        ];

        searchInput.addEventListener('input', () => {
            const searchTerm = searchInput.value.toLowerCase().trim();
            
            if (searchTerm.length > 2) {
                const filteredPosts = blogPosts.filter(post => 
                    post.title.toLowerCase().includes(searchTerm) || 
                    post.category.toLowerCase().includes(searchTerm)
                );
                
                displaySearchResults(filteredPosts);
            } else {
                searchResults.innerHTML = '';
                searchResults.classList.remove('active');
            }
        });

        function displaySearchResults(results) {
            searchResults.innerHTML = '';
            
            if (results.length > 0) {
                results.forEach(post => {
                    const resultItem = document.createElement('div');
                    resultItem.classList.add('search-result-item');
                    resultItem.innerHTML = `
                        <h4>${post.title}</h4>
                        <span>${post.category}</span>
                    `;
                    searchResults.appendChild(resultItem);
                    
                    resultItem.addEventListener('click', () => {
                        // For demo purposes, just clear the search
                        searchInput.value = '';
                        searchResults.classList.remove('active');
                    });
                });
                
                searchResults.classList.add('active');
            } else {
                const noResults = document.createElement('div');
                noResults.classList.add('search-result-item');
                noResults.textContent = 'No results found';
                searchResults.appendChild(noResults);
                searchResults.classList.add('active');
            }
        }

        // Newsletter Form Submission
        const newsletterForm = document.getElementById('newsletter-form');
        
        newsletterForm.addEventListener('submit', (e) => {
            e.preventDefault();
            const emailInput = newsletterForm.querySelector('.newsletter-input');
            
            if (emailInput.value) {
                // In a real application, this would send the email to a server
                alert(`Thank you for subscribing with ${emailInput.value}!`);
                emailInput.value = '';
            }
        });

        // Close search results when clicking outside
        document.addEventListener('click', (e) => {
            if (!e.target.closest('.search-container')) {
                searchResults.classList.remove('active');
            }
        });
    </script>
</body>
</html>
