---
layout: home
---
<!-- This customizes the homepage -->

<section class="intro">
    <h1>{{ site.title }}</h1>
    <p class="tagline">{{ site.portfolio.tagline }}</p>
    <p>Welcome to my portfolio. I build end-to-end data solutions—from SQL and cloud analytics to machine learning and interactive dashboards—that translate complex information into clear, actionable business insights.</p>
</section>

<section class="projects">
    <h2>Featured Projects</h2>
    <div class="project-grid">
        {% for post in site.posts %}
        <article class="project-card">
            <div class="project-content">
                <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
                <p class="project-tech"><strong>Tech:</strong> {{ post.tech | array_to_sentence_string }}</p>
                <p class="project-desc">{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
                <div class="project-links">
                    <a href="{{ post.project_url }}" class="btn" target="_blank">View Case Study</a>
                    <a href="{{ post.github_url }}" class="btn btn-secondary" target="_blank">View on GitHub</a>
                </div>
            </div>
        </article>
        {% endfor %}
    </div>
</section>

<style>
/* We'll add the CSS styles directly here for now */
:root {
    --primary: #1a5276;
    --secondary: #e67e22;
    --light: #f8f9fa;
    --dark: #2c3e50;
    --gray: #95a5a6;
}
body {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    line-height: 1.7;
    max-width: 1000px;
    margin: 40px auto;
    padding: 0 20px;
    color: #333;
}
.tagline { font-size: 1.3rem; color: var(--primary); font-weight: 300; }
.projects { margin-top: 50px; }
.project-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
    margin-top: 30px;
}
.project-card {
    background: #fff;
    padding: 25px;
    border-radius: 10px;
    border-top: 5px solid var(--secondary);
    box-shadow: 0 6px 16px rgba(0,0,0,0.05);
}
.project-card h3 { margin-top: 0; color: var(--dark); }
.project-tech { color: var(--gray); font-size: 0.9em; margin: 10px 0; }
.project-desc { color: #555; margin-bottom: 20px; }
.btn {
    display: inline-block;
    background-color: var(--primary);
    color: white;
    padding: 10px 20px;
    text-decoration: none;
    border-radius: 6px;
    font-weight: 600;
    font-size: 0.9em;
    margin-right: 10px;
}
.btn:hover { background-color: var(--dark); }
.btn-secondary { background-color: var(--gray); }
</style>
