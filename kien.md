<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Kien De Vera  Programmer</title>



<style>

@import url('https://fonts.googleapis.com/css2?family=DM+Mono:wght@300;400;500\\\\\\\&family=Manrope:wght@400;500;600;700;800\\\\\\\&display=swap');



:root {

\\\&#x20;   --bg: #090a09;

\\\&#x20;   --bg-soft: #10120f;

\\\&#x20;   --panel: rgba(24, 26, 22, .72);

\\\&#x20;   --panel-2: rgba(31, 33, 28, .55);

\\\&#x20;   --line: rgba(164, 168, 148, .16);

\\\&#x20;   --line-bright: rgba(181, 185, 165, .35);

\\\&#x20;   --stone: #a5a994;

\\\&#x20;   --stone-light: #d0d2c6;

\\\&#x20;   --stone-dark: #666a5c;

\\\&#x20;   --text: #e5e6dd;

\\\&#x20;   --muted: #777b70;

\\\&#x20;   --black: #050605;

}



\\\\\\\* {

\\\&#x20;   margin: 0;

\\\&#x20;   padding: 0;

\\\&#x20;   box-sizing: border-box;

}



html {

\\\&#x20;   scroll-behavior: smooth;

}



body {

\\\&#x20;   background: var(--bg);

\\\&#x20;   color: var(--text);

\\\&#x20;   font-family: "Manrope", sans-serif;

\\\&#x20;   overflow-x: hidden;

\\\&#x20;   cursor: none;

}



/\\\\\\\* =========================================================

\\\&#x20;  BACKGROUND

========================================================= \\\\\\\*/



\\\\#world {

\\\&#x20;   position: fixed;

\\\&#x20;   inset: 0;

\\\&#x20;   z-index: -10;

\\\&#x20;   overflow: hidden;

\\\&#x20;   background:

\\\&#x20;       radial-gradient(circle at 15% 20%, rgba(119,125,104,.12), transparent 30%),

\\\&#x20;       radial-gradient(circle at 82% 28%, rgba(83,88,74,.12), transparent 28%),

\\\&#x20;       radial-gradient(circle at 52% 90%, rgba(126,130,111,.08), transparent 30%),

\\\&#x20;       #090a09;

}



.ambient {

\\\&#x20;   position: absolute;

\\\&#x20;   width: 500px;

\\\&#x20;   height: 500px;

\\\&#x20;   border-radius: 50%;

\\\&#x20;   filter: blur(100px);

\\\&#x20;   opacity: .12;

\\\&#x20;   pointer-events: none;

}



.ambient.one {

\\\&#x20;   background: #9ba08c;

\\\&#x20;   top: -250px;

\\\&#x20;   left: -150px;

\\\&#x20;   animation: drift1 14s ease-in-out infinite alternate;

}



.ambient.two {

\\\&#x20;   background: #636957;

\\\&#x20;   right: -220px;

\\\&#x20;   top: 25%;

\\\&#x20;   animation: drift2 18s ease-in-out infinite alternate;

}



.ambient.three {

\\\&#x20;   background: #b1b49f;

\\\&#x20;   bottom: -300px;

\\\&#x20;   left: 40%;

\\\&#x20;   animation: drift3 20s ease-in-out infinite alternate;

}



@keyframes drift1 {

\\\&#x20;   to { transform: translate(160px, 120px); }

}



@keyframes drift2 {

\\\&#x20;   to { transform: translate(-130px, 100px); }

}



@keyframes drift3 {

\\\&#x20;   to { transform: translate(-100px, -130px); }

}



/\\\\\\\* Technical grid \\\\\\\*/



.grid {

\\\&#x20;   position: absolute;

\\\&#x20;   inset: -20%;

\\\&#x20;   opacity: .20;

\\\&#x20;   background-image:

\\\&#x20;       linear-gradient(rgba(159,164,145,.055) 1px, transparent 1px),

\\\&#x20;       linear-gradient(90deg, rgba(159,164,145,.055) 1px, transparent 1px);

\\\&#x20;   background-size: 75px 75px;

\\\&#x20;   transform:

\\\&#x20;       perspective(700px)

\\\&#x20;       rotateX(58deg)

\\\&#x20;       translateY(28%);

\\\&#x20;   transform-origin: center;

\\\&#x20;   animation: gridMove 22s linear infinite;

}



@keyframes gridMove {

\\\&#x20;   from { background-position: 0 0; }

\\\&#x20;   to { background-position: 0 150px; }

}



/\\\\\\\* Orbital rings \\\\\\\*/



.orbit {

\\\&#x20;   position: absolute;

\\\&#x20;   border: 1px solid rgba(166,170,151,.10);

\\\&#x20;   border-radius: 50%;

\\\&#x20;   transform-style: preserve-3d;

}



.orbit.one {

\\\&#x20;   width: 650px;

\\\&#x20;   height: 250px;

\\\&#x20;   right: -120px;

\\\&#x20;   top: 18%;

\\\&#x20;   transform: rotate(-24deg);

\\\&#x20;   animation: orbit 18s linear infinite;

}



.orbit.two {

\\\&#x20;   width: 500px;

\\\&#x20;   height: 190px;

\\\&#x20;   left: -150px;

\\\&#x20;   top: 55%;

\\\&#x20;   transform: rotate(25deg);

\\\&#x20;   animation: orbit 24s linear infinite reverse;

}



.orbit.three {

\\\&#x20;   width: 800px;

\\\&#x20;   height: 300px;

\\\&#x20;   left: 28%;

\\\&#x20;   bottom: -180px;

\\\&#x20;   transform: rotate(-12deg);

\\\&#x20;   animation: orbit 30s linear infinite;

}



@keyframes orbit {

\\\&#x20;   to { transform: rotate(336deg); }

}



/\\\\\\\* Circuit traces \\\\\\\*/



.circuit {

\\\&#x20;   position: absolute;

\\\&#x20;   inset: 0;

\\\&#x20;   opacity: .24;

\\\&#x20;   pointer-events: none;

}



.circuit span {

\\\&#x20;   position: absolute;

\\\&#x20;   display: block;

\\\&#x20;   height: 1px;

\\\&#x20;   background: linear-gradient(90deg, transparent, var(--stone-dark), transparent);

}



