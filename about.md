---
layout: default
title: About
permalink: /about/
---

<div class="about-page">
    <h1>About</h1>
    
    <div class="about-content">
        <p>Welcome to my collection of technical articles and essays. This is where I share my thoughts on software engineering, technology trends, and programming practices.</p>
        
        <p>I'm passionate about writing clean, maintainable code and exploring new technologies. Through these articles, I aim to share knowledge and insights that I've gained throughout my journey as a software engineer.</p>
        
        <h2>Topics I Write About</h2>
        <ul>
            <li>Software Testing & Quality Assurance</li>
            <li>Software Architecture & Design Patterns</li>
            <li>Programming Languages & Frameworks</li>
            <li>Development Tools & Best Practices</li>
            <li>Technology Trends & Industry Insights</li>
        </ul>
        
        <h2>Get in Touch</h2>
        <p>Feel free to reach out if you have questions about any of my articles or want to discuss technology topics.</p>
        
        {% if site.github_username %}
        <p>
            <a href="https://github.com/{{ site.github_username }}" target="_blank" rel="noopener">
                GitHub
            </a>
        </p>
        {% endif %}
    </div>
</div>

<style>
.about-page {
    max-width: 700px;
}

.about-content {
    line-height: 1.8;
}

.about-content h2 {
    margin-top: 2rem;
    margin-bottom: 1rem;
    color: #1a1a1a;
}

.about-content ul {
    margin-bottom: 1.5rem;
}

.about-content li {
    margin-bottom: 0.5rem;
    color: #4a5568;
}
</style>