# ASHİ Nöbet Sayım

ASHİ Nöbet Sayım, **Nöbet İçi Hareket Raporu** Excel dosyasını tek dosyalı HTML uygulaması içinde analiz eder. Uygulama Mac, Windows, iPhone ve iPad tarayıcılarında kullanılmak üzere hazırlanmıştır.

## Güncel dosya

Güncel uygulama dosyası: [`HUSER ASHİ NÖBET SAYIM RAPORU v2026.08.23.3.html`](./HUSER%20ASH%C4%B0%20N%C3%96BET%20SAYIM%20RAPORU%20v2026.08.23.3.html)

Uygulama sürümü: **2026.08.23.3**

## Güncelleme sistemi

Uygulama açılışta ve üst başlıktaki **Güncellemeyi kontrol et** düğmesine basıldığında [`ashi-update.json`](./ashi-update.json) manifestini kontrol eder. Manifestteki sürüm yerel sürümden daha yeni ise uygulama uyarı gösterir ve **Yeni sürümü indir** düğmesini açar. Güncelleme işlemi kullanıcı tarafından başlatılır; eski HTML dosyası otomatik olarak üzerine yazılmaz.

Manifestte yeni sürüm yayınlamak için `version` değerini artırın ve `downloadUrl` ile `fileName` değerlerini `HUSER ASHİ NÖBET SAYIM RAPORU v{sürüm}.html` biçimindeki yeni dosya adıyla eşleştirin. Böylece her indirme dosyası kendi sürüm numarasını taşır.

| Manifest alanı | Açıklama |
|---|---|
| `version` | Uygulamanın noktalı sürüm numarası |
| `downloadUrl` | İndirilecek güncel HTML dosyasının HTTPS adresi |
| `fileName` | İndirme sırasında kullanılacak dosya adı |
| `notes` | Kullanıcıya gösterilecek sürüm açıklaması |

## Analiz standardı

Tüm hesaplamalar rapor ayının birinci günü saat **09:00 dahil**, sonraki ayın birinci günü saat **09:00 hariç** olacak şekilde `[T0,T1)` penceresinde yapılır. Nöbet kayıtları Ekip Şefi, YSP ve Sürücü branşlarına göre istasyon-gün bazında değerlendirilir. Her branş ve istasyon-gün için hedef nöbet süresi 24 saattir.

Uygulamada iOS uyumlu Excel yükleme, dosya adı ve başlık doğrulaması, istasyon-gün eksik/fazla saat analizi, vardiya çakışması, filtreli analiz, mobil kart görünümü, 5 gün ve üzeri personel boşluk analizi ve biçimlendirilmiş Excel dışa aktarma özellikleri bulunur. **Sürücü Düzeni** bölümünde başlangıcı 21:00 ve bitişi ertesi gün 09:00 olan 12 saatlik nöbetlerden art arda 3 gece; 24 saatlik nöbetlerden ise nöbet günleri 2 gün arayla gelen 1, 3, 5 örneği gibi en az 3 kayıtlı diziler raporlanır ve Excel’e aktarılır.

## Güvenlik

Bu depoya Excel raporları, personel listeleri, kişisel veriler veya GitHub erişim anahtarları yüklenmez. Depo yalnızca uygulama kaynak dosyası, güncelleme manifesti ve kullanım açıklamalarını içerir. Uygulama içinde GitHub erişim anahtarı bulunmadığından, güncelleme kontrolü herkese açık manifest ve indirme dosyası üzerinden yapılır.

## Sonraki sürüm yayınlama adımları

1. Yeni HTML dosyasını `HUSER ASHİ NÖBET SAYIM RAPORU v2026.08.24.1.html` biçimindeki sürümlü adla hazırlayın.
2. HTML içindeki `ASHI_APP_VERSION` değerini aynı yeni sürüm numarasına yükseltin.
3. Yeni dosyayı bu depoya yeni adıyla ekleyin.
4. `ashi-update.json` içindeki `version`, `downloadUrl`, `fileName` ve `notes` alanlarını güncelleyin.
5. Değişiklikleri aynı ana dala gönderin.
6. Kullanıcı uygulamayı açtığında veya **Güncellemeyi kontrol et** düğmesine bastığında yeni sürüm uyarısını görür.

## Lisans ve kullanım

Bu uygulama HUSER ASHİ iç kullanımına yöneliktir. Depoda kullanıcı Excel verisi bulunmaz.
