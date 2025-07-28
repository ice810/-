<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Blog - Home</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg-dark: #111;
      --bg-post: #1c1c1c;
      --accent: #4eaaff;
      --accent-hover: #1d9eff;
      --text-light: #fff;
      --text-muted: #bbb;
    }

    body {
      margin: 0;
      font-family: 'Inter', sans-serif;
      background-color: var(--bg-dark);
      color: var(--text-light);
    }

    header {
      background-color: #181818;
      padding: 1.2rem 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.6);
    }

    header h1 {
      margin: 0;
      font-size: 2rem;
      font-weight: 600;
    }

    .lang-toggle {
      background-color: transparent;
      border: 1px solid var(--text-muted);
      color: var(--text-light);
      padding: 0.5rem 1rem;
      border-radius: 20px;
      cursor: pointer;
      font-weight: 600;
      transition: background 0.3s ease, color 0.3s ease;
    }

    .lang-toggle:hover {
      background-color: var(--accent);
      color: #000;
    }

    .container {
      max-width: 960px;
      margin: 0 auto;
      padding: 2rem 1rem;
    }

    .post {
      background-color: var(--bg-post);
      margin-bottom: 2rem;
      padding: 2rem;
      border-radius: 16px;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .post:hover {
      transform: translateY(-4px);
      box-shadow: 0 6px 20px rgba(0, 0, 0, 0.6);
    }

    .user-info {
      display: flex;
      align-items: center;
      margin-bottom: 1rem;
    }

    .user-info img {
      width: 55px;
      height: 55px;
      border-radius: 50%;
      margin-right: 15px;
      border: 2px solid var(--accent);
    }

    .username {
      font-weight: 600;
      font-size: 1.1rem;
      display: flex;
      flex-direction: column;
    }

    .username a {
      color: var(--accent);
      text-decoration: none;
    }

    .username a:hover {
      text-decoration: underline;
    }

    .followers {
      font-size: 0.9rem;
      color: var(--text-muted);
    }

    .share-button {
      margin-top: 0.7rem;
      background: linear-gradient(135deg, var(--accent), var(--accent-hover));
      border: none;
      color: #fff;
      padding: 0.45rem 1rem;
      border-radius: 12px;
      cursor: pointer;
      font-size: 0.9rem;
      font-weight: 600;
      box-shadow: 0 2px 10px rgba(78, 170, 255, 0.4);
      transition: transform 0.2s ease, background 0.3s ease;
    }

    .share-button:hover {
      transform: scale(1.05);
      background: linear-gradient(135deg, var(--accent-hover), var(--accent));
    }

    .post img, .post video {
      width: 100%;
      max-height: 480px;
      border-radius: 12px;
      object-fit: cover;
      margin-top: 0.8rem;
    }

    .caption {
      margin-top: 1rem;
      font-size: 1.15rem;
      line-height: 1.7;
      color: var(--text-muted);
    }

    footer {
      text-align: center;
      padding: 2rem 1rem;
      color: var(--text-muted);
      font-size: 0.95rem;
    }

    @media (max-width: 600px) {
      header h1 {
        font-size: 1.5rem;
      }
      .post {
        padding: 1.25rem;
      }
      .caption {
        font-size: 1rem;
      }
    }
  </style>
</head>
<body>
  <header>
    <h1 id="title">My Blog</h1>
    <button class="lang-toggle" onclick="toggleLanguage()">عربي</button>
  </header>

  <div class="container">
    <!-- Featured caption at the top -->
    <div class="post">
      <p class="caption" id="top-caption">Out here in the street standing tall all I have are bi....</p>
    </div>

    <!-- Instagram-style photo post by aa.abuwafy -->
    <div class="post">
      <div class="user-info">
        <img src="profile1.jpg" alt="aa.abuwafy">
        <span class="username">
          <a href="https://www.instagram.com/aa.abuwafy" target="_blank">aa.abuwafy</a>
          <span class="followers" id="followers-insta">160 followers</span>
        </span>
      </div>
      <img src="insta-photo1.jpg" alt="Photo by aa.abuwafy">
      <p class="caption" id="caption1">Chillin' in the city ☀️</p>
      <button class="share-button" onclick="sharePost('https://www.instagram.com/aa.abuwafy')">📤 Share</button>
    </div>

    <!-- TikTok-style video post by aa_abowafy -->
    <div class="post">
      <div class="user-info">
        <img src="profile2.jpg" alt="aa_abowafy">
        <span class="username">
          <a href="https://www.tiktok.com/@aa_abowafy" target="_blank">aa_abowafy</a>
          <span class="followers" id="followers-tt">400 followers</span>
        </span>
      </div>
      <video controls>
        <source src="tiktok-video1.mp4" type="video/mp4">
        Your browser does not support the video tag.
      </video>
      <p class="caption" id="caption2">Fun times with friends! 🎉</p>
      <button class="share-button" onclick="sharePost('https://www.tiktok.com/@aa_abowafy')">📤 Share</button>
    </div>
  </div>

  <footer>
    &copy; 2025 My Blog. All rights reserved.
  </footer>

  <script>
    let isArabic = false;

    function toggleLanguage() {
      isArabic = !isArabic;
      document.getElementById('title').innerText = isArabic ? 'مدونتي' : 'My Blog';
      document.querySelector('.lang-toggle').innerText = isArabic ? 'English' : 'عربي';
      document.getElementById('caption1').innerText = isArabic ? 'استجمام في المدينة ☀️' : "Chillin' in the city ☀️";
      document.getElementById('caption2').innerText = isArabic ? 'أوقات ممتعة مع الأصدقاء! 🎉' : "Fun times with friends! 🎉";
      document.getElementById('top-caption').innerText = isArabic ? 'واقف في الشارع بكل فخر، كل اللي عندي هو البي...' : 'Out here in the street standing tall all I have are bi....';
      document.getElementById('followers-insta').innerText = isArabic ? '١٦٠ متابع' : '160 followers';
      document.getElementById('followers-tt').innerText = isArabic ? '٤٠٠ متابع' : '400 followers';
      document.body.setAttribute('dir', isArabic ? 'rtl' : 'ltr');
    }

    function sharePost(link) {
      navigator.clipboard.writeText(link).then(() => {
        alert('Link copied to clipboard!');
      });
    }
  </script>
</body>
</html>
