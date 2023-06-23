# Protokol Nedir ?
Bilgisayar bilimleri açısından protokol bir ağ üzerindeki bilgisayarlar arasındaki iletișimi yöneten kurallar kümesidir.

Protokoller yazılım, donanım veya her ikisi tarafindan uygulanmaktadır. Protokoller network cihazlarının nasıl anlaşacaklarını, veriyi nasıl ileteceklerini ve verilerinin alındıktan sonra nasıl okunacağı gibi süreçleri berlirlerler.
Cihazların anlaşabilmesi için aynı dili konuşması gerekmektedir, protokoller bu noktada devreye girerler. Kısacası protokol aynı dili konuşmnak anlamına gelir.

## IP (Internet Protocol)
IP, internet veya ağ üzerinden gönderilen verilerin formatını belirleyen bir dizi kuraldır.

IP adresi ise, bir cihazı internet veya yerel ağ üzerinde tanımlayan benzersiz bir adrestir. İnternette her bilgisayarın bir IP adresi vardır.
IPv4 32 bit boyutunda olup, noktalarla ayrılmış 4 adet 8 bitlik sayıları ile temsil edilir.

Örneğin: 192.168.1.17

## DNS (Domain Name Server)
Alan ADı Sunucusu, hangi alan adının hangi IP adresine karşılık geldiği bilgisini tutar ve kullnıcıları doğru adreslere yönlendirir.

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

Yukarıda bahsedilen bu olata **Three Way Handshake** (üçlü El Sıkışma) adı verilir. 