.circuit span::after {

\\\&#x20;   content: "";

\\\&#x20;   position: absolute;

\\\&#x20;   width: 5px;

\\\&#x20;   height: 5px;

\\\&#x20;   border: 1px solid var(--stone-dark);

\\\&#x20;   border-radius: 50%;

\\\&#x20;   top: -2px;

}



.line1 {

\\\&#x20;   width: 280px;

\\\&#x20;   top: 25%;

\\\&#x20;   left: 0;

}



.line1::after { right: 0; }



.line2 {

\\\&#x20;   width: 190px;

\\\&#x20;   top: 66%;

\\\&#x20;   right: 0;

}



.line2::after { left: 0; }



.line3 {

\\\&#x20;   width: 360px;

\\\&#x20;   top: 82%;

\\\&#x20;   left: 10%;

}



.line3::after { right: 0; }



/\\\\\\\* Floating code \\\\\\\*/



.code-fragments {

\\\&#x20;   position: absolute;

\\\&#x20;   inset: 0;

\\\&#x20;   pointer-events: none;

}



.code-fragments span {

\\\&#x20;   position: absolute;

\\\&#x20;   color: rgba(180,184,164,.10);

\\\&#x20;   font: 11px "DM Mono", monospace;

\\\&#x20;   letter-spacing: 1px;

\\\&#x20;   animation: floatCode 12s ease-in-out infinite alternate;

}



.code-fragments span:nth-child(1) {

\\\&#x20;   top: 18%;

\\\&#x20;   left: 7%;

}



.code-fragments span:nth-child(2) {

\\\&#x20;   top: 37%;

\\\&#x20;   right: 8%;

\\\&#x20;   animation-delay: -4s;

}



.code-fragments span:nth-child(3) {

\\\&#x20;   top: 74%;

\\\&#x20;   left: 5%;

\\\&#x20;   animation-delay: -7s;

}



.code-fragments span:nth-child(4) {

\\\&#x20;   top: 86%;

\\\&#x20;   right: 13%;

\\\&#x20;   animation-delay: -2s;

}



@keyframes floatCode {

\\\&#x20;   to {

\\\&#x20;       transform: translateY(-18px);

\\\&#x20;       opacity: .22;

\\\&#x20;   }

}



/\\\\\\\* Grain \\\\\\\*/



.grain {

\\\&#x20;   position: fixed;

\\\&#x20;   inset: 0;

\\\&#x20;   pointer-events: none;

\\\&#x20;   z-index: 100;

\\\&#x20;   opacity: .035;

\\\&#x20;   background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 180 180' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.8'/%3E%3C/svg%3E");

}



/\\\\\\\* =========================================================

\\\&#x20;  CURSOR

========================================================= \\\\\\\*/



.cursor {

\\\&#x20;   position: fixed;

\\\&#x20;   pointer-events: none;

\\\&#x20;   z-index: 9999;

}



.cursor-core {

\\\&#x20;   width: 5px;

\\\&#x20;   height: 5px;

\\\&#x20;   background: var(--stone-light);

\\\&#x20;   border-radius: 50%;

\\\&#x20;   transform: translate(-50%, -50%);

\\\&#x20;   box-shadow:

\\\&#x20;       0 0 10px rgba(202,205,191,.7),

\\\&#x20;       0 0 25px rgba(158,163,143,.35);

}



.cursor-reticle {

\\\&#x20;   width: 34px;

\\\&#x20;   height: 34px;

\\\&#x20;   transform: translate(-50%, -50%);

}



.cursor-reticle::before,

.cursor-reticle::after {

\\\&#x20;   content: "";

\\\&#x20;   position: absolute;

\\\&#x20;   inset: 5px;

\\\&#x20;   border: 1px solid rgba(171,175,155,.65);

\\\&#x20;   border-radius: 50%;

}



.cursor-reticle::after {

\\\&#x20;   inset: -5px;

\\\&#x20;   border-color: rgba(150,155,136,.15);

\\\&#x20;   animation: cursorPulse 2s infinite;

}



.corner {

\\\&#x20;   position: absolute;

\\\&#x20;   width: 7px;

\\\&#x20;   height: 7px;

\\\&#x20;   border-color: var(--stone);

\\\&#x20;   border-style: solid;

}



.c1 { top: 0; left: 0; border-width: 1px 0 0 1px; }

.c2 { top: 0; right: 0; border-width: 1px 1px 0 0; }

.c3 { bottom: 0; left: 0; border-width: 0 0 1px 1px; }

.c4 { bottom: 0; right: 0; border-width: 0 1px 1px 0; }



@keyframes cursorPulse {

\\\&#x20;   50% {

\\\&#x20;       transform: scale(1.3);

\\\&#x20;       opacity: .15;

\\\&#x20;   }

}



body.hovering .cursor-reticle {

\\\&#x20;   transform: translate(-50%, -50%) rotate(45deg) scale(1.35);

}



body.hovering .cursor-core {

\\\&#x20;   background: #e2e3d9;

}



/\\\\\\\* =========================================================

\\\&#x20;  NAVIGATION

========================================================= \\\\\\\*/



nav {

\\\&#x20;   position: fixed;

\\\&#x20;   z-index: 500;

\\\&#x20;   top: 22px;

\\\&#x20;   left: 50%;

\\\&#x20;   transform: translateX(-50%);

\\\&#x20;   width: min(1160px, calc(100% - 40px));

\\\&#x20;   height: 58px;

\\\&#x20;   border: 1px solid var(--line);

\\\&#x20;   background: rgba(10,11,10,.72);

\\\&#x20;   backdrop-filter: blur(22px);

\\\&#x20;   display: flex;

\\\&#x20;   align-items: center;

\\\&#x20;   justify-content: space-between;

\\\&#x20;   padding: 0 18px;

}



.brand {

\\\&#x20;   display: flex;

\\\&#x20;   align-items: center;

\\\&#x20;   gap: 11px;

\\\&#x20;   font: 500 12px "DM Mono", monospace;

\\\&#x20;   letter-spacing: 1px;

}



.brand-mark {

\\\&#x20;   width: 25px;

\\\&#x20;   height: 25px;

\\\&#x20;   border: 1px solid var(--stone);

\\\&#x20;   display: grid;

\\\&#x20;   place-items: center;

\\\&#x20;   font-size: 9px;

}



.nav-links {

\\\&#x20;   display: flex;

\\\&#x20;   gap: 5px;

}



