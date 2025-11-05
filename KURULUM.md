# 🚀 GitHub Pages Deployment Kurulumu

## ✅ Yapılan Değişiklikler

### 1. **astro.config.mjs** Dosyası Düzenlendi
```javascript
export default defineConfig({
  integrations: [
    tailwind({ applyBaseStyles: false }),
    react(),
  ],
  output: 'static',
  site: 'https://muhammetyetis.github.io',
  base: '/railDevHub/',
});
```

**Önemli:**
- ❌ `site: 'https://raildevhub.pia-team.com'` (özel domain) kaldırıldı
- ✅ `site: 'https://muhammetyetis.github.io'` (GitHub Pages) eklendi
- ✅ `base: '/railDevHub/'` (repo adı) eklendi

### 2. **GitHub Actions Workflow** Oluşturuldu
- Dosya: `.github/workflows/deploy.yml`
- `main` branch'e push edildiğinde otomatik deploy
- Node.js 20 kullanılıyor
- `dist` klasöründen build çıktısı alınıyor
- CNAME veya özel domain ayarı **YOK**

---

## 🎯 GitHub'da Yapılması Gerekenler

### Adım 1: Değişiklikleri GitHub'a Gönder

```bash
git add .
git commit -m "GitHub Pages deployment yapılandırması"
git push origin main
```

### Adım 2: GitHub Pages Ayarlarını Yap

1. Repo'nuza gidin: https://github.com/muhammetyetis/railDevHub

2. **Settings** (Ayarlar) sekmesine tıklayın

3. Sol menüden **Pages** seçeneğini bulun

4. **Build and deployment** bölümünde:
   - **Source:** `GitHub Actions` seçin
   - Başka bir ayar yapmanıza gerek yok

5. **Save** butonuna basın

### Adım 3: Deployment'ı Takip Et

1. **Actions** sekmesine gidin: https://github.com/muhammetyetis/railDevHub/actions

2. "Deploy to GitHub Pages" workflow'unu göreceksiniz

3. İlk deploy 2-5 dakika sürebilir

4. Yeşil ✅ işareti gördüğünüzde deployment tamamlanmış demektir

### Adım 4: Sitenizi Ziyaret Edin

🌐 **Canlı Site:** https://muhammetyetis.github.io/railDevHub/

---

## 🔍 Hata Giderme

### ❌ "Domain is not a valid public domain" Hatası
**Çözüm:** Bu hata artık gelmeyecek çünkü:
- Özel domain kullanımı kaldırıldı
- CNAME dosyası yok
- Sadece GitHub Pages URL'si kullanılıyor

### ❌ Assets (CSS/JS) Yüklenmiyor
**Çözüm:** `base: '/railDevHub/'` ayarı eklendi. Tüm asset'ler doğru path'ten yüklenecek.

### ❌ Workflow Çalışmıyor
**Kontrol Et:**
- GitHub Pages source'u "GitHub Actions" olarak ayarlandı mı?
- `main` branch'e push yaptınız mı?
- Actions tab'ında hata mesajı var mı?

### ❌ 404 Hatası Alıyorum
**Kontrol Et:**
- URL doğru mu: `https://muhammetyetis.github.io/railDevHub/` (sonunda `/` var)
- Deployment tamamlandı mı? (Actions tab'ından kontrol edin)
- Tarayıcı cache'ini temizleyin (Ctrl+Shift+R)

---

## 🔄 Otomatik Deployment

Artık her `main` branch'e push yaptığınızda:
1. GitHub Actions otomatik çalışacak
2. Projenizi build edecek
3. GitHub Pages'e deploy edecek
4. 2-3 dakika içinde değişiklikler yayında olacak

**Tek yapmanız gereken:**
```bash
git add .
git commit -m "Değişiklik mesajınız"
git push origin main
```

---

## 📝 Önemli Notlar

- ✅ Özel domain (CNAME) kullanılmıyor
- ✅ Sadece GitHub Pages URL'si: `https://muhammetyetis.github.io/railDevHub/`
- ✅ Dark mode destekli landing page hazır
- ✅ Otomatik deployment aktif
- ✅ Node.js 20 kullanılıyor

---

## 🧪 Yerel Geliştirme

```bash
# Development server başlat
npm run dev
# → http://localhost:4321

# Production build test et
npm run build
npm run preview
# → http://localhost:4321
```

---

**Başarılı deployments! 🎉**

