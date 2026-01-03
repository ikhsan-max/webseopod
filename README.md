# WebSeoPod UI

Antarmuka single-page berbasis Vue 3 untuk memantau performa SEO, dirancang agar mudah diskalakan dan disesuaikan.

## Fitur
- **Layout hero modern** dengan kartu kinerja organik real-time.
- **Kartu metrik inti** untuk kesehatan teknis, ranking, CTR, dan traffic organik.
- **Daftar peluang & taskboard** untuk memprioritaskan eksperimen SEO.
- **Komponen reusable** (`StatCard`, `InsightCard`, `TaskList`) sehingga UI mudah di-extend.

## Menjalankan secara lokal
1. Pastikan Node.js 18+ tersedia.
2. Instal dependensi (atur registry jika perlu):
   ```bash
   npm install
   ```
3. Jalankan server pengembangan:
   ```bash
   npm run dev
   ```
4. Build produksi:
   ```bash
   npm run build
   ```

Jika akses ke registry npm dibatasi, setel mirror terlebih dahulu, misalnya:
```bash
npm config set registry https://registry.npmmirror.com
```
