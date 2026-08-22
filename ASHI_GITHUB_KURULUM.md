# ASHİ Güncelleme Sistemi — GitHub Kullanım Kılavuzu

## 1. İlk kullanım

GitHub’daki güncel ASHİ uygulama dosyasını indirin: `ashi_surucu_nobet_sayim_0900.html`. Dosyayı Mac veya Windows bilgisayarınızda sabit bir klasöre kaydedin ve tarayıcıda bu dosyayı açın.

Uygulama açıldığında güncelleme manifesti varsayılan olarak şu GitHub adresinden takip edilir:

`https://raw.githubusercontent.com/gumusorhan-wq/ashi-nobet-sayim/main/ashi-update.json`

Bu adresi ayrıca uygulamanın **Kılavuz > Sürüm güncelleme kontrolü** alanında görebilirsiniz. İsterseniz farklı bir manifest adresi yazabilirsiniz; adres tarayıcıda yerel olarak saklanır.

## 2. Güncelleme geldiğinde

Uygulama açılışta manifesti kontrol eder. Üst başlıkta **Yeni sürüm hazır** uyarısı ve **Yeni sürümü indir** düğmesi görünürse düğmeye basın. Yeni HTML dosyasını cihazınıza kaydedin ve eski HTML dosyasının yerine kullanın. Uygulama eski dosyanın üzerine otomatik yazmaz; son değiştirme işlemi kullanıcı tarafından yapılır.

Kontrolü beklemek istemezseniz üst başlıktaki **Güncellemeyi kontrol et** düğmesine basabilirsiniz. İnternet bağlantısı yoksa veya GitHub’a erişilemiyorsa uygulamanın analiz işlevleri çalışmaya devam eder; yalnızca sürüm kontrolü yapılamaz.

## 3. Yeni sürümün GitHub’a yayınlanması

Yeni bir sürüm hazırlandığında HTML içindeki `ASHI_APP_VERSION` değerini artırın. Güncel HTML dosyasını bu depodaki `ashi_surucu_nobet_sayim_0900.html` dosyasının yerine koyun. Ardından `ashi-update.json` dosyasında `version` değerini aynı yeni sürüm numarasına, `downloadUrl` değerini sabit HTML adresine ve `notes` değerini değişiklik açıklamasına göre güncelleyin.

`version` değeri yerel uygulamadaki sürümden büyük olduğu anda kullanıcıya güncelleme bildirimi gösterilir. Kararlı kullanım için HTML dosya adını ve GitHub adresini değiştirmeyin; sonraki sürümlerde yalnızca HTML içeriğini ve manifest sürümünü güncelleyin.

## 4. Güvenlik sınırı

Bu depoya Excel raporu, personel adı, T.C. kimlik numarası, nöbet listesi veya başka kişisel veri yüklenmemelidir. GitHub erişim anahtarı da HTML dosyasına eklenmemelidir. Depo yalnızca ASHİ uygulama dosyası, sürüm manifesti ve kullanım kılavuzunu barındırır.

Uygulama GitHub’dan yalnızca herkese açık `ashi-update.json` manifestini ve güncel HTML dosyasını okur. Güncelleme kontrolü otomatik dosya değiştirme yapmaz; kullanıcı uyarıyı gördükten sonra indirme işlemini kendisi başlatır.

## 5. Analiz kapsamı

Uygulamanın nöbet hesaplamaları rapor ayının birinci günü saat 09:00 dahil, sonraki ayın birinci günü saat 09:00 hariç olacak şekilde yapılır. Ekip Şefi, YSP ve Sürücü branşları istasyon-gün bazında 24 saat hedefiyle kontrol edilir. iOS Excel yükleme, dosya adı ve başlık doğrulaması, filtreli analiz, çakışma ve eksik saat listeleri, 5 gün ve üzeri boşluk analizi, mobil kart görünümü ve Excel dışa aktarma özellikleri korunur.
