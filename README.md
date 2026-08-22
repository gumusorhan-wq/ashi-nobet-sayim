# ASHİ Nöbet Sayım

ASHİ Nöbet Sayım, **Nöbet İçi Hareket Raporu** Excel dosyasını tek dosyalı HTML uygulaması içinde analiz eder. Uygulama Mac, Windows, iPhone ve iPad tarayıcılarında kullanılmak üzere hazırlanmıştır.

## Güncel dosya

Güncel uygulama dosyası: [`ashi_surucu_nobet_sayim_0900.html`](./ashi_surucu_nobet_sayim_0900.html)

Uygulama sürümü: **2026.08.23.1**

## Güncelleme sistemi

Uygulama açılışta ve üst başlıktaki **Güncellemeyi kontrol et** düğmesine basıldığında [`ashi-update.json`](./ashi-update.json) manifestini kontrol eder. Manifestteki sürüm yerel sürümden daha yeni ise uygulama uyarı gösterir ve **Yeni sürümü indir** düğmesini açar. Güncelleme işlemi kullanıcı tarafından başlatılır; eski HTML dosyası otomatik olarak üzerine yazılmaz.

Manifestte yeni sürüm yayınlamak için `version` değerini artırın ve `downloadUrl` değerinin güncel HTML dosyasını göstermesini sağlayın. Kararlı kullanım için HTML dosya adını değiştirmeden güncellemek ve yalnızca manifest sürümünü artırmak önerilir.

| Manifest alanı | Açıklama |
|---|---|
| `version` | Uygulamanın noktalı sürüm numarası |
| `downloadUrl` | İndirilecek güncel HTML dosyasının HTTPS adresi |
| `fileName` | İndirme sırasında kullanılacak dosya adı |
| `notes` | Kullanıcıya gösterilecek sürüm açıklaması |

## Analiz standardı

Tüm hesaplamalar rapor ayının birinci günü saat **09:00 dahil**, sonraki ayın birinci günü saat **09:00 hariç** olacak şekilde `[T0,T1)` penceresinde yapılır. Nöbet kayıtları Ekip Şefi, YSP ve Sürücü branşlarına göre istasyon-gün bazında değerlendirilir. Her branş ve istasyon-gün için hedef nöbet süresi 24 saattir.

Uygulamada iOS uyumlu Excel yükleme, dosya adı ve başlık doğrulaması, istasyon-gün eksik/fazla saat analizi, vardiya çakışması, filtreli analiz, mobil kart görünümü, 5 gün ve üzeri personel boşluk analizi ve biçimlendirilmiş Excel dışa aktarma özellikleri bulunur.

## Güvenlik

Bu depoya Excel raporları, personel listeleri, kişisel veriler veya GitHub erişim anahtarları yüklenmez. Depo yalnızca uygulama kaynak dosyası, güncelleme manifesti ve kullanım açıklamalarını içerir. Uygulama içinde GitHub erişim anahtarı bulunmadığından, güncelleme kontrolü herkese açık manifest ve indirme dosyası üzerinden yapılır.

## Sonraki sürüm yayınlama adımları

1. Yeni HTML dosyasını `ashi_surucu_nobet_sayim_0900.html` adıyla hazırlayın.
2. HTML içindeki `ASHI_APP_VERSION` değerini yeni sürüm numarasına yükseltin.
3. Bu depodaki HTML dosyasını yeni dosyayla değiştirin.
4. `ashi-update.json` içindeki `version`, `downloadUrl`, `fileName` ve `notes` alanlarını güncelleyin.
5. Değişiklikleri aynı ana dala gönderin.
6. Kullanıcı uygulamayı açtığında veya **Güncellemeyi kontrol et** düğmesine bastığında yeni sürüm uyarısını görür.

## Lisans ve kullanım

Bu uygulama HUSER ASHİ iç kullanımına yöneliktir. Depoda kullanıcı Excel verisi bulunmaz.
