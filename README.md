# ESP32-Wifi-Control-Car
ESP32- WIFI CONTROLLED CAR

KUTAY-EMİN-ROBOT: WiFi Kontrollü Mobil Robot Projesi
Bu projenin amacı, ESP32 mikrodenetleyicisi kullanarak kendi yerel kablosuz ağını (Access Point) oluşturan ve akıllı telefon, tablet veya bilgisayar üzerinden herhangi bir uygulama yüklemeye gerek kalmadan web tarayıcısı ile kontrol edilebilen mobil bir robot geliştirmektir. Sistem, düşük gecikme süresi ile anlık manevra kabiliyeti sunar.
Sistemin Çalışma Prensibi:
Projede ana kontrolcü olarak ESP32 geliştirme kartı ve motorları sürmek için L298N motor sürücü modülü kullanılmıştır. Sistem üç ana aşamada çalışır:
1. Ağ Oluşturma (SoftAP Modu):
Robot açıldığında, ESP32 kartı kendi bünyesinde "KUTAY-EMIN-ROBOT" isminde şifreli bir WiFi ağı yayını başlatır. Bu sayede robotu kullanmak için harici bir modeme veya internete ihtiyaç duyulmaz; robot kendi ağını yanında taşır.
2. Web Sunucusu ve Arayüz:
Kullanıcı, robotun ağına bağlandıktan sonra belirlenen IP adresi (192.168.4.1) üzerinden sisteme erişir. ESP32 içinde barındırılan HTML ve CSS tabanlı web arayüzü, kullanıcının ekranına yön butonlarını (İleri, Geri, Sağ, Sol, Dur) getirir.
3. Motor Kontrolü ve Hareket:
Kullanıcı arayüzden bir komut verdiğinde (örneğin "Sağ"), bu istek WiFi üzerinden robota iletilir. ESP32 bu komutu işleyerek L298N sürücüsüne gerekli dijital sinyalleri gönderir. Dönüşlerde "Tank Dönüşü" (Skid-Steering) mantığı kullanılır; yani sağa dönmek için sağ tekerlek durdurulurken sol tekerlek ileri döndürülür (veya tam tersi).
Hız ve Güç Yönetimi:
Robotun kontrolsüz hızlanmasını engellemek ve pillerin ömrünü uzatmak için PWM (Darbe Genişlik Modülasyonu) tekniği kullanılmıştır.
* Motorlara tam güç (%100) yerine, optimize edilmiş bir hız değeri (örneğin %60-70) gönderilir.
* Bu sayede robot virajlarda savrulmaz, kalkışlarda ani akım çekerek sistemi resetlemez ve daha kararlı bir sürüş sağlar.
Web Arayüzü Özellikleri:
* Responsive Tasarım: Hem telefon hem de bilgisayar ekranlarına otomatik uyum sağlar.
* Görsel Geri Bildirim: Yön okları (▲, ▼, ◄, ►) evrensel HTML kodları ile oluşturulmuştur, her cihazda düzgün görünür.
* Düşük Gecikme: AJAX teknolojisi kullanılarak sayfa yenilenmeden komutlar anlık olarak robota iletilir.
Kullanılan Donanımlar:
* ESP32 Geliştirme Kartı: WiFi özelliği ve işlemci (Beyin).
* L298N Motor Sürücü: Motorlara güç aktarımı (Kaslar).
* 2 Adet DC Redüktörlü Motor (Sarı): Hareket mekanizması.
* 2WD Robot Şasesi: Pleksiglas gövde.
* Li-ion Piller (18650) ve Yuvası: Güç kaynağı.
* Sarhoş Teker: Denge ve yönlendirme için ön tekerlek.
* Jumper Kablolar: Devre bağlantıları.
Kullanılan Yazılım:
* Arduino IDE: Kodlama ve derleme ortamı (C++ tabanlı).
Kullanılan Kütüphaneler:
* WiFi.h: ESP32'nin kablosuz ağ özelliklerini yönetmek ve Access Point (Erişim Noktası) oluşturmak için.
* WebServer.h: HTTP isteklerini (GET/POST) karşılamak ve HTML arayüzünü yayınlamak için.

YOUTUBE Linki: https://www.youtube.com/shorts/MzI0SJ3nXkc
KUTAY ÖZTÜRK VE MEHMET EMİN ÇİĞDEM TARAFINDAN YAPILMIŞTIR.
