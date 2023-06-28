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

## NTP Amplification Saldırıları
NTP protokolü, internete bağlı olan makinelerin saatlerini senkronize etmek için kullanılır.

Saldırganın public NTP (Network Tıme Protocol) sunucularını kullanarak hedef sistemin bant genişliğini, alabileceğinden fazla paket sayısına maruz bırakarak trafiğin yavaşlamasına, hatta sistemin servis dışı kalmasına neden olan saldırıdır.

Saldırgan, botnetleri kullanarak ve isteği UDP üzerinden gerçekleştirerek kendisini güvene almaktadır. Çünkü UDP, TCP gibi "Üçlü El Sıkışma” yapmadan veri akışını sağlamaktadır. UDP'de, kimlik kontrolü ve veri filtrelenme olmadığı için paketler güvensiz ve hızlı bir şekilde iletilir.

![image](https://github.com/kutayozturk/dos-ddos-saldiri-savunma/assets/94574681/c00d59cd-a44b-4e70-9fdd-4d9680c7a225)

- Saldırgan, saldırının miktarını arttırmak ve kendisini gizlemek için botnet kullanır.
- Botnet, sahte IP adresi içeren UDP paketlerini monlist komutunun aktif olduğu public NTP sunucularına gönderir. - Public NTP sunucularına gönderilen her UDP paketi, monlist komutunu kullanarak NTP sunucusuna istekte bulunur ve büyük bir yanıt alınır.
- NTP sunucusu, yanıtları sahte IP adresi olarak belirtilen hedef sistemine gönderilir.
- Hedef sistemin yanıt almasıyla ağ bant genişliği dolup ağ trafiği yavaşlar ve servis kesinti ile sonuçlanır.

## Protokol Saldırıları

Bağlantı oturum bilgisi (session) kullanan güvenlik Duvarı, yük dengeleme cihazları, yönlendiriciler vb. sistemler hedef alınır. çok sayıda oturum açma isteğinde bulunup, oturum tamamlanmadan yeni istekler gönderilir. Bu şekilde ağ ve güvenlik cihazlarının oturum tablolarını doldurup işlevsiz hale gelmesi sağlanır.

En popüler protokol saldırılarına örnek olarak SYN/SYN-ACK/ACK Flood verilebilir.

## SYN FLOOD Saldırıları

İnternet dünyasının en fazla kullanılan DDOS saldırı tipidir.

Mevcut sunucu kaynaklarını tüketerek meşru trafiğe kapatmayı amaçlayan önemli bir DDOS saldırısıdır.

SYN paketlerini tekrar tekrar göndererek, hedef makinedeki tüm kullanılabilir bağlantı noktalarını doldurabilir ve hedeflenen aygıtın trafiğe yavaş bir şekilde yanıt vermesine veya hiç yanıt vermemesine neden olacaktır.

![image](https://github.com/kutayozturk/dos-ddos-saldiri-savunma/assets/94574681/c7885015-6e73-4017-b3ff-706089e79570)

- Saldırgan, hedeflenen sunucuya genellikle sahte IP adresleriyle çok yüksek hacimde SYN paketleri gönderir.
- Sunucu daha sonra bağlantı isteklerinin her birine yanıt verir ve yanıtı almaya hazır bir açık bağlantı noktası bırakır.
- Sunucu hiçbir zaman ulaşmayan son ACK paketini beklerken, saldırgan daha fazla SYN paketi göndermeye devam eder.
- Her yeni SYN paketinin gelişi, sunucunun belirli bir süre için yeniden bir açık bir bağlantı noktasını geçici olarak sürdürmesine neden olur ve tüm kullanılabilir bağlantı noktaları tüketildikten sonra sunucu kilitlenmeye ve hizmet verememeye başlar.

## Uygulama Katmanı Saldırıları

Bu atak tipinde temel amaç yine kaynakları tüketmektir. Bu tip saldırılar web sayfalarının sunucuda üretildiği ve HTTP isteklerine yanıt olarak iletildiği 7. katman olan uygulama katmanını hedefler.

7. katman seviyesinde yapılan saldırıların savunması zor olabilmektedir.

Bunun nedeni de hangi trafiğin kötü niyetli olduğunu kestirmenin zorluğudur.

Bu ataklarda bant genişliği düşüktür ve genellikle belli zafiyetlerden yararlanılarak yapılmaktadır. Örneğin Apache'de bulunan bir açık gibi.

## HTTP Flood Saldırıları

Sunucuya, sunucunun cevap verebileceğinden çok daha fazla, artarda gönderilen HTTP isteklerinden oluşan saldırı türüdür.

Bu seviyedeki bir saldırı, ağı veya sunucuyu kaynaklarından devre dışı bırakmasıyla oluşur. Donanım artık yeterli kaynağa sahip olmadığında, istemciden gelen isteklere verilen yanıtlar daha fazla zaman gerektirir. Donanıma sayısız istek gönderilmeye devam ettiği için, sistemin sürekli olarak aşırı yüklenmesine neden olur ve sunucuya veya tüm ağa artık erişilemez.

![image](https://github.com/kutayozturk/dos-ddos-saldiri-savunma/assets/94574681/18a89814-499b-4a94-9cbf-432da6da52c4)

İstemcinin GET veya POST isteğine dayanır.

Bir istemci bu isteklerden birini gönderdiğinde, sunucu isteği işler ve sonucu istemciye geri gönderir.

GET isteği ile resimler ve metin blokları gibi statik içerik alınır. Dinamik kaynaklara erişim talep edilirse bir POST isteği kullanılır.GET yöntemi sunucudan veri alır ve POST yöntemi sunucuya veri gönderir.

Saldırıda her iki yöntem de uygulanabilir, ancak POST yöntemi sunucu tarafından karmaşık işlemleri tetiklediği için daha sık kullanılır.

## Slowloris Salıdrıları

Slowloris saldırısı, HTTP isteğini hedef web sunucusuna çok yavaş göndererek bağlantı kaynaklarını tüketmeye çalışır.Birçok web sunucusu yazılımını hedefleyebilir, ancak Apache I.x ve 2.x'e karşı oldukça etkili olduğu kanıtlanmıştır.

![image](https://github.com/kutayozturk/dos-ddos-saldiri-savunma/assets/94574681/8f7a53cb-6471-4257-84ae-cd77beedff21)

Tasarım gereği, web sunucusu, HTTP isteğinin tümünün ulaşmasını veya zaman aşımına uğramasını beklemelidir.

Saldırgan, sunucunun HTTP isteği zaman aşımı süresi dolmadan hemen önce HTTP gönderir. Bu bağlantıları mümkün olduğunca uzun süre açık tutmak içindir