.nav-links a {

\\\&#x20;   color: var(--muted);

\\\&#x20;   text-decoration: none;

\\\&#x20;   font: 10px "DM Mono", monospace;

\\\&#x20;   letter-spacing: 1px;

\\\&#x20;   padding: 9px 12px;

\\\&#x20;   transition: .3s;

}



.nav-links a:hover,

.nav-links a.active {

\\\&#x20;   color: var(--stone-light);

\\\&#x20;   background: rgba(159,164,145,.08);

}



.status {

\\\&#x20;   display: flex;

\\\&#x20;   align-items: center;

\\\&#x20;   gap: 7px;

\\\&#x20;   font: 9px "DM Mono", monospace;

\\\&#x20;   color: var(--muted);

}



.status-dot {

\\\&#x20;   width: 6px;

\\\&#x20;   height: 6px;

\\\&#x20;   border-radius: 50%;

\\\&#x20;   background: var(--stone);

\\\&#x20;   box-shadow: 0 0 10px rgba(165,169,148,.7);

\\\&#x20;   animation: blink 2s infinite;

}



@keyframes blink {

\\\&#x20;   50% { opacity: .35; }

}



/\\\\\\\* =========================================================

\\\&#x20;  GENERAL

========================================================= \\\\\\\*/



main {

\\\&#x20;   width: min(1160px, calc(100% - 40px));

\\\&#x20;   margin: auto;

}



section {

\\\&#x20;   position: relative;

\\\&#x20;   padding: 130px 0;

}



.eyebrow {

\\\&#x20;   display: flex;

\\\&#x20;   align-items: center;

\\\&#x20;   gap: 10px;

\\\&#x20;   color: var(--stone);

\\\&#x20;   font: 10px "DM Mono", monospace;

\\\&#x20;   letter-spacing: 2px;

\\\&#x20;   margin-bottom: 24px;

}



.eyebrow::before {

\\\&#x20;   content: "";

\\\&#x20;   width: 24px;

\\\&#x20;   height: 1px;

\\\&#x20;   background: var(--stone);

}



.section-title {

\\\&#x20;   font-size: clamp(36px, 5vw, 68px);

\\\&#x20;   line-height: 1;

\\\&#x20;   letter-spacing: -3px;

\\\&#x20;   font-weight: 700;

\\\&#x20;   max-width: 700px;

}



.section-title span {

\\\&#x20;   color: var(--muted);

}



.section-number {

\\\&#x20;   position: absolute;

\\\&#x20;   right: 0;

\\\&#x20;   top: 130px;

\\\&#x20;   font: 11px "DM Mono", monospace;

\\\&#x20;   color: var(--stone-dark);

}



/\\\\\\\* =========================================================

\\\&#x20;  HERO

========================================================= \\\\\\\*/



.hero {

\\\&#x20;   min-height: 100vh;

\\\&#x20;   display: grid;

\\\&#x20;   grid-template-columns: 1.2fr .8fr;

\\\&#x20;   align-items: center;

\\\&#x20;   padding-top: 120px;

}



.hero-left {

\\\&#x20;   position: relative;

}



.hero-kicker {

\\\&#x20;   display: inline-flex;

\\\&#x20;   border: 1px solid var(--line);

\\\&#x20;   padding: 8px 11px;

\\\&#x20;   color: var(--muted);

\\\&#x20;   font: 9px "DM Mono", monospace;

\\\&#x20;   margin-bottom: 25px;

\\\&#x20;   background: rgba(20,22,19,.35);

}



.hero h1 {

\\\&#x20;   font-size: clamp(48px, 7vw, 90px);

\\\&#x20;   line-height: .92;

\\\&#x20;   letter-spacing: -5px;

\\\&#x20;   font-weight: 700;

\\\&#x20;   max-width: 800px;

}



.hero h1 .muted {

\\\&#x20;   color: var(--muted);

}



.hero-description {

\\\&#x20;   margin-top: 28px;

\\\&#x20;   max-width: 510px;

\\\&#x20;   color: #85897d;

\\\&#x20;   line-height: 1.8;

\\\&#x20;   font-size: 14px;

}



.hero-actions {

\\\&#x20;   display: flex;

\\\&#x20;   gap: 12px;

\\\&#x20;   margin-top: 30px;

}



.button {

\\\&#x20;   text-decoration: none;

\\\&#x20;   color: var(--stone-light);

\\\&#x20;   border: 1px solid var(--line-bright);

\\\&#x20;   padding: 13px 17px;

\\\&#x20;   font: 10px "DM Mono", monospace;

\\\&#x20;   letter-spacing: 1px;

\\\&#x20;   transition: .3s;

\\\&#x20;   position: relative;

\\\&#x20;   overflow: hidden;

}



.button::before {

\\\&#x20;   content: "";

\\\&#x20;   position: absolute;

\\\&#x20;   inset: 0;

\\\&#x20;   background: var(--stone-light);

\\\&#x20;   transform: translateY(100%);

\\\&#x20;   transition: .35s;

\\\&#x20;   z-index: -1;

}



.button:hover {

\\\&#x20;   color: #10110f;

}



.button:hover::before {

\\\&#x20;   transform: translateY(0);

}



.hero-system {

\\\&#x20;   display: flex;

\\\&#x20;   justify-content: center;

}



.system-orb {

\\\&#x20;   width: 330px;

\\\&#x20;   height: 330px;

\\\&#x20;   position: relative;

\\\&#x20;   display: grid;

\\\&#x20;   place-items: center;

}



.system-orb::before,

.system-orb::after {

\\\&#x20;   content: "";

\\\&#x20;   position: absolute;

\\\&#x20;   border: 1px solid rgba(164,168,148,.18);

\\\&#x20;   border-radius: 50%;

}



.system-orb::before {

\\\&#x20;   inset: 20px;

\\\&#x20;   animation: spin 18s linear infinite;

}



.system-orb::after {

\\\&#x20;   inset: 55px;

\\\&#x20;   border-style: dashed;

\\\&#x20;   animation: spin 13s linear infinite reverse;

}



@keyframes spin {

\\\&#x20;   to { transform: rotate(360deg); }

}



