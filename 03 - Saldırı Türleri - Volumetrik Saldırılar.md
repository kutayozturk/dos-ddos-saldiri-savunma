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
