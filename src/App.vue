<script setup>
const tiktokUrl = 'https://www.tiktok.com/@diamond9451'

const stats = [
  {
    number: '短影音',
    label: 'Content Creation'
  },
  {
    number: 'TikTok',
    label: 'Main Platform'
  },
  {
    number: '@diamond9451',
    label: 'Account ID'
  }
]

const videos = [
  {
    title: '日常短片',
    desc: '用快速節奏記錄生活片段'
  },
  {
    title: '創意剪輯',
    desc: '結合音樂、轉場與視覺風格'
  },
  {
    title: '個人風格',
    desc: '建立具有辨識度的帳號形象'
  }
]
</script>

<template>
  <main class="page">
    <div class="background-glow glow-one"></div>
    <div class="background-glow glow-two"></div>

    <nav class="navbar">
      <div class="brand">
        <div class="brand-icon">D</div>
        <span>DIAMOND</span>
      </div>

      <a class="nav-button" :href="tiktokUrl" target="_blank" rel="noopener noreferrer">
        Visit TikTok
      </a>
    </nav>

    <section class="hero">
      <div class="hero-content">
        <p class="eyebrow">SHORT VIDEO CREATOR</p>

        <h1>
          Diamond
          <span>短影音帳號介紹</span>
        </h1>

        <p class="description">
          這是一個以短影音為核心的個人帳號介紹頁，透過簡潔的科技感視覺，
          呈現創作者風格、內容方向與 TikTok 帳號入口。
        </p>

        <div class="hero-actions">
          <a class="primary-button" :href="tiktokUrl" target="_blank" rel="noopener noreferrer">
            前往 TikTok
          </a>

          <a class="secondary-button" href="#about">
            查看介紹
          </a>
        </div>
      </div>

      <div class="profile-card">
        <div class="card-top">
          <div class="avatar">D</div>
          <div>
            <h2>@diamond9451</h2>
            <p>TikTok Creator</p>
          </div>
        </div>

        <div class="scan-box">
          <div class="scan-line"></div>
          <p>CREATOR PROFILE</p>
        </div>

        <div class="card-info">
          <span>Status</span>
          <strong>Online</strong>
        </div>
      </div>
    </section>

    <section class="stats">
      <div v-for="item in stats" :key="item.label" class="stat-card">
        <strong>{{ item.number }}</strong>
        <span>{{ item.label }}</span>
      </div>
    </section>

    <section id="about" class="about-section">
      <div class="section-title">
        <p>ABOUT ACCOUNT</p>
        <h2>帳號內容方向</h2>
      </div>

      <div class="video-grid">
        <article v-for="video in videos" :key="video.title" class="video-card">
          <div class="video-icon"></div>
          <h3>{{ video.title }}</h3>
          <p>{{ video.desc }}</p>
        </article>
      </div>
    </section>

    <footer class="footer">
      <p>© 2026 Diamond Short Video Profile</p>
    </footer>
  </main>
</template>

<style scoped>
.page {
  min-height: 100vh;
  position: relative;
  overflow: hidden;
  background:
    radial-gradient(circle at top left, rgba(0, 255, 255, 0.18), transparent 35%),
    radial-gradient(circle at bottom right, rgba(120, 80, 255, 0.22), transparent 35%),
    #080b14;
  color: #ffffff;
  font-family:
    Inter,
    "Microsoft JhengHei",
    system-ui,
    sans-serif;
}

.page::before {
  content: "";
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(255, 255, 255, 0.035) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 255, 255, 0.035) 1px, transparent 1px);
  background-size: 44px 44px;
  mask-image: linear-gradient(to bottom, black, transparent 80%);
  pointer-events: none;
}

.background-glow {
  position: absolute;
  width: 360px;
  height: 360px;
  border-radius: 50%;
  filter: blur(90px);
  opacity: 0.55;
}

.glow-one {
  top: 120px;
  left: -120px;
  background: #00e5ff;
}

