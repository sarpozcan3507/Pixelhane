
# ✦ PIXELHANE NEXUS V15 FULL

**Pixelhane**, tarayıcıda çalışan mini oyun kütüphanesi ve oyuncu topluluğu arayüzüdür. Tek HTML dosyası üzerinden açılır; tek kişilik oyunlar, aynı cihazda parti oyunları, kodla katılınan çevrimiçi özel odalar, oyuncu profili ve AI asistan paneli içerir.

- **Canlı site:** https://pixelhane-07.web.app/
- **GitHub:** https://github.com/sarpozcan3507/Pixelhane
- **Ana uygulama dosyası:** `index.html`

> Bu README, paylaşılan mevcut Pixelhane `index.html` dosyasındaki arayüz ve kod temel alınarak hazırlanmıştır. Çevrimiçi servislerin canlı çalışması ayrıca test edilmelidir.

## Özellikler

### Oyun kütüphanesi

Arayüzde 98 oyunluk bir katalog gösterilir. Oyunlar arama, sıralama ve kategori filtreleriyle bulunabilir. Kategoriler zekâ, refleks, kelime, bilgi, kart, kutu, parti, strateji, macera, bulmaca, arcade ve yaratıcı oyunlardır.

Örnek oyunlar: Sayı Avcısı, Taş Kâğıt Makas, Kelime Avcısı, Bilgi Arenası, Matematik Sprinti, Hafıza Laboratuvarı, Refleks Testi, XOX Düellosu, UNO Neon ve Pişti Arenası.

Katalogdaki her kart ayrı bir oyun motoru anlamına gelmez. Bazı oyunlar ortak mini oyun motorları veya sadeleştirilmiş kurallar kullanır.

### Oyun modları

- **Tek kişilik:** Desteklenen oyunları tek başına oyna ve XP kazan.
- **Aynı cihazda:** Desteklenen oyunlarda 2–4 kişi sırayla aynı ekranda oynayabilir.
- **Çevrimiçi özel oda:** Oyuncu/oda koduyla PeerJS üzerinden doğrudan bağlantı kurulur. Kodda senkronize oyun mantığı bulunan oyunlar çevrimiçi oynanabilir.

Bu sürümde genel otomatik eşleştirme (public matchmaking) sistemi yoktur. Bütün katalog oyunlarının çevrimiçi senkronize olduğu varsayılmamalıdır.

### Oyuncu ilerlemesi

- XP, seviye, oyun ve galibiyet istatistikleri
- Başarımlar, kişisel rekorlar ve son aktiviteler
- Oyuncu adı, avatar, biyografi, durum, renk ve profil arka planı

İlerleme ve sosyal verilerin önemli bölümü tarayıcının `localStorage` alanında tutulur. Bu veriler otomatik olarak başka cihaza taşınmaz; tarayıcı verileri silinirse kaybolabilir.

### Profil, arkadaşlar ve kulüpler

- Oyuncu kodu paylaşma ve arkadaş ekleme
- Doğrudan bağlantı kurulabilen arkadaşlara mesaj gönderme
- Mesajlara yanıt verme, tepki ekleme ve sabitleme
- Kulüp oluşturma, davet koduyla katılma ve kulüp sohbeti arayüzü

Arkadaş listesi, profil ve kulüp verileri için bu HTML sürümünde merkezi, tüm cihazları kapsayan bir kullanıcı hesabı sistemi bulunmaz. Bazı veriler yereldir; gerçek zamanlı bağlantı yalnızca PeerJS bağlantısı kurulabilen oyuncular arasında çalışır.

### AI asistanı

AI panelinde sohbet ve kod sekmeleri bulunur. Mevcut kod, sohbet isteklerini Groq Chat Completions API adresine gönderir ve `openai/gpt-oss-20b` modelini kullanır. Bu özellik oyun motorlarının çalışması için gerekli değildir.

**Güvenlik uyarısı:** Paylaşılan `index.html` dosyasında Groq API anahtarı doğrudan JavaScript koduna yazılmıştır. Tarayıcıda kullanılan veya herkese açık depoya konan anahtar gizli kalmaz. Dosyada bulunan eski anahtarı kullanmayın; Groq panelinden iptal edip yenisini oluşturun. Yeni anahtarı HTML'e, README dosyalarına veya herkese açık depoya eklemeyin. Güvenli kullanım için HTML'in sunucu tarafındaki bir API proxy/Edge Function'a istek gönderecek şekilde ayrıca güncellenmesi gerekir. Bu proxy mevcut tek HTML dosyasının parçası değildir; bu nedenle proxy kurulana kadar AI özelliği etkinleştirilmemelidir.

## Kullanılan teknolojiler

| Teknoloji | Kullanım |
|---|---|
| HTML, CSS, JavaScript | Tek dosyalı web arayüzü ve oyun mantığı |
| `localStorage` | Yerel profil, istatistik ve sosyal veriler |
| PeerJS 1.5.5 | Oyuncular arasında doğrudan bağlantı ve özel odalar |
| Supabase JavaScript v2 | Realtime presence bağlantısı |
| Groq API | AI asistan sohbeti ve kod yanıtları |

PeerJS ve Supabase istemcileri CDN üzerinden yüklenir. Bu nedenle ilk yükleme ve çevrimiçi özellikler için internet bağlantısı gerekir.

## Kurulum ve yayımlama

1. Depoyu ZIP olarak indirin veya `index.html` dosyasını alın.
2. Yerel deneme için `index.html` dosyasını güncel bir tarayıcıda açın.
3. Çevrimiçi özellikler için dosyayı HTTPS kullanan bir statik web barındırma hizmetinde yayımlayın.
4. Supabase Realtime bağlantısı, PeerJS özel odaları ve Firebase Hosting adımları için aşağıdaki kurulum rehberini izleyin.

Ayrıntılı yerel çalıştırma, GitHub Pages, Firebase Hosting, Supabase, PeerJS ve AI anahtarı güvenliği adımları için **[README-KURULUM.txt](README-KURULUM.txt)** dosyasına bakın.

## Veri ve gizlilik notları

- Bu sürümde Firebase Authentication veya klasik kullanıcı hesabı/giriş akışı bulunmaz.
- Oyun istatistikleri ve profil verilerinin çoğu tarayıcıda yerel tutulur.
- Supabase bağlantısı mevcut kodda Realtime presence amacıyla kullanılır; bu dosya tek başına merkezi profil/veritabanı senkronizasyonu kurmaz.
- Supabase istemci tarafında yalnızca publishable/anon anahtar kullanılmalıdır. `service_role` veya Secret anahtarı HTML'e eklenmemelidir.
- AI API anahtarını herkese açık HTML/JavaScript dosyasında tutmayın.

## Proje görseli

`pixelhane-icon.jpg`, Pixelhane için hazırlanmış kare logodur. Görsel 512 × 512 piksel ve 1 MB sınırının altındadır; uygulama simgesi veya proje görseli olarak yüklenebilir.

---

**PIXELHANE NEXUS V15 FULL**  
*Biraz oyun, bolca eğlence.*
