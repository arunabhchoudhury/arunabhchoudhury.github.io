<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio | [Your Name]</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #2c3e50;
            --accent-color: #3498db;
            --text-color: #333;
            --bg-color: #f4f7f6;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            background-color: var(--bg-color);
            margin: 0;
        }

        header {
            background: var(--primary-color);
            color: white;
            padding: 4rem 2rem;
            text-align: center;
        }

        header h1 { margin: 0; font-size: 2.5rem; }
        header p { font-size: 1.2rem; opacity: 0.9; margin-top: 10px; }

        .container {
            max-width: 900px;
            margin: 2rem auto;
            padding: 0 2rem;
        }

        section {
            background: white;
            padding: 2rem;
            margin-bottom: 2rem;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        h2 {
            border-bottom: 2px solid var(--accent-color);
            padding-bottom: 10px;
            color: var(--primary-color);
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin-top: 1rem;
        }

        .skill-item {
            background: #eef2f3;
            padding: 10px;
            border-radius: 5px;
            text-align: center;
            font-weight: bold;
            font-size: 0.9rem;
        }

        .project-card {
            border-left: 4px solid var(--accent-color);
            padding-left: 15px;
            margin-bottom: 20px;
        }

        .project-card h3 { margin: 0; color: var(--accent-color); }

        footer {
            text-align: center;
            padding: 2rem;
            font-size: 0.9rem;
            color: #777;
        }

        .social-links a {
            color: var(--primary-color);
            font-size: 1.5rem;
            margin: 0 10px;
            text-decoration: none;
        }

        .social-links a:hover { color: var(--accent-color); }
    </style>
</head>
<body>

<header>
    <h1>[Your Name]</h1>
    <p>Computational Biologist | PhD | Researcher</p>
    <div class="social-links" style="margin-top: 20px;">
        <a href="https://github.com/[your-username]" target="_blank"><i class="fab fa-github"></i></a>
        <a href="[LinkedIn-URL]" target="_blank"><i class="fab fa-linkedin"></i></a>
        <a href="mailto:your-email@example.com"><i class="fas fa-envelope"></i></a>
    </div>
</header>

<div class="container">
    
    <section id="about">
        <h2>About Me</h2>
        <p>
            Hello! I am a researcher specializing in <strong>[Your Research Area]</strong>. 
            I recently submitted my PhD thesis focusing on <strong>[Brief Thesis Topic]</strong>. 
            My work combines computational methods with biological insights to solve 
            complex problems in <strong>[Industry/Field]</strong>.
        </p>
    </section>

    <section id="research">
        <h2>Research Focus</h2>
        <div class="project-card">
            <h3>PhD Thesis: [Thesis Title]</h3>
            <p>A brief summary of your findings, the impact of your research, and the methodologies used.</p>
        </div>
    </section>

    <section id="skills">
        <h2>Technical Skills</h2>
        <div class="skills-grid">
            <div class="skill-item">Molecular Dynamics</div>
            <div class="skill-item">Python / R</div>
            <div class="skill-item">Drug Discovery</div>
            <div class="skill-item">Machine Learning</div>
            <div class="skill-item">Transcriptomics</div>
            <div class="skill-item">Bioinformatics</div>
        </div>
    </section>

    <section id="publications">
        <h2>Selected Publications</h2>
        <ul>
            <li><strong>Author Name, et al.</strong> (2025). "Title of your amazing research paper." <em>Journal Name</em>. DOI: XXXX</li>
            <li><strong>Author Name, et al.</strong> (2024). "Another key contribution." <em>Journal Name</em>. DOI: XXXX</li>
        </ul>
    </section>

</div>

<footer>
    &copy; 2026 [Your Name] | Built with GitHub Pages
</footer>

</body>
</html>