.glow-two {
  right: -120px;
  bottom: 80px;
  background: #7c3cff;
}

.navbar {
  width: min(1120px, calc(100% - 40px));
  margin: 0 auto;
  padding: 28px 0;
  position: relative;
  z-index: 2;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.brand {
  display: flex;
  align-items: center;
  gap: 12px;
  letter-spacing: 3px;
  font-size: 14px;
  font-weight: 700;
}

.brand-icon {
  width: 38px;
  height: 38px;
  border: 1px solid rgba(0, 229, 255, 0.6);
  border-radius: 12px;
  display: grid;
  place-items: center;
  color: #00e5ff;
  background: rgba(255, 255, 255, 0.06);
  box-shadow: 0 0 24px rgba(0, 229, 255, 0.25);
}

.nav-button,
.primary-button,
.secondary-button {
  text-decoration: none;
  transition: 0.25s;
}

.nav-button {
  padding: 10px 18px;
  border: 1px solid rgba(255, 255, 255, 0.16);
  border-radius: 999px;
  color: #ffffff;
  background: rgba(255, 255, 255, 0.06);
  backdrop-filter: blur(14px);
}

.nav-button:hover {
  border-color: rgba(0, 229, 255, 0.8);
  color: #00e5ff;
}

.hero {
  width: min(1120px, calc(100% - 40px));
  margin: 0 auto;
  padding: 90px 0 56px;
  position: relative;
  z-index: 2;
  display: grid;
  grid-template-columns: 1.2fr 0.8fr;
  gap: 56px;
  align-items: center;
}

.eyebrow {
  margin-bottom: 18px;
  color: #00e5ff;
  font-size: 13px;
  font-weight: 700;
  letter-spacing: 4px;
}

.hero h1 {
  margin: 0;
  font-size: clamp(48px, 8vw, 96px);
  line-height: 0.95;
  letter-spacing: -4px;
}

.hero h1 span {
  display: block;
  margin-top: 14px;
  font-size: clamp(28px, 4vw, 52px);
  color: rgba(255, 255, 255, 0.72);
  letter-spacing: -2px;
}

.description {
  max-width: 620px;
  margin: 28px 0 36px;
  color: rgba(255, 255, 255, 0.68);
  font-size: 17px;
  line-height: 1.9;
}

.hero-actions {
  display: flex;
  gap: 16px;
  flex-wrap: wrap;
}

.primary-button {
  padding: 14px 26px;
  border-radius: 999px;
  color: #061018;
  background: linear-gradient(135deg, #00e5ff, #8effff);
  font-weight: 800;
  box-shadow: 0 0 36px rgba(0, 229, 255, 0.35);
}

.primary-button:hover {
  transform: translateY(-3px);
  box-shadow: 0 0 48px rgba(0, 229, 255, 0.55);
}

.secondary-button {
  padding: 14px 26px;
  border-radius: 999px;
  color: #ffffff;
  border: 1px solid rgba(255, 255, 255, 0.18);
  background: rgba(255, 255, 255, 0.05);
}

.secondary-button:hover {
  border-color: rgba(255, 255, 255, 0.4);
}

.profile-card {
  min-height: 440px;
  border: 1px solid rgba(255, 255, 255, 0.13);
  border-radius: 32px;
  padding: 28px;
  background:
    linear-gradient(145deg, rgba(255, 255, 255, 0.14), rgba(255, 255, 255, 0.04)),
    rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(24px);
  box-shadow: 0 30px 80px rgba(0, 0, 0, 0.35);
}

.card-top {
  display: flex;
  gap: 16px;
  align-items: center;
}

.avatar {
  width: 66px;
  height: 66px;
  border-radius: 22px;
  display: grid;
  place-items: center;
  font-size: 28px;
  font-weight: 900;
  color: #061018;
  background: linear-gradient(135deg, #00e5ff, #ffffff);
}

.card-top h2 {
  margin: 0;
  font-size: 24px;
}

.card-top p {
  margin: 6px 0 0;
  color: rgba(255, 255, 255, 0.55);
}

.scan-box {
  height: 230px;
  margin: 38px 0 26px;
  position: relative;
  overflow: hidden;
  border-radius: 24px;
  border: 1px solid rgba(0, 229, 255, 0.24);
  background:
    linear-gradient(90deg, rgba(0, 229, 255, 0.05) 1px, transparent 1px),
    linear-gradient(rgba(0, 229, 255, 0.05) 1px, transparent 1px),
    rgba(0, 0, 0, 0.22);
  background-size: 22px 22px;
  display: grid;
  place-items: center;
}

.scan-box p {
  color: rgba(255, 255, 255, 0.4);
  letter-spacing: 4px;
  font-size: 12px;
}

.scan-line {
  position: absolute;
  left: 0;
  right: 0;
  height: 2px;
  background: #00e5ff;
  box-shadow: 0 0 24px #00e5ff;
  animation: scan 2.8s infinite linear;
}

@keyframes scan {
  0% {
    top: 0;
  }

  100% {
    top: 100%;
  }
}

.card-info {
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: rgba(255, 255, 255, 0.55);
}

.card-info strong {
  color: #00e5ff;
}

.stats {
  width: min(1120px, calc(100% - 40px));
  margin: 0 auto;
  position: relative;
  z-index: 2;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 18px;
}

.stat-card {
  padding: 24px;
  border-radius: 24px;
  border: 1px solid rgba(255, 255, 255, 0.11);
  background: rgba(255, 255, 255, 0.06);
  backdrop-filter: blur(18px);
}

.stat-card strong {
  display: block;
  margin-bottom: 8px;
  color: #ffffff;
  font-size: 22px;
}

.stat-card span {
  color: rgba(255, 255, 255, 0.5);
  font-size: 14px;
}

.about-section {
  width: min(1120px, calc(100% - 40px));
  margin: 0 auto;
  padding: 90px 0 70px;
  position: relative;
  z-index: 2;
}

.section-title {
  margin-bottom: 32px;
}

.section-title p {
  color: #00e5ff;
  font-size: 13px;
  font-weight: 800;
  letter-spacing: 4px;
}

.section-title h2 {
  margin: 8px 0 0;
  font-size: 38px;
}

.video-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 18px;
}

.video-card {
  padding: 28px;
  min-height: 210px;
  border-radius: 28px;
  border: 1px solid rgba(255, 255, 255, 0.11);
  background: rgba(255, 255, 255, 0.055);
  transition: 0.25s;
}

.video-card:hover {
  transform: translateY(-6px);
  border-color: rgba(0, 229, 255, 0.5);
  box-shadow: 0 20px 60px rgba(0, 229, 255, 0.12);
}

.video-icon {
  width: 46px;
  height: 46px;
  margin-bottom: 28px;
  border-radius: 16px;
  background:
    linear-gradient(135deg, #00e5ff, transparent),
    rgba(255, 255, 255, 0.08);
}

.video-card h3 {
  margin: 0 0 12px;
  font-size: 22px;
}

.video-card p {
  margin: 0;
  color: rgba(255, 255, 255, 0.6);
  line-height: 1.7;
}

.footer {
  width: min(1120px, calc(100% - 40px));
  margin: 0 auto;
  padding: 26px 0 40px;
  position: relative;
  z-index: 2;
  color: rgba(255, 255, 255, 0.38);
  font-size: 14px;
}

@media (max-width: 860px) {
  .hero {
    grid-template-columns: 1fr;
    padding-top: 54px;
  }

  .profile-card {
    min-height: auto;
  }

  .stats,
  .video-grid {
    grid-template-columns: 1fr;
  }

  .navbar {
    align-items: flex-start;
  }

  .hero h1 {
    letter-spacing: -2px;
  }
}
</style>