.orb-core {

\\\&#x20;   width: 120px;

\\\&#x20;   height: 120px;

\\\&#x20;   border: 1px solid var(--stone-dark);

\\\&#x20;   border-radius: 50%;

\\\&#x20;   display: grid;

\\\&#x20;   place-items: center;

\\\&#x20;   background:

\\\&#x20;       radial-gradient(circle, rgba(168,172,153,.15), transparent 65%),

\\\&#x20;       rgba(10,11,10,.8);

\\\&#x20;   box-shadow:

\\\&#x20;       inset 0 0 50px rgba(164,168,148,.08),

\\\&#x20;       0 0 50px rgba(164,168,148,.05);

}



.orb-core span {

\\\&#x20;   font: 14px "DM Mono", monospace;

\\\&#x20;   color: var(--stone);

}



.orbit-label {

\\\&#x20;   position: absolute;

\\\&#x20;   color: var(--stone-dark);

\\\&#x20;   font: 8px "DM Mono", monospace;

\\\&#x20;   letter-spacing: 1px;

}



.label-a { top: 10px; left: 50%; }

.label-b { right: 0; top: 48%; }

.label-c { bottom: 18px; left: 18%; }



/\\\\\\\* =========================================================

\\\&#x20;  ABOUT

========================================================= \\\\\\\*/



.about-grid {

\\\&#x20;   display: grid;

\\\&#x20;   grid-template-columns: .8fr 1.2fr;

\\\&#x20;   gap: 80px;

\\\&#x20;   margin-top: 65px;

}



.about-label {

\\\&#x20;   font: 11px "DM Mono", monospace;

\\\&#x20;   color: var(--stone);

}



.about-text {

\\\&#x20;   font-size: 19px;

\\\&#x20;   line-height: 1.75;

\\\&#x20;   color: #a1a499;

}



.about-text strong {

\\\&#x20;   color: var(--stone-light);

\\\&#x20;   font-weight: 600;

}



.info-grid {

\\\&#x20;   margin-top: 45px;

\\\&#x20;   display: grid;

\\\&#x20;   grid-template-columns: repeat(3, 1fr);

\\\&#x20;   gap: 1px;

\\\&#x20;   border: 1px solid var(--line);

\\\&#x20;   background: var(--line);

}



.info-card {

\\\&#x20;   background: rgba(13,14,13,.75);

\\\&#x20;   padding: 22px;

}



.info-card small {

\\\&#x20;   display: block;

\\\&#x20;   color: var(--stone-dark);

\\\&#x20;   font: 9px "DM Mono", monospace;

\\\&#x20;   margin-bottom: 10px;

}



.info-card strong {

\\\&#x20;   color: var(--stone-light);

\\\&#x20;   font-size: 13px;

}



/\\\\\\\* =========================================================

\\\&#x20;  PROJECTS

========================================================= \\\\\\\*/



.projects {

\\\&#x20;   margin-top: 65px;

\\\&#x20;   border-top: 1px solid var(--line);

}



.project {

\\\&#x20;   min-height: 150px;

\\\&#x20;   border-bottom: 1px solid var(--line);

\\\&#x20;   display: grid;

\\\&#x20;   grid-template-columns: 70px 1fr 220px 30px;

\\\&#x20;   align-items: center;

\\\&#x20;   gap: 20px;

\\\&#x20;   position: relative;

\\\&#x20;   transition: .4s;

}



.project::before {

\\\&#x20;   content: "";

\\\&#x20;   position: absolute;

\\\&#x20;   inset: 0;

\\\&#x20;   background: linear-gradient(90deg, rgba(157,162,143,.07), transparent);

\\\&#x20;   transform: scaleX(0);

\\\&#x20;   transform-origin: left;

\\\&#x20;   transition: .45s;

}



.project:hover::before {

\\\&#x20;   transform: scaleX(1);

}



.project-number {

\\\&#x20;   color: var(--stone-dark);

\\\&#x20;   font: 10px "DM Mono", monospace;

\\\&#x20;   position: relative;

}



.project-name {

\\\&#x20;   font-size: 24px;

\\\&#x20;   color: var(--stone-light);

\\\&#x20;   position: relative;

}



.project-description {

\\\&#x20;   color: var(--muted);

\\\&#x20;   font-size: 11px;

\\\&#x20;   line-height: 1.6;

\\\&#x20;   position: relative;

}



.project-arrow {

\\\&#x20;   color: var(--stone);

\\\&#x20;   font-size: 18px;

\\\&#x20;   transition: .3s;

\\\&#x20;   position: relative;

}



.project:hover .project-arrow {

\\\&#x20;   transform: translateX(5px);

}



/\\\\\\\* =========================================================

\\\&#x20;  LAB

========================================================= \\\\\\\*/



.lab-grid {

\\\&#x20;   margin-top: 65px;

\\\&#x20;   display: grid;

\\\&#x20;   grid-template-columns: repeat(4, 1fr);

\\\&#x20;   gap: 8px;

}



.lab-card {

\\\&#x20;   min-height: 190px;

\\\&#x20;   border: 1px solid var(--line);

\\\&#x20;   background: rgba(20,22,19,.55);

\\\&#x20;   padding: 20px;

\\\&#x20;   position: relative;

\\\&#x20;   overflow: hidden;

\\\&#x20;   transition: .4s;

}



.lab-card:hover {

\\\&#x20;   border-color: var(--line-bright);

\\\&#x20;   transform: translateY(-5px);

\\\&#x20;   background: rgba(30,32,28,.65);

}



.lab-index {

\\\&#x20;   font: 9px "DM Mono", monospace;

\\\&#x20;   color: var(--stone-dark);

}



.lab-icon {

\\\&#x20;   position: absolute;

\\\&#x20;   right: 20px;

\\\&#x20;   top: 20px;

\\\&#x20;   width: 25px;

\\\&#x20;   height: 25px;

\\\&#x20;   border: 1px solid var(--stone-dark);

}



.lab-icon::before,

.lab-icon::after {

\\\&#x20;   content: "";

\\\&#x20;   position: absolute;

\\\&#x20;   background: var(--stone-dark);

}



.lab-icon::before {

\\\&#x20;   width: 100%;

\\\&#x20;   height: 1px;

\\\&#x20;   top: 50%;

}



.lab-icon::after {

\\\&#x20;   height: 100%;

\\\&#x20;   width: 1px;

\\\&#x20;   left: 50%;

}



.lab-card h3 {

\\\&#x20;   margin-top: 70px;

\\\&#x20;   font-size: 17px;

}



