# METU Kontenjan Takip

ODTÜ derslerinin kontenjanını ve boş yer değişikliklerini takip eden bağımsız öğrenci aracı. ODTÜ’nün resmî uygulaması değildir; ders kaydı yapmaz veya yer ayırmaz.

## Kullanım

**[Chrome Web Mağazası’ndan yükle](https://chromewebstore.google.com/detail/metu-kontenjan-takip/dookdbojobjbpfjfmhdhjahkjhicpkdo)**

Bu depo, 2.4.115 sürümünün kaynaklarını inceleyebilmeniz için yayımlanmıştır.

**[Tam kaynak kodu arşivi — 2.4.115](https://github.com/ugurmetu/metu-kontenjan-takip/releases/tag/v2.4.115)**

Kaynak dosyaları bu sürümün Releases bölümünde `METU-Kontenjan-Takip-2.4.115-source.zip` içinde yayımlanır. Aşağıdaki klasörler ZIP açıldıktan sonra görülebilir. GitHub’ın otomatik oluşturduğu “Source code” arşivi yerine bu adlandırılmış dosyayı indirin. Mağazadaki güncelleme incelemesi tamamlanana kadar mağaza önceki onaylı sürümü sunabilir. Güncel kurulum için yukarıdaki resmî dağıtım bağlantısını kullanın.

Bilgisayar ve tarayıcı açık ve uyanık olmalı; yetkili ODTÜ Course Capacity sekmesine ve internete erişim sürmelidir. Telefonunuzda Telegram bildirimlerini alabilirsiniz. Bildirim bir yer ayırmaz; gecikme veya kesinti olabilir.

## Bu sürüm

- Beş adımlı sade kurulum ve sonunda tek “Kabul et ve kurulumu tamamla” düğmesi.
- Cihazda çalışan geliştirilmiş OCR; doğrulama görselleri harici OCR servisine gönderilmez.
- Türkçe / English arayüz, ders ve section seçimi, durdur / devam et.
- İsteğe bağlı ortak Telegram botu veya kendi botunuz.
- İsteğe bağlı, cihazda şifreli saklanan bilgilerle ODTÜ oturum yenileme.
- Yerel takip ve başarı istatistikleri.
- Ortak serviste gereksiz Telegram profil adı ve kullanıcı adı kayıtlarının kaldırılması.

## Dosyalar ve veri akışı

`extension/`: Mağaza paketini oluşturan tarayıcı kodu, yerel OCR dosyaları, testler ve lisans bildirimleri.

`telegram-service/`: Ortak Telegram botunun Cloudflare Worker / D1 kaynakları. Bildirimlerin doğru sohbete gitmesi için gerekli sohbet kimliği ve bağlantı yetkisi tutulur. Telegram profil adı ve kullanıcı adı yeni kayıtlara eklenmez; eski etiketler sınırlı bakım partileriyle temizlenir. ODTÜ giriş bilgileri bu servise gönderilmez. Kişisel bot seçeneği bildirimleri doğrudan Telegram’a gönderir.

Ayrıntılar: [gizlilik](https://metu-capacity-telegram.ugurmetu.chatgpt.site/privacy.html?lang=tr), [kullanım koşulları](https://metu-capacity-telegram.ugurmetu.chatgpt.site/terms.html?lang=tr), [yardım](https://metu-capacity-telegram.ugurmetu.chatgpt.site/faq.html?lang=tr).

## Geliştirme ve doğrulama

Node 24+ ile `extension` klasöründe `npm ci --ignore-scripts` ve `npm run test:extension`; `telegram-service` klasöründe `npm ci --ignore-scripts`, `npm test`, `npm run build`, `npm run validate` çalıştırılabilir. Yerel testler 1.314 eklenti ve 117 servis testinde geçti. Bunlar gerçek portalın sürekli erişilebilirliğini veya her bildirimin telefona ulaşmasını garanti etmez.

Paketlenmemiş bir kopyanın kimliği farklıdır; üretim ortak botuna kendiliğinden erişemez. Kendi servisinizde açıkça belirlenmiş uzantı kimliği izin listesi ve kendi gizli sunucu ayarlarınız gerekir. Gizli anahtarları depoya koymayın. `runtime-config.example.json` yalnız boş örnektir.

`release/STORE-SHA256SUMS.txt`, mağaza ZIP dosyasındaki her dosyanın SHA-256 özetini içerir; aynı dosyalar `extension/` altında incelenebilir. Özel oturum verileri, kullanıcı kayıtları ve eğitim görselleri bu depoda yayımlanmaz.

## Lisans ve iletişim

Kaynakların görünür olması sınırsız yeniden dağıtım lisansı verildiği anlamına gelmez; mevcut [uygulama lisansı](LICENSE) geçerlidir. Üçüncü taraf bileşenlerin ayrı lisansları kaynak arşivindeki `extension/vendor/THIRD-PARTY-NOTICES.md` bildirimlerinde korunmuştur.

Destek: kilic.ugur@metu.edu.tr. Açık issue’lara parola, çerez, token, eşleştirme kodu veya kişisel ekran görüntüsü eklemeyin.
