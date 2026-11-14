PIXELHANE NEXUS V15 FULL
KURULUM VE YAYIMLAMA REHBERİ
========================================

PROJE BAĞLANTILARI
------------------
Canlı site : https://pixelhane-07.web.app/
GitHub     : https://github.com/sarpozcan3507/Pixelhane
Ana dosya  : index.html
İkon       : pixelhane-icon.jpg

Bu rehber, paylaşılan mevcut Pixelhane index.html dosyasına göre hazırlanmıştır.
Mevcut sürüm tek HTML dosyasıdır. Node paketleri veya derleme işlemi,
oyunların temel çalışması için gerekli değildir.

1) DOSYALARI HAZIRLAMA
----------------------
GitHub deposunu ZIP olarak indirin veya index.html dosyasını alın.

Proje klasöründe şu dosyaları bulundurun:
- index.html
- README.md
- README-KURULUM.txt
- pixelhane-icon.jpg (isteğe bağlı kare uygulama/marka ikonu)

README dosyaları ve ikon oyunun çalışması için zorunlu değildir.
Ana uygulama dosyası index.html'dir.

2) YEREL OLARAK ÇALIŞTIRMA
--------------------------
1. index.html dosyasına çift tıklayın.
2. Dosyayı güncel Chrome, Safari, Firefox veya Edge tarayıcısında açın.
3. Tek kişilik mini oyunların temel bölümleri yerel olarak çalışır.

Notlar:
- Harici kütüphaneler CDN üzerinden yüklenir; ilk açılış için internet gerekir.
- Supabase presence, PeerJS ve AI asistan gibi çevrimiçi özellikler internet
  bağlantısına ve ilgili servislerin erişilebilir olmasına bağlıdır.
- Tarayıcı gizli modu, depolama engeli veya site verilerini temizleme işlemi
  localStorage kayıtlarını etkileyebilir.

3) GITHUB PAGES İLE ÜCRETSİZ YAYIMLAMA (TARAYICIDAN)
-----------------------------------------------------
1. https://github.com/sarpozcan3507/Pixelhane adresinde depoyu açın.
2. index.html dosyasının deponun ana dizininde olduğunu kontrol edin.
3. Depoya README.md, README-KURULUM.txt ve pixelhane-icon.jpg dosyalarını
   da ekleyebilirsiniz.
4. Settings > Pages bölümüne girin.
5. Build and deployment altında "Deploy from a branch" seçin.
6. Branch olarak main, klasör olarak /(root) seçin ve Save'e basın.
7. GitHub Pages'in verdiği site adresini açın.

GitHub Pages'te değişikliklerin yayına çıkması kısa bir süre alabilir.

4) FIREBASE HOSTING İLE YAYIMLAMA (İSTEĞE BAĞLI)
------------------------------------------------
Pixelhane'nin mevcut canlı adresi pixelhane-07.web.app şeklindedir.
Aynı Firebase Hosting projesine yayın yapacaksanız o projeye erişim yetkiniz
olmalıdır. Bu adım için Node.js/npm ve Firebase CLI gerekir.

Gerekenler:
- Node.js ve npm
- Firebase hesabına erişim
- Firebase Hosting projesinde yayımlama yetkisi

Terminal komutları:

npm install -g firebase-tools
firebase login
firebase init hosting

Kurulum sorularında:
- Mevcut Firebase projesini seçin.
- Public dizini olarak index.html dosyasının bulunduğu klasörü belirtin.
  Ana proje klasöründe çalışıyorsanız dizin olarak . yazabilirsiniz.
- Uygulama tek sayfalı bir site olsa da tüm URL'leri index.html'e yönlendirmek
  istemiyorsanız single-page app sorusuna No deyin.
- Var olan index.html dosyasının üzerine yazılmasını onaylamayın.

Bu kurulum firebase.json dosyasını oluşturabilir. Ardından:

firebase deploy --only hosting

Komut tamamlandığında Firebase'in verdiği Hosting adresini açın.
Proje seçiminde pixelhane-07 projesi hesabınızda görünüyorsa ve bu canlı
siteye bağlı olduğunu biliyorsanız onu seçin. Başka bir projeyi yanlışlıkla
seçmemeye dikkat edin.

5) SUPABASE REALTIME AYARI
--------------------------
Mevcut index.html dosyasında Supabase istemci kütüphanesi CDN üzerinden
çağrılır. Project URL ve publishable anahtar dosyada tanımlanmıştır.
Kod, Supabase'i pixelhane-presence adlı Realtime presence kanalı için kullanır.

Kontrol etmek için:
1. https://supabase.com/dashboard adresinden ilgili projeyi açın.
2. Projenin aktif ve Realtime hizmetinin erişilebilir olduğunu kontrol edin.
3. Siteyi açıp tarayıcı geliştirici konsolunda [PIXELHANE] mesajlarını inceleyin.

Önemli:
- Mevcut HTML'de Supabase profilleri saklayan bir veritabanı tablosu veya SQL
  migration bulunmamaktadır.
- Supabase bağlantısı tek başına hesap sistemi, kalıcı arkadaş listesi veya
  tüm cihazlarda profil senkronizasyonu sağlamaz.
- Tarayıcıda yalnızca publishable/anon anahtar kullanılabilir.
- Supabase service_role veya Secret anahtarını index.html dosyasına yazmayın.
- İleride veritabanı tablosu eklerseniz RLS ve erişim kurallarını ayrıca kurun.