.lab-card p {

\\\&#x20;   margin-top: 10px;

\\\&#x20;   color: var(--muted);

\\\&#x20;   font-size: 11px;

\\\&#x20;   line-height: 1.6;

}



/\\\\\\\* =========================================================

\\\&#x20;  SKILLS

========================================================= \\\\\\\*/



.stack {

\\\&#x20;   margin-top: 60px;

\\\&#x20;   display: grid;

\\\&#x20;   grid-template-columns: repeat(2, 1fr);

\\\&#x20;   border-top: 1px solid var(--line);

}



.stack-item {

\\\&#x20;   min-height: 90px;

\\\&#x20;   padding: 25px 0;

\\\&#x20;   border-bottom: 1px solid var(--line);

\\\&#x20;   display: flex;

\\\&#x20;   justify-content: space-between;

\\\&#x20;   align-items: center;

}



.stack-item:nth-child(odd) {

\\\&#x20;   padding-right: 35px;

\\\&#x20;   border-right: 1px solid var(--line);

}



.stack-item:nth-child(even) {

\\\&#x20;   padding-left: 35px;

}



.stack-name {

\\\&#x20;   color: var(--stone-light);

\\\&#x20;   font-size: 14px;

}



.stack-type {

\\\&#x20;   color: var(--stone-dark);

\\\&#x20;   font: 9px "DM Mono", monospace;

}



/\\\\\\\* =========================================================

\\\&#x20;  CONTACT

========================================================= \\\\\\\*/



.contact {

\\\&#x20;   min-height: 70vh;

\\\&#x20;   display: grid;

\\\&#x20;   place-items: center;

\\\&#x20;   text-align: center;

}



.contact .section-title {

\\\&#x20;   margin: auto;

}



.contact-text {

\\\&#x20;   max-width: 520px;

\\\&#x20;   margin: 25px auto;

\\\&#x20;   color: var(--muted);

\\\&#x20;   line-height: 1.8;

\\\&#x20;   font-size: 14px;

}



.contact-button {

\\\&#x20;   display: inline-block;

\\\&#x20;   margin-top: 15px;

}



/\\\\\\\* =========================================================

\\\&#x20;  FOOTER

========================================================= \\\\\\\*/



footer {

\\\&#x20;   border-top: 1px solid var(--line);

\\\&#x20;   padding: 25px 0;

\\\&#x20;   display: flex;

\\\&#x20;   justify-content: space-between;

\\\&#x20;   color: var(--stone-dark);

\\\&#x20;   font: 9px "DM Mono", monospace;

\\\&#x20;   letter-spacing: 1px;

}



/\\\\\\\* =========================================================

\\\&#x20;  REVEAL

========================================================= \\\\\\\*/



.reveal {

\\\&#x20;   opacity: 0;

\\\&#x20;   transform: translateY(25px);

\\\&#x20;   transition: opacity .8s ease, transform .8s ease;

}



.reveal.visible {

\\\&#x20;   opacity: 1;

\\\&#x20;   transform: translateY(0);

}



/\\\\\\\* =========================================================

\\\&#x20;  RESPONSIVE

========================================================= \\\\\\\*/



@media (max-width: 850px) {



\\\&#x20;   body {

\\\&#x20;       cursor: auto;

\\\&#x20;   }



\\\&#x20;   .cursor {

\\\&#x20;       display: none;

\\\&#x20;   }



\\\&#x20;   nav {

\\\&#x20;       width: calc(100% - 24px);

\\\&#x20;   }



\\\&#x20;   .nav-links {

\\\&#x20;       display: none;

\\\&#x20;   }



\\\&#x20;   main {

\\\&#x20;       width: calc(100% - 28px);

\\\&#x20;   }



\\\&#x20;   .hero {

\\\&#x20;       grid-template-columns: 1fr;

\\\&#x20;       gap: 60px;

\\\&#x20;   }



\\\&#x20;   .hero h1 {

\\\&#x20;       letter-spacing: -3px;

\\\&#x20;   }



\\\&#x20;   .hero-system {

\\\&#x20;       justify-content: flex-start;

\\\&#x20;   }



\\\&#x20;   .system-orb {

\\\&#x20;       width: 250px;

\\\&#x20;       height: 250px;

\\\&#x20;   }



\\\&#x20;   .about-grid {

\\\&#x20;       grid-template-columns: 1fr;

\\\&#x20;       gap: 30px;

\\\&#x20;   }



\\\&#x20;   .info-grid {

\\\&#x20;       grid-template-columns: 1fr;

\\\&#x20;   }



\\\&#x20;   .project {

\\\&#x20;       grid-template-columns: 40px 1fr 25px;

\\\&#x20;   }



\\\&#x20;   .project-description {

\\\&#x20;       display: none;

\\\&#x20;   }



\\\&#x20;   .lab-grid {

\\\&#x20;       grid-template-columns: repeat(2, 1fr);

\\\&#x20;   }



\\\&#x20;   .section-number {

\\\&#x20;       display: none;

\\\&#x20;   }

}



@media (max-width: 520px) {



\\\&#x20;   section {

\\\&#x20;       padding: 90px 0;

\\\&#x20;   }



\\\&#x20;   .hero {

\\\&#x20;       padding-top: 120px;

\\\&#x20;   }



\\\&#x20;   .hero h1 {

\\\&#x20;       font-size: 47px;

\\\&#x20;   }



\\\&#x20;   .section-title {

\\\&#x20;       font-size: 40px;

\\\&#x20;       letter-spacing: -2px;

\\\&#x20;   }



\\\&#x20;   .hero-description {

\\\&#x20;       font-size: 13px;

\\\&#x20;   }



\\\&#x20;   .hero-actions {

\\\&#x20;       flex-wrap: wrap;

\\\&#x20;   }



\\\&#x20;   .lab-grid {

\\\&#x20;       grid-template-columns: 1fr;

\\\&#x20;   }



\\\&#x20;   .stack {

\\\&#x20;       grid-template-columns: 1fr;

\\\&#x20;   }



\\\&#x20;   .stack-item:nth-child(odd) {

\\\&#x20;       padding-right: 0;

\\\&#x20;       border-right: none;

\\\&#x20;   }



\\\&#x20;   .stack-item:nth-child(even) {

\\\&#x20;       padding-left: 0;

\\\&#x20;   }



\\\&#x20;   footer {

\\\&#x20;       flex-direction: column;

\\\&#x20;       gap: 10px;

\\\&#x20;   }

}


