# ✦ PIXELHANE NEXUS V15 FULL

**Pixelhane**, tek bir HTML dosyası üzerinden çalışan; mini oyun kütüphanesi, oyuncu ilerlemesi, profil özelleştirme, arkadaş özellikleri ve çok oyunculu modlar sunan tarayıcı tabanlı bir oyun merkezidir.

🌐 **Canlı site:** https://pixelhane-07.web.app/  
📦 **GitHub:** https://github.com/sarpozcan3507/Pixelhane

> Proje şu anda tek HTML tabanlı bir uygulamadır. Kurulum veya derleme adımı gerektirmez; bazı çevrimiçi özellikler internet bağlantısına ve ilgili servislerin erişilebilir olmasına bağlıdır.

---

## 🎮 Oyun kütüphanesi

Pixelhane arayüzünde 98 oyunluk bir kütüphane bulunur. Oyunlar kategoriye göre filtrelenebilir, aranabilir ve sıralanabilir.

Kategoriler:

- 🧠 Zekâ ve mantık
- ⚡ Refleks
- 🔤 Kelime
- 📚 Bilgi
- 🃏 Kart oyunları
- ♟️ Kutu oyunları
- 🎉 Parti oyunları
- 🧭 Strateji
- 🚀 Macera
- 🧩 Bulmaca
- 🕹️ Arcade
- 🎨 Yaratıcı oyunlar

Örnek oyunlar: Sayı Avcısı, Taş Kâğıt Makas, Kelime Avcısı, Bilgi Arenası, Matematik Sprinti, Hafıza Laboratuvarı, Refleks Testi, XOX Düellosu, UNO Neon ve Pişti Arenası.

Oyun kartlarının bir kısmı ortak mini oyun motorlarını kullanır; her kartın tamamen farklı bir oyun altyapısı olduğu varsayılmamalıdır.

## 🏆 Oyuncu ilerlemesi

- Oyun tamamladıkça XP kazanma
- Oyuncu seviyesi ve seviye ilerlemesi
- Tamamlanan oyun ve kazanılan oyun istatistikleri
- Kişisel rekorlar
- Başarımlar
- Son oynanan oyunların listesi

Oyun istatistikleri tarayıcının `localStorage` alanında saklanır. Tarayıcı verileri temizlenirse veya farklı bir tarayıcı/cihaz kullanılırsa bu yerel ilerleme otomatik olarak taşınmaz.

## 👤 Profil ve sosyal özellikler

- Oyuncu adı, avatar ve biyografi düzenleme
- Çevrimiçi, uzakta, lobide, oyunda ve çevrimdışı durum seçenekleri
- Profil rengi ve arka plan tasarımı seçme
- Oyuncu kodunu kopyalama ve arkadaş ekleme
- Doğrudan bağlantı kurulabilen arkadaşlarla mesajlaşma
- Mesajlara yanıt verme, tepki ekleme ve sabitleme
- Kulüp oluşturma ve davet koduyla kulübe katılma

Profil, arkadaş ve kulüp bilgilerinin önemli bölümü bu tarayıcıda yerel olarak saklanır. Bu sürümde merkezi kullanıcı hesabı ve tüm cihazlar arasında çalışan genel bir arkadaş listesi bulunmaz. Çevrimiçi arkadaş bağlantıları PeerJS üzerinden doğrudan kurulur.

## 🌐 Oyun modları ve multiplayer

Desteklenen oyunlarda üç mod sunulur:

1. **Tek kişilik:** Oyunu tek başına oyna ve kendi rekorunu geliştir.
2. **Aynı cihazda:** Desteklenen oyunları 2–4 kişi sırayla, tek cihaz üzerinde oyna.
3. **Çevrimiçi özel oda:** Oda/oyuncu koduyla başka bir oyuncuya doğrudan bağlan.

Çevrimiçi bağlantıda PeerJS kullanılır. Bazı oyunlar için senkronize oyun motorları vardır; bütün oyunların çevrimiçi olarak aynı şekilde senkronize edildiği garanti edilmez. Bu sürümde herkese açık otomatik eşleştirme sistemi yoktur.

