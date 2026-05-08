<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <title>Samiksha Patil — Portfolio</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link
    href="https://fonts.googleapis.com/css2?family=Nunito:wght@300;400;600;700;900&family=Gowun+Batang:wght@400;700&family=DM+Mono:wght@400;500&display=swap"
    rel="stylesheet">
  <style>
    :root {
      --blush: #F3CCDE;
      --lilac: #D6A8C4;
      --mauve: #BA88AE;
      --plum: #9E6899;
      --deep: #5B3765;
      --white: #FDF8FC;
      --soft-bg: #FAF0F6;
      --ink: #2D1B36;
      --ink-soft: #6B4C7A;
      --star: #E8C4F0;
    }

    *,
    *::before,
    *::after {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Nunito', sans-serif;
      background: var(--soft-bg);
      color: var(--ink);
      overflow-x: hidden;
      cursor: default;
    }

    /* ── CURSOR — subtle dot only ── */
    .cursor-dot {
      width: 8px;
      height: 8px;
      background: var(--plum);
      border-radius: 50%;
      position: fixed;
      pointer-events: none;
      z-index: 9999;
      transform: translate(-50%, -50%);
      transition: width 0.2s, height 0.2s, background 0.2s;
    }

    body.cursor-hover .cursor-dot {
      width: 16px;
      height: 16px;
      background: var(--lilac);
    }

    /* ── FLOATING STARS (BG DECO) ── */
    .bg-stars {
      position: fixed;
      inset: 0;
      pointer-events: none;
      z-index: 0;
      overflow: hidden;
    }

    .bg-star {
      position: absolute;
      color: var(--star);
      animation: float-star linear infinite;
      opacity: 0.45;
      user-select: none;
      font-size: 13px;
    }

    @keyframes float-star {
      0% {
        transform: translateY(100vh) rotate(0deg);
        opacity: 0;
      }

      10% {
        opacity: 0.45;
      }

      90% {
        opacity: 0.45;
      }

      100% {
        transform: translateY(-10vh) rotate(360deg);
        opacity: 0;
      }
    }

    /* ── NAVBAR ── */
    nav {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      z-index: 200;
      padding: 18px 6%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: rgba(253, 248, 252, 0.88);
      backdrop-filter: blur(16px);
      border-bottom: 1px solid rgba(186, 136, 174, 0.2);
    }

    .nav-logo {
      font-family: 'Gowun Batang', serif;
      font-size: 20px;
      font-weight: 700;
      color: var(--deep);
      letter-spacing: -0.5px;
    }

    .nav-logo span {
      color: var(--plum);
    }

    .nav-links {
      display: flex;
      gap: 32px;
      list-style: none;
    }

    .nav-links a {
      text-decoration: none;
      font-size: 13px;
      font-weight: 700;
      letter-spacing: 0.06em;
      text-transform: uppercase;
      color: var(--ink-soft);
      transition: color 0.2s;
      position: relative;
    }

    .nav-links a::after {
      content: '';
      position: absolute;
      bottom: -3px;
      left: 0;
      right: 0;
      height: 2px;
      background: var(--lilac);
      border-radius: 2px;
      transform: scaleX(0);
      transition: transform 0.25s;
    }

    .nav-links a:hover {
      color: var(--deep);
    }

    .nav-links a:hover::after {
      transform: scaleX(1);
    }

    .nav-hire {
      background: linear-gradient(135deg, var(--plum), var(--deep));
      color: white !important;
      padding: 9px 20px;
      border-radius: 100px;
      font-size: 13px !important;
      box-shadow: 0 4px 15px rgba(91, 55, 101, 0.3);
    }

    .nav-hire::after {
      display: none !important;
    }

    .nav-hire:hover {
      opacity: 0.9;
      transform: translateY(-1px);
    }

    /* ── HERO ── */
    .hero {
      min-height: 100vh;
      padding: 120px 6% 80px;
      display: grid;
      grid-template-columns: 1.1fr 1fr;
      align-items: center;
      gap: 60px;
      position: relative;
      background:
        radial-gradient(ellipse 60% 50% at 80% 50%, rgba(243, 204, 222, 0.45) 0%, transparent 70%),
        radial-gradient(ellipse 40% 40% at 10% 80%, rgba(214, 168, 196, 0.3) 0%, transparent 60%),
        var(--soft-bg);
    }

    .hero-tag {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: white;
      border: 1.5px solid var(--blush);
      padding: 7px 16px;
      border-radius: 100px;
      font-size: 12px;
      font-weight: 700;
      color: var(--plum);
      letter-spacing: 0.08em;
      text-transform: uppercase;
      margin-bottom: 24px;
      box-shadow: 0 4px 12px rgba(186, 136, 174, 0.15);
      animation: fadeUp 0.6s ease both;
    }

    .live-dot {
      width: 7px;
      height: 7px;
      border-radius: 50%;
      background: #5CB87A;
      box-shadow: 0 0 0 3px rgba(92, 184, 122, 0.25);
      animation: pulse 2s infinite;
    }

    @keyframes pulse {

      0%,
      100% {
        opacity: 1
      }

      50% {
        opacity: 0.4
      }
    }

    .hero-name {
      font-family: 'Gowun Batang', serif;
      font-size: clamp(48px, 7vw, 88px);
      line-height: 1.0;
      letter-spacing: -2px;
      color: var(--ink);
      margin-bottom: 8px;
      animation: fadeUp 0.7s ease 0.1s both;
    }

    .hero-name em {
      font-style: italic;
      background: linear-gradient(135deg, var(--plum), var(--mauve));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .hero-sub {
      font-size: 16px;
      color: var(--ink-soft);
      font-weight: 600;
      letter-spacing: 0.04em;
      margin-bottom: 20px;
      animation: fadeUp 0.7s ease 0.18s both;
    }

    .hero-desc {
      font-size: 15px;
      color: var(--ink-soft);
      line-height: 1.85;
      max-width: 480px;
      margin-bottom: 40px;
      font-weight: 400;
      animation: fadeUp 0.7s ease 0.26s both;
    }

    .hero-vibes {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-bottom: 36px;
      animation: fadeUp 0.7s ease 0.32s both;
    }

    .vibe-tag {
      padding: 6px 14px;
      border-radius: 100px;
      font-size: 12px;
      font-weight: 700;
      background: white;
      border: 1.5px solid var(--blush);
      color: var(--ink-soft);
    }

    .vibe-tag.purple {
      background: var(--blush);
      border-color: var(--blush);
      color: var(--deep);
    }

    .vibe-tag.mauve {
      background: rgba(186, 136, 174, 0.15);
      border-color: var(--mauve);
      color: var(--plum);
    }

    .hero-btns {
      display: flex;
      gap: 14px;
      flex-wrap: wrap;
      animation: fadeUp 0.7s ease 0.38s both;
    }

    .btn-main {
      background: linear-gradient(135deg, var(--plum) 0%, var(--deep) 100%);
      color: white;
      padding: 14px 28px;
      border-radius: 100px;
      text-decoration: none;
      font-size: 14px;
      font-weight: 700;
      box-shadow: 0 8px 24px rgba(91, 55, 101, 0.35);
      transition: all 0.3s;
      display: inline-flex;
      align-items: center;
      gap: 8px;
    }

    .btn-main:hover {
      transform: translateY(-3px);
      box-shadow: 0 14px 30px rgba(91, 55, 101, 0.4);
    }

    .btn-ghost {
      border: 2px solid var(--lilac);
      color: var(--deep);
      padding: 14px 28px;
      border-radius: 100px;
      text-decoration: none;
      font-size: 14px;
      font-weight: 700;
      transition: all 0.3s;
    }

    .btn-ghost:hover {
      background: var(--blush);
      border-color: var(--blush);
      transform: translateY(-2px);
    }

    /* Hero right — bubble card collage */
    .hero-right {
      position: relative;
      height: 460px;
      animation: fadeUp 0.8s ease 0.2s both;
    }

    .bubble-card {
      position: absolute;
      background: white;
      border-radius: 24px;
      padding: 22px 26px;
      box-shadow: 0 12px 40px rgba(158, 104, 153, 0.15);
      border: 1.5px solid rgba(243, 204, 222, 0.6);
      transition: transform 0.35s;
    }

    .bubble-card:hover {
      transform: translateY(-6px) rotate(0deg) !important;
    }

    .bc-1 {
      top: 0;
      left: 0;
      width: 200px;
      transform: rotate(-3deg);
    }

    .bc-2 {
      top: 30px;
      right: 0;
      width: 210px;
      transform: rotate(2.5deg);
      background: linear-gradient(135deg, #F3CCDE, #D6A8C4);
    }

    .bc-3 {
      bottom: 60px;
      left: 20px;
      width: 230px;
      transform: rotate(1.5deg);
    }

    .bc-4 {
      bottom: 10px;
      right: 10px;
      width: 180px;
      transform: rotate(-2deg);
      background: linear-gradient(135deg, var(--deep), var(--plum));
      color: white;
    }

    .bc-emoji {
      font-size: 28px;
      margin-bottom: 8px;
      display: block;
    }

    .bc-label {
      font-size: 10px;
      font-weight: 700;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      opacity: 0.6;
      margin-bottom: 4px;
      font-family: 'DM Mono', monospace;
    }

    .bc-val {
      font-family: 'Gowun Batang', serif;
      font-size: 26px;
      font-weight: 700;
      line-height: 1;
    }

    .bc-sub {
      font-size: 12px;
      opacity: 0.7;
      margin-top: 4px;
      font-weight: 600;
    }

    .float-star-deco {
      position: absolute;
      font-size: 22px;
      animation: wobble 3s ease-in-out infinite;
      user-select: none;
      color: var(--lilac);
    }

    @keyframes wobble {

      0%,
      100% {
        transform: rotate(-10deg)
      }

      50% {
        transform: rotate(10deg)
      }
    }

    /* ── SECTIONS SHARED ── */
    section {
      padding: 100px 6%;
      position: relative;
      z-index: 1;
    }

    .sec-eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-family: 'DM Mono', monospace;
      font-size: 11px;
      font-weight: 500;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--plum);
      margin-bottom: 16px;
    }

    .sec-eyebrow::before {
      content: '✦';
      font-size: 10px;
    }

    .sec-title {
      font-family: 'Gowun Batang', serif;
      font-size: clamp(30px, 4vw, 50px);
      line-height: 1.1;
      letter-spacing: -1px;
      color: var(--ink);
      margin-bottom: 16px;
    }

    .sec-title em {
      font-style: italic;
      color: var(--plum);
    }

    /* ── ABOUT ── */
    #about {
      background: white;
      border-top: 1px solid rgba(214, 168, 196, 0.2);
      border-bottom: 1px solid rgba(214, 168, 196, 0.2);
    }

    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1.4fr;
      gap: 80px;
      align-items: start;
    }

    .about-photo-card {
      background: linear-gradient(145deg, var(--blush) 0%, var(--lilac) 100%);
      border-radius: 30px;
      padding: 32px;
      text-align: center;
      box-shadow: 0 20px 50px rgba(158, 104, 153, 0.2);
      position: relative;
      overflow: hidden;
    }

    .about-photo-card::before {
      content: '';
      position: absolute;
      top: -40px;
      right: -40px;
      width: 120px;
      height: 120px;
      background: rgba(255, 255, 255, 0.2);
      border-radius: 50%;
    }

    .about-avatar {
      width: 100px;
      height: 100px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--plum), var(--deep));
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 42px;
      margin: 0 auto 16px;
      box-shadow: 0 8px 20px rgba(91, 55, 101, 0.3);
    }

    .about-name-card {
      font-family: 'Gowun Batang', serif;
      font-size: 22px;
      font-weight: 700;
      color: var(--deep);
      margin-bottom: 4px;
    }

    .about-loc {
      font-size: 13px;
      color: var(--ink-soft);
      font-weight: 600;
      margin-bottom: 20px;
    }

    .about-stat-row {
      display: flex;
      justify-content: space-around;
      background: rgba(255, 255, 255, 0.5);
      border-radius: 16px;
      padding: 16px;
    }

    .about-stat {
      text-align: center;
    }

    .about-stat-num {
      font-family: 'Gowun Batang', serif;
      font-size: 26px;
      font-weight: 700;
      color: var(--deep);
    }

    .about-stat-lbl {
      font-size: 11px;
      color: var(--ink-soft);
      font-weight: 700;
    }

    .about-right {
      padding-top: 8px;
    }

    .about-desc {
      font-size: 16px;
      line-height: 1.9;
      color: var(--ink-soft);
      margin-bottom: 32px;
      font-weight: 400;
    }

    .personal-section {
      background: var(--soft-bg);
      border-radius: 20px;
      padding: 24px;
      border: 1.5px solid rgba(214, 168, 196, 0.3);
      margin-top: 28px;
    }

    .personal-title {
      font-size: 13px;
      font-weight: 700;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: var(--plum);
      margin-bottom: 14px;
      font-family: 'DM Mono', monospace;
    }

    .personal-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }

    .p-tag {
      padding: 7px 14px;
      border-radius: 100px;
      font-size: 13px;
      font-weight: 600;
      background: white;
      border: 1.5px solid rgba(214, 168, 196, 0.4);
      color: var(--ink-soft);
      transition: all 0.25s;
    }

    .p-tag:hover {
      background: var(--blush);
      border-color: var(--blush);
      color: var(--deep);
      transform: scale(1.04);
    }

    /* ── SKILLS ── */
    #skills {
      background: var(--soft-bg);
    }

    .skills-intro {
      display: grid;
      grid-template-columns: 1fr 2fr;
      gap: 80px;
      align-items: start;
    }

    .skill-category {
      margin-bottom: 36px;
    }

    .skill-cat-name {
      font-size: 11px;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      font-weight: 700;
      color: var(--plum);
      font-family: 'DM Mono', monospace;
      margin-bottom: 14px;
    }

    .skill-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }

    .s-tag {
      padding: 8px 16px;
      border-radius: 12px;
      font-size: 13px;
      font-weight: 700;
      background: white;
      border: 1.5px solid rgba(186, 136, 174, 0.25);
      color: var(--ink-soft);
      transition: all 0.25s;
      box-shadow: 0 2px 8px rgba(158, 104, 153, 0.08);
    }

    .s-tag:hover {
      background: var(--deep);
      color: white;
      transform: translateY(-3px) scale(1.04);
      box-shadow: 0 8px 20px rgba(91, 55, 101, 0.25);
    }

    .bar-item {
      margin-bottom: 24px;
    }

    .bar-top {
      display: flex;
      justify-content: space-between;
      font-size: 14px;
      font-weight: 700;
      color: var(--ink);
      margin-bottom: 10px;
    }

    .bar-pct {
      font-family: 'DM Mono', monospace;
      font-size: 12px;
      color: var(--plum);
    }

    .bar-track {
      height: 8px;
      background: rgba(186, 136, 174, 0.2);
      border-radius: 100px;
      overflow: hidden;
    }

    .bar-fill {
      height: 100%;
      border-radius: 100px;
      background: linear-gradient(90deg, var(--lilac), var(--plum));
      transform: scaleX(0);
      transform-origin: left;
      transition: transform 1.3s cubic-bezier(0.16, 1, 0.3, 1);
    }

    .bar-fill.go {
      transform: scaleX(1);
    }

    /* ── PROJECTS ── */
    #projects {
      background: linear-gradient(160deg, var(--deep) 0%, #3A2048 100%);
      color: white;
    }

    #projects .sec-eyebrow {
      color: var(--blush);
    }

    #projects .sec-title {
      color: white;
    }

    #projects .sec-title em {
      color: var(--blush);
    }

    .proj-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 24px;
      margin-top: 60px;
    }

    .proj-card {
      background: rgba(255, 255, 255, 0.06);
      border: 1px solid rgba(255, 255, 255, 0.1);
      border-radius: 28px;
      padding: 36px;
      transition: all 0.35s;
      position: relative;
      overflow: hidden;
    }

    .proj-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      height: 3px;
      background: linear-gradient(90deg, var(--lilac), var(--blush));
      transform: scaleX(0);
      transition: transform 0.4s;
    }

    .proj-card:hover::before {
      transform: scaleX(1);
    }

    .proj-card:hover {
      background: rgba(255, 255, 255, 0.1);
      transform: translateY(-5px);
    }

    .proj-card.featured {
      grid-column: span 2;
      display: grid;
      grid-template-columns: 1.2fr 1fr;
      gap: 40px;
      align-items: center;
    }

    .proj-card.featured::before {
      background: linear-gradient(90deg, var(--blush), var(--lilac));
    }

    .proj-num {
      font-family: 'Gowun Batang', serif;
      font-size: 72px;
      font-weight: 700;
      color: rgba(255, 255, 255, 0.05);
      line-height: 1;
      margin-bottom: -10px;
      display: block;
    }

    .proj-name {
      font-family: 'Gowun Batang', serif;
      font-size: 26px;
      font-weight: 700;
      color: white;
      margin-bottom: 12px;
      letter-spacing: -0.3px;
    }

    .proj-desc {
      font-size: 14px;
      line-height: 1.8;
      color: rgba(255, 255, 255, 0.55);
      margin-bottom: 24px;
    }

    .proj-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 7px;
      margin-bottom: 24px;
    }

    .proj-tag {
      padding: 4px 12px;
      border-radius: 100px;
      font-size: 11px;
      font-family: 'DM Mono', monospace;
      letter-spacing: 0.04em;
      background: rgba(214, 168, 196, 0.15);
      color: rgba(243, 204, 222, 0.8);
      border: 1px solid rgba(214, 168, 196, 0.2);
    }

    .proj-link {
      display: inline-flex;
      align-items: center;
      gap: 7px;
      font-size: 13px;
      font-weight: 700;
      color: var(--blush);
      text-decoration: none;
      letter-spacing: 0.04em;
      transition: gap 0.25s;
    }

    .proj-link:hover {
      gap: 12px;
    }

    .proj-live-badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      background: rgba(92, 184, 122, 0.15);
      border: 1px solid rgba(92, 184, 122, 0.3);
      color: #7DCCA0;
      padding: 5px 12px;
      border-radius: 100px;
      font-size: 11px;
      font-weight: 700;
      font-family: 'DM Mono', monospace;
      margin-bottom: 14px;
    }

    .proj-features {
      background: rgba(255, 255, 255, 0.05);
      border-radius: 18px;
      padding: 24px;
      border: 1px solid rgba(255, 255, 255, 0.08);
    }

    .proj-feat-title {
      font-size: 11px;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: rgba(255, 255, 255, 0.3);
      font-family: 'DM Mono', monospace;
      margin-bottom: 14px;
    }

    .proj-feat-item {
      display: flex;
      align-items: center;
      gap: 10px;
      font-size: 13px;
      color: rgba(255, 255, 255, 0.6);
      margin-bottom: 10px;
    }

    .feat-check {
      color: var(--blush);
      font-size: 14px;
    }

    /* ── EDUCATION ── */
    #education {
      background: white;
      border-top: 1px solid rgba(214, 168, 196, 0.2);
    }

    .edu-layout {
      display: grid;
      grid-template-columns: 1fr 1.8fr;
      gap: 80px;
      align-items: start;
    }

    .edu-card {
      background: linear-gradient(145deg, var(--soft-bg), var(--blush));
      border-radius: 28px;
      padding: 36px;
      border: 1.5px solid rgba(214, 168, 196, 0.3);
      box-shadow: 0 20px 50px rgba(158, 104, 153, 0.12);
      position: relative;
      overflow: hidden;
    }

    .edu-card::after {
      content: '✦';
      position: absolute;
      bottom: 16px;
      right: 24px;
      font-size: 80px;
      color: rgba(158, 104, 153, 0.08);
      line-height: 1;
    }

    .edu-badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      background: var(--deep);
      color: white;
      padding: 6px 14px;
      border-radius: 100px;
      font-size: 12px;
      font-weight: 700;
      margin-bottom: 20px;
    }

    .edu-deg {
      font-family: 'Gowun Batang', serif;
      font-size: 22px;
      font-weight: 700;
      margin-bottom: 6px;
    }

    .edu-school {
      font-size: 13px;
      color: var(--ink-soft);
      font-weight: 600;
      margin-bottom: 24px;
    }

    .cgpa-row {
      display: flex;
      align-items: baseline;
      gap: 6px;
      margin-bottom: 4px;
    }

    .cgpa-big {
      font-family: 'Gowun Batang', serif;
      font-size: 48px;
      font-weight: 700;
      color: var(--deep);
      line-height: 1;
    }

    .cgpa-denom {
      font-size: 22px;
      color: var(--ink-soft);
    }

    .cgpa-lbl {
      font-size: 12px;
      color: var(--ink-soft);
      font-weight: 600;
    }

    .edu-right {
      padding-top: 12px;
    }

    .edu-highlights {
      display: flex;
      flex-direction: column;
      gap: 16px;
    }

    .edu-hl {
      display: flex;
      align-items: flex-start;
      gap: 16px;
      background: var(--soft-bg);
      border-radius: 16px;
      padding: 20px;
      border: 1.5px solid rgba(214, 168, 196, 0.2);
      transition: all 0.25s;
    }

    .edu-hl:hover {
      transform: translateX(6px);
      border-color: var(--lilac);
    }

    .edu-hl-icon {
      width: 42px;
      height: 42px;
      border-radius: 12px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 20px;
      flex-shrink: 0;
    }

    .ic-purple {
      background: var(--blush);
    }

    .ic-green {
      background: rgba(168, 230, 176, 0.2);
    }

    .ic-indigo {
      background: rgba(158, 104, 153, 0.1);
    }

    .edu-hl-body h4 {
      font-size: 14px;
      font-weight: 700;
      margin-bottom: 3px;
    }

    .edu-hl-body p {
      font-size: 13px;
      color: var(--ink-soft);
      line-height: 1.5;
    }

    .ongoing-card {
      background: linear-gradient(135deg, var(--deep), #3A2048);
      border-radius: 20px;
      padding: 24px;
      margin-top: 20px;
      color: white;
    }

    .ongoing-label {
      font-size: 11px;
      font-family: 'DM Mono', monospace;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--blush);
      margin-bottom: 8px;
    }

    .ongoing-name {
      font-family: 'Gowun Batang', serif;
      font-size: 18px;
      font-weight: 700;
      margin-bottom: 8px;
    }

    .ongoing-desc {
      font-size: 13px;
      color: rgba(255, 255, 255, 0.6);
      line-height: 1.6;
    }

    /* ── CONTACT ── */
    #contact {
      background: var(--soft-bg);
      border-top: 1px solid rgba(214, 168, 196, 0.2);
    }

    .contact-layout {
      display: grid;
      grid-template-columns: 1fr;
      gap: 48px;
      max-width: 640px;
    }

    .contact-links {
      display: flex;
      flex-direction: column;
      gap: 14px;
      margin-top: 32px;
    }

    .c-link {
      display: flex;
      align-items: center;
      gap: 16px;
      padding: 18px 22px;
      border-radius: 18px;
      background: white;
      border: 1.5px solid rgba(214, 168, 196, 0.3);
      text-decoration: none;
      color: var(--ink);
      font-weight: 600;
      font-size: 14px;
      transition: all 0.3s;
      box-shadow: 0 4px 14px rgba(158, 104, 153, 0.07);
    }

    .c-link:hover {
      background: linear-gradient(135deg, var(--plum), var(--deep));
      color: white;
      border-color: transparent;
      transform: translateX(6px);
      box-shadow: 0 10px 28px rgba(91, 55, 101, 0.25);
    }

    .c-icon {
      width: 40px;
      height: 40px;
      border-radius: 12px;
      background: var(--soft-bg);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 18px;
      flex-shrink: 0;
      transition: background 0.3s;
    }

    .c-link:hover .c-icon {
      background: rgba(255, 255, 255, 0.15);
    }


    /* ── FOOTER ── */
    footer {
      background: var(--deep);
      color: rgba(255, 255, 255, 0.5);
      padding: 36px 6%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 20px;
      font-size: 13px;
    }

    .footer-logo {
      font-family: 'Gowun Batang', serif;
      font-size: 20px;
      font-weight: 700;
      color: white;
    }

    .footer-logo span {
      color: var(--blush);
    }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp {
      from {
        opacity: 0;
        transform: translateY(28px)
      }

      to {
        opacity: 1;
        transform: translateY(0)
      }
    }

    .reveal {
      opacity: 0;
      transform: translateY(24px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }

    .reveal.vis {
      opacity: 1;
      transform: translateY(0);
    }

    /* ── RESPONSIVE ── */
    @media (max-width: 900px) {
      .hero {
        grid-template-columns: 1fr;
        padding-top: 100px;
      }

      .hero-right {
        display: none;
      }

      .about-grid,
      .skills-intro,
      .edu-layout {
        grid-template-columns: 1fr;
        gap: 50px;
      }

      .proj-grid {
        grid-template-columns: 1fr;
      }

      .proj-card.featured {
        grid-column: span 1;
        grid-template-columns: 1fr;
      }

      .nav-links {
        display: none;
      }

      footer {
        flex-direction: column;
        text-align: center;
      }
    }
  </style>
</head>

<body>

  <div class="cursor-dot" id="dot"></div>

  <!-- Floating BG stars -->
  <div class="bg-stars" id="bgStars"></div>

  <!-- NAVBAR -->
  <nav>
    <div class="nav-logo">samiksha<span> ✦</span></div>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#education">Education</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <section class="hero" id="home">
    <div class="hero-left">
      <div class="hero-tag"><span class="live-dot"></span> Open to Internships &amp; Collabs</div>
      <h1 class="hero-name">Samiksha<br><em>Patil</em></h1>
      <div class="hero-sub">Full-Stack Developer &amp; AI Engineer</div>
      <p class="hero-desc">
        Building production-ready web apps with React, FastAPI &amp; PostgreSQL —
        with AI-driven features woven into everything I make. Based in Mumbai, India.
      </p>
      <div class="hero-vibes">
        <span class="vibe-tag purple">📚 BSc IT '26</span>
        <span class="vibe-tag">🤖 AI Enthusiast</span>
        <span class="vibe-tag mauve">☁️ Cloud Explorer</span>
        <span class="vibe-tag">🔐 Cybersecurity Interest</span>
        <span class="vibe-tag purple">🚀 Builder Mindset</span>
      </div>
      <div class="hero-btns">
        <a href="#projects" class="btn-main">View Projects ✦</a>
        <a href="https://www.linkedin.com/in/sammmikshapatil" class="btn-ghost">LinkedIn →</a>
      </div>
    </div>

    <div class="hero-right">
      <div class="bubble-card bc-1">
        <span class="bc-emoji">🎓</span>
        <div class="bc-label">Current CGPA</div>
        <div class="bc-val">9.2</div>
        <div class="bc-sub">BSc IT · Sem 5</div>
      </div>
      <div class="bubble-card bc-2">
        <div class="bc-label" style="color:var(--deep);">Status</div>
        <div class="bc-val" style="font-size:18px; color:var(--deep); line-height:1.4;">Building &amp; Shipping ✦</div>
        <div class="bc-sub" style="color:var(--deep);opacity:0.7;">React · FastAPI · AWS</div>
      </div>
      <div class="bubble-card bc-3">
        <span class="bc-emoji">🚀</span>
        <div class="bc-label">Projects Live</div>
        <div class="bc-val">03</div>
        <div class="bc-sub">EduShield · StockAI · SevaSetu</div>
      </div>
      <div class="bubble-card bc-4">
        <div class="bc-label" style="color:var(--blush);">Currently Working On</div>
        <div class="bc-val" style="font-size:18px; line-height:1.4;">🔬 Shield AI — IDS</div>
        <div class="bc-sub" style="color:var(--blush);opacity:0.7;">ML · CIC-IDS2017 dataset</div>
      </div>
      <div class="float-star-deco" style="top:10px;right:80px;">✦</div>
      <div class="float-star-deco" style="bottom:130px;left:80px;animation-delay:0.8s;font-size:16px;">★</div>
      <div class="float-star-deco" style="top:180px;right:30px;animation-delay:1.5s;font-size:12px;">✦</div>
    </div>
  </section>

  <!-- ABOUT -->
  <section id="about">
    <div class="about-grid">
      <div class="reveal">
        <div class="about-photo-card">
          <div class="about-avatar">🌸</div>
          <div class="about-name-card">Samiksha Patil</div>
          <div class="about-loc">📍 Mumbai, India</div>
          <div class="about-stat-row">
            <div class="about-stat">
              <div class="about-stat-num">9.2</div>
              <div class="about-stat-lbl">CGPA</div>
            </div>
            <div class="about-stat">
              <div class="about-stat-num">03</div>
              <div class="about-stat-lbl">Projects</div>
            </div>
            <div class="about-stat">
              <div class="about-stat-num">6+</div>
              <div class="about-stat-lbl">Tech Stack</div>
            </div>
          </div>
        </div>
      </div>
      <div class="reveal" style="transition-delay:0.1s">
        <span class="sec-eyebrow">About Me</span>
        <h2 class="sec-title">Driven by code,<br><em>obsessed with craft</em> ✦</h2>
        <p class="about-desc">
          Hey! I'm Samiksha — a full-stack developer and aspiring AI engineer who loves turning ideas into real,
          production-ready systems. Whether it's building an AI plagiarism detection platform, a stock analysis engine,
          or a volunteer matching app, I care deeply about building things that actually work and feel great to use.
          <br><br>
          I specialize in React, FastAPI, and PostgreSQL, with a growing interest in AI/ML integration and cloud
          infrastructure. My CGPA of 9.2 reflects the dedication I put into both learning and building.
        </p>
        <div class="personal-section">
          <div class="personal-title">✦ Beyond Code</div>
          <div class="personal-tags">
            <span class="p-tag">📖 Avid reader</span>
            <span class="p-tag">🎵 Music while coding</span>
            <span class="p-tag">🧩 Problem-solving</span>
            <span class="p-tag">✏️ Note-taker &amp; documenter</span>
            <span class="p-tag">🌐 Open-source curious</span>
            <span class="p-tag">☕ Tea person</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section id="skills">
    <div class="skills-intro">
      <div class="reveal">
        <span class="sec-eyebrow">Skills</span>
        <h2 class="sec-title">Tools I<br><em>love</em> ✦</h2>
        <div style="margin-top:36px;">
          <div class="skill-category">
            <div class="skill-cat-name">Frontend</div>
            <div class="skill-tags">
              <span class="s-tag">React.js</span>
              <span class="s-tag">Tailwind CSS</span>
              <span class="s-tag">HTML5</span>
              <span class="s-tag">CSS3</span>
            </div>
          </div>
          <div class="skill-category">
            <div class="skill-cat-name">Backend &amp; DB</div>
            <div class="skill-tags">
              <span class="s-tag">FastAPI</span>
              <span class="s-tag">PostgreSQL</span>
              <span class="s-tag">REST APIs</span>
              <span class="s-tag">Auth</span>
            </div>
          </div>
          <div class="skill-category">
            <div class="skill-cat-name">AI / ML</div>
            <div class="skill-tags">
              <span class="s-tag">Scikit-learn</span>
              <span class="s-tag">HuggingFace</span>
              <span class="s-tag">Data Processing</span>
            </div>
          </div>
          <div class="skill-category">
            <div class="skill-cat-name">Languages</div>
            <div class="skill-tags">
              <span class="s-tag">Python</span>
              <span class="s-tag">JavaScript</span>
              <span class="s-tag">C++</span>
              <span class="s-tag">Java</span>
              <span class="s-tag">Flutter</span>
              <span class="s-tag">SQL</span>
            </div>
          </div>
          <div class="skill-category">
            <div class="skill-cat-name">Tools &amp; Infra</div>
            <div class="skill-tags">
              <span class="s-tag">AWS S3</span>
              <span class="s-tag">Firebase</span>
              <span class="s-tag">Git / GitHub</span>
              <span class="s-tag">Render</span>
            </div>
          </div>
        </div>
      </div>

      <div class="skill-bars reveal" style="transition-delay:0.12s; padding-top:80px;">
        <div class="bar-item">
          <div class="bar-top"><span>Python &amp; FastAPI</span><span class="bar-pct">90%</span></div>
          <div class="bar-track">
            <div class="bar-fill" data-w="0.90"></div>
          </div>
        </div>
        <div class="bar-item">
          <div class="bar-top"><span>React &amp; Frontend</span><span class="bar-pct">85%</span></div>
          <div class="bar-track">
            <div class="bar-fill" data-w="0.85"></div>
          </div>
        </div>
        <div class="bar-item">
          <div class="bar-top"><span>PostgreSQL &amp; Databases</span><span class="bar-pct">80%</span></div>
          <div class="bar-track">
            <div class="bar-fill" data-w="0.80"></div>
          </div>
        </div>
        <div class="bar-item">
          <div class="bar-top"><span>AI / ML Integration</span><span class="bar-pct">78%</span></div>
          <div class="bar-track">
            <div class="bar-fill" data-w="0.78"></div>
          </div>
        </div>
        <div class="bar-item">
          <div class="bar-top"><span>AWS &amp; Cloud Tools</span><span class="bar-pct">70%</span></div>
          <div class="bar-track">
            <div class="bar-fill" data-w="0.70"></div>
          </div>
        </div>
        <div class="bar-item">
          <div class="bar-top"><span>System Design &amp; APIs</span><span class="bar-pct">75%</span></div>
          <div class="bar-track">
            <div class="bar-fill" data-w="0.75"></div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section id="projects">
    <div class="reveal">
      <span class="sec-eyebrow">Featured Work</span>
      <h2 class="sec-title">Projects that<br><em>actually ship</em> ✦</h2>
    </div>

    <div class="proj-grid">
      <!-- EduShield - featured -->
      <div class="proj-card featured reveal" style="transition-delay:0.1s">
        <div>
          <span class="proj-num">01</span>
          <h3 class="proj-name">EduShield</h3>
          <p class="proj-desc">My final year project — an AI-powered academic integrity platform. Detects plagiarism and
            AI-generated content, with role-based access for students and faculty, AWS S3 file storage, and a scalable
            FastAPI backend.</p>
          <div class="proj-tags">
            <span class="proj-tag">React</span>
            <span class="proj-tag">FastAPI</span>
            <span class="proj-tag">PostgreSQL</span>
            <span class="proj-tag">AWS S3</span>
            <span class="proj-tag">HuggingFace</span>
            <span class="proj-tag">AI Detection</span>
          </div>
          <a href="#" class="proj-link">View Project →</a>
        </div>
        <div class="proj-features">
          <div class="proj-feat-title">Core Features</div>
          <div class="proj-feat-item"><span class="feat-check">✦</span> AI plagiarism detection engine</div>
          <div class="proj-feat-item"><span class="feat-check">✦</span> AI-generated content classifier</div>
          <div class="proj-feat-item"><span class="feat-check">✦</span> Role-based auth (student/faculty)</div>
          <div class="proj-feat-item"><span class="feat-check">✦</span> AWS S3 scalable file storage</div>
          <div class="proj-feat-item"><span class="feat-check">✦</span> Section-wise assignment management</div>
        </div>
      </div>

      <!-- StockAI -->
      <div class="proj-card reveal" style="transition-delay:0.15s">
        <span class="proj-num">02</span>
        <div class="proj-live-badge"><span
            style="width:7px;height:7px;background:#7DCCA0;border-radius:50%;display:inline-block;"></span> Live</div>
        <h3 class="proj-name">StockAI</h3>
        <p class="proj-desc">Full-stack stock analysis platform with real-time market data and AI-driven trading
          signals. Implements RSI, EMA, MACD, and volatility indicators. Built with robust retry and fallback logic for
          high API reliability.</p>
        <div class="proj-tags">
          <span class="proj-tag">React</span>
          <span class="proj-tag">Tailwind CSS</span>
          <span class="proj-tag">FastAPI</span>
          <span class="proj-tag">yfinance</span>
          <span class="proj-tag">Firebase</span>
          <span class="proj-tag">Render</span>
        </div>
        <a href="https://stock-analysis-2f871.web.app" target="_blank" class="proj-link">View Live Site →</a>
      </div>

      <!-- SevaSetu -->
      <div class="proj-card reveal" style="transition-delay:0.2s">
        <span class="proj-num">03</span>
        <div class="proj-live-badge"><span
            style="width:7px;height:7px;background:#7DCCA0;border-radius:50%;display:inline-block;"></span> Live</div>
        <h3 class="proj-name">SevaSetu v2</h3>
        <p class="proj-desc">A volunteer and help-matching platform connecting people who need support with those who
          can provide it. Implemented authentication, user workflows, and a refined UI/UX — fully deployed.</p>
        <div class="proj-tags">
          <span class="proj-tag">React</span>
          <span class="proj-tag">Firebase</span>
          <span class="proj-tag">Authentication</span>
          <span class="proj-tag">UX Design</span>
        </div>
        <a href="https://seva-setu-9a8e3.web.app/" target="_blank" class="proj-link">View Live Site →</a>
      </div>
    </div>
  </section>

  <!-- EDUCATION -->
  <section id="education">
    <div class="edu-layout">
      <div class="reveal">
        <span class="sec-eyebrow">Education</span>
        <h2 class="sec-title">Always <em>learning</em> ✦</h2>
        <div style="margin-top:32px;">
          <div class="edu-card">
            <div class="edu-badge">🎓 Currently Enrolled</div>
            <div class="edu-deg">BSc in Information Technology</div>
            <div class="edu-school">2023 – 2026 · Mumbai</div>
            <div class="cgpa-row">
              <span class="cgpa-big">9.2</span>
              <span class="cgpa-denom">/10</span>
            </div>
            <div class="cgpa-lbl">CGPA · Semester 5 · Top performer ✦</div>
          </div>
        </div>
      </div>

      <div class="edu-right reveal" style="transition-delay:0.1s">
        <div class="edu-highlights">
          <div class="edu-hl">
            <div class="edu-hl-icon ic-purple">🤖</div>
            <div class="edu-hl-body">
              <h4>Artificial Intelligence &amp; ML</h4>
              <p>Hands-on model training, content analysis, and intrusion detection system design using CIC-IDS2017
                dataset</p>
            </div>
          </div>
          <div class="edu-hl">
            <div class="edu-hl-icon ic-green">💻</div>
            <div class="edu-hl-body">
              <h4>Full-Stack Web Development</h4>
              <p>Production applications using React, FastAPI, PostgreSQL — deployed with Firebase &amp; Render</p>
            </div>
          </div>
          <div class="edu-hl">
            <div class="edu-hl-icon ic-indigo">🔐</div>
            <div class="edu-hl-body">
              <h4>Cybersecurity &amp; System Design</h4>
              <p>Network anomaly detection, role-based auth systems, and secure backend architectures</p>
            </div>
          </div>
          <div class="edu-hl">
            <div class="edu-hl-icon ic-purple">☁️</div>
            <div class="edu-hl-body">
              <h4>Cloud Infrastructure</h4>
              <p>AWS S3 integrations, Firebase deployment, Render hosting — real cloud workflows from semester 3</p>
            </div>
          </div>
        </div>

        <div class="ongoing-card" style="margin-top:24px;">
          <div class="ongoing-label">🔬 Ongoing Project</div>
          <div class="ongoing-name">Shield AI — Intrusion Detection System</div>
          <div class="ongoing-desc">
            Building an ML-based network intrusion detection system trained on the CIC-IDS2017 dataset, capable of
            detecting network anomalies and DoS attacks in real-time across multiple model architectures.
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact">
    <div class="contact-layout">
      <div class="reveal">
        <span class="sec-eyebrow">Contact</span>
        <h2 class="sec-title">Let's build<br><em>something great</em> ✦</h2>
        <p style="font-size:15px; color:var(--ink-soft); line-height:1.8; margin-bottom:8px;">
          Open to internships, collaborations, freelance gigs, or just a good conversation about AI, systems, or tech.
          Drop me a message — I'd love to hear from you.
        </p>
        <div class="contact-links">
          <a href="mailto:patilsamiksha179@gmail.com" class="c-link">
            <div class="c-icon">📧</div>
            patilsamiksha179@gmail.com
          </a>
          <a href="https://www.linkedin.com/in/sammmikshapatil" target="_blank" class="c-link">
            <div class="c-icon">💼</div>
            linkedin.com/in/sammmikshapatil
          </a>
          <a href="https://stock-analysis-2f871.web.app" target="_blank" class="c-link">
            <div class="c-icon">📈</div>
            StockAI — Live Project
          </a>
          <a href="https://seva-setu-9a8e3.web.app/" target="_blank" class="c-link">
            <div class="c-icon">🤝</div>
            SevaSetu v2 — Live Project
          </a>
          <a href="https://github.com/sammmiksha" target="_blank" class="c-link">
            <div class="c-icon">🐙</div>
            github.com/sammmiksha
          </a>
        </div>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <div class="footer-logo">samiksha<span> ✦</span></div>
    <div>Made with focus &amp; a lot of caffeine ☕</div>
    <div>© 2026 Samiksha Patil · All Rights Reserved</div>
  </footer>

  <script>
    // ── CURSOR — minimal dot, no sparkles ──
    const dot = document.getElementById('dot');
    document.addEventListener('mousemove', e => {
      dot.style.left = e.clientX + 'px';
      dot.style.top = e.clientY + 'px';
    });
    document.querySelectorAll('a, button').forEach(el => {
      el.addEventListener('mouseenter', () => document.body.classList.add('cursor-hover'));
      el.addEventListener('mouseleave', () => document.body.classList.remove('cursor-hover'));
    });

    // ── FLOATING BG STARS ──
    const bgStars = document.getElementById('bgStars');
    const starChars = ['✦', '★', '✸', '·'];
    for (let i = 0; i < 14; i++) {
      const s = document.createElement('div');
      s.className = 'bg-star';
      s.textContent = starChars[i % starChars.length];
      s.style.left = Math.random() * 100 + 'vw';
      s.style.animationDuration = (20 + Math.random() * 20) + 's';
      s.style.animationDelay = (-Math.random() * 20) + 's';
      bgStars.appendChild(s);
    }

    // ── SCROLL REVEAL ──
    const obs = new IntersectionObserver(entries => {
      entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('vis'); });
    }, { threshold: 0.1 });
    document.querySelectorAll('.reveal').forEach(el => obs.observe(el));

    // ── SKILL BARS ──
    document.querySelectorAll('.bar-fill').forEach(b => {
      b.style.width = (parseFloat(b.dataset.w) * 100) + '%';
    });
    const barObs = new IntersectionObserver(entries => {
      entries.forEach(e => {
        if (e.isIntersecting) e.target.querySelectorAll('.bar-fill').forEach(b => b.classList.add('go'));
      });
    }, { threshold: 0.3 });
    document.querySelectorAll('.skill-bars').forEach(el => barObs.observe(el));
  </script>
</body>

</html>
