<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Muhammad Usman Sarwar — AI/ML Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet" />
<style>
:root {
  --bg: #030712;
  --bg2: #0a0f1e;
  --bg3: #0d1425;
  --glass: rgba(255,255,255,0.045);
  --glass-border: rgba(255,255,255,0.10);
  --glass-hover: rgba(255,255,255,0.075);
  --indigo: #6C63FF;
  --cyan: #22D3EE;
  --violet: #A78BFA;
  --emerald: #34D399;
  --amber: #FBBF24;
  --rose: #FB7185;
  --text: #E2E8F0;
  --text-muted: #94A3B8;
  --text-dim: #64748B;
  --glow-indigo: rgba(108,99,255,0.18);
  --glow-cyan: rgba(34,211,238,0.14);
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

html { scroll-behavior: smooth; }

body {
  font-family: 'Inter', sans-serif;
  background: var(--bg);
  color: var(--text);
  min-height: 100vh;
  overflow-x: hidden;
}

/* ── STARFIELD ─────────────────────────────────── */
#stars-canvas {
  position: fixed;
  inset: 0;
  z-index: 0;
  pointer-events: none;
}

/* ── GRID OVERLAY ──────────────────────────────── */
.grid-overlay {
  position: fixed;
  inset: 0;
  z-index: 0;
  pointer-events: none;
  background-image:
    linear-gradient(rgba(108,99,255,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(108,99,255,0.04) 1px, transparent 1px);
  background-size: 60px 60px;
}

/* ── MAIN CONTENT ──────────────────────────────── */
main {
  position: relative;
  z-index: 1;
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 24px 80px;
}

/* ── GLASS UTILITY ─────────────────────────────── */
.glass {
  background: var(--glass);
  border: 1px solid var(--glass-border);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border-radius: 20px;
}

.glass-card {
  background: var(--glass);
  border: 1px solid var(--glass-border);
  backdrop-filter: blur(24px);
  -webkit-backdrop-filter: blur(24px);
  border-radius: 16px;
  padding: 28px 32px;
  transition: transform 0.3s cubic-bezier(.22,1,.36,1), border-color 0.3s, background 0.3s, box-shadow 0.3s;
  transform-style: preserve-3d;
  cursor: default;
}

.glass-card:hover {
  background: var(--glass-hover);
  border-color: rgba(108,99,255,0.28);
  box-shadow: 0 0 40px rgba(108,99,255,0.10), 0 24px 64px rgba(0,0,0,0.4);
  transform: translateY(-4px) rotateX(1deg) rotateY(-0.5deg);
}

/* ── HERO ──────────────────────────────────────── */
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 80px 0 60px;
  text-align: center;
}

.hero-inner {
  max-width: 780px;
}

.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: rgba(108,99,255,0.12);
  border: 1px solid rgba(108,99,255,0.30);
  border-radius: 100px;
  padding: 8px 18px;
  font-size: 12px;
  font-weight: 500;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--violet);
  margin-bottom: 36px;
  font-family: 'JetBrains Mono', monospace;
}

.hero-badge .dot {
  width: 6px; height: 6px;
  border-radius: 50%;
  background: var(--emerald);
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0%,100% { opacity: 1; }
  50% { opacity: 0.4; }
}

.hero-name {
  font-family: 'Space Grotesk', sans-serif;
  font-size: clamp(44px, 7vw, 82px);
  font-weight: 700;
  line-height: 1.04;
  letter-spacing: -0.03em;
  margin-bottom: 20px;
}