## 🤖 AI asistanı

Pixelhane'de oyun ekranından ayrı bir AI asistan paneli bulunur. Panelde sohbet ve kod sekmeleri vardır. Mevcut HTML sürümündeki sohbet isteği Groq API'sine gönderilir ve varsayılan model adı `openai/gpt-oss-20b` olarak ayarlanmıştır.

AI özelliklerinin çalışması sağlayıcı API erişimine, geçerli bir API anahtarına, model kullanılabilirliğine ve sağlayıcının limitlerine bağlıdır. AI yanıtları oyunun kendisi veya multiplayer bağlantısı için gerekli değildir.

## 🧰 Kullanılan teknolojiler

| Teknoloji | Kullanım |
|---|---|
| HTML | Uygulama yapısı |
| CSS | Arayüz, düzen ve animasyonlar |
| JavaScript | Oyunlar, profil, ilerleme ve etkileşimler |
| `localStorage` | Yerel oyun ve profil verileri |
| PeerJS 1.5.5 | Doğrudan oyuncu/oda bağlantıları |
| Supabase JavaScript v2 | Realtime presence bağlantısı |
| Groq API | AI asistanı sohbet ve kod yanıtları |

PeerJS ve Supabase istemcileri CDN üzerinden yüklenir. Bu nedenle ilk açılış ve çevrimiçi özellikler için internet bağlantısı gerekir.

## 🚀 Çalıştırma

### En kolay yöntem

Canlı siteyi tarayıcıda aç:

https://pixelhane-07.web.app/

### Kendi kopyanı çalıştırma

1. GitHub deposunu ZIP olarak indir veya `index.html` dosyasını al.
2. Dosyayı güncel bir tarayıcıda aç. Çevrimiçi özellikleri test etmek için HTTPS üzerinden yayımlanmış bir adres kullanman önerilir.
3. Supabase Realtime veya AI asistanı gibi dış servisleri kullanacaksan ilgili proje ve API ayarlarının doğru olduğundan emin ol.

Bu sürüm tek HTML dosyasıdır; `package.json`, npm kurulumu veya bir derleme komutu gerektirmez.

## 🔐 Güvenlik ve veri notları

- Tarayıcıda saklanan veriler sunucu yedeği değildir.
- Supabase publishable/anon anahtarı istemci tarafında kullanılabilir; veritabanı erişimi için doğru RLS ve kanal izinleri ayrıca yapılandırılmalıdır.
- **Groq gibi özel API anahtarları HTML veya herkese açık GitHub deposunda tutulmamalıdır.** Tarayıcıya yazılan anahtar herkes tarafından görülebilir ve kullanılabilir. Anahtar sunucu tarafındaki bir Edge Function/proxy üzerinden saklanmalıdır.
- Bir API anahtarı daha önce herkese açık HTML dosyasına eklendiyse sağlayıcı panelinden iptal edilip yenilenmelidir.
- PeerJS ile doğrudan bağlantı, merkezi hesap sistemi veya genel bir güvenlik/denetim sunucusu anlamına gelmez.

## 📱 Mobil uyumluluk

Arayüz telefon ve masaüstü ekranlarına uyum sağlayacak şekilde tasarlanmıştır. Uygulama tarayıcıda çalışır. Android APK'ya dönüştürülmesi ayrı bir paketleme işlemidir; APK kullanmak, çevrimiçi özellikleri çevrimdışı hale getirmez.

## 📌 Proje durumu

Bu README, Pixelhane deposunda bulunmayan bir README.md dosyası için, mevcut `index.html` arayüzü ve kodunda görülen özellikler temel alınarak hazırlanmıştır. Çevrimiçi servislerin canlı yapılandırması ve her multiplayer oyunundaki senkronizasyon ayrıca test edilmelidir.

---

**PIXELHANE NEXUS V15 FULL**  
*Biraz oyun, bolca eğlence.*
