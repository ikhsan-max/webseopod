<script setup>
import StatCard from './components/StatCard.vue';
import InsightCard from './components/InsightCard.vue';
import TaskList from './components/TaskList.vue';

const stats = [
  {
    title: 'Organic visitors',
    value: '132,480',
    change: '+18.4% vs last month',
    tone: 'positive',
    detail: 'Consistent lift from content refreshes',
  },
  {
    title: 'Avg. position',
    value: '#6.2',
    change: '+0.9',
    tone: 'positive',
    detail: 'Climbing on 24 tracked keywords',
  },
  {
    title: 'CTR (SERP)',
    value: '4.8%',
    change: '+0.7%',
    tone: 'positive',
    detail: 'Higher from enhanced snippets',
  },
  {
    title: 'Technical health',
    value: '92/100',
    change: '-1.3%',
    tone: 'neutral',
    detail: 'Monitor CLS on mobile templates',
  },
];

const searchTrends = [
  { label: 'Mon', value: 36 },
  { label: 'Tue', value: 54 },
  { label: 'Wed', value: 62 },
  { label: 'Thu', value: 58 },
  { label: 'Fri', value: 71 },
  { label: 'Sat', value: 64 },
  { label: 'Sun', value: 77 },
];

const opportunities = [
  {
    title: 'People also ask ranking',
    description: '3 new PAA questions unlocked around your brand story and pricing. Add concise FAQ answers to product pages.',
    tags: ['FAQ schema', 'Content refresh'],
    impact: 'High',
  },
  {
    title: 'Broken backlinks',
    description: '27 referring domains point to 4xx URLs. Redirect or recreate content to reclaim authority.',
    tags: ['Link equity', 'Redirects'],
    impact: 'Medium',
  },
  {
    title: 'Image search coverage',
    description: 'Add descriptive ALT text and lazy-loading to hero illustrations to improve media visibility.',
    tags: ['Accessibility', 'Performance'],
    impact: 'Medium',
  },
];

const tasks = [
  {
    title: 'Ship next 3 pillar articles',
    detail: 'Map to “buy” intent keywords with structured how-to sections.',
    impact: 'High impact',
    status: 'In progress',
  },
  {
    title: 'Implement FAQ schema on pricing',
    detail: 'Target long-tail questions that surface in PAA panels.',
    impact: 'High impact',
    status: 'Planned',
  },
  {
    title: 'Lower LCP on blog layout',
    detail: 'Defer third-party widgets and serve hero via next-gen formats.',
    impact: 'Medium impact',
    status: 'Planned',
  },
  {
    title: 'Reclaim broken backlinks',
    detail: 'Redirect legacy /2019/ paths to updated canonical URLs.',
    impact: 'Quick win',
    status: 'Ready to run',
  },
];

const keywordFocus = [
  { label: 'Programmatic SEO', growth: '+42%', volume: '9.8k' },
  { label: 'AI content brief', growth: '+27%', volume: '7.2k' },
  { label: 'Site audit checklist', growth: '+31%', volume: '5.9k' },
  { label: 'Structured data generator', growth: '+19%', volume: '3.4k' },
];
</script>