.hero-name .line1 { color: var(--text); }
.hero-name .line2 {
  background: linear-gradient(135deg, var(--indigo) 0%, var(--cyan) 60%, var(--violet) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-tagline {
  font-size: 18px;
  color: var(--text-muted);
  font-weight: 400;
  line-height: 1.65;
  max-width: 600px;
  margin: 0 auto 44px;
}

.hero-tagline strong { color: var(--text); font-weight: 500; }

.hero-links {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  justify-content: center;
  margin-bottom: 60px;
}

.btn-link {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 12px 22px;
  border-radius: 12px;
  font-size: 14px;
  font-weight: 500;
  text-decoration: none;
  border: 1px solid var(--glass-border);
  background: var(--glass);
  color: var(--text);
  backdrop-filter: blur(12px);
  transition: all 0.25s;
}

.btn-link:hover {
  background: var(--glass-hover);
  border-color: var(--indigo);
  color: #fff;
  transform: translateY(-2px);
  box-shadow: 0 8px 32px rgba(108,99,255,0.20);
}

.btn-link svg { width: 16px; height: 16px; }

.btn-link.primary {
  background: linear-gradient(135deg, var(--indigo), var(--violet));
  border-color: transparent;
  color: #fff;
}

.btn-link.primary:hover {
  box-shadow: 0 8px 40px rgba(108,99,255,0.40);
  transform: translateY(-2px);
}

/* ── STAT STRIP ────────────────────────────────── */
.stat-strip {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 16px;
  margin-bottom: 100px;
}

.stat-item {
  background: var(--glass);
  border: 1px solid var(--glass-border);
  border-radius: 14px;
  padding: 20px 24px;
  text-align: center;
  backdrop-filter: blur(16px);
  transition: all 0.3s;
}

.stat-item:hover {
  border-color: rgba(108,99,255,0.30);
  background: var(--glass-hover);
  transform: translateY(-3px);
}

.stat-num {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 32px;
  font-weight: 700;
  letter-spacing: -0.02em;
  background: linear-gradient(135deg, var(--cyan), var(--indigo));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.stat-label {
  font-size: 12px;
  color: var(--text-dim);
  margin-top: 4px;
  text-transform: uppercase;
  letter-spacing: 0.08em;
}

/* ── SECTION ───────────────────────────────────── */
section {
  margin-bottom: 80px;
}

.section-eyebrow {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 36px;
}

.eyebrow-line {
  height: 1px;
  flex: 1;
  background: linear-gradient(90deg, rgba(108,99,255,0.3), transparent);
}

.eyebrow-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  text-transform: uppercase;
  letter-spacing: 0.14em;
  color: var(--indigo);
  white-space: nowrap;
}

.section-title {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 36px;
  font-weight: 700;
  letter-spacing: -0.02em;
  margin-bottom: 6px;
}

.section-sub {
  color: var(--text-muted);
  font-size: 16px;
  margin-bottom: 36px;
}

/* ── ABOUT ─────────────────────────────────────── */
.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}

.about-text {
  font-size: 16px;
  color: var(--text-muted);
  line-height: 1.8;
}

.about-text strong { color: var(--text); }

.about-highlight {
  background: rgba(108,99,255,0.08);
  border: 1px solid rgba(108,99,255,0.18);
  border-radius: 14px;
  padding: 24px 28px;
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.about-detail {
  display: flex;
  align-items: flex-start;
  gap: 14px;
}

.about-icon {
  width: 36px; height: 36px;
  border-radius: 10px;
  display: flex; align-items: center; justify-content: center;
  font-size: 16px;
  flex-shrink: 0;
}

.about-detail-text { font-size: 14px; color: var(--text-muted); line-height: 1.5; }
.about-detail-text strong { color: var(--text); display: block; font-size: 13px; margin-bottom: 2px; }

/* ── EXPERTISE TERMINAL ────────────────────────── */
.terminal {
  background: rgba(3,7,18,0.85);
  border: 1px solid rgba(108,99,255,0.20);
  border-radius: 16px;
  overflow: hidden;
  backdrop-filter: blur(20px);
}

.terminal-bar {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 14px 20px;
  background: rgba(255,255,255,0.03);
  border-bottom: 1px solid rgba(255,255,255,0.06);
}

.t-dot { width: 10px; height: 10px; border-radius: 50%; }
.t-red { background: #FF5F57; }
.t-yellow { background: #FEBC2E; }
.t-green { background: #28C840; }

.terminal-filename {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: var(--text-dim);
  margin-left: 8px;
}

.terminal-body {
  padding: 28px 32px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 13.5px;
  line-height: 2;
}

.t-comment { color: #4A5568; }
.t-key { color: var(--cyan); }
.t-str { color: var(--emerald); }
.t-bracket { color: var(--violet); }
.t-comma { color: var(--text-dim); }
.t-var { color: #FBBF24; }
.t-eq { color: var(--rose); }

/* ── SKILLS GRID ───────────────────────────────── */
.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
}

.skill-category {
  background: var(--glass);
  border: 1px solid var(--glass-border);
  border-radius: 16px;
  padding: 24px 28px;
  backdrop-filter: blur(20px);
  transition: all 0.3s;
}

.skill-category:hover {
  border-color: rgba(108,99,255,0.25);
  background: var(--glass-hover);
  transform: translateY(-3px);
}

.skill-cat-header {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 18px;
}

.skill-cat-icon {
  width: 38px; height: 38px;
  border-radius: 10px;
  display: flex; align-items: center; justify-content: center;
  font-size: 18px;
}

.skill-cat-name {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 16px;
  font-weight: 600;
  color: var(--text);
}

.skill-pills {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.pill {
  font-size: 12px;
  font-weight: 500;
  padding: 5px 13px;
  border-radius: 100px;
  border: 1px solid;
  font-family: 'Inter', sans-serif;
  letter-spacing: 0.01em;
}

.pill-indigo { background: rgba(108,99,255,0.10); border-color: rgba(108,99,255,0.25); color: var(--violet); }
.pill-cyan { background: rgba(34,211,238,0.10); border-color: rgba(34,211,238,0.25); color: var(--cyan); }
.pill-emerald { background: rgba(52,211,153,0.10); border-color: rgba(52,211,153,0.25); color: var(--emerald); }
.pill-amber { background: rgba(251,191,36,0.10); border-color: rgba(251,191,36,0.25); color: var(--amber); }
.pill-rose { background: rgba(251,113,133,0.10); border-color: rgba(251,113,133,0.25); color: var(--rose); }

/* ── PROJECTS ──────────────────────────────────── */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 20px;
}

.project-card {
  background: var(--glass);
  border: 1px solid var(--glass-border);
  border-radius: 18px;
  padding: 28px 30px;
  backdrop-filter: blur(24px);
  transition: all 0.35s cubic-bezier(.22,1,.36,1);
  position: relative;
  overflow: hidden;
  transform-style: preserve-3d;
}

.project-card::before {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: 18px;
  background: radial-gradient(ellipse at 20% 20%, var(--card-glow, rgba(108,99,255,0.08)) 0%, transparent 60%);
  pointer-events: none;
  opacity: 0;
  transition: opacity 0.3s;
}

.project-card:hover {
  transform: translateY(-6px) rotateX(1.5deg) rotateY(-1deg);
  border-color: rgba(108,99,255,0.30);
  box-shadow: 0 32px 80px rgba(0,0,0,0.5), 0 0 60px var(--card-glow, rgba(108,99,255,0.10));
}

.project-card:hover::before { opacity: 1; }

.project-header {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  margin-bottom: 16px;
}

.project-icon-wrap {
  width: 48px; height: 48px;
  border-radius: 14px;
  display: flex; align-items: center; justify-content: center;
  font-size: 22px;
}

.project-link {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 34px; height: 34px;
  border-radius: 10px;
  background: var(--glass);
  border: 1px solid var(--glass-border);
  color: var(--text-muted);
  text-decoration: none;
  font-size: 14px;
  transition: all 0.2s;
}

.project-link:hover { color: var(--text); background: var(--glass-hover); border-color: var(--indigo); }

.project-name {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 18px;
  font-weight: 700;
  margin-bottom: 8px;
  letter-spacing: -0.01em;
}

.project-desc {
  font-size: 14px;
  color: var(--text-muted);
  line-height: 1.65;
  margin-bottom: 18px;
}

.project-metrics {
  display: flex;
  gap: 16px;
  margin-bottom: 18px;
}

.metric {
  display: flex;
  flex-direction: column;
  gap: 2px;
}

.metric-val {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 20px;
  font-weight: 700;
  letter-spacing: -0.02em;
}

.metric-key {
  font-size: 11px;
  color: var(--text-dim);
  text-transform: uppercase;
  letter-spacing: 0.08em;
}

.project-tags { display: flex; flex-wrap: wrap; gap: 6px; }

.tag {
  font-size: 11px;
  padding: 4px 10px;
  border-radius: 6px;
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(255,255,255,0.08);
  color: var(--text-muted);
  font-family: 'JetBrains Mono', monospace;
}

/* ── EXPERIENCE ────────────────────────────────── */
.exp-timeline {
  position: relative;
  padding-left: 32px;
}

.exp-timeline::before {
  content: '';
  position: absolute;
  left: 0;
  top: 12px;
  bottom: 12px;
  width: 1px;
  background: linear-gradient(180deg, var(--indigo), rgba(108,99,255,0.15), transparent);
}

.exp-item {
  position: relative;
  margin-bottom: 28px;
}

.exp-item:last-child { margin-bottom: 0; }

.exp-dot {
  position: absolute;
  left: -39px;
  top: 14px;
  width: 14px; height: 14px;
  border-radius: 50%;
  border: 2px solid var(--indigo);
  background: var(--bg);
  transition: background 0.3s, box-shadow 0.3s;
}

.exp-item:hover .exp-dot {
  background: var(--indigo);
  box-shadow: 0 0 16px rgba(108,99,255,0.6);
}

.exp-card {
  background: var(--glass);
  border: 1px solid var(--glass-border);
  border-radius: 16px;
  padding: 24px 28px;
  backdrop-filter: blur(20px);
  transition: all 0.3s;
}

.exp-card:hover {
  border-color: rgba(108,99,255,0.22);
  background: var(--glass-hover);
  transform: translateX(4px);
}

.exp-header {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 16px;
  margin-bottom: 12px;
}

.exp-company {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 17px;
  font-weight: 700;
}

.exp-role {
  font-size: 14px;
  color: var(--violet);
  font-weight: 500;
  margin-top: 2px;
}

.exp-badge {
  font-size: 11px;
  padding: 5px 12px;
  border-radius: 100px;
  background: rgba(108,99,255,0.10);
  border: 1px solid rgba(108,99,255,0.22);
  color: var(--violet);
  white-space: nowrap;
  font-family: 'JetBrains Mono', monospace;
}

.exp-list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.exp-list li {
  font-size: 14px;
  color: var(--text-muted);
  padding-left: 18px;
  position: relative;
  line-height: 1.55;
}

.exp-list li::before {
  content: '▸';
  position: absolute;
  left: 0;
  color: var(--cyan);
  font-size: 10px;
  top: 3px;
}

.exp-list li strong { color: var(--text); }

/* ── CERTS ─────────────────────────────────────── */
.certs-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 16px;
}

.cert-card {
  background: var(--glass);
  border: 1px solid var(--glass-border);
  border-radius: 14px;
  padding: 20px 24px;
  backdrop-filter: blur(16px);
  display: flex;
  align-items: center;
  gap: 16px;
  transition: all 0.3s;
}

.cert-card:hover {
  border-color: rgba(108,99,255,0.25);
  background: var(--glass-hover);
  transform: translateY(-3px);
}

.cert-icon {
  width: 44px; height: 44px;
  border-radius: 12px;
  display: flex; align-items: center; justify-content: center;
  font-size: 20px;
  flex-shrink: 0;
}

.cert-name { font-size: 14px; font-weight: 600; margin-bottom: 3px; }
.cert-issuer { font-size: 12px; color: var(--text-dim); }

/* ── GITHUB STATS ──────────────────────────────── */
.github-section .glass-card { text-align: center; }

.github-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
  margin-bottom: 24px;
}

.github-stat {
  background: rgba(108,99,255,0.07);
  border: 1px solid rgba(108,99,255,0.14);
  border-radius: 12px;
  padding: 20px;
  text-align: center;
  transition: all 0.3s;
}

.github-stat:hover {
  background: rgba(108,99,255,0.12);
  border-color: rgba(108,99,255,0.25);
  transform: translateY(-2px);
}

.github-stat-val {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 28px;
  font-weight: 700;
  background: linear-gradient(135deg, var(--indigo), var(--cyan));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.github-stat-label { font-size: 12px; color: var(--text-dim); margin-top: 4px; }

.github-imgs { display: flex; flex-direction: column; gap: 16px; }

.github-img-wrap {
  border-radius: 12px;
  overflow: hidden;
  border: 1px solid var(--glass-border);
}

.github-img-wrap img { width: 100%; display: block; }

/* ── GOAL ──────────────────────────────────────── */
.goal-card {
  background: linear-gradient(135deg, rgba(108,99,255,0.10) 0%, rgba(34,211,238,0.06) 100%);
  border: 1px solid rgba(108,99,255,0.22);
  border-radius: 24px;
  padding: 60px 48px;
  text-align: center;
  position: relative;
  overflow: hidden;
  backdrop-filter: blur(24px);
}

.goal-card::before {
  content: '';
  position: absolute;
  top: -80px; left: 50%;
  transform: translateX(-50%);
  width: 400px; height: 400px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(108,99,255,0.12) 0%, transparent 60%);
  pointer-events: none;
}

.goal-quote {
  font-family: 'Space Grotesk', sans-serif;
  font-size: clamp(18px, 2.5vw, 24px);
  font-weight: 500;
  line-height: 1.6;
  color: var(--text);
  max-width: 700px;
  margin: 0 auto 32px;
  position: relative;
}

.goal-quote .accent {
  background: linear-gradient(135deg, var(--indigo), var(--cyan));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

/* ── CONNECT ───────────────────────────────────── */
.connect-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 14px;
}

.connect-item {
  display: flex;
  align-items: center;
  gap: 14px;
  background: var(--glass);
  border: 1px solid var(--glass-border);
  border-radius: 14px;
  padding: 16px 20px;
  text-decoration: none;
  color: var(--text);
  backdrop-filter: blur(16px);
  transition: all 0.3s;
}

.connect-item:hover {
  background: var(--glass-hover);
  border-color: rgba(108,99,255,0.28);
  transform: translateY(-3px);
  box-shadow: 0 12px 40px rgba(0,0,0,0.3);
}

.connect-icon {
  width: 40px; height: 40px;
  border-radius: 10px;
  display: flex; align-items: center; justify-content: center;
  font-size: 18px;
  flex-shrink: 0;
}

.connect-label { font-size: 12px; color: var(--text-dim); margin-bottom: 2px; }
.connect-val { font-size: 13px; font-weight: 500; }

/* ── FOOTER ────────────────────────────────────── */
footer {
  position: relative;
  z-index: 1;
  text-align: center;
  padding: 40px 24px;
  border-top: 1px solid rgba(255,255,255,0.06);
}

.footer-text {
  font-size: 13px;
  color: var(--text-dim);
  font-family: 'JetBrains Mono', monospace;
}

/* ── RESPONSIVE ────────────────────────────────── */
@media (max-width: 768px) {
  .stat-strip { grid-template-columns: repeat(2, 1fr); }
  .about-grid { grid-template-columns: 1fr; }
  .github-grid { grid-template-columns: 1fr; }
  .exp-timeline { padding-left: 20px; }
  .exp-dot { left: -27px; }
}

@media (max-width: 480px) {
  .stat-strip { grid-template-columns: repeat(2, 1fr); }
  .hero-links { flex-direction: column; align-items: center; }
}

/* ── SCROLL REVEAL ─────────────────────────────── */
.reveal {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 0.7s cubic-bezier(.22,1,.36,1), transform 0.7s cubic-bezier(.22,1,.36,1);
}
.reveal.visible { opacity: 1; transform: translateY(0); }

</style>
</head>
<body>

<canvas id="stars-canvas"></canvas>
<div class="grid-overlay"></div>

<main>

  <!-- ── HERO ── -->
  <section class="hero">
    <div class="hero-inner">
      <div class="hero-badge">
        <span class="dot"></span>
        Available for AI/ML Roles &amp; Collaborations
      </div>

      <h1 class="hero-name">
        <span class="line1">Muhammad Usman</span><br>
        <span class="line2">Sarwar</span>
      </h1>

      <p class="hero-tagline">
        <strong>AI/ML Engineer · GenAI Builder · LLM Architect</strong><br>
        I design and ship <strong>production-ready intelligent systems</strong> — RAG pipelines, agentic workflows, and LLM-powered applications that solve real problems at scale.
      </p>

      <div class="hero-links">
        <a class="btn-link primary" href="https://www.linkedin.com/in/muhammad-usman-018535253" target="_blank">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
          LinkedIn
        </a>
        <a class="btn-link" href="https://github.com/Usmansarwar143" target="_blank">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
          GitHub
        </a>
        <a class="btn-link" href="https://usmansarwar143.github.io/portfolio/" target="_blank">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><line x1="2" y1="12" x2="22" y2="12"/><path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"/></svg>
          Portfolio
        </a>
        <a class="btn-link" href="mailto:usmanwerke@gmail.com">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
          Email
        </a>
      </div>

      <!-- Stat Strip -->
      <div class="stat-strip reveal">
        <div class="stat-item">
          <div class="stat-num">7+</div>
          <div class="stat-label">AI Projects</div>
        </div>
        <div class="stat-item">
          <div class="stat-num">5</div>
          <div class="stat-label">Internships</div>
        </div>
        <div class="stat-item">
          <div class="stat-num">3.54</div>
          <div class="stat-label">CGPA / 4.00</div>
        </div>
        <div class="stat-item">
          <div class="stat-num">99.6%</div>
          <div class="stat-label">FYP Accuracy</div>
        </div>
      </div>
    </div>
  </section>

  <!-- ── ABOUT ── -->
  <section class="reveal">
    <div class="section-eyebrow">
      <div class="eyebrow-line"></div>
      <span class="eyebrow-label">01 · About</span>
      <div class="eyebrow-line" style="background:linear-gradient(90deg,transparent,rgba(108,99,255,0.3))"></div>
    </div>
    <h2 class="section-title">The Builder Behind the Code</h2>
    <p class="section-sub">Computer Systems Engineering graduate. AI/ML practitioner. Shipping since day one.</p>

    <div class="about-grid">
      <div class="glass-card" style="display:flex;flex-direction:column;gap:16px;">
        <p class="about-text">
          I'm a <strong>CS Engineering graduate</strong> from Sukkur IBA University (CGPA 3.54/4.00, May 2026), based in Pakistan. I don't just study AI — I build with it.
        </p>
        <p class="about-text">
          My work spans <strong>RAG pipelines, agentic systems, LLM fine-tuning, and computer vision</strong> — all deployed in real environments, not just notebooks. My FYP SafeDrive AI runs YOLOv8n-cls on a Raspberry Pi 4 at <strong>9.72 FPS with 99.6% accuracy</strong>.
        </p>
        <p class="about-text">
          Currently pursuing <strong>AI/ML engineering roles</strong> across Pakistan and remote/international positions, while exploring multimodal AI and advanced agentic architectures.
        </p>
      </div>

      <div class="about-highlight">
        <div class="about-detail">
          <div class="about-icon" style="background:rgba(108,99,255,0.15);">🎓</div>
          <div class="about-detail-text">
            <strong>Education</strong>
            B.E. Computer Systems Engineering · Sukkur IBA University · 2026
          </div>
        </div>
        <div class="about-detail">
          <div class="about-icon" style="background:rgba(34,211,238,0.12);">📍</div>
          <div class="about-detail-text">
            <strong>Location</strong>
            Rahim Yar Khan, Pakistan · Open to Lahore, Karachi, Islamabad, Remote
          </div>
        </div>
        <div class="about-detail">
          <div class="about-icon" style="background:rgba(52,211,153,0.12);">🚀</div>
          <div class="about-detail-text">
            <strong>Focus Area</strong>
            Generative AI · LLMs · RAG · Agentic Systems · Computer Vision
          </div>
        </div>
        <div class="about-detail">
          <div class="about-icon" style="background:rgba(251,191,36,0.12);">🏆</div>
          <div class="about-detail-text">
            <strong>Highlight</strong>
            Co-trained Gen AI workshop · Sukkur IBA University · 2024
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ── EXPERTISE TERMINAL ── -->
  <section class="reveal">
    <div class="section-eyebrow">
      <div class="eyebrow-line"></div>
      <span class="eyebrow-label">02 · Expertise</span>
      <div class="eyebrow-line" style="background:linear-gradient(90deg,transparent,rgba(108,99,255,0.3))"></div>
    </div>
    <h2 class="section-title">What I Build With</h2>
    <p class="section-sub">A system snapshot of my engineering toolkit.</p>

    <div class="terminal">
      <div class="terminal-bar">
        <div class="t-dot t-red"></div>
        <div class="t-dot t-yellow"></div>
        <div class="t-dot t-green"></div>
        <span class="terminal-filename">expertise.py</span>
      </div>
      <div class="terminal-body">
        <div><span class="t-var">expertise</span> <span class="t-eq">=</span> <span class="t-bracket">{</span></div>
        <div style="padding-left:28px;"><span class="t-comment"># Core specialization</span></div>
        <div style="padding-left:28px;"><span class="t-key">"LLM Engineering"</span><span class="t-comma">:</span> <span class="t-bracket">[</span><span class="t-str">"Fine-tuning"</span><span class="t-comma">,</span> <span class="t-str">"Prompt Engineering"</span><span class="t-comma">,</span> <span class="t-str">"Instruction Tuning"</span><span class="t-comma">,</span> <span class="t-str">"Anthropic API"</span><span class="t-bracket">]</span><span class="t-comma">,</span></div>
        <div style="padding-left:28px;"><span class="t-key">"RAG Systems"</span><span class="t-comma">:</span> <span class="t-bracket">[</span><span class="t-str">"LangChain"</span><span class="t-comma">,</span> <span class="t-str">"FAISS"</span><span class="t-comma">,</span> <span class="t-str">"ChromaDB"</span><span class="t-comma">,</span> <span class="t-str">"Vector Search"</span><span class="t-bracket">]</span><span class="t-comma">,</span></div>
        <div style="padding-left:28px;"><span class="t-key">"Agentic AI"</span><span class="t-comma">:</span> <span class="t-bracket">[</span><span class="t-str">"Dual-Memory Systems"</span><span class="t-comma">,</span> <span class="t-str">"Multi-LLM Routing"</span><span class="t-comma">,</span> <span class="t-str">"Tool Use"</span><span class="t-bracket">]</span><span class="t-comma">,</span></div>
        <div style="padding-left:28px;"><span class="t-key">"Computer Vision"</span><span class="t-comma">:</span> <span class="t-bracket">[</span><span class="t-str">"YOLOv8"</span><span class="t-comma">,</span> <span class="t-str">"OpenCV"</span><span class="t-comma">,</span> <span class="t-str">"CNNs"</span><span class="t-comma">,</span> <span class="t-str">"Edge Deployment"</span><span class="t-bracket">]</span><span class="t-comma">,</span></div>
        <div style="padding-left:28px;"><span class="t-key">"ML/DL"</span><span class="t-comma">:</span> <span class="t-bracket">[</span><span class="t-str">"PyTorch"</span><span class="t-comma">,</span> <span class="t-str">"TensorFlow"</span><span class="t-comma">,</span> <span class="t-str">"Transformers"</span><span class="t-comma">,</span> <span class="t-str">"HuggingFace"</span><span class="t-bracket">]</span><span class="t-comma">,</span></div>
        <div style="padding-left:28px;"><span class="t-key">"Backend &amp; Deploy"</span><span class="t-comma">:</span> <span class="t-bracket">[</span><span class="t-str">"FastAPI"</span><span class="t-comma">,</span> <span class="t-str">"Streamlit"</span><span class="t-comma">,</span> <span class="t-str">"HuggingFace Spaces"</span><span class="t-bracket">]</span><span class="t-comma">,</span></div>
        <div style="padding-left:28px;"><span class="t-key">"Languages"</span><span class="t-comma">:</span> <span class="t-bracket">[</span><span class="t-str">"Python"</span><span class="t-comma">,</span> <span class="t-str">"C++"</span><span class="t-comma">,</span> <span class="t-str">"JavaScript"</span><span class="t-comma">,</span> <span class="t-str">"Java"</span><span class="t-bracket">]</span><span class="t-comma">,</span></div>
        <div><span class="t-bracket">}</span></div>
      </div>
    </div>

    <div style="margin-top:24px;" class="skills-grid">
      <div class="skill-category">
        <div class="skill-cat-header">
          <div class="skill-cat-icon" style="background:rgba(108,99,255,0.14);">🤖</div>
          <span class="skill-cat-name">AI / GenAI</span>
        </div>
        <div class="skill-pills">
          <span class="pill pill-indigo">LangChain</span>
          <span class="pill pill-indigo">HuggingFace</span>
          <span class="pill pill-indigo">Anthropic API</span>
          <span class="pill pill-indigo">Mistral-7B</span>
          <span class="pill pill-indigo">Llama 3</span>
          <span class="pill pill-indigo">Qwen</span>
        </div>
      </div>
      <div class="skill-category">
        <div class="skill-cat-header">
          <div class="skill-cat-icon" style="background:rgba(34,211,238,0.12);">🧠</div>
          <span class="skill-cat-name">ML / Deep Learning</span>
        </div>
        <div class="skill-pills">
          <span class="pill pill-cyan">PyTorch</span>
          <span class="pill pill-cyan">TensorFlow</span>
          <span class="pill pill-cyan">YOLOv8</span>
          <span class="pill pill-cyan">OpenCV</span>
          <span class="pill pill-cyan">Scikit-learn</span>
        </div>
      </div>
      <div class="skill-category">
        <div class="skill-cat-header">
          <div class="skill-cat-icon" style="background:rgba(52,211,153,0.12);">🗄️</div>
          <span class="skill-cat-name">Vector DBs &amp; Retrieval</span>
        </div>
        <div class="skill-pills">
          <span class="pill pill-emerald">FAISS</span>
          <span class="pill pill-emerald">ChromaDB</span>
          <span class="pill pill-emerald">Vector Search</span>
          <span class="pill pill-emerald">Embeddings</span>
        </div>
      </div>
      <div class="skill-category">
        <div class="skill-cat-header">
          <div class="skill-cat-icon" style="background:rgba(251,191,36,0.12);">⚡</div>
          <span class="skill-cat-name">Deployment &amp; APIs</span>
        </div>
        <div class="skill-pills">
          <span class="pill pill-amber">FastAPI</span>
          <span class="pill pill-amber">Streamlit</span>
          <span class="pill pill-amber">HF Spaces</span>
          <span class="pill pill-amber">Raspberry Pi</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ── PROJECTS ── -->
  <section class="reveal">
    <div class="section-eyebrow">
      <div class="eyebrow-line"></div>
      <span class="eyebrow-label">03 · Projects</span>
      <div class="eyebrow-line" style="background:linear-gradient(90deg,transparent,rgba(108,99,255,0.3))"></div>
    </div>
    <h2 class="section-title">Shipped, Not Just Studied</h2>
    <p class="section-sub">Production AI systems with real metrics, real deployments.</p>

    <div class="projects-grid">

      <div class="project-card" style="--card-glow:rgba(251,113,133,0.10);">
        <div class="project-header">
          <div class="project-icon-wrap" style="background:rgba(251,113,133,0.12);">🚗</div>
          <a class="project-link" href="#" title="View Project">↗</a>
        </div>
        <div class="project-name">SafeDrive AI</div>
        <div class="project-desc">YOLOv8n-cls driver monitoring system deployed on Raspberry Pi 4. Real-time drowsiness and distraction detection at the edge — my Final Year Project.</div>
        <div class="project-metrics">
          <div class="metric">
            <span class="metric-val" style="color:var(--rose);">99.6%</span>
            <span class="metric-key">Accuracy</span>
          </div>
          <div class="metric">
            <span class="metric-val" style="color:var(--rose);">9.72</span>
            <span class="metric-key">FPS on Pi</span>
          </div>
        </div>
        <div class="project-tags">
          <span class="tag">YOLOv8n-cls</span><span class="tag">Raspberry Pi 4</span><span class="tag">OpenCV</span><span class="tag">NCNN</span>
        </div>
      </div>

      <div class="project-card" style="--card-glow:rgba(108,99,255,0.12);">
        <div class="project-header">
          <div class="project-icon-wrap" style="background:rgba(108,99,255,0.12);">⏳</div>
          <a class="project-link" href="#" title="View Project">↗</a>
        </div>
        <div class="project-name">Chronos AI</div>
        <div class="project-desc">Dual-memory agentic RAG system with long-term context retention across sessions. Combines short-term conversation memory with persistent ChromaDB vector store.</div>
        <div class="project-metrics">
          <div class="metric">
            <span class="metric-val" style="color:var(--indigo);">+45%</span>
            <span class="metric-key">Personalization</span>
          </div>
          <div class="metric">
            <span class="metric-val" style="color:var(--indigo);">Dual</span>
            <span class="metric-key">Memory Arch</span>
          </div>
        </div>
        <div class="project-tags">
          <span class="tag">ChromaDB</span><span class="tag">Mistral-7B</span><span class="tag">LangChain</span><span class="tag">Agentic</span>
        </div>
      </div>

      <div class="project-card" style="--card-glow:rgba(34,211,238,0.10);">
        <div class="project-header">
          <div class="project-icon-wrap" style="background:rgba(34,211,238,0.10);">⚡</div>
          <a class="project-link" href="https://github.com/Usmansarwar143/career-counceller" title="View Project" target="_blank">↗</a>
        </div>
        <div class="project-name">Ascend AI</div>
        <div class="project-desc">Multi-LLM routing pipeline orchestrating Llama 3, Qwen, and Gemma. Intelligent query routing selects the optimal model per task type for maximum throughput.</div>
        <div class="project-metrics">
          <div class="metric">
            <span class="metric-val" style="color:var(--cyan);">+40%</span>
            <span class="metric-key">Faster Processing</span>
          </div>
          <div class="metric">
            <span class="metric-val" style="color:var(--cyan);">99.9%</span>
            <span class="metric-key">Uptime</span>
          </div>
        </div>
        <div class="project-tags">
          <span class="tag">Llama 3</span><span class="tag">Qwen</span><span class="tag">Gemma</span><span class="tag">Multi-LLM</span>
        </div>
      </div>

      <div class="project-card" style="--card-glow:rgba(52,211,153,0.10);">
        <div class="project-header">
          <div class="project-icon-wrap" style="background:rgba(52,211,153,0.10);">🩺</div>
          <a class="project-link" href="https://github.com/Usmansarwar143/u-care-friendly-chatbot" title="View Project" target="_blank">↗</a>
        </div>
        <div class="project-name">U-Care Bot</div>
        <div class="project-desc">AI-powered health assistant built on Mistral-7B. Handles diverse medical query types with empathetic, contextually relevant responses via Streamlit.</div>
        <div class="project-metrics">
          <div class="metric">
            <span class="metric-val" style="color:var(--emerald);">100+</span>
            <span class="metric-key">Query Types</span>
          </div>
          <div class="metric">
            <span class="metric-val" style="color:var(--emerald);">+30%</span>
            <span class="metric-key">Relevance</span>
          </div>
        </div>
        <div class="project-tags">
          <span class="tag">Mistral-7B</span><span class="tag">Streamlit</span><span class="tag">NLP</span><span class="tag">HealthAI</span>
        </div>
      </div>

      <div class="project-card" style="--card-glow:rgba(167,139,250,0.10);">
        <div class="project-header">
          <div class="project-icon-wrap" style="background:rgba(167,139,250,0.12);">💬</div>
          <a class="project-link" href="https://github.com/Usmansarwar143/developershub-internship-tasks/tree/main/Task%2305" title="View Project" target="_blank">↗</a>
        </div>
        <div class="project-name">EmpathyBot</div>
        <div class="project-desc">Fine-tuned LLM on EmpatheticDialogues dataset for human-like emotional response generation. Custom instruction tuning with measurable empathy quality improvements.</div>
        <div class="project-metrics">
          <div class="metric">
            <span class="metric-val" style="color:var(--violet);">+25%</span>
            <span class="metric-key">Empathy Score</span>
          </div>
          <div class="metric">
            <span class="metric-val" style="color:var(--violet);">Fine-tuned</span>
            <span class="metric-key">LLM</span>
          </div>
        </div>
        <div class="project-tags">
          <span class="tag">Fine-tuning</span><span class="tag">EmpatheticDialogues</span><span class="tag">NLP</span>
        </div>
      </div>

      <div class="project-card" style="--card-glow:rgba(251,191,36,0.08);">
        <div class="project-header">
          <div class="project-icon-wrap" style="background:rgba(251,191,36,0.10);">🎠</div>
          <a class="project-link" href="#" title="View Project">↗</a>
        </div>
        <div class="project-name">AI LinkedIn Carousel Generator</div>
        <div class="project-desc">React app powered by the Anthropic API with Python/Playwright export pipeline. Generates beautifully formatted LinkedIn carousels from any topic in seconds.</div>
        <div class="project-metrics">
          <div class="metric">
            <span class="metric-val" style="color:var(--amber);">Claude</span>
            <span class="metric-key">Powered</span>
          </div>
          <div class="metric">
            <span class="metric-val" style="color:var(--amber);">Auto</span>
            <span class="metric-key">Export</span>
          </div>
        </div>
        <div class="project-tags">
          <span class="tag">Anthropic API</span><span class="tag">React</span><span class="tag">Playwright</span>
        </div>
      </div>

    </div>
  </section>

  <!-- ── EXPERIENCE ── -->
  <section class="reveal">
    <div class="section-eyebrow">
      <div class="eyebrow-line"></div>
      <span class="eyebrow-label">04 · Experience</span>
      <div class="eyebrow-line" style="background:linear-gradient(90deg,transparent,rgba(108,99,255,0.3))"></div>
    </div>
    <h2 class="section-title">5 Internships. Real Deliverables.</h2>
    <p class="section-sub">Built end-to-end AI systems in production environments across remote and on-site roles.</p>

    <div class="exp-timeline">

      <div class="exp-item">
        <div class="exp-dot"></div>
        <div class="exp-card">
          <div class="exp-header">
            <div>
              <div class="exp-company">DevelopersHub Corporation</div>
              <div class="exp-role">AI/ML Intern · Remote</div>
            </div>
            <span class="exp-badge">AI/ML</span>
          </div>
          <ul class="exp-list">
            <li>Built <strong>6+ end-to-end AI/ML solutions</strong> across diverse domains</li>
            <li>Developed production-grade <strong>RAG pipelines + NLP auto-tagging</strong> (+30% accuracy)</li>
            <li>Consistent <strong>80–88% model accuracy</strong> across classification tasks</li>
            <li>Collaborated in agile sprints delivering quality AI features on schedule</li>
          </ul>
        </div>
      </div>

      <div class="exp-item">
        <div class="exp-dot"></div>
        <div class="exp-card">
          <div class="exp-header">
            <div>
              <div class="exp-company">Elevvo Pathways</div>
              <div class="exp-role">AI/ML Intern · Remote</div>
            </div>
            <span class="exp-badge">Deep Learning</span>
          </div>
          <ul class="exp-list">
            <li>Designed and deployed <strong>10+ ML/DL models</strong> in production</li>
            <li>Built <strong>CNN-based image &amp; audio classifiers</strong> with 85–95% accuracy</li>
            <li>Achieved up to <strong>90% accuracy</strong> across classification tasks</li>
            <li>Deep hands-on experience with Transformers and fine-tuning pipelines</li>
          </ul>
        </div>
      </div>

      <div class="exp-item">
        <div class="exp-dot"></div>
        <div class="exp-card">
          <div class="exp-header">
            <div>
              <div class="exp-company">CodeGradients</div>
              <div class="exp-role">Python Intern · On-site</div>
            </div>
            <span class="exp-badge">Python</span>
          </div>
          <ul class="exp-list">
            <li>Automated manual workflows, reducing manual effort by <strong>30–40%</strong></li>
            <li>Improved overall code quality and test coverage by <strong>25%</strong></li>
            <li>Delivered reusable Python utility modules across multiple projects</li>
          </ul>
        </div>
      </div>

      <div class="exp-item">
        <div class="exp-dot"></div>
        <div class="exp-card">
          <div class="exp-header">
            <div>
              <div class="exp-company">TechnoHacks EduTech &amp; Skillify Zone</div>
              <div class="exp-role">AI/ML Intern · Remote</div>
            </div>
            <span class="exp-badge">AI/ML</span>
          </div>
          <ul class="exp-list">
            <li>Delivered ML projects covering NLP, classification, and data analysis</li>
            <li>Strengthened fundamentals in data preprocessing and model evaluation</li>
          </ul>
        </div>
      </div>

    </div>
  </section>

  <!-- ── CERTS ── -->
  <section class="reveal">
    <div class="section-eyebrow">
      <div class="eyebrow-line"></div>
      <span class="eyebrow-label">05 · Certifications</span>
      <div class="eyebrow-line" style="background:linear-gradient(90deg,transparent,rgba(108,99,255,0.3))"></div>
    </div>
    <h2 class="section-title">Credentials</h2>
    <p class="section-sub">Verified expertise across the GenAI and ML stack.</p>

    <div class="certs-grid">
      <div class="cert-card">
        <div class="cert-icon" style="background:rgba(108,99,255,0.12);">🧠</div>
        <div>
          <div class="cert-name">Prompt Engineering for LLMs</div>
          <div class="cert-issuer">LinkedIn Learning</div>
        </div>
      </div>
      <div class="cert-card">
        <div class="cert-icon" style="background:rgba(34,211,238,0.10);">⚛️</div>
        <div>
          <div class="cert-name">Quantum Computing Fundamentals</div>
          <div class="cert-issuer">LinkedIn Learning</div>
        </div>
      </div>
      <div class="cert-card">
        <div class="cert-icon" style="background:rgba(52,211,153,0.10);">🚀</div>
        <div>
          <div class="cert-name">GenAI App Development</div>
          <div class="cert-issuer">PEC · PakAngels · Aspire Pakistan</div>
        </div>
      </div>
    </div>
  </section>

  <!-- ── GITHUB STATS ── -->
  <section class="reveal github-section">
    <div class="section-eyebrow">
      <div class="eyebrow-line"></div>
      <span class="eyebrow-label">06 · GitHub</span>
      <div class="eyebrow-line" style="background:linear-gradient(90deg,transparent,rgba(108,99,255,0.3))"></div>
    </div>
    <h2 class="section-title">Activity &amp; Stats</h2>
    <p class="section-sub">Consistent output across AI, ML, and GenAI repositories.</p>

    <div class="glass-card">
      <div class="github-grid">
        <div class="github-stat">
          <div class="github-stat-val">50+</div>
          <div class="github-stat-label">Applications Sent</div>
        </div>
        <div class="github-stat">
          <div class="github-stat-val">7+</div>
          <div class="github-stat-label">Repos</div>
        </div>
        <div class="github-stat">
          <div class="github-stat-val">3</div>
          <div class="github-stat-label">Certifications</div>
        </div>
      </div>
      <div class="github-imgs">
        <div class="github-img-wrap">
          <img src="https://github-readme-stats.vercel.app/api?username=Usmansarwar143&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true&hide_border=true&bg_color=0d1117" alt="GitHub Stats" loading="lazy" />
        </div>
        <div class="github-img-wrap">
          <img src="https://github-readme-streak-stats.herokuapp.com/?user=Usmansarwar143&theme=tokyonight&hide_border=true&background=0d1117" alt="GitHub Streak" loading="lazy" />
        </div>
        <div class="github-img-wrap">
          <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Usmansarwar143&layout=compact&langs_count=8&theme=tokyonight&hide_border=true&bg_color=0d1117" alt="Top Languages" loading="lazy" />
        </div>
      </div>
    </div>
  </section>

  <!-- ── GOAL ── -->
  <section class="reveal">
    <div class="section-eyebrow">
      <div class="eyebrow-line"></div>
      <span class="eyebrow-label">07 · Mission</span>
      <div class="eyebrow-line" style="background:linear-gradient(90deg,transparent,rgba(108,99,255,0.3))"></div>
    </div>
    <div class="goal-card">
      <div style="font-size:40px;margin-bottom:20px;">🎯</div>
      <blockquote class="goal-quote">
        To build <span class="accent">scalable, human-centered AI systems</span> that harness the power of Generative AI, LLMs, and intelligent automation — making technology more accessible, empathetic, and impactful for everyone.
      </blockquote>
      <div style="display:flex;gap:12px;justify-content:center;flex-wrap:wrap;">
        <span class="pill pill-indigo">Generative AI</span>
        <span class="pill pill-cyan">LLM Architecture</span>
        <span class="pill pill-emerald">Real-World Impact</span>
        <span class="pill pill-amber">Agentic Systems</span>
      </div>
    </div>
  </section>

  <!-- ── CONNECT ── -->
  <section class="reveal">
    <div class="section-eyebrow">
      <div class="eyebrow-line"></div>
      <span class="eyebrow-label">08 · Connect</span>
      <div class="eyebrow-line" style="background:linear-gradient(90deg,transparent,rgba(108,99,255,0.3))"></div>
    </div>
    <h2 class="section-title">Let's Build Together</h2>
    <p class="section-sub">Open to AI/ML roles, research collaborations, and impactful projects.</p>

    <div class="connect-grid">
      <a class="connect-item" href="https://www.linkedin.com/in/muhammad-usman-018535253" target="_blank">
        <div class="connect-icon" style="background:rgba(10,102,194,0.14);">💼</div>
        <div>
          <div class="connect-label">LinkedIn</div>
          <div class="connect-val">muhammad-usman-018535253</div>
        </div>
      </a>
      <a class="connect-item" href="https://github.com/Usmansarwar143" target="_blank">
        <div class="connect-icon" style="background:rgba(255,255,255,0.07);">🐙</div>
        <div>
          <div class="connect-label">GitHub</div>
          <div class="connect-val">Usmansarwar143</div>
        </div>
      </a>
      <a class="connect-item" href="https://usmansarwar143.github.io/portfolio/" target="_blank">
        <div class="connect-icon" style="background:rgba(52,211,153,0.10);">🌐</div>
        <div>
          <div class="connect-label">Portfolio</div>
          <div class="connect-val">usmansarwar143.github.io</div>
        </div>
      </a>
      <a class="connect-item" href="mailto:usmanwerke@gmail.com">
        <div class="connect-icon" style="background:rgba(234,67,53,0.12);">📧</div>
        <div>
          <div class="connect-label">Email</div>
          <div class="connect-val">usmanwerke@gmail.com</div>
        </div>
      </a>
      <a class="connect-item" href="tel:+923163238191">
        <div class="connect-icon" style="background:rgba(108,99,255,0.12);">📞</div>
        <div>
          <div class="connect-label">Phone</div>
          <div class="connect-val">+92 316 3238191</div>
        </div>
      </a>
    </div>
  </section>

</main>

<footer>
  <p class="footer-text">
    ⭐ Muhammad Usman Sarwar · AI/ML Engineer · Built with ♥ and lots of LangChain
  </p>
</footer>

<script>
/* ── STARFIELD ── */
(function() {
  const canvas = document.getElementById('stars-canvas');
  const ctx = canvas.getContext('2d');
  let w, h, stars = [];

  function resize() {
    w = canvas.width = window.innerWidth;
    h = canvas.height = window.innerHeight;
  }

  function initStars(n) {
    stars = [];
    for (let i = 0; i < n; i++) {
      stars.push({
        x: Math.random() * w,
        y: Math.random() * h,
        r: Math.random() * 1.2 + 0.1,
        a: Math.random(),
        speed: Math.random() * 0.3 + 0.05,
        twinkle: Math.random() * Math.PI * 2
      });
    }
  }

  let t = 0;
  function draw() {
    ctx.clearRect(0, 0, w, h);
    t += 0.008;
    stars.forEach(s => {
      s.twinkle += s.speed * 0.04;
      const alpha = s.a * (0.5 + 0.5 * Math.sin(s.twinkle));
      ctx.beginPath();
      ctx.arc(s.x, s.y, s.r, 0, Math.PI * 2);
      ctx.fillStyle = `rgba(255,255,255,${alpha})`;
      ctx.fill();
    });
    requestAnimationFrame(draw);
  }

  resize();
  initStars(220);
  draw();
  window.addEventListener('resize', () => { resize(); initStars(220); });
})();

/* ── 3D TILT ON PROJECT CARDS ── */
document.querySelectorAll('.project-card, .glass-card').forEach(card => {
  card.addEventListener('mousemove', e => {
    const r = card.getBoundingClientRect();
    const x = (e.clientX - r.left) / r.width - 0.5;
    const y = (e.clientY - r.top) / r.height - 0.5;
    card.style.transform = `translateY(-6px) rotateX(${-y * 6}deg) rotateY(${x * 6}deg)`;
  });
  card.addEventListener('mouseleave', () => {
    card.style.transform = '';
  });
});

/* ── SCROLL REVEAL ── */
const reveals = document.querySelectorAll('.reveal');
const io = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.classList.add('visible');
      io.unobserve(e.target);
    }
  });
}, { threshold: 0.08 });
reveals.forEach(r => io.observe(r));
</script>
</body>
</html>
