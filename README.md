📝 Proje Özeti
Bu proje, Gree (ve Sinclair, ECA vb. fason üretimler) klimaların iç ünitesinde bulunan standart 4-pin UART konnektörünü kullanarak klimayı yerel ağ üzerinden akıllı hale getirmeyi sağlar.
Bulut bağımlılığı olmadan, ESP32 mikrodenetleyicisi ve ESPHome yazılımı kullanılarak klima doğrudan Home Assistant'a entegre edilebilir.

🛠️ Donanım ve Bağlantı Şeması
Gereksinimler:
ESP32 Geliştirme Kartı
4-pin Jumper Kablo
Klima anakartından çıkan 4 tel sırasıyla: +5VDC RX TX GND Aşağıdaki sıralamayla ESP32'ye bağlayın.

+5VDC	  --> ESP 32'deki VIN / 5V	

Klima RX  -->	GPIO17 (TX2)

Klima TX  -->	GPIO16 (RX2)

GND       -->	GND	Ortak toprak bağlantısı.


Donanım Notu (Lojik Seviye): ESP32 pinleri 5V toleranslı olduğu için doğrudan bağlantı çalışmaktadır. Ancak endüstriyel uzun ömürlülük ve kartı korumak adına,
Klimanın TX pininden ESP32'nin GPIO16 (RX) pinine gelen sinyal hattına basit bir gerilim bölücü (seri 10k, GND'ye 20k direnç) eklenerek 3.3V seviyesine düşürülmesi tavsiye edilir.

🚀 Kullanım
Kodu derleyip ESP32'ye yükleyin (İlk yüklemede bilgisayardan, sonrakilerde Wi-Fi üzerinden OTA ile güncelleyebilirsiniz).
Kartı klimaya bağlayıp klimaya enerji verin.
Cihaz Home Assistant ağına otomatik olarak düşecek ve climate entegrasyonu olarak belirecektir.
Doğrudan tarayıcı üzerinden kontrol etmek isterseniz, ESP32'nin aldığı yerel IP adresini tarayıcınıza yazmanız yeterlidir.

## 👏 Teşekkür ve Atıf (Credits)
Bu projedeki klima haberleşme altyapısı, topluluk tarafından geliştirilen [gekkehenkie11/esphome_gree_ac](https://github.com/gekkehenkie11/esphome_gree_ac) kütüphanesini temel almaktadır. Gree/Sinclair protokolünün tersine mühendislikle çözülmesi ve ESPHome entegrasyonu için asıl geliştiriciye teşekkür ederim.

    