6) PEERJS VE ÇEVRİMİÇİ ODALAR
-----------------------------
PeerJS kütüphanesi index.html içinde CDN üzerinden yüklenir. Oyuncu bağlantısı
ve özel oda özelliği PeerJS sinyalleşmesi ve oyuncular arasında doğrudan
bağlantı kurulmasına dayanır.

Test etmek için:
1. Siteyi iki farklı cihazda veya iki ayrı tarayıcı profilinde açın.
2. İki tarafta da internet bağlantısı olduğunu kontrol edin.
3. Oyuncu kodunu kopyalayın ve diğer cihazdaki oda/oyuncu kodu alanına girin.
4. Özel oda oluşturup desteklenen bir oyunda bağlantıyı test edin.

Notlar:
- Bu sürümde herkese açık otomatik oyuncu eşleştirme sistemi yoktur.
- Çevrimiçi oyun senkronizasyonu yalnızca desteklenen oyun motorlarında vardır.
  Katalogdaki her oyunun çevrimiçi oynanabildiği varsayılmamalıdır.
- Ağ, tarayıcı veya PeerJS hizmeti kaynaklı bağlantı sorunları yaşanabilir.

7) AI ASİSTANI VE GROQ API ANAHTARI — ÇOK ÖNEMLİ
-------------------------------------------------
AI panelinin mevcut kodu şu API adresine istek gönderir:
https://api.groq.com/openai/v1/chat/completions

Varsayılan model:
openai/gpt-oss-20b

GÜVENLİK UYARISI:
Paylaşılan index.html dosyasında GROQ_API_KEY JavaScript değişkenine
bir API anahtarı doğrudan yazılmıştır. Tarayıcıya gönderilen her anahtar,
ziyaretçiler ve kaynak kodunu inceleyen kişiler tarafından görülebilir.
Bu nedenle dosyada bulunan anahtarı artık güvenli kabul etmeyin.

YAPILMASI GEREKENLER:
1. Groq kontrol panelini açın: https://console.groq.com/keys
2. HTML dosyasında daha önce kullanılan anahtarı iptal edin.
3. Yeni bir anahtar oluşturun; ancak yeni anahtarı GitHub'a, README dosyasına
   veya herkese açık HTML/JavaScript dosyasına eklemeyin.
4. Güvenli kullanım için AI isteğini sunucu tarafındaki bir API proxy/Edge
   Function üzerinden gönderecek şekilde index.html kodunu güncelleyin.
5. Anahtarı yalnızca sunucu tarafındaki gizli değişkende saklayın.

Bu sunucu tarafı proxy mevcut tek HTML dosyasının parçası değildir.
Bu nedenle proxy geliştirilip bağlanana kadar AI özelliğini yayımlanmış
sürümde etkinleştirmeyin. API anahtarını HTML'e tekrar koymak güvenli değildir.
AI özelliği isteğe bağlıdır; mini oyunların temel çalışması için gerekli değildir.

8) VERİLER NEREDE SAKLANIR?
---------------------------
Mevcut kodda:
- Oyun XP, seviye, galibiyet, rekor ve geçmiş verileri localStorage'da tutulur.
- Profil, arkadaş, not, kulüp ve sohbet verilerinin bir bölümü localStorage'da
  tutulur.
- Supabase Realtime presence, çevrimiçi oturum durumunu bildirmeye yardımcı olur.
- PeerJS doğrudan oyuncu/oda bağlantılarını kurar.

Bu nedenle tarayıcı verisini temizlerseniz yerel ilerleme ve sosyal veriler
kaybolabilir. Bu sürümde tüm verileri hesapla başka cihaza taşıyan merkezi
bir hesap sistemi yoktur.

9) SORUN GİDERME
----------------
Oyun açılmıyorsa:
- index.html dosyasının tam indiğini kontrol edin.
- Tarayıcıyı güncelleyin.
- İnternet bağlantısını kontrol edin; CDN kütüphaneleri haricen yüklenir.
- Tarayıcı geliştirici konsolundaki hata mesajlarını kontrol edin.

Supabase bağlanmıyorsa:
- Proje URL'si ve publishable anahtarın doğru olduğunu kontrol edin.
- Supabase projesinin aktif ve Realtime hizmetinin erişilebilir olduğunu
  kontrol edin.

Çevrimiçi oda bağlanmıyorsa:
- İki cihazda da internet olduğunu kontrol edin.
- Oyuncu kodunu eksiksiz kopyalayın.
- Karşı oyuncunun bağlantı sayfasının açık olduğundan emin olun.
- PeerJS veya ağ kaynaklı geçici sorun ihtimalini göz önünde bulundurun.

AI yanıt vermiyorsa:
- API anahtarını HTML'e açık şekilde koymayın.
- Sunucu proxy'sinin doğru yapılandırıldığını kontrol edin.
- Modelin API hesabınızda kullanılabilir olduğundan emin olun.

10) YAYIN ÖNCESİ KONTROL LİSTESİ
--------------------------------
[ ] index.html ana dizinde ve tarayıcıda açılıyor.
[ ] README.md ve README-KURULUM.txt depoda güncel.
[ ] pixelhane-icon.jpg kare ve 1 MB'tan küçük.
[ ] Site HTTPS üzerinden yayında.
[ ] Supabase Realtime bağlantısı test edildi.
[ ] PeerJS oyuncu kodu ve özel oda iki cihazda test edildi.
[ ] Yerel kayıtların localStorage'da kaldığı açıklandı.
[ ] Eski Groq anahtarı iptal edildi.
[ ] AI proxy kurulmadan yeni API anahtarı HTML'e eklenmedi.

TAMAMLANDI
----------
PIXELHANE NEXUS V15 FULL
Biraz oyun, bolca eğlence.