</head>



<body>



<!-- =====================================================

\\\&#x20;    BACKGROUND




<div id="world">



\&#x20;   <div class="ambient one"></div>

\&#x20;   <div class="ambient two"></div>

\&#x20;   <div class="ambient three"></div>



\&#x20;   <div class="grid"></div>



\&#x20;   <div class="orbit one"></div>

\&#x20;   <div class="orbit two"></div>

\&#x20;   <div class="orbit three"></div>



\&#x20;   <div class="circuit">

\&#x20;       <span class="line1"></span>

\&#x20;       <span class="line2"></span>

\&#x20;       <span class="line3"></span>

\&#x20;   </div>



\&#x20;   <div class="code-fragments">

\&#x20;       <span>const system = initialize();</span>

\&#x20;       <span>\\\&lt;interface /\\\&gt;</span>

\&#x20;       <span>01 // BUILD // TEST // DEPLOY</span>

\&#x20;       <span>await createFuture();</span>

\&#x20;   </div>



</div>



<div class="grain"></div>





<!-- =====================================================

\\\&#x20;    CURSOR




<div class="cursor cursor-core" id="cursorCore"></div>



<div class="cursor cursor-reticle" id="cursorReticle">

\&#x20;   <span class="corner c1"></span>

\&#x20;   <span class="corner c2"></span>

\&#x20;   <span class="corner c3"></span>

\&#x20;   <span class="corner c4"></span>

</div>





<!-- =====================================================

\\\&#x20;    NAVIGATION




<nav>



\&#x20;   <div class="brand">

\&#x20;       <div class="brand-mark">W</div>

\&#x20;       <span>WILFREDO.DEV</span>

\&#x20;   </div>



\&#x20;   <div class="nav-links">

\&#x20;       <a href="#home" class="active">HOME</a>

\&#x20;       <a href="#about">ABOUT</a>

\&#x20;       <a href="#work">WORK</a>

\&#x20;       <a href="#lab">LAB</a>

\&#x20;       <a href="#contact">CONTACT</a>

\&#x20;   </div>



\&#x20;   <div class="status">

\&#x20;       <span class="status-dot"></span>

\&#x20;       SYSTEM ONLINE

\&#x20;   </div>



</nav>





<main>



<!-- =====================================================

\\\&#x20;    HERO




<section class="hero" id="home">



\&#x20;   <div class="hero-left reveal">



\&#x20;       <div class="hero-kicker">

\&#x20;           // DIGITAL SYSTEMS / WEB DEVELOPMENT

\&#x20;       </div>



\&#x20;       <h1>

\&#x20;          KIEN<br>

\&#x20;           <span class="muted">DE VERA</span>

\&#x20;       </h1>



\&#x20;       <p class="hero-description">

\&#x20;           Programmer and digital builder focused on creating

\&#x20;           an interfaces, practical systems, and

\&#x20;           experiences where technology meets design.

\&#x20;       </p>



\&#x20;       <div class="hero-actions">

\&#x20;           <a href="#work" class="button interactive">

\&#x20;               VIEW WORK →

\&#x20;           </a>



\&#x20;           <a href="#contact" class="button interactive">

\&#x20;               START A PROJECT

\&#x20;           </a>

\&#x20;       </div>



\&#x20;   </div>





\&#x20;   <div class="hero-system reveal">



\&#x20;       <div class="system-orb">



\&#x20;           <div class="orb-core">

\&#x20;               <span> K </span>

\&#x20;           </div>



\&#x20;           <span class="orbit-label label-a">

\&#x20;               CORE\\\_01

\&#x20;           </span>



\&#x20;           <span class="orbit-label label-b">

\&#x20;               ONLINE

\&#x20;           </span>



\&#x20;           <span class="orbit-label label-c">

\&#x20;               DEV.SYSTEM

\&#x20;           </span>



\&#x20;       </div>



\&#x20;   </div>



</section>





<!-- =====================================================

\\\&#x20;    ABOUT




<section id="about">



\&#x20;   <span class="section-number">01 / 04</span>



\&#x20;   <div class="eyebrow reveal">

\&#x20;       THE PROGRAMMER

\&#x20;   </div>



\&#x20;   <h2 class="section-title reveal">

\&#x20;       Building with logic.<br>

\&#x20;       <span>Designing with intent.</span>

\&#x20;   </h2>



\&#x20;   <div class="about-grid reveal">



\&#x20;       <div class="about-label">

\&#x20;           PROFILE / 001

\&#x20;       </div>



\&#x20;       <div>



\&#x20;           <p class="about-text">

\&#x20;               I'm <strong>Kien De Vera</strong>,

\&#x20;               a programmer interested in web development,

\&#x20;               software systems, networking, and digital

\&#x20;               experiences.

\&#x20;               <br><br>

\&#x20;               I enjoy turning ideas into functional interfaces

\&#x20;               and continuously experimenting with better ways

\&#x20;               to build, solve, and communicate through technology.

\&#x20;           </p>



\&#x20;           <div class="info-grid">



\&#x20;               <div class="info-card">

\&#x20;                   <small>ROLE</small>

\&#x20;                   <strong>PROGRAMMER</strong>

\&#x20;               </div>



\&#x20;               <div class="info-card">

\&#x20;                   <small>FOCUS</small>

\&#x20;                   <strong>WEB / SYSTEMS</strong>

\&#x20;               </div>



\&#x20;               <div class="info-card">

\&#x20;                   <small>STATUS</small>

\&#x20;                   <strong>BUILDING</strong>

\&#x20;               </div>



\&#x20;           </div>



\&#x20;       </div>



\&#x20;   </div>



</section>





<!-- =====================================================

\\\&#x20;    WORK




<section id="work">



\&#x20;   <span class="section-number">02 / 04</span>



\&#x20;   <div class="eyebrow reveal">

\&#x20;       SELECTED WORK

\&#x20;   </div>



\&#x20;   <h2 class="section-title reveal">

\&#x20;       Projects that turn<br>

\&#x20;       <span>ideas into systems.</span>

\&#x20;   </h2>



\&#x20;   <div class="projects reveal">



\&#x20;       <div class="project interactive">



\&#x20;           <div class="project-number">01</div>



