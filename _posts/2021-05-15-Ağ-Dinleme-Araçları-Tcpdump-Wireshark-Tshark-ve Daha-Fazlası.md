# TCPDUMP NEDİR?
Tcpdum kali linux üzerinde genellikle kurulu gelen bir userın kendi network bağlatısı üzerinde TCP/IP paketlerini veya diğer paketleri izleyip, inceleyip, kaydedip ve analizlemesini sağlayan C programlama diliyle yazılmış ve libpcap kütüphanesi ile oluşturulmuş bir filtreleme yazılımıdır. `"which parametresi"` kullanarak sisteminizde kurulu olup olmadığını kontrol edebilirsiniz.

![tcpdump1](https://user-images.githubusercontent.com/55113204/117137831-f91ad000-adb2-11eb-8882-d4382b4a8e19.PNG)

## -D Parametresi
Bu parametre ile Tcpdum üzerinde dinlenebilecek network interfacelerinin hepsini görüntülemekteyiz.

![tcpdump2](https://user-images.githubusercontent.com/55113204/117138147-4ac35a80-adb3-11eb-9548-a10d30cc88aa.PNG)

## -i Parametresi
Bu parametre ile dinlenmek istenen network interfaceni de belirterek ağı sniffleyebiliriz.

![tcpdump3](https://user-images.githubusercontent.com/55113204/117138426-b0afe200-adb3-11eb-94d3-920a1ba41072.PNG)

## -nnSX port 443 Parametresi
Bu parametre ağdaki HTTPS trafiğini analizlenmesi için çıktı veren parametredir. Sağ taraftaki kısımın tam gözükmemesinin nedeni şifrelenmiş olmasından dolayıdır. Bu parametre sayesinde ağdaki IP adreslerini de öğrenebilmekteyiz.

![tcpdump5](https://user-images.githubusercontent.com/55113204/117141581-5fa1ed00-adb7-11eb-8a4d-08d743b95060.PNG)

## host x.x.x.x -v Parametresi
Bu parametre ile bir IP adresindeki trafiği izleyebilmekteyiz. `"v parametresi"` ise paketin protokol içeriğini de gösteren detaylı bir analiz yapmaktadır.

![tcpdump6](https://user-images.githubusercontent.com/55113204/117141890-c1625700-adb7-11eb-8761-fa9096a9cd2b.PNG)

## -vv Parametresi
Bu parametre ile bir paketin NFS `(Dosyaların; masaüstü, sunucular, dizüstü pcler gibi cihazlar arasında şeffaf bir şekilde paylaşılması ve uzaktan bir bilgisayara bağlanarak kendi pcsindeymiş gibi görüntülenmesi, güncellenmesi, depolanmasına izin veren protokoldür.)` ve SMB `(Dosyaları, yazıcıları, bilgisayarlar arasında adlandırılmış bağlantı kanallarını, seri bağlantı noktalarını gibi iletişim soyutlamalarını paylaşmak için kullanılan protokoldür.)` protokollerinin içeriğini de gösteren detayşlı bir analizleme tekniği sunar.

![tcpdump7](https://user-images.githubusercontent.com/55113204/117144218-58c8a980-adba-11eb-89b8-0ce882de069c.PNG)

## -vvv Parametresi
Bu parametre ile telnet içiriğini gösteren ayrıntılı bir çıktı verir.

![tcpdump8](https://user-images.githubusercontent.com/55113204/117185491-904b4c00-ade2-11eb-91ca-7fa1f7c51d77.PNG)

## -q Parametresi
Bu parametre ile paketlerin sadece temel bilgilerine ulaşmamızı sağlayan parametredir.

![tcpdump9](https://user-images.githubusercontent.com/55113204/117185839-ef10c580-ade2-11eb-8215-51211395f2ec.PNG)

## -c Parametresi
Girilen değer kadar miktardaki paketleri inceleyen parametredir.

![tcpdump10](https://user-images.githubusercontent.com/55113204/117186268-5464b680-ade3-11eb-8bf2-5eff4c2bf0d6.PNG)

## -n Parametresi
Bu parametre ile paketlerin hem IP adreslerini hemde port numaralarını vermektedir.

![tcpdump11](https://user-images.githubusercontent.com/55113204/117186797-df45b100-ade3-11eb-9834-c79b9308feb8.PNG)

## -n dst x.x.x.x Parametresi
Bu parametre ile belirtilen destination (hedef) IP adresine giden paketler hakkında bilgi sahibi olabiliriz.

![tcpdump12](https://user-images.githubusercontent.com/55113204/117187445-96422c80-ade4-11eb-805e-c3a9dad76e79.PNG)

## -n src x.x.x.x Parametresi
Bu paremetre ile source IP adresinden gelen IP paketlerini listelemektedir.

![tcpdump13](https://user-images.githubusercontent.com/55113204/117188907-3ea4c080-ade6-11eb-90e1-3c63b8f94fc6.PNG)

## -n x.x.x.x Parametresi 
Belirtilen IP adresine gelen ve giden tüm paketleri analizlemektedir.

![tcpdump14](https://user-images.githubusercontent.com/55113204/117217898-e0d69f80-ae0a-11eb-9dbc-76c32e2bb918.PNG)

## -n dst net x.x.x.x 
Bu parametre ile destination ağ adresine giden ağ paketleri analizlenmiş olur.

![tcpdump16](https://user-images.githubusercontent.com/55113204/117223134-b211f680-ae15-11eb-847a-ae3d4791b9b5.PNG)

## -n src net x.x.x.x
Bu parametre ile source ağ adresinden giden paketlerin analizlenmesi sağlanır.

![tcpdump18](https://user-images.githubusercontent.com/55113204/117223277-01f0bd80-ae16-11eb-8a4e-dd8a51e492c3.PNG)

## -n net x.x.x.x 
Bu parametre ile ağdaki gelen giden tüm paketler dinlenebilir.

![tcpdump17](https://user-images.githubusercontent.com/55113204/117223012-6b240100-ae15-11eb-96df-ce3236e20c11.PNG)

## -w Parametresi (Dosya Kayıt)
Bu parametre ile ağdaki analizlenen paketlerin çıktılarını bir dosyaya kayıt eden parametredir.  `"c parametresi"` parametresi ile belirtilen sayı kadar paket listelenmesini sağlar.

![tcpdump19](https://user-images.githubusercontent.com/55113204/117223898-652f1f80-ae17-11eb-8e24-2305e83e87e4.PNG)

## -n port port_numarası Parametresi
Bu parametre ile bir porttaki giden gelen paketlerin analizlenmesini sağlamaktadır.

![tcpdump20](https://user-images.githubusercontent.com/55113204/117224230-1635ba00-ae18-11eb-8d78-c967722a8814.PNG)

## -e Parametresi
Bu parametre ile yakalanan paketlerin MAC adreslerini elde edebiliriz.

![tcpdump21](https://user-images.githubusercontent.com/55113204/117224668-3c0f8e80-ae19-11eb-87df-21d7e21f83e3.PNG)

## -r Parametresi (Dosya Okuma)
Bu parametre ile kayıt edilen dosyayı okumayı sağlar.

![tcpdump22](https://user-images.githubusercontent.com/55113204/117225311-b260c080-ae1a-11eb-8e01-19e46eace86f.PNG)

## -v arp Parametresi
Bu parametre ile arp paketlerini listelemektedir.

![tcpdump23](https://user-images.githubusercontent.com/55113204/117225550-4599f600-ae1b-11eb-8d8e-31022bb65ffb.PNG)

## -n src port port_numarası Parametresi
Bu parametresi belirlenmiş port numarasındaki sourceden giden paketleri analizlemektedir.

![tcpdump24](https://user-images.githubusercontent.com/55113204/117225854-04561600-ae1c-11eb-8a6d-dda04e7d5bb5.PNG)

## -n dst port port_numarası Parametresi
Hedef adresteki belirlenmiş hedef port numarasına giden paketleri listelemektedir.

![tcpdump25](https://user-images.githubusercontent.com/55113204/117226027-61ea6280-ae1c-11eb-881c-8b33972e5be7.PNG)

## -v icmp Parametresi
Bu parametre ile ağdaki icmp paketlerini listelenmektedir.

![tcpdump26](https://user-images.githubusercontent.com/55113204/117226161-b5f54700-ae1c-11eb-9e8d-4f7707952c40.PNG)

Hedef Port ya da Host  İçin Trafik Yakalama
Belirlediğimiz bir IP adresi ve Port numarası için nmap taraması yapmaktayız.

![bir](https://user-images.githubusercontent.com/55113204/117451886-c7893c80-af4b-11eb-8523-5af87c77418b.PNG)

Daha sonra bu ağdaki gelen giden paketleri ama belirttiğimiz port ve network olması gerekiyor onları izleyip bir dosyaya kayıt etmeliyiz.

![iki](https://user-images.githubusercontent.com/55113204/117451977-e4be0b00-af4b-11eb-9dc4-8e74ecd858fb.PNG)


Öncelikle nmap taraması yaparak hangi portların açık kapalı olduğuna erişmemiz sağlanır.

![nt1](https://user-images.githubusercontent.com/55113204/117448569-9575db80-af47-11eb-9d22-65ad8e483218.PNG)

## Nmap Taramaları Tcpdump Kullanarak Nasıl Yakalanır?

![nt3](https://user-images.githubusercontent.com/55113204/117448686-b63e3100-af47-11eb-85c6-b00d046c9c55.PNG)

Daha sonra tcpdump kullanarak taranan ağdaki gelen giden paketlerin bilgilerini elde edebilmekteyiz.

![nt2](https://user-images.githubusercontent.com/55113204/117448803-da9a0d80-af47-11eb-9a68-74c61a333201.PNG)

## DDoS Saldırılarında Tcpdump Kullanımının Mantığı Nedir?

Herkese açık bir sisteminiz varsa bu açık kaynaklı sisteminizden herkesin faydalanacağı anlamanı gelmektedir. Bu saldırganın DDoS attack ile sizin hizmetlerinize izinsiz erişmek istediğini ve diğer gerçek kullanıcıların erişmesini engelleyebilmeyi sağlamaktadır. DDoS korumasına sahip olarak sizin bu istekleri engelleyebilmesinizi ve gelebilecek tehtitleri görmenizi sağlamaktadır. Network yöneticilerinin sisteminizi yenileyebilmesi ve iyileştirebilmesi için değişiklikler yaparken DDoS saldırı günlüklerini yakalabilmektedir. Bunu aşağıda gösterildiği gibi yapılabilmektedir. Bu komut ile paketlerin analizi için providera iletebilirsiniz.

![üç](https://user-images.githubusercontent.com/55113204/117453342-8134dd00-af4d-11eb-9a15-599f8212cc22.PNG)

Daha sonra -r parametresi ile yakalayıp sonuc dosyasına attığımız çıktıları görüntüleyelim. Ben burada çok fazla paket aldığımdan dolayı yarıda kestim.

![dört](https://user-images.githubusercontent.com/55113204/117453427-9f024200-af4d-11eb-886a-c056b262daef.PNG)

Wireshark/Tshark Kullanarak Paket Analizi İşlemleri Nasıl Yapılır ?
Tcpdump sunucu tarafından paketler alınırken o paketleri yakalayıp analizlenmesini sağlayan bir programdır. Bunun Windows üzerindeki muadili ise Wiresharktır. Tshark de bir ağ protokolü analizliyicisi olup canlı olan bir ağda paketlerin yakalanmasını ve önceden önceden yakalanmış paketlerin analizlenmesini, yakalanan paketlerin kodu çözülmüş halde çıktı elde etmeye ve bu çıktıları bir dosyaya aktarmayı sağlamaktadır. Default olarak bir seçeneğe kurulmadan Tshark, tcpdump gibi çalışmaktadır. 

Eğer bir analizleme koşulu girmezsek tshark default olarak eth0 üzerindeki giden gelen paketleri analizleyecektir.

![altı](https://user-images.githubusercontent.com/55113204/117461614-716dc680-af56-11eb-8bd9-4c9e4eaa90c2.PNG)


Örnek olarak aşağıda tshark kullanarak bir eth0 ağındaki 80 portundaki giden gelen paketleri analizlemiş bulunmaktayız. Burada doğrudan bir parametre yazabilmek için bpf (berkeley packet filter) syntaxı olan -f parametresini kullandık.

![beş](https://user-images.githubusercontent.com/55113204/117460831-9877c880-af55-11eb-8b6b-c2d3601c160f.PNG)

Eğer ekrana değilde bir dosyaya yazdırmak istiyorsak -w parametresi, yazdırdığımız dosyaları okumak istiyorsak -r parametresi kullanırız.

![yedi](https://user-images.githubusercontent.com/55113204/117462267-2acc9c00-af57-11eb-9852-27a913219667.PNG)

![sekiz](https://user-images.githubusercontent.com/55113204/117462366-43d54d00-af57-11eb-9dd3-e095e753ac16.PNG)

Farklı bir arabirimi dinlemeye alacaksak bu arabirimleri görmek için -D paramtresini kullanabiliriz.

![dokuz](https://user-images.githubusercontent.com/55113204/117462819-b34b3c80-af57-11eb-9080-5c62eda9cf43.PNG)

Tsharkta tcpdump gibi port bazlı izleme yapmaktadır. HTTP protokolü çalışırken hangi uygulamaların kullanıldığını bakmak için ise;

![on](https://user-images.githubusercontent.com/55113204/117465148-0f16c500-af5a-11eb-8e6d-e1daf6d0c56c.PNG)

Broadcast yayını yapan paketleri de yakalayabilmekteyiz.

![onbir](https://user-images.githubusercontent.com/55113204/117467374-4c7c5200-af5c-11eb-8044-26ff8ac907a2.PNG)

IPv6 paketlerini de yakalayabiliriz.

![oniki](https://user-images.githubusercontent.com/55113204/117467781-ada42580-af5c-11eb-9129-9a4e27555ad6.PNG)

Bazı filtreleme parametreleri kullanarak sadece source adresini, destination adresini, port numarası gibi bilgileri elde edebiliriz.
Burada sadece bu alandaki paketlerin destination adreslerini getirmiş olduk.

![onüç](https://user-images.githubusercontent.com/55113204/117468446-5c486600-af5d-11eb-941f-19389bdf6a0c.PNG)

Burada giden frameleri source adresleri ile gösterdik.

![ondört](https://user-images.githubusercontent.com/55113204/117468740-a92c3c80-af5d-11eb-8bae-c07af72148d5.PNG)

Bir destination adresine giden paketin 80 portundan gidenleri gösterilmesi sağlayabiliriz.

![onbeş](https://user-images.githubusercontent.com/55113204/117511480-718db680-af96-11eb-8af9-3d80ffcbe052.PNG)

Port numarasına göre bir ağ analizi de yapabiliriz.

![onaltı](https://user-images.githubusercontent.com/55113204/117515605-69864480-af9f-11eb-9036-dfd2d7c4cd21.PNG)

DNS trafiğinin içindeki sadece belirli bir domaini çekmek için ise şöyle bir syntax yazılabilir. Bu listelenmiş bir trafikteki paket analizidir.

![hgo1](https://user-images.githubusercontent.com/55113204/117539128-e0f4bc00-b011-11eb-952f-cebea05218f5.PNG)

Bir cisco cihazına ait bilgileri almak istiyorsak eğer böyle bir syntax yazılabilir.

![hgo3](https://user-images.githubusercontent.com/55113204/117539536-cde2eb80-b013-11eb-9666-3f6acda1a468.PNG)

MAC adresine paket taraması yapmak için yazılabilecek bir syntax aşağıdadır.

![hgo4](https://user-images.githubusercontent.com/55113204/117540053-f966d580-b015-11eb-9811-cb8c01507b69.PNG)

# Wireshark
Linux, Windows ve MacOS işletim sistemlerinde desteklenen birçok kriter çevresinde paket filtreleme sağlayan ve çeşitli formatlarda kayıt edilmesine imkan sunan,
anlık paketleri yakalayıp görünütleyebilen ve çeşitli istatistikler oluşturabilen, ağ trafiğini canlı izlenebilme ve protokol hataları, ağ içeresindeki hataları tespit edip
çözmeye yardımcı olan son olarak da tersine mühendislik çalışmaları gibi bir çok farklı konuda tercih edilen bir araçtır.

## WinPcap
 Anlık olarak ağ trafiğini yakalayıp wireshark aracına gönderen kısımdır. 
 
## Wireshark Ayrıntılı İnceleme

 Standart olarak açılan pencere terminale de yazılarak açılabilmektedir. 

![wire1](https://user-images.githubusercontent.com/55113204/117575551-07d2f100-b0eb-11eb-8ddc-566e2ac5f692.PNG)


İlk açılan sayfayı inceleyelim.

![wire2](https://user-images.githubusercontent.com/55113204/117575563-128d8600-b0eb-11eb-8c78-b8f3ef9c2596.PNG)


Wireshark aracı en yetkili kişi yani root olarak çalışmaktadır. Bunun amacı wireshark aracı bizim ağ kartlarımıza erişmek istemesinden dolayıdır. 
İstenilen ağ kartlarına erişiminde kullanılan ağ kartları hakkında bilgi edinilmesini sağlayan bölüme Capture yazısına tıklayarak ulaşmaktayız.

![wire3](https://user-images.githubusercontent.com/55113204/117575584-2638ec80-b0eb-11eb-98f4-9cb0df3b5e20.PNG)


Şimdi paket yakalamak için eth0 ağ kartını seçip firefoxa girelim ve elde edilen sonuçlarımızı bir bakalım.

![wire4](https://user-images.githubusercontent.com/55113204/117575608-423c8e00-b0eb-11eb-97dc-f1e5fc03544f.PNG)

![wire5](https://user-images.githubusercontent.com/55113204/117575624-4ec0e680-b0eb-11eb-8801-ec7e103769de.PNG)


Kendi filtremizi elde etmek istiyorsak eğer bunun için de wireshark bize imkan sunmaktadır.

![wire6](https://user-images.githubusercontent.com/55113204/117575644-6009f300-b0eb-11eb-9914-f950e4fd78ec.PNG)


Örnek olarak ARP paketlerini listeledik.

![wire7](https://user-images.githubusercontent.com/55113204/117575650-69935b00-b0eb-11eb-98e4-a11240ed71e5.PNG)


Kendi filtreleme butonumuzu oluşturmak için ise şu şekilde adımlar izlenmektedir.

![wire8](https://user-images.githubusercontent.com/55113204/117575663-7617b380-b0eb-11eb-8a5c-44a28fc1c896.PNG)

![wire9](https://user-images.githubusercontent.com/55113204/117575673-816adf00-b0eb-11eb-83de-ad4e65ab674f.PNG)


Filtreleme butonunu silmek için ise izlenilen yol aşağıda gösterilmiştir.

![wire10](https://user-images.githubusercontent.com/55113204/117575679-8d56a100-b0eb-11eb-9dff-80bf3b5c3035.PNG)


Özel olarak bir kolon eklenmek istediğimiz de ise;

![wire11](https://user-images.githubusercontent.com/55113204/117575684-9b0c2680-b0eb-11eb-822e-cc73a676e469.PNG)


MAC adresleri için aktif çözümlemesini aktifleştirmek için;

![wire12](https://user-images.githubusercontent.com/55113204/117575691-a3646180-b0eb-11eb-9b8c-7d6686895a77.PNG)


Wireshark adres çözümlemeyi kendi içerinde bulunan manuf ismindeki dosyayı sürekli güncelleyerek ve kullanarak yapmaktadır.

![wire13](https://user-images.githubusercontent.com/55113204/117575696-acedc980-b0eb-11eb-9768-58b0820b6d59.PNG)


HTTP isteklerini analiz etmek istiyorsak eğer şu şekilde bir yol izlenebilir.

![wire14](https://user-images.githubusercontent.com/55113204/117575704-b7a85e80-b0eb-11eb-826d-c0b9277a0a03.PNG)

![wire15](https://user-images.githubusercontent.com/55113204/117575713-c0009980-b0eb-11eb-8dbe-2ee7bc017992.PNG)


Diğer bir analizleme yöntemi ise Packet Counter seçeneğidir.

![wire16](https://user-images.githubusercontent.com/55113204/117575723-ca229800-b0eb-11eb-94ca-b1ae61525717.PNG)

![wire17](https://user-images.githubusercontent.com/55113204/117575737-d0187900-b0eb-11eb-9185-20cbf9d8a1b7.PNG)


IP adreslerini analiz etmek istersek eğer aşağıdaki şekildeki gibi IPv4 yolunu takip ederek ALL Addresses seçeneğinden istediğimiz sonuçları elde edebiliriz.

![wire18](https://user-images.githubusercontent.com/55113204/117575743-da3a7780-b0eb-11eb-9111-4c515ea0d58e.PNG)

![wire19](https://user-images.githubusercontent.com/55113204/117575750-e0c8ef00-b0eb-11eb-813d-9aa4d64628c8.PNG)


Wiresharkta e hangi protokolden kaç tane paket olduğunu görmek istiyorsak Protocol Hierarchy seçeneği bize yardımcı olmaktadır.

![wire20](https://user-images.githubusercontent.com/55113204/117575759-e9b9c080-b0eb-11eb-99ed-4637cbe7dbf4.PNG)

![wire21](https://user-images.githubusercontent.com/55113204/117575769-f1796500-b0eb-11eb-8094-f4100349e6f6.PNG)


Yakalanan paketlerin özet bilgilerine ulaşmak istiyorsak Capture File Properties alanı seçilmelidir.

![wire22](https://user-images.githubusercontent.com/55113204/117575789-0229db00-b0ec-11eb-8db3-abe331843777.PNG)

![wire23](https://user-images.githubusercontent.com/55113204/117575794-08b85280-b0ec-11eb-9d44-c31c7f07e91e.PNG)


Tüm paketlerin adres çözümlemesini yapmak istiyorsak elde aşağıdaki yolu izlemeliyiz.

![wire24](https://user-images.githubusercontent.com/55113204/117575803-1077f700-b0ec-11eb-92be-878476ab4998.PNG)

![wire25](https://user-images.githubusercontent.com/55113204/117575814-18379b80-b0ec-11eb-9cf6-17c5eecb489d.PNG)


Ağınıza ait ARP saldırılarını gözlemlemek için şu filtreler kullanılabilmektedir.

![wire27](https://user-images.githubusercontent.com/55113204/117575831-2980a800-b0ec-11eb-97e7-51d4fcfd508a.PNG)

![wire26](https://user-images.githubusercontent.com/55113204/117575832-2a193e80-b0ec-11eb-8d55-6416c31bd6fd.PNG)


Wireshark ile ağın trafiği içindeki bazı paketleri export etmek istersek eğer aşağıdaki yolu kullanabiliriz. 

![wire28](https://user-images.githubusercontent.com/55113204/117575847-356c6a00-b0ec-11eb-94f3-6910a633bf2c.PNG)

![wire29](https://user-images.githubusercontent.com/55113204/117575862-3ef5d200-b0ec-11eb-84c6-72d84df22935.PNG)

Bir diğer export etme yöntemi ise sadece seçilen paketin export edilmesidir.

![wire30](https://user-images.githubusercontent.com/55113204/117575889-53d26580-b0ec-11eb-9320-3dc7e1f482c8.PNG)

![wire31](https://user-images.githubusercontent.com/55113204/117575898-5c2aa080-b0ec-11eb-831f-74774ce8cdcd.PNG)

Başka bir export etme yöntemi ise belirli bir aralıktaki paketlerin export edilmesidir.

![wire32](https://user-images.githubusercontent.com/55113204/117575920-7e242300-b0ec-11eb-842c-1e010982d55a.PNG)

Yada belirli bir paketlerin export edilmesi de yapılabilir.

![wire33](https://user-images.githubusercontent.com/55113204/117575962-9eec7880-b0ec-11eb-810c-9cb0bea358b5.PNG)

Sadece paketin üstüne tıklayarakta export edilip paket seçilme işlemi yapılabilir.

![wire34](https://user-images.githubusercontent.com/55113204/117575994-c8a59f80-b0ec-11eb-91b8-7969a1da48c0.PNG)

Burada da sadece benim işaretlediklerim seçilmektedir.

![wire35](https://user-images.githubusercontent.com/55113204/117576000-ce02ea00-b0ec-11eb-8af0-d6d2ff94f60a.PNG)


İki .pcap paketi birleştirmek için mergecap isimli araç kullanılarak farklı bir dosyaya atılabilir.

![wire36](https://user-images.githubusercontent.com/55113204/117576073-191cfd00-b0ed-11eb-9e3a-24fc47092519.PNG)


.pcap paketlerini okumak için ise capinfos aracı kullanılır.

![wire37](https://user-images.githubusercontent.com/55113204/117576083-20dca180-b0ed-11eb-80f4-a749594e210b.PNG)

## DHCP İçin Kullanılabilecek Filtreler
![wire40](https://user-images.githubusercontent.com/55113204/117576273-fe975380-b0ed-11eb-9424-d8d1f0f11b2b.PNG)

![wire41](https://user-images.githubusercontent.com/55113204/117576275-fe975380-b0ed-11eb-9f5c-07adb3ed1ca5.PNG)

![wire42](https://user-images.githubusercontent.com/55113204/117576276-ff2fea00-b0ed-11eb-83f5-7b2b7d6872f3.PNG)

![wire43](https://user-images.githubusercontent.com/55113204/117576278-ff2fea00-b0ed-11eb-8f45-b23f750bfbcb.PNG)

![wire44](https://user-images.githubusercontent.com/55113204/117576279-ffc88080-b0ed-11eb-8511-f7b23c76d147.PNG)

![wire38](https://user-images.githubusercontent.com/55113204/117576280-ffc88080-b0ed-11eb-8b0a-5a66cc6d1a84.PNG)

![wire39](https://user-images.githubusercontent.com/55113204/117576281-ffc88080-b0ed-11eb-99f7-894f049808ca.PNG)

## HTTP İçin Kullanılabilecek Filtreler
Bu parametreleri kullanarak http bağlantıların verileri de ayıklamış oluruz.
![wire48](https://user-images.githubusercontent.com/55113204/117576404-8aa97b00-b0ee-11eb-9700-161acadc849f.PNG)

![wire49](https://user-images.githubusercontent.com/55113204/117576406-8aa97b00-b0ee-11eb-9fc4-8c13b700fc71.PNG)

![wire50](https://user-images.githubusercontent.com/55113204/117576407-8b421180-b0ee-11eb-8add-ae0ad0b0c14e.PNG)

![wire45](https://user-images.githubusercontent.com/55113204/117576408-8b421180-b0ee-11eb-8d6c-a8db4abe9440.PNG)

![wire46](https://user-images.githubusercontent.com/55113204/117576409-8bdaa800-b0ee-11eb-9517-205aeb2e2d29.PNG)

![wire47](https://user-images.githubusercontent.com/55113204/117576410-8bdaa800-b0ee-11eb-8e8f-1a5e375a0ebc.PNG)

## ARP İçin Kullanılabilecek Filtreler
![wire55](https://user-images.githubusercontent.com/55113204/117576580-2c30cc80-b0ef-11eb-9233-6435b1db9a1e.PNG)

![wire56](https://user-images.githubusercontent.com/55113204/117576581-2cc96300-b0ef-11eb-94b0-c7a91ba55ef6.PNG)

![wire51](https://user-images.githubusercontent.com/55113204/117576583-2d61f980-b0ef-11eb-8ed5-aa571d036445.PNG)

![wire52](https://user-images.githubusercontent.com/55113204/117576585-2d61f980-b0ef-11eb-883e-21f7ce6bcce0.PNG)

![wire53](https://user-images.githubusercontent.com/55113204/117576586-2d61f980-b0ef-11eb-9339-a696d0760850.PNG)

![wire54](https://user-images.githubusercontent.com/55113204/117576587-2dfa9000-b0ef-11eb-87c5-fb24b7720c0d.PNG)

## DNS İçin Kullanılabilecek Filtreler
![wire58](https://user-images.githubusercontent.com/55113204/117576742-ba0cb780-b0ef-11eb-9614-c5f701153221.PNG)

![wire59](https://user-images.githubusercontent.com/55113204/117576745-baa54e00-b0ef-11eb-954a-08889dd81b64.PNG)

![wire60](https://user-images.githubusercontent.com/55113204/117576746-baa54e00-b0ef-11eb-89b0-3ce2265a6f72.PNG)

![wire57](https://user-images.githubusercontent.com/55113204/117576747-baa54e00-b0ef-11eb-828b-17ea7cb7095f.PNG)

## İnternet Protokol İçin Kullanılabilecek Filtreler
![wire63](https://user-images.githubusercontent.com/55113204/117576884-28517a00-b0f0-11eb-9bef-ce64e518639a.PNG)

![wire64](https://user-images.githubusercontent.com/55113204/117576886-28517a00-b0f0-11eb-9607-9859d28d9b8b.PNG)

![wire65](https://user-images.githubusercontent.com/55113204/117576887-28ea1080-b0f0-11eb-9702-645a8aef9b27.PNG)

![wire61](https://user-images.githubusercontent.com/55113204/117576888-28ea1080-b0f0-11eb-9807-70759c8097fb.PNG)

![wire62](https://user-images.githubusercontent.com/55113204/117576889-2982a700-b0f0-11eb-9b01-0c768bb07016.PNG)

## TCP İçin Kullanılabilecek Filtreler
![wire68](https://user-images.githubusercontent.com/55113204/117576967-7e262200-b0f0-11eb-82ad-34b91d54d82b.PNG)

![wire69](https://user-images.githubusercontent.com/55113204/117576968-7ebeb880-b0f0-11eb-99c0-073f30ed4a94.PNG)

![wire66](https://user-images.githubusercontent.com/55113204/117576969-7f574f00-b0f0-11eb-9ea5-21d19793f548.PNG)

![wire67](https://user-images.githubusercontent.com/55113204/117576970-7f574f00-b0f0-11eb-8e2e-3a1bdfc70d9f.PNG)

## FTP İçin Kullanılabilecek Filtreler
![wire72](https://user-images.githubusercontent.com/55113204/117577071-e8d75d80-b0f0-11eb-86b0-be142d9b5eb0.PNG)

![wire73](https://user-images.githubusercontent.com/55113204/117577072-e96ff400-b0f0-11eb-9fe3-4f5ead8fbba9.PNG)

![wire74](https://user-images.githubusercontent.com/55113204/117577073-e96ff400-b0f0-11eb-837b-fe2b28ed2c29.PNG)

![wire70](https://user-images.githubusercontent.com/55113204/117577074-e96ff400-b0f0-11eb-8e77-ee47a861c0d9.PNG)

![wire71](https://user-images.githubusercontent.com/55113204/117577075-ea088a80-b0f0-11eb-9cfd-333d21a9d26e.PNG)

## ICMP İçin Kullanılabilecek Filtreler
![wire76](https://user-images.githubusercontent.com/55113204/117577118-276d1800-b0f1-11eb-8105-baa5bd43a025.PNG)

![wire75](https://user-images.githubusercontent.com/55113204/117577119-2805ae80-b0f1-11eb-88ea-d8b95c343bb6.PNG)

## Wireshark Kullanarak Firewall Kuralı Nasıl Yazılır?

İlk önce bir paket seçilir daha sonra tool kısmından Firewall ACL Rules alanı seçilir. 

![dev1](https://user-images.githubusercontent.com/55113204/117588843-ca905280-b12e-11eb-8e55-8232c14e9eb0.PNG)

Çıkan sayfadan istenilen şekilde bir kural oluşturulabilir.

![dev2](https://user-images.githubusercontent.com/55113204/117588919-412d5000-b12f-11eb-9e96-a3ec36767a15.PNG)

## Wireshark ile HTTP/HTTPS Analizi

İlk önce HTTP analizini yapalım. Tcpdump ile ağ paketlerimizi bir dosyaya atabiliriz. Daha sonra güvenli olmayan bir siteye girip Wiresharkı başlatalım. Ve siteye giriş yapıp parolamızı ve kullanıcı adının nasıl ağı dinleyen biri tarafından izlenildiğine şahit olmak için aşağıyadaki örneğe bakabiliriz.

Tcpdump ile ağı koklayıp kayıt ediyoruz. 

![http5](https://user-images.githubusercontent.com/55113204/117656630-432ff700-b1a1-11eb-9e56-249631aa8e23.PNG)

HTTP bağlantılı bir siteye giriyoruz.

![http3](https://user-images.githubusercontent.com/55113204/117656740-5fcc2f00-b1a1-11eb-9d85-582485558829.PNG)

Wiresharkı açıp ağ trafiğini izliyoruz. 

![http](https://user-images.githubusercontent.com/55113204/117656855-85f1cf00-b1a1-11eb-97ec-632eaf2cd9d3.PNG)

Ve herhangi bir paketin içeriğine bakalım. Gördüğünüz gibi admin ve parola gösterilmektedir.

![http4](https://user-images.githubusercontent.com/55113204/117656954-a752bb00-b1a1-11eb-9401-2d63920f6aa6.PNG)

Hex kısmında da görülmektedir.

![http2](https://user-images.githubusercontent.com/55113204/117656981-b33e7d00-b1a1-11eb-92b2-c91348071f09.PNG)

Ama HTTPS de gösterilmemektedir. Bunun sebebi ise SSL Dijital Sertifika gerektirdiğinden dolayı güvenli olmasıdır.

![https](https://user-images.githubusercontent.com/55113204/117657201-f4cf2800-b1a1-11eb-8601-e821de840a02.PNG)

## HTTPs Trafiği Çözümleme İşlemi Nedir?
Pentest testleri esnasında elde edilen PCAP dosyaları analiz edilmek kritik bilgilere ulaşılabilir. Bunu ngrep aracı ile inceleyebiliriz.

UDP trafiğine ulaşmak istersek eğer şu şekilde bir araba gerçekleştirebiliriz.

![^ngrep](https://user-images.githubusercontent.com/55113204/117664473-7aef6c80-b1aa-11eb-9da4-3a20e0f702fc.PNG)

TCP trafiğine ulaşmak istersek ise aşağıdaki gibi bir arama gerçekleştirebiliriz.

![ngre](https://user-images.githubusercontent.com/55113204/117664742-cd308d80-b1aa-11eb-9e22-7435fe1af66a.PNG)

Şimdi de Wireshark kullanarak şifrelenen .pcap dosyasının trafiğine de bakabiliriz. 

## Trafik Analizlerinde  Özet Bilgi Nasıl Alnınır?

Çeşitli ağ trafiği dinleme araçları kullanarak bir ağ trafiğinin özet bilgilerini alabiliriz ama ben burada tshark kullanarak giden gelen framelerin özet bilgilerini almış bulunmaktayım. Burada sadece ttl değerleri, source address, destination address, ve frame durumları (SYN-ACK) bilgileri elde edilir.

![bir](https://user-images.githubusercontent.com/55113204/118411454-5b21e200-b69d-11eb-8ab8-6130bd6010b3.PNG)


## Wireshark ile Tshark Arasındaki Farklar Nelerdir ?
Wiresharkın terminal üzerinde çalışan haline tshark diyebiliriz.
Wiresharkta program üzerinde ağ analizlenebilirken tshark ile parametreler kullanılarak ağ analizlemesi yapılmaktadır.
Tshark Wiresharka göre performansı daha iyidir.
Tshark komut satırı esnekliği de sağlamaktadır.

## Tcpdump ile Tshark Arasındaki Farklar Nelerdir ?
Tshark Tcpdumptan çok daha fazla paket ayırıştırıcıya sahiptir.
Tcpdump sınırlı protokole sahiptir. Bundan dolayı sınırlı kod çözer ve çoğu NIX plartformunda mevcuttur.
Tshark Wiresharkın komut satırındaki versiyonudur.
Tcpdump’dan farklı olarak statefull çalışan tshark canlı trafik hakkında yada daha önceden yakalanmış trafik hakkında istatistiki bilgileri elde etmemize yarayan parametreleri de vardır.

## WEP/WPA Şifreli Trafik Çözümleme İşlemleri Nasıl Yapılır ?
WEP (Wired Equivalent Privacy), dünyada en çok kullanılan Wi-fi güvenlik algoritması olan ve ağın güvenliğini sağlamak için ortaya çıkan şifreleme yönteminlerinden biridir. Bunun nedeni ise birçok routerın rol alması ve geriye uyumluluğudur.


Bunun için şu şekilde adımları izleriz. Edit -> Preferences -> Protocol -> IEEE 802.11 -> Edit ve burada anahtarlarımızı girerek şifreyi çözümleriz.

![wire1](https://user-images.githubusercontent.com/55113204/117675139-fce49300-b1b4-11eb-9013-a5e307bf4fa1.PNG)

![wire2](https://user-images.githubusercontent.com/55113204/117675176-02da7400-b1b5-11eb-838e-0ca63f45ce23.PNG)

## Network Forensics Çalışmalarında Tshark Kullanımı
İlk önce ağ trafiğindeki paketlerimizi yakalayıp bir dosyanın içine atıyoruz.

![yakalan1](https://user-images.githubusercontent.com/55113204/117681487-d295d400-b1ba-11eb-862c-863f53e9c300.PNG)

Daha sonra yakalananları wiresharktaki filtreleme işleminde ki bir http POST dönenleri getiriyoruz.

![yakalan](https://user-images.githubusercontent.com/55113204/117681588-efcaa280-b1ba-11eb-9169-471c9320eec7.PNG)

Başka bir örnek verecek olursak yakalanan paketlerin tüm hostlarını getirebiliriz.

![yakalan2](https://user-images.githubusercontent.com/55113204/117681923-40da9680-b1bb-11eb-8ab4-3cb05078736f.PNG)

Yada belirli bir dns server kullanmış verileri getirmektedir.

![yakalan3](https://user-images.githubusercontent.com/55113204/117682446-ba728480-b1bb-11eb-97e1-8c97c83f676a.PNG)

Başka bir adım ise hostları ziyaret sayısına göre ve ilk 10 tanesini ve farklı olanları getirelim.

![yakalan4](https://user-images.githubusercontent.com/55113204/117684257-7ed8ba00-b1bd-11eb-95e1-ae08e0666fa6.PNG)

User Agentlerı aşağıdaki komutla getirebiliriz.

![yakalan5](https://user-images.githubusercontent.com/55113204/117684989-3241ae80-b1be-11eb-963d-a23583b5bf4b.PNG)

HTTP GET isteği atmak istersek eğer aşağıdaki gibi bir syntax yazabiliriz.

![yakalan7](https://user-images.githubusercontent.com/55113204/117685776-e80cfd00-b1be-11eb-8d1b-8864c464638e.PNG)

![yakalan6](https://user-images.githubusercontent.com/55113204/117685788-ec391a80-b1be-11eb-8f5f-13805ca3195b.PNG)

Ve başka bir adım olarak ise web sayfalarına ne çeşit istekler yapıldığını, kaç kere yapıldığını uri ları ile birlikte çıktı alabiliriz.

![yakalan8](https://user-images.githubusercontent.com/55113204/117686516-9f097880-b1bf-11eb-8f72-a1f8ab7bbde1.PNG)

Server taraflı gönderilen HTTP ve HTTPS paketlerin analizlenmesini de yapabiliriz.

![yakalan9](https://user-images.githubusercontent.com/55113204/117687229-41c1f700-b1c0-11eb-8758-b1f86bb9d23a.PNG)


## Network Forensics 
Bilgisayar ağlarında Adli Bilişim yani Network Forensics ağ trafiğinin temel yapıda analizlenmesini sağlamaktadır. Herhangi bir olay yada vaka sonrasında analiz için firewall, 
ids/ips, honeypot gibi cihazların ağ trafik kayıt sistemlerinin kayıtlarına ihtiyaç duyulmaktadır. Bu kayıtların analizi için de kullanılan en önemli araçlardan biri ise Wiresharktır.

## Network Forensics Bileşenleri Nelerdir ?
Verileri yakalama, kaydetme, keşfetme ve analiz etme ile birlikte 4 Bileşenden oluşur.
~ Capturing ve Recording Data: Herhangi bir tane veriyi düşürmeden birden çok terebayt uzunluğundaki verileri yakalar ve depolar bu yüzden çok verimlidir. Her Network Forensics'in sürdürülebilir iş hacmi, saniye başına paket sayısı, veri yönetimi ve arama fonksiyonları gibi sınırlamaları vardır. Bu sınırlamalar pratik lab sonuçlarına göre belirlenip raporlanmalıdır. 
~ Discovering Data : Kaydedilen verilere çözüm işlemlerinin uygulanmasıdır. Bu IP adresine, içeriğine, uygulamasına filtreleme gibi özelliklerle yapılabilir.
~ Analyzing Data : Keşif işleminde yakalanan paketlerin anormal durumlarını incelemek için hangi durumların kaydedildiğini belirlemenizde yardımcı olur.

## Ağ Trafiğinden Veri Ayıklama Nasıl Olur Ne işimize yarar ?
Ağ trafiğini izleyebilen uygulamalar sayesinde gelen giden paketlerin takibi yapılarak ağda istenilen paketlerin çıkarılıp incelenmesi için çeşitli parametler yada toollar kullanarak veriler ayıklanabilir. Bu ayıklamanın yapılma amacı paketlerin bütünlüğünde herhangi bir aksaklık olup olmadığını anlamak, verilerin güvenli bir şekilde taşınıp taşınmadığını anlamak ve verilerin hedefe ulaşıp ulaşmadığını anlamak gibi çeşitli nedenlerle yapılarak ağ hakkında detaylı bilgi sahibi olup korumamızı sağlamaktadır.

## Tünelleme Kullanan kullanıcılar Ngrep ile Nasıl Belirlenir ?
Ngrep'i diğer ağ dinleme araçlardan ayıran en temel özellik yakalanan verilerde genişletilmiş düzenli ifadeleri arayabilmemizdir. Bu tekniği öğrenmek, yalnızca portları değil verileri de filtreleyerek, istediğiniz verileri görmenizi inanılmaz derecede kolaylaştırır.
Ngrep ile ssh bağlantısı kurmadan tünnelleme ile ssh bağlantısı kurmuş bir cihazı aşağıdaki komut ile buluruz. Burada SSH portu 22'yi kullanmadan SSH bağlantısı kurmaya çalışan bir cihaz arıyoruz.

![yakalan9 PNG10](https://user-images.githubusercontent.com/55113204/117711580-1947f600-b1dc-11eb-9242-3d2eeed2916e.PNG)

## ChaosReader Nedir?

TCP / UDP oturumlarını izlemek ve uygulama verilerini snoop veya tcpdump günlüklerinden almak için ücretsiz bir araç olan ve telnet oturumlarını, FTP dosyalarını, HTTP aktarımlarını (HTML, GIF, JPEG), SMTP e-postalarını vb. ağ trafik günlüklerini içinde yakalanan verilerden alacağı için bir tür snarf programıdır. Günlük dosyalarını oluşturmak için tcpdump veya snoop'u (varsa) çağırır ve ardından bunları işler. Telnet, rlogin, IRC, X11 ve VNC oturumları için gerçek zamanlı yeniden oynatma programları dahil olmak üzere tüm oturum ayrıntılarına bağlanan bir html dizin dosyası oluşturulur; ve resim raporları ve HTTP GET / POST içerik raporları gibi raporlar. Chaosreader bağımsız modda da çalışabilir.

Aşağıda bir HTTPs dosyasını okuma sonucunu vermektedir.

![yakala1](https://user-images.githubusercontent.com/55113204/117716671-8a8aa780-b1e2-11eb-872a-8cad139502b8.PNG)

![yakalan10](https://user-images.githubusercontent.com/55113204/117716719-9bd3b400-b1e2-11eb-83bb-6110a0719537.PNG)

![yakala2](https://user-images.githubusercontent.com/55113204/117716748-a55d1c00-b1e2-11eb-9953-863c18ff3bd8.PNG)

## Tcpxtract Nedir?

Dosya türü üstbilgilerine ve altbilgilerine dayalı olarak dosya ayıklamak, eski bir veri kurtarma tekniğidir. En başta gibi araçlardosyaları rastgele veri akışlarından kurtarmak için bu tekniği kullanır. Tcpxtract, bu tekniği özellikle bir ağ üzerinden iletilen dosyaları yakalama uygulaması için kullanır. Yani dosya imzalarına dayalı olarak ağ trafiğinden dosya ayıklamak için kullanılan bir araçtır. Libcap kütüphanesini kullanır. Canlı bir ağa veya tcpdump formatlı bir yakalama dosyasına karşı kullanılabilir.

Öncelikle wireshark ile paketleri yakalayıp kayıt ediyoruz.

![yakala1](https://user-images.githubusercontent.com/55113204/117730917-db57cb80-b1f5-11eb-99db-e713a06f04e9.PNG)

Daha sonra yakaladığımız bu paketleri tcpxtract ile görüntülenebilir dosya haline getirip tekrar bir dosyaya atıyoruz.

![yakala](https://user-images.githubusercontent.com/55113204/117731213-689b2000-b1f6-11eb-971c-e7b457b332e3.PNG)

## Tcpflow Nedir?

TCP paketlerini yakalayan verileri protokol analizi ve hata ayıklama için uygun bir şekilde depolayan bir programdır. Tcpdump paketlerini de işleyebilen bu araç Her TCP akışı kendi dosyasında saklamasını sağlar.

Tüm ağı dinlemek için sadece tcpflowu çalıştırabiliriz.

![yakala2](https://user-images.githubusercontent.com/55113204/117732791-26271280-b1f9-11eb-9c5b-5596557c915c.PNG)

Bir ağı dinleyip bunu paketleri kayıt edip paketleri okuyabiliriz.

![yakala3](https://user-images.githubusercontent.com/55113204/117736831-3a6f0d80-b201-11eb-9a0d-4e7dc536e235.PNG)

![yakala5](https://user-images.githubusercontent.com/55113204/117736839-41961b80-b201-11eb-995d-efedf544fc12.PNG)

![yakala4](https://user-images.githubusercontent.com/55113204/117736845-48249300-b201-11eb-889e-aa45722839f4.PNG)

## NetworkMiner Nedir?

Network Forensic aracı, HTTP ve HTTP2 trafiğinden e-postaları, şifre karmalarını, FTP aktarımlarını ve yapıları ayıklamak için kullanan bir tooldur. Wireshark gibi bir ağ dinleme aracıyla elde ettiğimiz ağın giden gelen paket trafiğini Networkminera import ediyoruz. Daha sonra arayüzü sayesinde istediğimiz verileri kolayca görebiliyoruz.

İlk olarak hostlarına ayrılmış paketlerin detaylı bilgilerine ulaşabiliriz ona bir bakalım. Burada host bilgilerinin getirmiş olduğu bilgiler doğrultusunda pektlerin hangi hosttan IP ve MAC adresleri bilgilerinden paketin TTL süresi gibi bilgilerine erişilmektedir.

![yeni1](https://user-images.githubusercontent.com/55113204/117843008-20780e00-b287-11eb-8084-db688e22d335.PNG)

Files kısmında dosyalara ulaşabilmekteyiz. Dosyaların source adresten hedef kaynağına kadar giderken kullanılan ptorokoller de dahil olmak üzere bilgi almaktayız.

![yeni2](https://user-images.githubusercontent.com/55113204/117843570-9a0ffc00-b287-11eb-90e3-c0931b969869.PNG)

Cihazlar arasındaki anlaşmayı sağlayan sessionda bu cihazların bilgilerini vermektedir.

![yeni3](https://user-images.githubusercontent.com/55113204/117843716-bdd34200-b287-11eb-8006-55e43ca267f9.PNG)

Kullanılan DNSlerde gösterilmektedir.

![yeni4](https://user-images.githubusercontent.com/55113204/117843834-d7748980-b287-11eb-9cb0-3b7bea3287d5.PNG)

Parametreler ve değerleri, Source Adresler, Destination Adresler ve bunların portları da dahil olmak üzere analizlememizi sağlayan onlarca bilgi edinmemizi sağlamaktadır.

![yeni5](https://user-images.githubusercontent.com/55113204/117844129-1b678e80-b288-11eb-828d-8f86512c1c68.PNG)

Ayrıntılı bir Client Server bilgisine ulaşılmak istendiğinde de Credentials (kimlik bilgileri) kısmına bakabiliriz.

![yeni6](https://user-images.githubusercontent.com/55113204/117844688-90d35f00-b288-11eb-87b9-3c94051d22be.PNG)

Varsa Imageleri görüntüleyebiliriz.

![yeni7](https://user-images.githubusercontent.com/55113204/117844838-af395a80-b288-11eb-9fc6-64fecfeb5fb9.PNG)

## SSL Kullanılan Ortamlarda Network forensics İşlemleri Nasıl olur ?
Bunun için birinci yol ngrep komutu ile olur. Bunun nasıl yapıldığını yukarıda açıkladım. İkinci yol ise Wireshark kullanarak bir TLS protokolünüze key import edip onun ssl şifrelerinizi çözmenizi sağlayarak yapıyorsunuz.

![yeni8](https://user-images.githubusercontent.com/55113204/117879335-85475e80-b2af-11eb-8ab7-9f9b84347191.PNG)

## Network Forensics Çalışmalarını Atlatma İşlemleri Nasıl Yapılır ?

* Dışa doğru herhangi bir TCP portu açıksa;

•OpenVPN kullanarak doğrudan VPN kurulabilir.

•Açık port üzerinden SSH tünelleme yapılarak tüm trafik kolayca tünellenebilir

•Dışarıdaki bir kullanıcı iç ağa sokulabilir.

* UDP üzerinden de tünelleme yöntemi yapılabilir.

•Genellikle UDP 53(dns), UDP 500(IKE) portu dışa doğru açık unutulur.

•Herhangi bir UDP portu açıksa OpenVPN kullanarak tüm trafik sınırsız bir şekilde tünel içerisinden dışarı çıkarılabilir.

•Kullanmak için admin hakları gerektirir.

•Dışarıda bir adet openvpn sunucu ihtiyacı vardır–Ücretsiz openvpn hizmeti sunan yerle

* ICMP Üzerinden Tünelleme Yöntemleri

•ICMP genellikle sorun giderme amaçlı kullanılır. Ping, traceroute vs.

•Özellikle otel vs gibi ücretli internet hizmeti sunan yerlerde dışa doğru ICMP echo request paketlerine yetkisiz izin verilir

•ICMP tünelleme kullanılarak tüm trafik bu protokol üzerinden tünellebilir

•Dışarıda bir sunucu gerektirir

* Proxy ile HTTPS’i Kontrol Etmek

•Kullanıcı browser’ina ayar girilerek tüm HTTP/HTTPS trafiği proxy üzerinden çıkarılabilir

•OpenVPN 443/TCP portunda

•SSH Socks proxy kullanımı

* Ultrasurf kullanımı tünnelleme yazılımlarının en ünlüsü

* DNS Tünelleme

•Amaç sadece yerel ağ dns sunucusuna erişimi olan iç ağ kullanıcısının bu DNS sunucuyu aracı olarak kullanarak internete paket gönderip alabilmesi.

* SSH Tünelleme

•En basit kullanıma sahip tünelleme yöntemlerindendir. Putty 443 portdan çalışan bir SSH sunucusu tüm erişim düzenleyicileri aşabilir.

* WebTunnel

•Aradaki engelleme cihazlarına normal HTTP istekleri gibi gözükeceği için yakalanma riski düşüktür

## Bilgisayar Ağlarında Şifreleme İşlemleri ve Avantajları ve Dezavantajları 

• * WEB (Wired Equivalent Privacy)
Her türlü harici saldırıdan kablosuz haberleşmeyi korumak için kullanılan algoritmaya WEB algoritması denir. WEP’in ikinci fonksiyonu ise kablosuz ağa yetkisiz erişimleri engellemektir. WEB'te güvenliği sağlamak için kimlik doğrulama, gizlilik, bilgi değiştirme kontrolü olmak üzere 3 adımdan oluşmaktadır.

• * WPA (WI-FI PROTECTED ACCESS)
WPA ise WEP’ten sonra ortaya atılan ve WEP’in dezavantajlarının bertaraf edilmeye çalışıldığı bir diğer şifreleme yöntemidir. WPA ile kimlik denetimi zorunlu olmuştur ve iki aşamadan oluşmuştur. Birincisi açık sistem kimlik denetiminin kullanılması ve kablosuz istemcinin veri paketi göndermek için kablosuz erişim noktasına sinyal göndermesidir. İkincisi ise 802.1X standardının kullanıcı seviye kimlik denetimini gerçekleştirmesidir.

• * Şifreleme yöntemleri içerisinde en zayıf ve güvenilirliği en düşük olan yöntem WEP şifrelemesidir. Günümüzde WEP şifrelemeleri her türlü saldırıya açık durumdadır. Bunun sebebi olarak WEP’te IV değerinin çok düşük olması, veri bütünlüğünün zayıf olması, rekeying korumasının olmaması, tekrar koruma işleminin yapılmaması sayılabilir. Bu dezavantajlar WEP’te yapılan bazı düzenlemeler ve sürümler ile giderilmeye çalışılmışsa da tam anlamıyla güvenlik sağlanamamıştır. WEP’ten daha sonra ortaya çıkarılan WPA ve WPA2  şifreleme yöntemleri ile güvenlik daha da artırılmış ve gönderilen verilerin bütünlüğü korunmuştur. Bu amaçla WEP’te 24 bit olan IV değeri 48 bite çıkarılmış, Mikael ve CBC-MAC gibi algoritmalar ile ekstra şifreleme işlemleri yapılmış, ayrıca güvenlik seviyesinin artırılması için değişik özelliklerde ve çok sayıda şifreleme anahtarı kullanılmıştır. Tüm bu incelemelerin ışığında kablosuz ağ için en güvenilir şifreleme metodu olarak WPA 2 görülmektedir. Ancak WPA2 için çok önemli bir dezavantaj söz konusudur ki bu da şu an için WPA 2 uyumlu donanım cihazlarının yeteri kadar bulunmaması ve mevcut olan cihazların maliyetinin yüksek olmasıdır. Bununla birlikte WPA 2 uyumlu cihazların WEP ve WPA ile de uyumlu olduğu söylenebilir. 

## SSL Wrapper Nedir?

Güvenli olan SSL tüneli içindeki güvenli olmayan bir ağ iletişimi şifreleyen ve kimlik doğrulama mekanizması sağlayan bir araçtır. Bir tarafta yada her iki taraftada şifreleme yapmaktadır.Seçeneklerden ilki olarak Client, SSL Wrapper ile giden istemci trafiğini şifreler. İkinci seçenek ise Server, SSL Wrapper ile gelen server trafiğinin şifresini çözer ve SSL sonlandırma proxy'si uygular. Yada her iki tarafta, iki eşleştirilmiş SSL Wrapper ile düz TCP trafiğini güvenli SSL tüneline kapatır.

İki modda dinleme yapabilir. Birinci mod Dinlenen port SSL, host normal düz TCP'dir.
İkinci mod ise Dinlenen port düz TCP, host ise SSL'dir.

./ssl_wrapper dinlenecek_adres hedef_adres şeklinde çalışır.

![sslwrappet](https://user-images.githubusercontent.com/55113204/118412007-4e52bd80-b6a0-11eb-9f0b-57b5af6a0451.PNG)


## Şifreleme protokolleri Nelerdir? 
### • 3-D Secure
 İnternet'ten yapılan kredi ve banka kartı işlemleri için ek bir güvenlik katmanı olarak tasarlanmış XML tabanlı bir protokoldur. Bu protokolün temel konsepti çevrimiçi onaylama ile finansal onaylamanın birleştirilmesidir. Bu ilave güvenlik onayı 3 boyutlu model üzerine kurulmuştur. 
### • HTTPS 
HTTPS için temel motivasyon, erişilen web sitesinin kimlik doğrulaması ve aktarılan verilerin alışverişi sırasında gizliliğin ve bütünlüğünün korunmasıdır.
### • DKIM (Alan adı Anahtarlarıyla Tanımlanmış E-Posta)
E-posta alıcısının, belirli bir alandan geldiği iddia edilen bir e-postanın gerçekten bu alanın sahibi tarafından yetkilendirildiğini kontrol etmesini sağlar. Bu yöntemle e-postalarda sahte gönderici adresleriyle yemleme ve yığın e-posta gibi saldırıları önlemek amaçlanmıştır.
### • SAE (Eşzamanlı Eşit Kimlik Doğrulama)
Anahtar kilit eşleri birbirlerini keşfettiğinde ve güvenlik devrede ise SAE değişiminde yer alırlar. SAE başarılı bir şekilde tamamlanırsa, her bir taraf diğer tarafın mesh parolasına sahip olduğunu bilir ve SAE değişiminin bir yan ürünü olarak, iki eş kriptografik olarak güçlü bir anahtar oluşturur. 
### • Zero-knowledge proof (Sıfır bilgi ispatı)
Bilginizi ispat etme yönteminiz genel olarak ideal bir kriptografik fonksiyonunun varsayımlarıdır.
### • Signal Protokolü (TextSecure Protokolü) 
Sesli aramalar, video görüşmeleri [1] ve anlık mesajlaşma konuşmaları için uçtan-uca şifreleme sağlamak için kullanılabilen federe olmayan kriptografik protokoldür
### • SPEKE 
Parola doğrulamalı anahtar anlaşması için kullanılan kriptografik bir yöntemdir. Ek olarak saldırgan aynı zamanda parolayı bilen bir taraf ile her bir etkileşiminde parola için yalnızca ve en fazla bir tahminde bulunabilir.
### • WPA
Kablosuz bilgisayar ağlarını güvenceye almak için geliştirilen, güvenlik protokol ve sertifika programlarıdır.
### • X.509
Bir X.509 sertifikası bir açık anahtar ve bir kimlik içerir ve bir sertifika yetkilisi tarafından imzalanır veya kendinden imzalı olarak imzalanır. Sertifika güvenilir bir sertifika yetkilisi tarafından imzalandığında veya başka yollarla doğrulandığında, bu sertifikayı tutan biri, başka bir tarafla güvenli iletişim kurmak için sertifikanın içerdiği açık anahtara güvenebilir veya ilgili özel anahtar ile dijital olarak imzalanmış belgeleri doğrulayabilir.
### • ZRTP
Bu protokolde, Voice over Internet Protocol (VoIP) protokolüne dayanan iki uç nokta arasında şifreleme yapabilmek için anahtarlar üzerinde anlaşma yapılmaktadır.


## SSL Nedir?
Bir SSL sertifikası kişilerin web sitelerine girdiklerinde onların bilgilerini korur. bu verilere müdahale etmeye çalışan herhangi birinin yalnızca şifresini çözmesi neredeyse imkansız olan bozuk karakter karışımını göreceği anlamına gelir. SSL, her iki cihazın da gerçekten iddia ettikleri kişi olmasını sağlamak için iki iletişim cihazı arasında el sıkışma adı verilen bir kimlik doğrulama sürecini başlatır. SSL ayrıca veri bütünlüğünü sağlamak için verileri dijital olarak imzalar ve verilerin amaçlanan alıcıya ulaşmadan önce değiştirilmediğini doğrular.

![ssl](https://user-images.githubusercontent.com/55113204/117897018-820d9c00-b2ca-11eb-9089-b30ad0b09415.png)

## TLS Nedir?
İnternette iletişim sağlanırken güvenliği sağlayan bir şifreleme protokolüdür. TLS şifrelemesini kullanan bir iletişim oturumunu başlatan işlemdir. Bir TLS el sıkışması sırasında, iletişim kuran iki taraf birbirlerini tanımak, birbirlerini doğrulamak, kullanacakları şifreleme algoritmalarını oluşturmak ve oturum anahtarları üzerinde anlaşmak için mesaj alışverişinde bulunur. 

![tls](https://user-images.githubusercontent.com/55113204/117898408-956e3680-b2cd-11eb-9633-a1d96d5fbfaa.PNG)

## SSH Nedir?
Clientların serverlarını internet üzerinden kontrol etmeyi sağlayan protokoldür. Telnetin şifrelenmiş hali olarak oluşturuldu. Uzaktaki servera giden yada gelen paketlerin şifrelenmiş olarak gidiğ geldiğini bilir ve bu özellikte onun güvenli olduğunu göstermektedir. 

![ssh](https://user-images.githubusercontent.com/55113204/117978552-aa34e380-b33a-11eb-97bb-d80e8f9d2d93.PNG)

![image](https://user-images.githubusercontent.com/55113204/109421160-42335a00-79e7-11eb-9fd5-24a2d9fed1e7.png)


## SSL/TLS Protokol Analizi

Şifrelenmiş olan bu protokol için şifresini çözmek için bir key gereklidir. Biz burada bir örnek olsun diye şifrelenmiş bir trafik ve onun keylenmiş halini göstereceğiz.

İlk önce şifrelenmiş pcap paketini wiresharka import edelim.

![şifresiz](https://user-images.githubusercontent.com/55113204/117986631-78c01600-b342-11eb-8d17-a2cacc835340.PNG)

Dahas sonra keyi de Edit -> Preferences -> Protocol -> TLS -> Edit şeklinde bir yol izleyerek import edelim.

![şifreleniyor](https://user-images.githubusercontent.com/55113204/117986869-ac9b3b80-b342-11eb-8865-cc911552868b.PNG)

Şifresinin çözülmüş halini görelim.

![tls key1](https://user-images.githubusercontent.com/55113204/117986993-ca68a080-b342-11eb-8ba2-c18f95da1f7f.PNG)

Ve File -> Export Objects Alanında http trafiğinde takılan paketlerin içini görebilmekteyiz.

![tls key2](https://user-images.githubusercontent.com/55113204/117987220-f2580400-b342-11eb-9634-0922520649c2.PNG)

Kaydettiğimiz bir http paketinin içeriğini görüntüleriz ve neler olduğunu inceleyebiliriz.

![son](https://user-images.githubusercontent.com/55113204/117987599-4bc03300-b343-11eb-8b71-06abb8eb2226.PNG)

## SSL/TLS Arasındaki Farkları Avantajları Dezavantajları Nelerdir ?

SSL, TLS'in daha ilkel halidir. TLS, SSL'in yeni sürümü olarak ortaya çıkmıştır çünkü gün geçtikçe kusurları ortaya çaıkmıştır. SSL tam olarak açık kaynak vermediğinden bir süre sonra güvenlik açıkları olduğu ortaya çıkmıştır. TLS'nin SSL'ye göre avantajı, güvenli kabul edilmesidir ve dezavantajı, yalnızca SSLv3'ü destekleyen istemcilerin hizmetlere bağlanamamasıdır. SSL'nin avantajı, eski tarayıcılarla çalışmasıdır. Dezavantajı, yeni tarayıcıların güvenlik uyarıları vermesidir.

## OSI Katmanında TLS’in Yeri ve Önemi

•• SSL/TLS, çift yönlü bayt akışı sağlayan temel bir aktarım ortamı kullanır. Bu onu 4. tabakanın üzerinde olduğunu gösterir.

•• SSL/TLS, verileri özellikle üçlü el sıkışma mesajları içerebilen kayıtlar olarak düzenler. El sıkışma mesajları 5. (Session) katmana benzer. Bu, SSL/TLS'yi 6. veya 7. katmana koyar.

•• Bununla birlikte, SSL/TLS'nin aktardığı şey, aslında çift yönlü bir bayt akışı olan "application data" dır. SSL/TLS kullanan uygulamalar, onu gerçekten bir taşıma protokolü olarak kullanır. Daha sonra bu "application data" içinde kendi veri temsillerini ve mesajlarını ve ve mesajların anlamlarını kullanırlar. Bu sebeple, SSL / TLS, OSI modelinde 4. katmanda bulunur.

## SSL/TLS’e Yönelik Gerçekleştirilmiş Saldırılar Nelerdir ?

### • Şifre Paketi Düşürme Saldırısı

Saldırganlar istemcide gönderilen “Client Hello” mesajından bulunan şifre paketlerini silip yerine “Null” (şifreleme yapmama anlamına gelir) şifrelerle değiştirip sunucuya gönderirler. Sunucunun iletişimi güvenli hâle getirmek için yapabileceği  bir şey kalmaz. Ya bağlantıyı sonlandırır ya da “Null” şifrelemeyi kabul eder.
### • Bleichenbacher Saldırısı

Saldırının gerçekleşebilmesi için saldırganın sunucuya istediği mesajı şifrelemesi ve şifreli mesaja da ulaşabilmesi gerekmektedir. Sonrasında saldırgan tahminlerde bulunarak hedefini daraltır ve daha önce seçmiş olduğu şifreli bir mesajın açık hâline erişir. Açık hâli elde edilen şifreli paketin istemcinin sunucuya gönderdiği ve ön ana giz değerini içeren Client Key Exchange mesajı olması durumunda, saldırgan oturum anahtarını hesaplayabilir ve tüm oturum verilerine erişebilir.
### • Beast 

Saldırı, el sıkışma gerçekleştikten ve simetrik anahtar ile gizli iletişim başladıktan sonra gerçekleşir. Taraflar simetrik şifreleme için AES ve şifreleme yöntemi için CBC modu seçilmiş ise, saldırıya açık hâle gelirler. SSL/TLS Haberleşme Protokolüne Yönelik Saldırılar BEAST saldırısını kritik yapan unsur, saldırıların nasıl gelişebildiğini göstermesidir.
### • CRIME

Taraflar arasında ortak oturum anahtarı oluşturulduktan sonra, çerezler de bu oturum anahtarı ile şifrelenirler. CRIME saldırısı da şifrelenmiş çerez içerisindeki gizli değeri ele geçirebilir.
### • TIME

Bu saldırının başarılı olabilmesi için saldırganın ağ paketlerini dinleyebilir olması kısıtlaması vardır. TIME saldırısı, sıkıştırılmış verilerin büyüklüğünü giriş ve çıkış zaman farklılıklarından ölçerek gerçekleştirilmektedir.
### • Lucky 13

Bu saldırı, araya giren saldırganın oturum anahtarı oluşturulurken Şifre-Bloku Zincirleme (Cipher Block Chaining – CBC) kipi kullanılması hâlinde şifreli metinlerden açık metinleri ortaya çıkarabilmektedir. CBC kipi içeren bir şifre paketi ile oluşan oturumda şifre çözme işlemi yapılırken küçük zaman farklılıkları oluşur. Lucky13 saldırısında tam olarak da bu zaman farklılıkları kullanılarak gerçekleştirilmekteydi.
### • POODLE

TLS versiyonları ile el sıkışma başarısız olursa, taraflar SSLv3 ile konuşmaya çalışabilir. Bu durum ağ kesintilerinden kaynaklı olabileceği gibi, bir saldırgan tarafından da zorlanmış olabilir. Bu saldırı sonucunda SSLv3’ün kesin olarak güvensiz olduğunu ortaya çıkmıştır.
### • Heartbleed

Bağlantı kuran iki cihaz arasında dikkatli bir şekilde belirlenmiş veri paketi kadar veri gönderilmediği taktirde arta kalan veriyi dekendi hafızasından (RAM) gönderirse saldırgan sunucunun hafızasında bulunan kritik verilere (diğer kullanıcıların anahtarları, şifreleri vs.) erişimi gerçekleşir. Bu bilginin uzunluğunun sunucu tarafından kontrol edilmemesi, heartbleed açıklığının temelidir. Heartbeat eklentisi ise; birbiri ile bağlantı kuran cihazların, birbirleri ile iletişimlerinin aktif olup olmadığını kontrol etmek için gönderilen periyodik sinyallerden oluşan bir protokoldür. 
### • FREAK

Bu açıklığa göre istemci, ithal RSA anahtarı içeren şifre paketleri ile el sıkışmayı kabul etmektedir. İstemci başlangıçta bu şifre paketlerini önermemiş olsa dahi sunucunun isteği ile tercih etmektedir. 
### • Logjam

İthal şifre paketlerinin kullanmaktadır. Ancak Logjam, hem saldırı senaryosu hem de Diffie-Hellman’ı hedef almasından ötürü kritik bir saldırıdır.
### • DROWN

DROWN saldırısı genel hâli ile Bleichenbacher saldırısının geliştirilmiş hâli kullanılarak ve birtakım protokol açıklıkları kullanılarak gerçekleştirilen bir saldırıdır. 2048-bit uzunluğundaki bir RSA TLS şifreli metnini çözebilmek için saldırganın, 1000 adet TLS el sıkışmasını ele geçirmesi, 40000 adet SSLv2 bağlantısı gerçeklemesi ve toplamda 2 üssü 50 çevrim dışı işlem yapması gerekir.

## sslsniff Nedir?

sslsniff , SSL / TLS bağlantıları için ortadaki adam (MITM) saldırıları oluşturmak için tasarlanmıştır ve anında erişilen etki alanları için dinamik olarak sertifikalar oluşturur. Yeni sertifikalar, sağlanan herhangi bir sertifika ile imzalanan bir sertifika zincirinde oluşturulur.
sslsniff ayrıca, mümkün olduğunda bağlantıların sessiz müdahalesini sağlamak için boş önek veya OCSP saldırıları gibi diğer saldırıları da destekler.


## HTTP ve SSL Kullanılan Ortamlardaki Tehlikeler Nelerdir ?

"Http" kullanılırken veriler şifrelenmez, düz metin olarak gönderilir. Bu, giriş bilgilerinizin, şifrelerinizin ve hatta kredi kartı bilgilerinizin bunlara erişebilen herkes tarafından okunabileceği anlamına gelir. Aynısı güvenli e-posta ayarları için de geçerlidir. E-posta için standart güvenli olmayanlar yerine güvenli bağlantı noktalarını kullanmanızı öneririz. Giden SMTP sunucunuz için 465 veya 587 kullandığınızda, tamamen şifrelenir, varsayılan bağlantı noktası 25 ise düz metin olarak gönderilir. IMAP için eşdeğer güvenli bağlantı noktası, varsayılan 143 yerine 993'tür. E-postanız için güvenli olmayan bağlantı noktalarını kullanmak, oturum açma bilgilerinizin ve e-postalarınızın düz metin olarak gönderildiği ve kesilip okunabileceği anlamına gelir. Bu, e-postanızın güvenliğinin ihlal edilmesinin yaygın bir yoludur - genellikle hesabının spam göndermek için ele geçirilmesine neden olur. SSL olmayan web sitelerini ve güvenli olmayan e-posta bağlantı noktalarını kullanırken en büyük risk alanları, kafelerde, havaalanlarında veya otellerde halka açık WiFi kullandığınızda ortaya çıkar. Aynı halka açık WiFi ağındaki herhangi biri potansiyel olarak diğer kullanıcılar tarafından iletilen verilere müdahale edebilir.

## sslstrip
Web sitelerinde güvenliği sağlayan ssl sertifikalarını çıkararak, internet protokolünü değiştirerek yani https protokolünü kullanan siteleri http kullanımı şeklinde sağlayarak tüm trafiği ve öenmli bilgileri düz metin olarak aktarılmasını sağlayan bir tooldur.

![sslsniff](https://user-images.githubusercontent.com/55113204/118301039-4aca0580-b4eb-11eb-8eab-6c95dab4451b.PNG)



## ssldump 

SSL/TLS ile şifrelenmiş olan ağ trafiğindeki şifreleri çözmeye yarayan bir araçtır. SSLDump ile servera ait gizli olan anahtarlar elimizde gibi davranılır ve ve HTTPS gibi şifrelenmiş benzeri protokolleri trafik üzerinden geçen bilgileri okunabilmektedir. Daha önceden kaydedilmiş olan pcap dosyalarını da analiz edebilir.

![ssldump](https://user-images.githubusercontent.com/55113204/118159543-ca8d9c80-b425-11eb-9792-8de6093881dd.PNG)

## ssh tünelleme 

ssh tünelleme ile bir ağ üzerindeki tüm trafik şifreli bir şekilde bir başka server üzerinde akmaktadır. Bu sebeple giden gelen paketler incelenmez ve bundan dolayı zararlı yazılımlar hedefe ulaştırılabilir çünkü portlar kontrol edilmez.

![ssh-local1](https://user-images.githubusercontent.com/55113204/118415165-7ac30580-b6b1-11eb-9559-ee9b3f70635e.png)

## SSH Kullanarak Firewall/IPS/ Atlatma İşlemleri Nasıl Yapılır?

Bir pentest yapılan kurumda ağda dışarıya iletişim belirli portlar haricinde kısıtlanmıştır. Bunu aşabilmek için de açık olan bir port üzerinden dışarıya SSH tünel kurulumu yapılmaktadır. Yada bir kurum kendisine test yapılmasını istediği zaman hangi IP adresleri üzerinden denemeler yapıldığını bilmek istediğinden ve duruma göre IPS/Firewall/WAF sistemlerinden kendisine test yapılan sistemlerden özel erişim sağlanmasına izin vermektedir. Pentest ekibi birden fazla kişiden oluşuyorsa bunlar aynı IP adresi üzerinden çıkış yapabilmek için çıkış IP adresi yada VPS server kullanabilirler ve bu VPS server eğer linuxta ise birden fazla kişi bu servera bağlanarak sızma testini gerçekleştirebilirler. Bunun için SSHuttle aracını kullanabiliriz. Proxy sunucusu kurulumu yapılır.

![on](https://user-images.githubusercontent.com/55113204/118418353-cc26c100-b6c0-11eb-8c59-b7e72258f63e.PNG)

 Daha sonra atlama işlemi için aşağıdaki gibi bir syntax yazılabilir.
 
![onn](https://user-images.githubusercontent.com/55113204/118418393-ef517080-b6c0-11eb-9f8b-b58694c44a79.PNG)

## SSH Tünelleme ile İçerik Filtreleme Sistemlerini Atlatma İşlemleri Nasıl Yapılır ?

rootshell.be gibi 443. portta çalışan ve SSH port Forwarding’e açık  bir SSH servisi sunuyor. Bu siteye kaydolarak ve Putty gibi bir araç kullanarak filtreleme sistemlerinden tünelleme yapabilirsiniz.

![dokuz](https://user-images.githubusercontent.com/55113204/118418929-1dd04b00-b6c3-11eb-953f-6e18732eec04.PNG)

![sekiz](https://user-images.githubusercontent.com/55113204/118418934-232d9580-b6c3-11eb-89ba-64cfa48727d9.PNG)

Daha sonra netstat -an | find "8080" komutunu girip çıktı aldığımızda 127.0.0.1 ağında TCP ile dinleme yapıldığını görmekteyiz. Son olarak da kullanılan browserdan socks proxy kısmına "127.0.0.1 8080" yapılandırıması yapılarak browser kapatılıp açılır ve işlem son bulur.

## Sahte SSL Sertifikaları Nasıl Tespit Edilir ?

* Host adı doğrulanması,

* Tüm sertifika zincirinin imzalarını doğrulama,

* Her sertifika için meta veriler üzerinde ek kontroller yapma,

* Sertifikanın süresinin dolup dolmadığı veya henüz geçerli olup olmadığı, "politika kısıtlamaları", "anahtar kullanımları", "genişletilmiş anahtar kullanımları" gibi birçok ek şeyi kontrol edilmesi,

* Sertifikayı düzenleyenden sertifikanın public anahtarını alınması ve bu public anahtarı kullanarak doğrulanacak sertifikanın imzasını doğrulanabilmesi,

* Sertifikalar güven zinciri diye birbirlerini takip ettiklerinden dolayı güvenilen bir veya daha fazla yayıncıdan oluşan bir zincire sahiptir ve Tarayıcılar ve neredeyse tüm SSL sertifika kütüphaneleri bu zincir kontrolünü yapar veya en azından seçeneği sunar. Sahte sertifikalar bu denetimden başarısız olabilmesi,

* İmzalı root sertifikasının default olarak güvendiği sertifikalar arasında olup olmadığının kontrol edilmesi ile SSL sertifikarının sahte olup olmadığı tespit edilebilir.




**¯\\\_(ツ)\_/¯**
