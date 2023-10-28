# Protokol Nedir ?
Bilgisayar bilimleri açısından protokol bir ağ üzerindeki bilgisayarlar arasındaki iletișimi yöneten kurallar kümesidir.

Protokoller yazılım, donanım veya her ikisi tarafindan uygulanmaktadır. Protokoller network cihazlarının nasıl anlaşacaklarını, veriyi nasıl ileteceklerini ve verilerinin alındıktan sonra nasıl okunacağı gibi süreçleri berlirlerler.
Cihazların anlaşabilmesi için aynı dili konuşması gerekmektedir, protokoller bu noktada devreye girerler. Kısacası protokol aynı dili konuşmak anlamına gelir.

## IP (Internet Protocol)
IP, internet veya ağ üzerinden gönderilen verilerin formatını belirleyen bir dizi kuraldır.

IP adresi ise, bir cihazı internet veya yerel ağ üzerinde tanımlayan benzersiz bir adrestir. İnternette her bilgisayarın bir IP adresi vardır.
IPv4 32 bit boyutunda olup, noktalarla ayrılmış 4 adet 8 bitlik sayıları ile temsil edilir.

Örneğin: 192.168.1.17

## DNS (Domain Name Server)
Alan Adı Sunucusu, hangi alan adının hangi IP adresine karşılık geldiği bilgisini tutar ve kullnıcıları doğru adreslere yönlendirir.

DNS adresi aslında numaralardan oluşan IP adresine lapak takmak, isim vermek olarak düşünüebilir.

IP adreslerini ezberlemek ve akılda tutmak zor olduğundan bu sisteme geçilmiştir.

## HTTP (Hypertext Transfer Protocol)
Bir sunucu (server) ile bir istemci (client) arasındaki haberleşmeye olanak sağlayan iletişim protokolüdür.

İstemcilerin web sayfaların sunuculardan nasıl isteyeceğini ve sunucuların bu sayfaları istemcilere nasıl aktaracağını HTTP tanımlar.

> **HTTP Nasıl Çalışır?**
> 
>ilk olarak TCP baglantısı açılır, kullanıcı istek (HTTP isteği) gönderir sunucu da buna uygun cevap döner ve TCP baglantisi kapatilir.


## TCP (Transmission Control Protocol)
Bilgisayarlar arasındaki iletişimin, küçük paketler halinde ve kayıpsız olarak gerçekleştirilmesini sağlayan protokoldür.

İnternette kullanılan en yaygın protokoldür.

Network ağlarında iletişimde kayıpsız veri gönderebilmek amacıyla yazılmıştır. HTTP, HTTPS, POP3, SSH, SMTP, Telnet, FTP gibi protokollerin veri iletimi TCP aracılığla yapılır.

## TCP Bağlantısı Nasıl Çalışır?

- X bilgisayuarı Y bilgisayarına bir SYN mesajı yollar.
- Y bilgisayarı X bilgisayarının istediğini anladığına dair bir SYN+ACK mesajı yollar
- X bilgisayarı Y bilgisayına ACK yollar.

Yukarıda bahsedilen bu olaya **Three Way Handshake** (üçlü El Sıkışma) adı verilir. 

![image](https://github.com/kutayozturk/dos-ddos-saldiri-savunma/assets/94574681/dff9e5c6-97db-4c31-a3f9-faf88dba8014)

- ACK: Verinin karşı tarafa sorunsuzca ulaştığını belirtir.
- SYN: TCP bağlantısının kurulacağını belirtir.
- FIN: TCP oturumunun sonlandırılmasını sağlar.
- RST: Bağlantılarda hatalar meydana geldiğinde, alıcı ve göndericinin bağlantıyı kesmesini sağlar.
- URG: Gelen veri parçasının öncelikli olarak işleme alınmasını sağlar
- PSH: Veri parçaları içerisinde öncelik belirlemek için kullanılır.

## UDP (User Datagram Protocol)

Veri aktarım protokollerinden biridir. Verilerin herhangi bir bağlantı kurmadan karşı tarafa gönderilmesini sağlayan protokoldür.

UDP'yi kullanan protokollerden bazıları DNS, TFTP ve SNMP protokolleridir.

## ICMP (Internet Control Message Protocol)

ICMP, TPC/IP'nin işlemesine yardımcı olan bşir protokoldür.

Her hostta mutlaka ICMP protokolü çalışır.

Hata durumunda host tarafından geri bilgilendirilmeyi sağlar.

ICMP ağ hakkında bazı bilgileri toplamak içinde kullanılır.

traceroute ve ping komutları ICMP kullanır.

![image](https://github.com/kutayozturk/dos-ddos-saldiri-savunma/assets/94574681/cfdce281-5164-487a-bc67-a24cca0e0930)

