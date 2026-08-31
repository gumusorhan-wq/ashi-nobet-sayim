# ASHİ Güncelleme Sistemi — GitHub Kullanım Kılavuzu

## 1. İlk kullanım

GitHub’daki güncel ASHİ uygulama dosyasını indirin: `HUSER ASHİ NÖBET SAYIM RAPORU v01.13.html`. Dosyayı Mac veya Windows bilgisayarınızda sabit bir klasöre kaydedin ve tarayıcıda bu dosyayı açın.

Uygulama açıldığında güncelleme kaynağı uygulama içinde tanımlı güvenli GitHub adresinden otomatik olarak takip edilir. Bu adres kullanıcı arayüzünde ve **Kılavuz** bölümünde gösterilmez; kullanıcıdan ayrıca adres girmesi istenmez.

## 2. Güncelleme geldiğinde

Uygulama açılışta manifesti kontrol eder. Üst başlıkta **Yeni sürüm hazır** uyarısı ve **Yeni sürümü indir** düğmesi görünürse düğmeye basın. Yeni HTML dosyasını cihazınıza kaydedin ve eski HTML dosyasının yerine kullanın. Uygulama eski dosyanın üzerine otomatik yazmaz; son değiştirme işlemi kullanıcı tarafından yapılır.

Kontrolü beklemek istemezseniz üst başlıktaki **Güncellemeyi kontrol et** düğmesine basabilirsiniz. İnternet bağlantısı yoksa veya GitHub’a erişilemiyorsa uygulamanın analiz işlevleri çalışmaya devam eder; yalnızca sürüm kontrolü yapılamaz.

## 3. Son 6 ayın yerel arşivi

v01.13’ten itibaren yüklenen rapor ayları, işlenmiş rapor durumu ile birlikte yalnızca raporu açtığınız tarayıcının yerel **IndexedDB** alanında saklanır. Arşiv paneli hem ilk açılış ekranında, Excel yükleme alanının altında hem de Kılavuz bölümünde gösterilir. İki görünüm aynı yerel kayıtları kullanır. Veriler GitHub’a veya başka bir sunucuya gönderilmez. Tarayıcı site verilerini temizlemek yerel arşivi de temizler.

Arşiv paneli son 6 rapor ayını gösterir. Aynı ay tekrar yüklendiğinde uygulama mevcut kaydı güncellemeden önce onay ister. İptal edilirse mevcut kayıt ve mevcut rapor korunur; onaylanırsa aynı ay anahtarı güncellenir ve çift kayıt oluşturulmaz. Arşiv kartındaki **Aç** düğmesi raporu yeniden görüntüler. **Sil** düğmesi ayrıca onay ister ve yalnızca seçilen arşiv kopyasını kaldırır; ekranda açık olan raporu silmez. Altıncı ayı aşan yeni kayıt geldiğinde en eski kayıt otomatik olarak çıkarılır.

## 4. Normal nöbet listeleri

Normal nöbet listeleri bölümünde **Komuta Kontrol Listesi** ve **Başhekimlik Listesi** ayrı butonlarla açılır. İstasyon adı alanındaki **Manisa Komuta Kontrol Merkezi** ve **Başhekimlik** birim kayıtları bu listelere dahil edilir. Her liste sürücü grubundaki mantıkla personel bazında tek satır ve toplam nöbet sayısı gösterir. Başhekimlik listesinde branş veya görev türü ayrımı yapılmaz; bu birimde nöbet tutan herkes listelenir. Özel listelere ayrıca analiz ve Excel dışa aktarımı uygulanmaz.

## 5. Çoklu İstasyon sayımı

Çoklu İstasyon sayımı kişi adedine göre yapılmaz. Kişinin asıl/kendi istasyonundaki nöbetleri sayım dışı bırakılır; yalnızca asıl istasyondan farklı istasyonlarda tuttuğu nöbetler sayılır. Ekran ve Excel çıktısı toplam farklı istasyon nöbet sayısını kişi sayısından ayrı gösterir; istasyon satırlarında yalnızca bu nöbetlerin adedi yazılır.

## 6. Yeni sürümün GitHub’a yayınlanması

Yeni bir sürüm hazırlandığında HTML içindeki `ASHI_APP_VERSION` değerini artırın. Güncel dosya v01.13’tür; bundan sonraki sürümler `v01.14`, `v01.15` biçiminde ilerletilir. Yeni HTML dosyasını `HUSER ASHİ NÖBET SAYIM RAPORU v01.13.html` biçimindeki yeni sürüm adıyla hazırlayın. Ardından `ashi-update.json` dosyasında `version` değerini yeni sürüm numarasına, `downloadUrl` değerini yeni sürümlü HTML adresine, `fileName` değerini sürümlü HTML adına ve `notes` değerini değişiklik açıklamasına göre güncelleyin.

`version` değeri yerel uygulamadaki sürümden büyük olduğu anda kullanıcıya güncelleme bildirimi gösterilir. Yeni HTML dosyası her sürümde `HUSER ASHİ NÖBET SAYIM RAPORU v{sürüm}.html` biçiminde adlandırılır; uygulamanın indirme düğmesi manifestteki `fileName` değerini kullanır. Böylece indirilen dosya her zaman sürüm numarasını taşır.

## 7. Güvenlik sınırı

Bu depoya Excel raporu, personel adı, T.C. kimlik numarası, nöbet listesi veya başka kişisel veri yüklenmemelidir. GitHub erişim anahtarı da HTML dosyasına eklenmemelidir. Depo yalnızca ASHİ uygulama dosyası, sürüm manifesti ve kullanım kılavuzunu barındırır.

Uygulama GitHub’dan yalnızca herkese açık `ashi-update.json` manifestini ve güncel HTML dosyasını okur. Güncelleme kontrolü otomatik dosya değiştirme yapmaz; kullanıcı uyarıyı gördükten sonra indirme işlemini kendisi başlatır.

## 8. Analiz kapsamı

Uygulamanın nöbet hesaplamaları rapor ayının birinci günü saat 09:00 dahil, sonraki ayın birinci günü saat 09:00 hariç olacak şekilde yapılır. Ekip Şefi, YSP ve Sürücü branşları istasyon-gün bazında 24 saat hedefiyle kontrol edilir. Sürücü Düzeni analizinde başlangıcı 21:00 ve bitişi ertesi gün 09:00 olan 12 saatlik nöbetlerden art arda 3 gece; 24 saatlik nöbetlerden ise nöbet günleri 2 gün arayla gelen 1, 3, 5 örneği gibi en az 3 kayıtlı diziler bildirilir. iOS Excel yükleme, Nöbet İçi Hareket Raporu veya Nöbet Listesi Raporu dosya adı ve başlık doğrulaması, filtreli analiz, çakışma ve eksik saat listeleri, 5 gün ve üzeri boşluk analizi, mobil kart görünümü ve Excel dışa aktarma özellikleri korunur.