\&#x20;           <div class="project-name">

\&#x20;               CITE Event Platform

\&#x20;           </div>



\&#x20;           <div class="project-description">

\&#x20;               Event registration, participant monitoring,

\&#x20;               rosters and real-time event information.

\&#x20;           </div>



\&#x20;           <div class="project-arrow">↗</div>



\&#x20;       </div>





\&#x20;       <div class="project interactive">



\&#x20;           <div class="project-number">02</div>



\&#x20;           <div class="project-name">

\&#x20;               Network Infrastructure

\&#x20;           </div>



\&#x20;           <div class="project-description">

\&#x20;               VLAN configuration, DHCP, server connectivity

\&#x20;               and structured network environments.

\&#x20;           </div>



\&#x20;           <div class="project-arrow">↗</div>



\&#x20;       </div>





\&#x20;       <div class="project interactive">



\&#x20;           <div class="project-number">03</div>



\&#x20;           <div class="project-name">

\&#x20;               Digital Portfolio

\&#x20;           </div>



\&#x20;           <div class="project-description">

\&#x20;               Interactive personal identity system combining

\&#x20;               development, motion and visual design.

\&#x20;           </div>



\&#x20;           <div class="project-arrow">↗</div>



\&#x20;       </div>





\&#x20;       <div class="project interactive">



\&#x20;           <div class="project-number">04</div>



\&#x20;           <div class="project-name">

\&#x20;               Student Information System

\&#x20;           </div>



\&#x20;           <div class="project-description">

\&#x20;               Conceptual digital system for organizing

\&#x20;               student information and administrative workflows.

\&#x20;           </div>



\&#x20;           <div class="project-arrow">↗</div>



\&#x20;       </div>



\&#x20;   </div>



</section>





<!-- =====================================================

\\\&#x20;    DIGITAL LAB




<section id="lab">



\&#x20;   <span class="section-number">03 / 04</span>



\&#x20;   <div class="eyebrow reveal">

\&#x20;       DIGITAL LAB

\&#x20;   </div>



\&#x20;   <h2 class="section-title reveal">

\&#x20;       Tools inside<br>

\&#x20;       <span>the workspace.</span>

\&#x20;   </h2>





\&#x20;   <div class="lab-grid reveal">



\&#x20;       <div class="lab-card interactive">



\&#x20;           <span class="lab-index">01</span>



\&#x20;           <div class="lab-icon"></div>



\&#x20;           <h3>Frontend</h3>



\&#x20;           <p>

\&#x20;               HTML, CSS, JavaScript and interactive

\&#x20;               interface development.

\&#x20;           </p>



\&#x20;       </div>





\&#x20;       <div class="lab-card interactive">



\&#x20;           <span class="lab-index">02</span>



\&#x20;           <div class="lab-icon"></div>



\&#x20;           <h3>Programming</h3>



\&#x20;           <p>

\&#x20;               Logic, algorithms, data handling and

\&#x20;               application development.

\&#x20;           </p>



\&#x20;       </div>





\&#x20;       <div class="lab-card interactive">



\&#x20;           <span class="lab-index">03</span>



\&#x20;           <div class="lab-icon"></div>



\&#x20;           <h3>Networking</h3>



\&#x20;           <p>

\&#x20;               Network configuration, VLANs, DHCP,

\&#x20;               servers and connectivity.

\&#x20;           </p>



\&#x20;       </div>





\&#x20;       <div class="lab-card interactive">



\&#x20;           <span class="lab-index">04</span>



\&#x20;           <div class="lab-icon"></div>



\&#x20;           <h3>UI / UX</h3>



\&#x20;           <p>

\&#x20;               Visual systems, interaction design,

\&#x20;               motion and digital experiences.

\&#x20;           </p>



\&#x20;       </div>



\&#x20;   </div>





\&#x20;   <div class="stack reveal">



\&#x20;       <div class="stack-item">

\&#x20;           <span class="stack-name">HTML / CSS</span>

\&#x20;           <span class="stack-type">FRONTEND</span>

\&#x20;       </div>



\&#x20;       <div class="stack-item">

\&#x20;           <span class="stack-name">JAVASCRIPT</span>

\&#x20;           <span class="stack-type">LOGIC</span>

\&#x20;       </div>



\&#x20;       <div class="stack-item">

\&#x20;           <span class="stack-name">NETWORKING</span>

\&#x20;           <span class="stack-type">INFRASTRUCTURE</span>

\&#x20;       </div>



\&#x20;       <div class="stack-item">

\&#x20;           <span class="stack-name">DATABASES</span>

\&#x20;           <span class="stack-type">DATA</span>

\&#x20;       </div>



\&#x20;       <div class="stack-item">

\&#x20;           <span class="stack-name">GIT / VERSION CONTROL</span>

\&#x20;           <span class="stack-type">WORKFLOW</span>

\&#x20;       </div>



\&#x20;       <div class="stack-item">

\&#x20;           <span class="stack-name">UI / UX</span>

\&#x20;           <span class="stack-type">DESIGN</span>

\&#x20;       </div>



\&#x20;   </div>



</section>





<!-- =====================================================

\\\&#x20;    CONTACT




<section class="contact" id="contact">



\&#x20;   <div class="reveal">



\&#x20;       <div class="eyebrow" style="justify-content:center;">

\&#x20;           LET'S BUILD

\&#x20;       </div>



\&#x20;       <h2 class="section-title">

\&#x20;           Have an idea?<br>

\&#x20;           <span>Let's make it real.</span>

\&#x20;       </h2>



\&#x20;       <p class="contact-text">

\&#x20;           Whether it's a website, digital system, network

\&#x20;           project, or experimental idea — this is where the

\&#x20;           next build begins.

\&#x20;       </p>



\&#x20;       <a href="mailto:kienvalantindeveral@gmail.com"

\&#x20;          class="button contact-button interactive">

\&#x20;           CONTACT DE VERA →

\&#x20;       </a>



\&#x20;   </div>



</section>





<footer>



\&#x20;   <span>© 2026 KIEN DE VERA</span>



\&#x20;   <span>

\&#x20;       DESIGNED / DEVELOPED BY KIEN

\&#x20;   </span>



</footer>



</main>





<script>



/\\\\\\\* =========================================================

\\\&#x20;  CUSTOM CURSOR

========================================================= \\\\\\\*/