<template>
  <div class="page">
    <header class="page-hero">
      <div class="blurred" aria-hidden="true"></div>
      <div class="container">
        <nav class="nav">
          <div class="logo">
            <span class="logo-dot"></span>
            <div>
              <div class="logo-title">WebSeoPod</div>
              <div class="logo-sub">Insightful SEO cockpit</div>
            </div>
          </div>
          <div class="nav-actions">
            <a class="nav-link" href="#">Docs</a>
            <a class="nav-link" href="#">Templates</a>
            <a class="nav-link" href="#">Support</a>
            <button class="btn btn-primary">Start free trial</button>
          </div>
        </nav>

        <div class="hero">
          <div class="hero-copy">
            <div class="badge">
              <span>✨</span>
              <span>Fokus kecepatan & skalabilitas</span>
            </div>
            <h1>UI baru yang modern untuk menganalisis & menskalakan SEO</h1>
            <p>
              Monitoring real-time, rekomendasi yang dapat dieksekusi, dan tampilan visual bersih yang
              memudahkan tim konten, growth, maupun engineer mengambil keputusan.
            </p>
            <div class="hero-actions">
              <button class="btn btn-primary">Mulai optimasi</button>
              <button class="btn btn-secondary">Lihat demo langsung</button>
            </div>
            <div class="hero-highlight">
              <div class="pill">Jam tayang 99.9%</div>
              <div class="pill">Terukur untuk ribuan halaman</div>
              <div class="pill">Integrasi GA4 & Search Console</div>
            </div>
          </div>
          <div class="hero-panel glass-card">
            <div class="panel-header">
              <div>
                <p class="eyebrow">Live visibility</p>
                <h3>Organic performance</h3>
              </div>
              <div class="chip positive">+18.4%</div>
            </div>
            <div class="panel-grid">
              <div>
                <p class="label">Clicks</p>
                <p class="metric">12.7k</p>
              </div>
              <div>
                <p class="label">Impressions</p>
                <p class="metric">881k</p>
              </div>
              <div>
                <p class="label">CTR</p>
                <p class="metric">4.8%</p>
              </div>
              <div>
                <p class="label">Avg position</p>
                <p class="metric">6.2</p>
              </div>
            </div>
            <div class="chart">
              <div v-for="trend in searchTrends" :key="trend.label" class="bar-wrap">
                <div class="bar" :style="{ height: `${trend.value}%` }"></div>
                <span class="bar-label">{{ trend.label }}</span>
              </div>
            </div>
            <div class="panel-footer">
              <div>
                <p class="label">Fokus mingguan</p>
                <p class="mini">SERP snippet test & cleanup redirect chain</p>
              </div>
              <button class="btn btn-secondary small">Tambah kartu</button>
            </div>
          </div>
        </div>
      </div>
    </header>

    <main class="container">
      <section class="section">
        <div class="section-head">
          <div>
            <p class="eyebrow">Kesehatan realtime</p>
            <h2>Semua metrik SEO inti dalam satu tampilan</h2>
            <p class="muted">
              Pantau performa organik, kesiapan teknis, dan perubahan harian. UI ringan ini siap disesuaikan
              untuk tim konten, growth, maupun engineer.
            </p>
          </div>
          <button class="btn btn-secondary">Ekspor laporan</button>
        </div>
        <div class="stat-grid">
          <StatCard v-for="item in stats" :key="item.title" v-bind="item" />
        </div>
      </section>

      <section class="section split">
        <div class="glass-card">
          <div class="section-head tight">
            <div>
              <p class="eyebrow">Keyword momentum</p>
              <h3>Performa SERP harian</h3>
              <p class="muted">Pergerakan keyword yang paling berdampak minggu ini.</p>
            </div>
            <button class="btn btn-secondary small">Sinkron GSC</button>
          </div>
          <div class="keyword-list">
            <div v-for="keyword in keywordFocus" :key="keyword.label" class="keyword-row">
              <div class="keyword-label">
                <span class="pill">Trending</span>
                <span class="keyword">{{ keyword.label }}</span>
              </div>
              <div class="keyword-metrics">
                <span class="badge">{{ keyword.growth }}</span>
                <span class="muted">Volume {{ keyword.volume }}</span>
              </div>
            </div>
          </div>
        </div>

        <div class="glass-card">
          <div class="section-head tight">
            <div>
              <p class="eyebrow">Opportunities</p>
              <h3>Prioritas eksekusi</h3>
              <p class="muted">Dari audit teknis, konten, sampai backlink.</p>
            </div>
            <button class="btn btn-secondary small">Simpan view</button>
          </div>
          <div class="card-grid">
            <InsightCard v-for="item in opportunities" :key="item.title" v-bind="item" />
          </div>
        </div>
      </section>

      <section class="section">
        <div class="section-head">
          <div>
            <p class="eyebrow">Workboard</p>
            <h2>Kelola eksperimen SEO seperti produk</h2>
            <p class="muted">Status task yang jelas, impact label, dan call-to-action langsung di dalam UI.</p>
          </div>
          <button class="btn btn-secondary">Buat sprint</button>
        </div>
        <TaskList :items="tasks" />
      </section>
    </main>
  </div>
</template>

<style scoped>
.page {
  position: relative;
  overflow-x: hidden;
}

.page-hero {
  position: relative;
  padding: 2rem 0 3rem;
}

.blurred {
  position: absolute;
  inset: -10% -20% auto;
  height: 420px;
  background: radial-gradient(circle at 40% 35%, rgba(37, 99, 235, 0.28), transparent 35%),
    radial-gradient(circle at 70% 10%, rgba(16, 185, 129, 0.18), transparent 30%),
    linear-gradient(120deg, rgba(37, 99, 235, 0.12), rgba(16, 185, 129, 0.1));
  filter: blur(60px);
  opacity: 0.75;
  pointer-events: none;
}

.nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  padding: 0.5rem 0 1.5rem;
}

.logo {
  display: inline-flex;
  align-items: center;
  gap: 0.75rem;
}

.logo-dot {
  width: 14px;
  height: 14px;
  border-radius: 50%;
  background: linear-gradient(120deg, #60a5fa, #34d399);
  box-shadow: 0 10px 30px rgba(37, 99, 235, 0.45);
}

.logo-title {
  font-weight: 700;
  letter-spacing: -0.01em;
}

.logo-sub {
  color: var(--text-muted);
  font-size: 0.85rem;
}

.nav-actions {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.nav-link {
  color: #0f172a;
  font-weight: 600;
  padding: 0.5rem 0.75rem;
  border-radius: 10px;
  transition: background 0.15s ease, transform 0.15s ease;
}

.nav-link:hover {
  background: rgba(255, 255, 255, 0.7);
  transform: translateY(-1px);
}

.hero {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1.5rem;
  align-items: center;
  margin-top: 1.5rem;
}

.hero-copy h1 {
  font-size: clamp(2.4rem, 4vw, 3.1rem);
  margin: 0.5rem 0;
  color: #0f172a;
}

.hero-copy p {
  color: var(--text-muted);
  margin-bottom: 1.25rem;
  max-width: 640px;
}

.hero-actions {
  display: flex;
  align-items: center;
  gap: 0.8rem;
  margin-bottom: 1rem;
}

.hero-highlight {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.hero-panel {
  border: 1px solid rgba(15, 23, 42, 0.06);
}

.panel-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
  margin-bottom: 0.75rem;
}

.panel-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 1rem;
  margin: 1rem 0;
}

.label {
  color: var(--text-muted);
  font-size: 0.9rem;
  margin: 0;
}

.metric {
  margin: 0.25rem 0 0;
  font-size: 1.4rem;
  font-weight: 700;
}

.chart {
  display: grid;
  grid-template-columns: repeat(7, minmax(0, 1fr));
  align-items: end;
  gap: 0.75rem;
  padding: 1rem 0;
  border-radius: 12px;
  background: linear-gradient(180deg, rgba(37, 99, 235, 0.08), rgba(37, 99, 235, 0));
}

.bar-wrap {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.35rem;
}

.bar {
  width: 100%;
  max-width: 36px;
  background: linear-gradient(180deg, #60a5fa, #2563eb);
  border-radius: 10px 10px 6px 6px;
  box-shadow: 0 8px 20px rgba(37, 99, 235, 0.3);
}

.bar-label {
  font-size: 0.85rem;
  color: var(--text-muted);
}

.panel-footer {
  margin-top: 0.5rem;
  padding-top: 0.75rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  border-top: 1px solid rgba(15, 23, 42, 0.06);
}

.eyebrow {
  text-transform: uppercase;
  font-size: 0.85rem;
  letter-spacing: 0.08em;
  color: #475467;
  margin: 0 0 0.35rem 0;
  font-weight: 700;
}

h2,
h3 {
  margin: 0.1rem 0;
  color: #0f172a;
}

.muted {
  color: var(--text-muted);
  margin: 0.25rem 0 0;
}

.section-head {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 1rem;
}

.section-head.tight h3 {
  margin-bottom: 0.2rem;
}

.section-head p {
  max-width: 560px;
}

.split {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 1.25rem;
}

.keyword-list {
  display: flex;
  flex-direction: column;
  gap: 0.9rem;
}

.keyword-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 0.75rem;
  padding: 0.85rem 1rem;
  border-radius: 14px;
  border: 1px solid rgba(15, 23, 42, 0.05);
  background: rgba(255, 255, 255, 0.8);
}

.keyword-label {
  display: flex;
  align-items: center;
  gap: 0.65rem;
}

.keyword {
  font-weight: 700;
}

.keyword-metrics {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.chip {
  padding: 0.35rem 0.65rem;
  border-radius: 999px;
  font-weight: 700;
  font-size: 0.85rem;
}

.chip.positive {
  background: rgba(16, 185, 129, 0.15);
  color: #047857;
}

.small {
  padding: 0.6rem 0.9rem;
  font-size: 0.95rem;
  box-shadow: none;
}

.hero-panel .small {
  background: rgba(37, 99, 235, 0.08);
}

.mini {
  margin: 0;
  color: var(--text-muted);
  font-size: 0.95rem;
}

@media (max-width: 960px) {
  .nav-actions {
    display: none;
  }
}
</style>
