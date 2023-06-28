![image](https://github.com/kutayozturk/dos-ddos-saldiri-savunma/assets/94574681/c25c9eab-c188-4be6-84b1-de850bd169c7)

# Volumetrik Saldırılar
Saldırganlar tarafından en sık kullanılan atak çeşidi olup, sistem kaynaklarını tüketmeyi hedeflemektedir. 

Sık karşılaşılan volumetrik saldırı çeşitleri
- UDP Flood
- ICMP Flood
- Reflection Amplification Saldırıları

## UDP Flood Saldırıları
UDP Flooad salırıları, bağlantısız ve oturumsuz bir ağ protokolü olan UDP'yi etkielyen ve temel amacı güvenlik duvarının oturum tablosunu doldurarak erişilemez halen getiren DDoS türüdür.

UDP flood saldırıalrının işleyiş biçimi temelde, hedef sistemin ratgele portlarına çok sayıda UDP paketi göndermesi prensibine dayanır.

![image](https://github.com/kutayozturk/dos-ddos-saldiri-savunma/assets/94574681/7e79cbe1-5dc9-434f-9dc0-2944b21b76ce)

Çok sayıda UDP paketine maruz kalan hedef sistem öncelikle;
- Portı dinleyen bir uygulama var mı diye kontrol eder
- Hiçbir uygulamanın o protu dinlemediğini görür
- ICMP "Hedef Erişlemez" paketi ile cevap verir

  Bu döngü sonubnda çok sayıda UDP paketine, çok sayıda ICMP paketi ile karşılık vermek zorunda kalan hedef sistem sonunda erişilemez hale gelir.

### UDP Flood Saldırılarına Karşı Alınabilecek Önlemler
- Güçlü güvenlik duvarları kullanmak
- Belirli IP adresinden gelecek istekleri sınırlandırmak
- Timeout değerleri düşürülebilir
- Timeout değeleri kullanılarak UDP Sessionları'nın hızlıca kapatılması s
- Rate Limiting özelliği ile bir IP'den 500'den fazla istek geldiyse o IP adresini engellemek

## ICMP Flood Saldırıları

Normalde iki bilgisayar arasında ICMP talebi gönderildiğinde, gönderen ile alıcı cihaz arasındaki bağlantıyı teşhis etmke için kullanılır. Bununla birlikte bu tarz saldırılar hedefe yönelik aşırı yük oluşturmak için kullanılır.

ICMP talep paketleri ile hedef sistemin hem giden hem gelen bant genişliğine aşırı yük bindirerek sistemin çalışamaz hale getirmek amaçlanmaktadır.

![image](https://github.com/kutayozturk/dos-ddos-saldiri-savunma/assets/94574681/b25b479b-0d4d-499b-9c8d-f65f1bee7954)

### ICMP Saldırılarına Karşı Alınabilecek Önlemler
- Gelen paketlerin boyut sınırlandırılması yapılabilir
- Süre aralığı verilip gelen paketleribn sayısı ve boyutu kısıtlanabilir
- ICMP hata mesajlarının dışarı çıkışına izin verilmemeli
- İnternetten iç ağa ICMP trafiği engellenmelidir


## Reflection Amplification Saldırıları

Yansıma saldırılarında, saldırganlar bir hedefin IP adresini taklit eder ve bir bilgi talebi gönderir. Sunucu daha sonra istege yanit vererek hedefin IP adresine bir yanıt gönderir.

Amplification tipi saldırılarda trafik kapasitesi yüksek, aracı sistemler kullanarak saldırgan sahip oldugu bandwidth miktarından çok daha fazlasını hedef sisteme yönlendirir.

Amplifikasyon saldırıları "asimetriktir", yani saldırgan tarafından daha fazla sayıda hedef kaynağın bașarısız olmasına neden olmak için daha az sayıda veya düșük düzeyde kaynağa ihtiyaç duyulur.

Bu saldırı türünde, kurbanın IP adresi ile DNS sunucularına sorgular gönderilir. Kurban gönderilen bu DNS sorgularının yanıtlarını alır.

Nispeten az miktarda kaynak ve çaba ile bir saldırgan, hedef sitenin performansını önemli ölçüde azaltabilir, hatta tamamen kapanmasını sağlayacak miktarda DNS isteği gönderebilir.

![image](https://github.com/kutayozturk/dos-ddos-saldiri-savunma/assets/94574681/2b7e6238-296c-40bf-9b9e-fd98e15d1179)

Saldırgan, DNS çözümleyicisine göndereceği isteğin kaynak IP adresini hedef IP adresi olarak ayarlar.

UDP paketleriyle yapılan isteklerin yanıtlarının büyük boyutlu olması için "ANY" argümanı gibi argümanları ileten DNS çözümleyicileri tespit edilir.

Saldırgan, Botnet kullanarak hazırlanan UDP paketleri ile DNS çözümleyicilerine istekte bulunur.

Gönderilen isteğe karşı DNS çözümleyicileri, hedefin IP adresine yanıt verir.

Hedef, istek göndermediği DNS çözümleyicilerinden yanıt alır.

Hedefin bulunduğu ağın alt yapısı gelen trafiğin yoğunluğu nedeniyle yavaşlayabilir ve hizmet reddi verebilir.