const cursorCore = document.getElementById("cursorCore");

const cursorReticle = document.getElementById("cursorReticle");



let mouseX = window.innerWidth / 2;

let mouseY = window.innerHeight / 2;



let coreX = mouseX;

let coreY = mouseY;



let reticleX = mouseX;

let reticleY = mouseY;



window.addEventListener("mousemove", (e) => {



\\\&#x20;   mouseX = e.clientX;

\\\&#x20;   mouseY = e.clientY;



});



function animateCursor() {



\\\&#x20;   coreX += (mouseX - coreX) \\\\\\\* .35;

\\\&#x20;   coreY += (mouseY - coreY) \\\\\\\* .35;



\\\&#x20;   reticleX += (mouseX - reticleX) \\\\\\\* .13;

\\\&#x20;   reticleY += (mouseY - reticleY) \\\\\\\* .13;



\\\&#x20;   cursorCore.style.left = coreX + "px";

\\\&#x20;   cursorCore.style.top = coreY + "px";



\\\&#x20;   cursorReticle.style.left = reticleX + "px";

\\\&#x20;   cursorReticle.style.top = reticleY + "px";



\\\&#x20;   requestAnimationFrame(animateCursor);

}



animateCursor();





/\\\\\\\* Cursor interaction \\\\\\\*/



document.querySelectorAll(".interactive, a, button").forEach(element => {



\\\&#x20;   element.addEventListener("mouseenter", () => {

\\\&#x20;       document.body.classList.add("hovering");

\\\&#x20;   });



\\\&#x20;   element.addEventListener("mouseleave", () => {

\\\&#x20;       document.body.classList.remove("hovering");

\\\&#x20;   });



});





/\\\\\\\* =========================================================

\\\&#x20;  REVEAL ON SCROLL

========================================================= \\\\\\\*/



const observer = new IntersectionObserver(

\\\&#x20;   entries => {



\\\&#x20;       entries.forEach(entry => {



\\\&#x20;           if (entry.isIntersecting) {

\\\&#x20;               entry.target.classList.add("visible");

\\\&#x20;           }



\\\&#x20;       });



\\\&#x20;   },

\\\&#x20;   {

\\\&#x20;       threshold: .12

\\\&#x20;   }

);



document.querySelectorAll(".reveal").forEach(element => {

\\\&#x20;   observer.observe(element);

});





/\\\\\\\* =========================================================

\\\&#x20;  ACTIVE NAVIGATION

========================================================= \\\\\\\*/



const sections = document.querySelectorAll("section\\\\\\\[id]");

const navLinks = document.querySelectorAll(".nav-links a");



const sectionObserver = new IntersectionObserver(

\\\&#x20;   entries => {



\\\&#x20;       entries.forEach(entry => {



\\\&#x20;           if (entry.isIntersecting) {



\\\&#x20;               navLinks.forEach(link => {

\\\&#x20;                   link.classList.remove("active");

\\\&#x20;               });



\\\&#x20;               const active =

\\\&#x20;                   document.querySelector(

\\\&#x20;                       .nav-links a\\\\\\\[href="#${entry.target.id}"]

\\\&#x20;                   );



\\\&#x20;               if (active) {

\\\&#x20;                   active.classList.add("active");

\\\&#x20;               }



\\\&#x20;           }



\\\&#x20;       });



\\\&#x20;   },

\\\&#x20;   {

\\\&#x20;       threshold: .45

\\\&#x20;   }

);



sections.forEach(section => {

\\\&#x20;   sectionObserver.observe(section);

});





/\\\\\\\* =========================================================

\\\&#x20;  MOUSE PARALLAX BACKGROUND

========================================================= \\\\\\\*/



const grid = document.querySelector(".grid");

const ambientOne = document.querySelector(".ambient.one");

const ambientTwo = document.querySelector(".ambient.two");



window.addEventListener("mousemove", e => {



\\\&#x20;   const x = (e.clientX / window.innerWidth - .5);

\\\&#x20;   const y = (e.clientY / window.innerHeight - .5);



\\\&#x20;   grid.style.transform = `

\\\&#x20;       perspective(700px)

\\\&#x20;       rotateX(58deg)

\\\&#x20;       translate(${x \\\\\\\* -18}px, ${28 + y \\\\\\\* -8}%)

\\\&#x20;   `;



\\\&#x20;   ambientOne.style.transform =

\\\&#x20;       translate(${x \\\\\\\* 35}px, ${y \\\\\\\* 35}px);



\\\&#x20;   ambientTwo.style.transform =

\\\&#x20;       translate(${x \\\\\\\* -25}px, ${y \\\\\\\* -25}px);



});





/\\\\\\\* =========================================================

\\\&#x20;  PROJECT TILT

========================================================= \\\\\\\*/



document.querySelectorAll(".lab-card").forEach(card => {



\\\&#x20;   card.addEventListener("mousemove", e => {



\\\&#x20;       const rect = card.getBoundingClientRect();



\\\&#x20;       const x =

\\\&#x20;           (e.clientX - rect.left) /

\\\&#x20;           rect.width - .5;



\\\&#x20;       const y =

\\\&#x20;           (e.clientY - rect.top) /

\\\&#x20;           rect.height - .5;



\\\&#x20;       card.style.transform = `

\\\&#x20;           perspective(700px)

\\\&#x20;           rotateX(${y \\\\\\\* -3}deg)

\\\&#x20;           rotateY(${x \\\\\\\* 3}deg)

\\\&#x20;           translateY(-5px)

\\\&#x20;       `;



\\\&#x20;   });



\\\&#x20;   card.addEventListener("mouseleave", () => {



\\\&#x20;       card.style.transform = "";



\\\&#x20;   });



});





/\\\\\\\* =========================================================

\\\&#x20;  SYSTEM STATUS

========================================================= \\\\\\\*/



const status = document.querySelector(".status");



setInterval(() => {



\\\&#x20;   const states = \\\\\\\[

\\\&#x20;       "SYSTEM ONLINE",

\\\&#x20;       "READY TO BUILD",

\\\&#x20;       "DEV MODE ACTIVE"

\\\&#x20;   ];



\\\&#x20;   const current =

\\\&#x20;       states\\\\\\\[Math.floor(Math.random() \\\\\\\* states.length)];



\\\&#x20;   status.lastChild.textContent = " " + current;



}, 4000);






</body>

</html>



