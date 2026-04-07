
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Arunabh Choudhury — Computational Biology</title>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:opsz,wght@9..40,300;9..40,400;9..40,500&display=swap" rel="stylesheet" />
    <style>
        *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

        :root {
            --serif: 'DM Serif Display', Georgia, serif;
            --sans: 'DM Sans', system-ui, sans-serif;
            --teal-900: #04342C;
            --teal-800: #085041;
            --teal-700: #0F6E56;
            --teal-600: #1D9E75;
            --teal-200: #9FE1CB;
            --teal-100: #E1F5EE;
            --text: #1a1a18;
            --text-muted: #6b6b65;
            --border: rgba(0,0,0,0.1);
            --bg: #ffffff;
            --bg2: #f7f6f2;
            --bg3: #f1f0ea;
        }

        @media (prefers-color-scheme: dark) {
            :root {
                --text: #e8e6de;
                --text-muted: #9a9890;
                --border: rgba(255,255,255,0.1);
                --bg: #1a1a18;
                --bg2: #222220;
                --bg3: #2a2a28;
                --teal-100: #04342C;
                --teal-600: #5DCAA5;
                --teal-700: #1D9E75;
            }
        }

        html { scroll-behavior: smooth; }
        body { font-family: var(--sans); color: var(--text); background: var(--bg3); line-height: 1.6; font-size: 16px; }

        .site { max-width: 900px; margin: 0 auto; padding: 0 2rem 5rem; }

        nav {
            position: sticky; top: 0; z-index: 100; background: var(--bg3);
            border-bottom: 0.5px solid var(--border); display: flex;
            justify-content: space-between; align-items: center; padding: 1rem 0; margin-bottom: 3.5rem;
        }

        .nav-logo { font-family: var(--serif); font-size: 17px; color: var(--text); text-decoration: none; }
        .nav-links { display: flex; gap: 1.75rem; list-style: none; }
        .nav-links a { font-size: 12px; color: var(--text-muted); text-decoration: none; text-transform: uppercase; letter-spacing: 0.07em; transition: 0.2s; }
        .nav-links a:hover { color: var(--teal-700); }

        .hero { display: grid; grid-template-columns: 1fr 140px; gap: 2rem; align-items: start; margin-bottom: 3.5rem; }
        .hero h1 { font-family: var(--serif); font-size: 52px; line-height: 1.05; letter-spacing: -1.5px; margin-bottom: 1.25rem; }
        .hero h1 em { font-style: italic; color: var(--teal-700); }
        .hero-bio { font-size: 15px; line-height: 1.8; color: var(--text-muted); max-width: 540px; margin-bottom: 1.75rem; }
        
        .btn-primary { background: var(--teal-700); color: #fff; padding: 10px 22px; border-radius: 6px; font-size: 13px; font-weight: 500; text-decoration: none; display: inline-block; transition: 0.2s; }
        .btn-primary:hover { background: var(--teal-800); }

        .avatar-box { width: 130px; height: 130px; border-radius: 50%; background: var(--teal-100); border: 2px solid var(--teal-200); display: flex; align-items: center; justify-content: center; }
        .avatar-initials { font-family: var(--serif); font-size: 40px; color: var(--teal-700); }

        .stats-row { display: grid; grid-template-columns: repeat(4, 1fr); gap: 1px; background: var(--border); border-radius: 14px; overflow: hidden; margin-bottom: 4rem; }
        .stat { background: var(--bg); padding: 1.5rem 1rem; text-align: center; }
        .stat-num { font-family: var(--serif); font-size: 34px; color: var(--teal-700); line-height: 1; }
        .stat-label { font-size: 12px; color: var(--text-muted); margin-top: 6px; }

        .section { margin-bottom: 4rem; }
        .section-header { display: flex; align-items: center; gap: 14px; margin-bottom: 2rem; }
        .section-label { font-size: 11px; letter-spacing: 0.12em; text-transform: uppercase; color: var(--teal-600); font-weight: 500; }
        .section-line { flex: 1; height: 0.5px; background: var(--border); }

        .pub-list { border: 0.5px solid var(--border); border-radius: 14px; overflow: hidden; }
        .pub-item { background: var(--bg); padding: 1.1rem 1.5rem; border-bottom: 0.5px solid var(--border); transition: 0.15s; }
        .pub-item:hover { background: var(--bg2); }
        .pub-meta { display: flex; align-items: center; gap: 8px; margin-bottom: 5px; font-size: 11px; font-weight: 500; color: var(--teal-600); }
        .pub-title { font-size: 14px; font-weight: 500; margin-bottom: 5px; color: var(--text); }
        .pub-authors { font-size: 12px; color: var(--text-muted); }
        .pub-authors a { color: var(--teal-700); text-decoration: none; }

        .more-pubs { display: none; }
        .more-pubs.visible { display: block; }
        .toggle-btn { width: 100%; background: var(--bg2); border: none; padding: 1rem; font-family: var(--sans); font-size: 13px; color: var(--teal-700); cursor: pointer; }

        .timeline { position: relative; padding-left: 1.75rem; border-left: 1px solid var(--border); }
        .timeline-item { margin-bottom: 2rem; position: relative; }
        .timeline-item::before { content: ''; position: absolute; left: calc(-1.75rem - 6.5px); top: 7px; width: 12px; height: 12px; border-radius: 50%; background: var(--teal-600); border: 2.5px solid var(--bg3); }

        footer { border-top: 0.5px solid var(--border); padding-top: 1.75rem; margin-top: 2rem; display: flex; justify-content: space-between; font-size: 12px; color: var(--text-muted); }

        @media (max-width: 640px) {
            .hero { grid-template-columns: 1fr; }
            .stats-row { grid-template-columns: repeat(2, 1fr); }
            .nav-links { display: none; }
        }
    </style>
</head>
<body>

<div class="site">
    <nav>
        <a href="#" class="nav-logo">Arunabh Choudhury</a>
        <ul class="nav-links">
            <li><a href="#research">Research</a></li>
            <li><a href="#publications">Publications</a></li>
            <li><a href="#education">Education</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <section class="hero">
        <div>
            <div style="font-size: 12px; color: var(--teal-600); font-weight: 600; margin-bottom: 10px; letter-spacing: 2px;">PH.D. CANDIDATE · COMPUTATIONAL BIOLOGY</div>
            <h1>Computational <em>Biology</em></h1>
            <p class="hero-bio">
                Researcher at CIRBSc, Jamia Millia Islamia, New Delhi. 
                Specializing in structure-based drug design and microsecond MD simulations to discover 
                novel therapeutics for neuroinflammatory diseases.
            </p>
            <div style="display:flex; gap:10px;">
                <a class="btn-primary" href="https://scholar.google.com/citations?user=m7P7WS0AAAAJ" target="_blank">Google Scholar ↗</a>
                <a class="btn-primary" style="background:transparent; border:1px solid var(--teal-600); color:var(--teal-700);" href="mailto:arunabhch98@gmail.com">Contact Me</a>
            </div>
        </div>
        <div class="avatar-box"><span class="avatar-initials">AC</span></div>
    </section>

    <div class="stats-row">
        <div class="stat"><div class="stat-num">30+</div><div class="stat-label">Publications</div></div>
        <div class="stat"><div class="stat-num">2026</div><div class="stat-label">Thesis Submitted</div></div>
        <div class="stat"><div class="stat-num">9.15</div><div class="stat-label">M.Sc. CGPA</div></div>
        <div class="stat"><div class="stat-num">4</div><div class="stat-label">Conferences</div></div>
    </div>

    <section class="section" id="research">
        <div class="section-header"><span class="section-label">Research Focus</span><div class="section-line"></div></div>
        <div style="background: var(--teal-100); padding: 1.5rem; border-radius: 10px; border-left: 4px solid var(--teal-600);">
            <p style="font-size: 15px; color: var(--teal-800);">
                My research integrates <strong>transcriptomics, microsecond MM/PBSA analyses, and machine learning</strong> 
                to prioritize therapeutic targets for Alzheimer’s disease and related tauopathies.
            </p>
        </div>
    </section>

    <section class="section" id="publications">
        <div class="section-header"><span class="section-label">Selected Publications</span><div class="section-line"></div></div>
        <div class="pub-list">
            <div class="pub-item">
                <div class="pub-meta">2025 · BIOTECHNOLOGY ADVANCES</div>
                <div class="pub-title">Current advancement in AI-integrated drug discovery: Methods and applications</div>
                <div class="pub-authors">Mathur Y., <strong>Choudhury A.</strong>, et al. · <a href="https://doi.org/10.1016/j.biotechadv.2025.108642" target="_blank">DOI ↗</a></div>
            </div>
            <div class="pub-item">
                <div class="pub-meta">2025 · BBRC</div>
                <div class="pub-title">Structure-guided discovery of tau-phosphorylating kinase DYRK1A inhibitors</div>
                <div class="pub-authors"><strong>Choudhury A.</strong>, Khan S., et al. · <a href="https://doi.org/10.1016/j.bbrc.2025.152166" target="_blank">DOI ↗</a></div>
            </div>
            <div class="pub-item">
                <div class="pub-meta">2025 · INT. J. BIOL. MACROMOL.</div>
                <div class="pub-title">Targeting tau hyperphosphorylation-mediated neuroinflammation... via ABL1 kinase inhibition</div>
                <div class="pub-authors"><strong>Choudhury A.</strong>, Prabha S., et al. · <a href="https://doi.org/10.1016/j.ijbiomac.2025.145785" target="_blank">DOI ↗</a></div>
            </div>

            <div class="more-pubs" id="more-pubs">
                <div class="pub-item">
                    <div class="pub-meta">2025 · SCIENTIFIC REPORTS</div>
                    <div class="pub-title">Repurposing resveratrol for redox-mediated inhibition of MTH1 in breast cancer</div>
                    <div class="pub-authors">Taiyab A., <strong>Choudhury A.</strong>, et al.</div>
                </div>
                <div class="pub-item">
                    <div class="pub-meta">2024 · BIOMEDICINE & PHARMACOTHERAPY</div>
                    <div class="pub-title">Exploring MTH1 inhibitory potential of Thymoquinone and Baicalin</div>
                    <div class="pub-authors">Taiyab A., <strong>Choudhury A.</strong>, et al.</div>
                </div>
                <div class="pub-item">
                    <div class="pub-meta">2022 · PLOS ONE</div>
                    <div class="pub-title">Comparative analysis of web-based programs for single amino acid substitutions</div>
                    <div class="pub-authors"><strong>Choudhury A.</strong>, Mohammad T., et al.</div>
                </div>
            </div>
            <button class="toggle-btn" id="toggle-btn" onclick="togglePubs()">Show all 30+ publications ↓</button>
        </div>
    </section>

    <section class="section" id="education">
        <div class="section-header"><span class="section-label">Education & Experience</span><div class="section-line"></div></div>
        <div class="timeline">
            <div class="timeline-item">
                <div style="font-size:11px; font-weight:600; color:var(--teal-600);">2022 – PRESENT</div>
                <div style="font-weight:500;">Ph.D. Biological Sciences (Thesis Submitted)</div>
                <div style="font-size:13px; color:var(--text-muted);">Centre for Interdisciplinary Research in Basic Sciences, JMI, New Delhi</div>
            </div>
            <div class="timeline-item">
                <div style="font-size:11px; font-weight:600; color:var(--teal-600);">2020 – 2022</div>
                <div style="font-weight:500;">Project Assistant</div>
                <div style="font-size:13px; color:var(--text-muted);">CIRBSc, Jamia Millia Islamia, New Delhi</div>
            </div>
            <div class="timeline-item">
                <div style="font-size:11px; font-weight:600; color:var(--teal-600);">2018 – 2020</div>
                <div style="font-weight:500;">M.Sc. Bioinformatics (CGPA 9.15/10)</div>
                <div style="font-size:13px; color:var(--text-muted);">Jamia Millia Islamia, New Delhi</div>
            </div>
        </div>
    </section>

    <footer id="contact">
        <p>© 2026 Arunabh Choudhury · arunabhch98@gmail.com</p>
        <p>CIRBSc, Jamia Millia Islamia, New Delhi</p>
    </footer>
</div>

<script>
    function togglePubs() {
        const more = document.getElementById('more-pubs');
        const btn = document.getElementById('toggle-btn');
        const open = more.classList.toggle('visible');
        btn.textContent = open ? 'Show fewer publications ↑' : 'Show all 30+ publications ↓';
    }
</script>
</body>
</html>
