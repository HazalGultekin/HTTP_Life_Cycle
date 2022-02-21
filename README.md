# HTTP Yaşam Döngüsü


## 1- Girilen domain IP adresine çevrilir: 
Tarayıcıya girilen domain (örneğin: www.google.com) DNS sunucularına sorularak IP adresi bulunur.

### DNS(Domain Name System): 
Alan adlarını(www.google.com) IP adreslerine çevirir.(77.125.658….)

### Cloudflare Nedir?
DNS ayarlarını yapıyor.
İnternet güvenliği, DDoS, içerik dağıtımı, alan adı ve sunucu konularında hizmet veriyor. 
Sitenizi güvenli ve hızlı bir şekilde yayınlayabilmenize imkân tanıyan sistem, cache özelliği ile de sitenizi %30 oranında hızlandırabiliyor. 
Siber saldırılara karşı da etkili olan servis, bu sayede ticari sitelerde de rahatlıkla kullanılabiliyor.



## 2- IP adresine TCP bağlantısı(request) açılır: 
Bulunan IP adresine TCP bağlantısı açılıp(request) girilen domain host header ı ile gönderilir.
GET/HTTP/1.1
Host: www.google.com
Burada kullanıcının istediği sayfa anasayfa olduğundan “/” parametresi GET metodu ile gönderilmiştir. 

 ### TCP( Transmission Control Protocol ) :
 Bilgisayarlar arasındaki iletişimin küçük paketler halinde ve kayıpsız olarak gerçekleşmesini sağlayan bir protokoldür.
 
En önemli özelliği: Kimlik doğrulaması yapması ve veriyi gönderirken veya alırken veri bütünlüğünü korumasıdır.
 Çalışma mantığı 3 başlıkta incelenir: 
Birinci aşamada hedefe bir bağlantı isteği gönderilir. 
İkinci aşamada bağlantının gerçekleştiği onaylanır ve veri transferi başlar.
Üçüncü aşamada ise veri transferinin tamamlandığı taraflara iletilerek bağlantı sonlandırılır.


## 3- Server cevap(response) döner: 
IP adresinde bulunan server isteği işleyip cevap(response) dönüyor.
Server bu isteği işlerken port bilgisine bakarak ilgili web sunucusuna (ngnix, apache, iis) yönlendirir.
Web sunucusu gelen host header’ı ile hangi siteyi çalıştıracağına karar verip ilgili sitenin kodunu işletir.



### Web sunucusu nedir?
Hosting(barındırma) işlemini internet protokolü(IP) üzerinde sunan bir sunucudur.
Web sitesine ait dosyalar için depo vazifesi gören ve İnternet kullanıcılarının erişimine sunan bilgisayarlara Web sunucusu (web server), bu veri saklama ve yayınlama işlemine de Web hosting denir.

### Nginx nedir?
Yüksek trafikli, yoğun istek girişi olan web siteleri için biçilmiş web sunucusudur.
Nginx diğer web sunucularına göre %400 daha yüksek performanslı, daha hızlı ve daha az cpu kullanır.

Temel Özellikleri
**Reverse PROXY(Ters Vekil Sunucusu) :**  Client’tan gelen istekleri sunucu adına alan vekil sunucu diyebiliriz. Gelen istekleri karşılayarak sunucuya iletir ve dönen cevapları istemciye iletir.

Sağladığı Avantajlar
Sunucuların varlığını ve özelliğini gizleyebilir.
İstemcileri web tabanlı saldırılara karşı koruyabilir.
Web sunucuları üzerinde yükü azaltarak, web isteklerine hızlı bir şekilde cevap verir.

**Load Balancing (Yük Dengeleme) :** Server üzerindeki fazla yükleri diğer serverlara dağıtarak işlemlerin birden fazla makinede kısa sürede çözülmesini sağlar.

**Virtual Host (Sanal Sunucu) ** 
**Statik ve index dosyalarının sunumu, otomatik indeksleme.**


# 4- Cevap render edilir: Cevabı alan browser gelen cevabı ekrana basar(render). 

Browser render işleminde html ile layout’u, css ile tasarımı oluşturur. 
Javascript ise yukarıdaki işlemler yapıldıktann sonra hem css hem html üzerine(DOM) değişiklikler yaprak siteye dinamiklik kazandırır.

