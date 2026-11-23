[index.html](https://github.com/user-attachments/files/35271580/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="theme-color" content="#090909">
  <title>CANDICE MOVIE | A Short Film</title>

  <style>
    :root {
      color-scheme: dark;
      --background: #090909;
      --foreground: #eee9e3;
      --muted: #aaa29b;
      --accent: #b4413e;
    }

    * {
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      background: var(--background);
      color: var(--foreground);
      font-family: Georgia, "Times New Roman", serif;
    }

    a {
      color: inherit;
    }

    .hero {
      min-height: 88vh;
      display: grid;
      align-items: end;
      padding: 3rem clamp(1.5rem, 7vw, 7rem);
      position: relative;
      isolation: isolate;
      overflow: hidden;
      background:
        linear-gradient(0deg, #090909 0%, rgba(9, 9, 9, .45) 70%),
        linear-gradient(90deg, rgba(9, 9, 9, .7), rgba(9, 9, 9, .15)),
        url("https://images.unsplash.com/photo-1593359677879-a4bb92f829d1?auto=format&fit=crop&w=2000&q=85")
        center / cover no-repeat;
    }

    /* Subtle static texture over the TV image */
    .hero::before {
      content: "";
      position: absolute;
      inset: -50%;
      z-index: 0;
      pointer-events: none;
      opacity: .13;
      mix-blend-mode: screen;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 180 180' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.65'/%3E%3C/svg%3E");
      animation: static-shift .18s steps(2) infinite;
    }

    .hero::after {
      content: "";
      position: absolute;
      inset: 0;
      z-index: 0;
      pointer-events: none;
      background: rgba(7, 8, 7, .3);
    }

    @keyframes static-shift {
      0%   { transform: translate(0, 0); }
      25%  { transform: translate(-1%, 1%); }
      50%  { transform: translate(1%, -1%); }
      75%  { transform: translate(1%, 1%); }
      100% { transform: translate(-1%, 0); }
    }

    nav,
    .hero-content {
      position: relative;
      z-index: 1;
    }

    nav {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      display: flex;
      justify-content: space-between;
      padding: 1.5rem clamp(1.5rem, 7vw, 7rem);
      font: 0.75rem/1.2 Arial, sans-serif;
      letter-spacing: .18em;
      text-transform: uppercase;
    }

    nav a {
      color: var(--foreground);
      text-decoration: none;
    }

    nav a:hover {
      color: var(--accent);
    }

    .eyebrow {
      color: #d1c5bb;
      font: 0.75rem/1.5 Arial, sans-serif;
      letter-spacing: .28em;
      text-transform: uppercase;
    }

    h1 {
      max-width: 900px;
      margin: .5rem 0 1rem;
      font-size: clamp(3.5rem, 11vw, 9rem);
      line-height: .9;
      letter-spacing: .035em;
      font-weight: 400;
    }

    .hero p {
      max-width: 34rem;
      color: #ddd5cd;
      font-size: clamp(1rem, 2vw, 1.25rem);
      line-height: 1.7;
    }

    .button {
      display: inline-block;
      margin-top: 1.25rem;
      padding: .9rem 1.2rem;
      border: 1px solid rgba(238, 233, 227, .65);
      text-decoration: none;
      font: 0.72rem Arial, sans-serif;
      letter-spacing: .15em;
      text-transform: uppercase;
      transition: background .2s, border-color .2s;
    }

    .button:hover {
      background: var(--accent);
      border-color: var(--accent);
    }

    main section {
      padding: clamp(4rem, 9vw, 8rem) clamp(1.5rem, 18vw, 18rem);
    }

    .quote {
      text-align: center;
      border-bottom: 1px solid #292523;
    }

    blockquote {
      margin: 1.5rem 0 0;
      color: #e9dfd7;
      font-size: clamp(2.5rem, 7vw, 6rem);
      line-height: 1.05;
    }

    .synopsis {
      background: #10100f;
    }

    h2 {
      margin: 0 0 1.5rem;
      font-size: clamp(2rem, 5vw, 3.5rem);
      font-weight: 400;
    }

    .synopsis p {
      max-width: 45rem;
      color: #c9c1ba;
      font-size: clamp(1.1rem, 2vw, 1.4rem);
      line-height: 1.8;
    }

    .credits {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      gap: 2rem;
      border-top: 1px solid #292523;
    }

    .credit-label {
      display: block;
      margin-bottom: .6rem;
      color: var(--muted);
      font: 0.7rem Arial, sans-serif;
      letter-spacing: .18em;
      text-transform: uppercase;
    }

    .credit-name {
      font-size: 1.25rem;
    }

    footer {
      padding: 1.5rem;
      color: #827a74;
      text-align: center;
      font: 0.7rem Arial, sans-serif;
      letter-spacing: .12em;
      text-transform: uppercase;
    }

    @media (max-width: 600px) {
      .credits {
        flex-direction: column;
        gap: 2rem;
      }
    }

    @media (prefers-reduced-motion: reduce) {
      html {
        scroll-behavior: auto;
      }

      .hero::before {
        animation: none;
      }

      *,
      *::before,
      *::after {
        transition-duration: .01ms !important;
      }
    }
  </style>
</head>

<body>
  <header class="hero" id="top">
    <nav aria-label="Main navigation">
      <a href="#top">Candice Movie</a>
      <a href="#film">The Film</a>
    </nav>

    <div class="hero-content">
      <div class="eyebrow">An independent short film</div>
      <h1>CANDICE<br>MOVIE</h1>
      <p>A perfect life. A beautiful face. Something is terribly wrong.</p>
      <a class="button" href="#film">Enter the story</a>
    </div>
  </header>

  <main id="film">
    <section class="quote" aria-label="Dialogue">
      <div class="eyebrow">Who has never said</div>
      <blockquote>“It was an accident”</blockquote>
    </section>

    <section class="synopsis">
      <div class="eyebrow">A Horror Thriller from Mason Gao</div>
      <h2>Some dreams should stay dreams.</h2>
      <p>
        A devoted husband finds himself in a parallel universe—married to the
        woman of his dreams. But this seemingly perfect new life hides a dark
        reality.
      </p>
    </section>

    <section class="credits" aria-label="Film credits">
      <div>
        <span class="credit-label">Written by</span>
        <span class="credit-name">Mason Gao</span>
      </div>

      <div>
        <span class="credit-label">Directed by</span>
        <span class="credit-name">Kenny Kendawg</span>
      </div>
    </section>
  </main>

  <footer>
    CANDICE MOVIE · Independent Short Film
  </footer>
</body>
</html>
