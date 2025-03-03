# DHCP Nedir?
Cihazlara IP ataması yapan bu sistem internet bağlantıları için yol gösterici kurallar ve süreçler oluşturan bir protokoldür. Çalışma şekli olarak her cihaz için aynı mantık işler. DHCP sayesinde dinamik olarak IP adresi alan bir bilgisayar internette etkin rol alabilmektedir. DHCP'den IP adresi almak isteyen cihazlar DHCP sunucusuna giderler ve orada başka IP'ler ile çakışmadan kendi IP adresini alabilmektedir. Aynı zamanda farklı bir ağa bağlanmak isteyen bir cihazın, ağdaki Modem/Router'ın Default Gateway sayesinde DHCP yardımıyla bağlanabilmektedir.

## Kullanım Alanları
DHCP Server'lar ağda internete bağlanmak isteyen cihazlara IP adresi vermek için depo oluşturmuş ağdaki bir makinedir ve bir aynı ağdaki bilgisayarların farklı IP adresleri almasını sağlamaktadır. Aynı zamanda ağa bağlanan cihazın Subnet Mask'ının da belirlenmesini sağlamaktadır. Özellikle büyük çaplı ağlarda DHCP ile yapılandırma hem daha kolaydır hem de daha çok güvenilirdir, avantajlıdır.

## DHCP Başlık Bilgisi
![DHCP-header1-1-1024x549](https://user-images.githubusercontent.com/55113204/116402636-5522a900-a835-11eb-8deb-721af547ed74.png)

Opcode : Burası 8 bitlik alandır. Burada BOOT (önyükleme) isteği ve cevabı dönmektedir.
Hardware Type: 8 bitlik alandır. Ethernet, IEEE 802, ARCNET, LocalNet, LocalTalk, SMDS, Asenkron İletim Modu, ATM, Fiber Kanal, Frame Bayrağı, ISO 7816-3 üzerinden IP ve ARP istekleri, IPSec ve ARPSec tüneli, 	Wiegand Interface, Saf IP, MAPOS gibi hizmetleri sağlamaktadır.
Hardware address length: 8 bitlik alandır. 
Hop Count: 8 bitlik alandır. Bu alan relay agent (farklı subnette bulunan DHCP server üzerinden kendi subnetinizi dağıtım fırsatı veren servis) için kullanılır. 
Transaction ID: 32 bittir. Client (istemci) ile Server (sunucu) arasında mesajları ve ilişkiyi sağlamak için client tarafından seçilen rastgele sayılardır.
Number of seconds: 16 bitlik alandır. Client'ın bir adres edinmesi ve yenileme işlemine başlamasından bu yana geçen süreye denir.
Flags: 16 bitlik alandır. RFC 1542'e göre DHCP ve BOOTP Arasında Birlikte Çalışma belirlenmiştir.
Client IP Address: 32 bitlik alandır ve İstemcinin IP adresidir.
Your IP Address: 32 bitlik alandır ve sizin IP adresinizdir.
Server IP Address: 32 bitlik alandır ve sunucunun IP adresidir.
Gateway IP Address: 32 bitlik alandır. Bağlantının kurulduğu çıkış yolunun yani gatewayin IP adresidir.
Client hardware Address: 16 bitlik alandır. Burasının adresi client'ın interface adresidir. 
Server hostname: 16 bitlik alandır.
Boot filename: 128 bitlik alandır.
Options : Buranın uzunluğu değişkendir ve etiketli parametrelerin bir listesinden oluşmaktadır.

## DHCP Çalışma Mantığı
DHCP'nin en güzel çalışma şekli dinamik olmasıdır. Tek bir IP adresi veya da belirli bir IP adresine bağlı olmaksızın bir havuzdan yani çoğu bilgisayara atanmış bir subnetten (alt ağ) kullanılabilir bir IP atar. DHCP'nin aslında bir IP adresi ataması demek ona belirli bir süre için IP adresi kiralar demektir. Default olarak bu 5 günlük bir süredir. Şu şekilde çalışır. Öncelikle internete bağlanmak için cihazınızın internetini açın daha sonra burada bulunduğunuz ağ DHCP'nizden bir IP adresi ister. Bu isteğe discover mesaj denir. DHCP server bu istek üzerine cihaza bir IP adresi kiralar,verir. Buna DHCP offer mesajı denmektedir. Cihaz (client) gelen ilk teklif mesajındaki IP adresini kabul eder ve bunu kabul ettiğinden dolayı bu IP adresini doğrulamak adına DHCP request mesajı olarak yanıt vermektedir. Daha sonra DHCP sizin yeni IP adresinizi ve diğer yapılandırma işlemlerinizi ağ sunucularınızda güncelleme yapmaktadır. Bunuun sonucunda da dönen mesaja DHCP Ack mesajı denmektedir. Son olarakta cihazınız bu IP adresinizi kiralama süresinizce kabul etmeketedir. Bu kiralama süresi bittiğinde DHCP server otomatik olarak aynı yöntemlerle cihaza yeni bir IP adersi atmaktadır. 
Aşağıdaki görsellde de bu anlattığımız bu mantığı destekleyen görsel bulunmaktadır.
![csg68-01-how-dhcp-works](https://user-images.githubusercontent.com/55113204/116412325-3d502280-a83f-11eb-8348-63df50da770c.png)

## DHCP için kullanılan Portlar
DHCP relay ve DHCP proxy için router üzerinden yönlendirilen paketlerin DHCP servera ulaşması için UDP'nin hep source adresi hem destination adresi için 67. port kullanılmaktadır. Clientten servera giden paketler için 67. port kullanılırken Serverdan Clienta gidebilmek içinde 68. port kullanılmaktadır. 
![Ekran Alıntısı](https://user-images.githubusercontent.com/55113204/116414428-201c5380-a841-11eb-9dd2-2aaaa75d8ae1.PNG)
 
## DHCPDiscover, Offer, Request, ACK Mesajları
### DHCPDiscover Mesajı
Client bir IP adresi isteği zaman ilk olarak DHCPDiscover mesajını broadcast yapmaktadır. Bir server clienttan DHCPDiscover mesajı aldığı zaman ilk olarak client için bir ağ adresi seçimi yapar. Eğer mevcut olarak bir adres yoksa server durumu sistem yöneticisine bildirir. Yada adres mevcutsa şu şekilde adımlar izlenmektedir.
1- Clienttın mevcut olarak bağlantıda kayıtlı olduğu adresi verebilir, 
2- Clientın önceki adresi olan yani süresi dolmuş IP adresi veya serbest olarak IP havuzuna bırakılmış IP adresi hala duruyorsa bu verilebilir, 
3- Clientın istediği bir IP adresi hala geçerli ise ve başka bir cihaza verilmemiş ise bu IP adresi tahsis edilebilir,
4- Son olarakta Serverın belirlediği kullanılabilen bir IP adresi subnetine veya relay agenta göre verilebilmektedir.

DHCP Discovery mesajından sonra server clienta bir DHCP offer mesajı ile cevap vermektedir.

### DHCPOffer Mesajı
Burada hangi serverın client tarafından seçilip bu isteği aldığına bakılmaksızın bu sunucular tek tip dönüş yanıtı sağlamak amacıyla birden çok DHCP server clienta dönüş yapmaktadır. Dönüş mesajında clientın network adresini ve clientın IP adresini ne kadar süreyle kiralanacağı bilgisini taşımaktadır. Sistemde birden fazla DHCP server bulunma ihtimali vardır. Bu sebeple clienta en hızlı dönüş yapan server clienta IP adresi verebilmektedir. Bundan dolayı bu mesajda kendisini de tanıtmalıdır. Bu tanıtma Target IP Address (henüz belli olmadığı için değer 0.0.0.0'dır), Target MAC Address (client MAC adresi), Source IP Address (DHCP server IP adresi), Source MAC Address (DHCP server MAC adresi) bilgilerini de içermelidir. 

### DHCPRequest Mesajı
Bu mesaj DHCP Offer mesajına karşılık olarak yayınlanan mesajdır. Client bu mesaj ile aynı subnette kullanılabilir bir DHCP server olduğunu anlar. Bundan dolayı serverdan kendisi için kullanabileceği bir IP adresi de içeren network yapılandırılmasına sahip olan verileri ister. Burada IP adresini aldığını ve kullanacağını bildiren client, serverlara ben bu IP adresini aldım demek adına bir broadcast mesajı yollayarak diğer IP atamak isteyen serverlarla bağlantısını bitirir. Clientın IP isteğine birden çok server dönüş yapmış ise diğer serverlara başka bir serverla anlaştığını bildiren bir mesaj sonrası serverlar, network yapılandırma verilerini dahili olarak depolamaktadır. 

### DHCPAcknowledgement Mesajı
Clienttan Request mesajıyla dönüş alan bir DHCP server artık ona bir IP adresi verecek sunucu olduğunu anlamaktadır. Bundan dolayı DHCP server, clientın bilgilerini kayıt ederek ona bir IP adresi, subnet mask, DNS server IP adresi veya adresleri, Default gateway ve kiralama süresinin olduğu bir mesajla dönüş yapmaktadır. 

![Message-exchange-models-in-DHCP](https://user-images.githubusercontent.com/55113204/116435913-89599200-a854-11eb-95fb-066ef9f554d4.png)

## DHCP Relay Agent
DHCP relay agent kendi ağı dışındaki farklı bir server ile request ve replyleri iletmek için kullanılan herhangi bir TCP/IP ana makinesidir. Şu şekilde de yorumlanabilir farklı bir subnetteki DHCP serverdan kendi subnetindeki cihazlara IP adresi aldırarak iletişime geçmesini sağlayan cihazdır. Bu şekilde kendi ağının dışındaki cihazlarla iletişime geçilmesi sağlanmaktadır.

## DHCP Relay Agent Çalışma Mantığı
DHCP Relay Agent bir DHCP server ile DHCP client arasında bulunan bu cihaz aynı yerel ağ (LAN) üzerinde bulunmayan DHCP sunucusundan IP adresi almasını sağlamaktadır. Bir DHCP client bir IP adresi almak için yapılan DHCP isteğini her zaman broadcast adresini kullanarak yapar. Nasıl yapılandırıldığına bağlı olarak yerel bir subnete bağlı olan bir router ara birimi DHCP mesajı aldığında bu mesajı DHCP servera iletebilmektedir yada iptal edebilmektedir. İnterface DHCP relay olarak yapılandırılmamışsa mesajı iptal eder, yapılandırılmış ise mesajı DHCP servera iletebilmektedir. Bir router tek bir noktaya broadcast yapabildiği için ve DHCP mesajları da bir broadcast mesajları oldukları için routerın interfaceyi broadcast mesajını yeni bir tek noktaya broadcast mesajıyla sarar ve bu mesajı DHCP sunucusuna iletir. DHCP server tek bir noktadan broadcast mesajı aldığını isteğin bir DHCP clienttan olduğunu anlar ve DHCP relay tarafından yapıldığını da farkeder. Bunun sebebi bir DHCP clinet sadece tek bir DHCP servera broadcast yapmaz. DHCP server clienttan subnetini belirlemek için gelen tek bir noktaya broadcast mesajının source adresini kullanır. Default gateway IP adresi belirlendikten sonra DHCP server havuzlarını kontol ederek aynı default gatewayi kullanan havuzu bulur ve bu havuzdan kullanılabilecek IP adresini seçer ve tek bir noktaya broadcast mesajıyla sarar ve DHCP relaye geri gönderir. DHCP relay DHCP servardan bir tek noktaya broadcast mesajı aldığı zaman, bu mesajı yerel broadcast mesajına dönüştürür yerel subnete gönderir. Client DHCPOffer mesajını yerel broadcast mesaj olarak alır.

![dhcp-relay-agent](https://user-images.githubusercontent.com/55113204/116472921-31845080-a87f-11eb-933f-904b14ead684.jpg)

## DHCP Saldırıları
DHCP yoluyla gerçekleştirilen üç tip saldırı vardır. Bunlardan biri DHCP starvation saldırısı diğeri ise DHCP spoofing saldırısıdır.

### DHCP Starvation Saldırısı
DHCP serverları hedef alan dijital saldırıdır. Saldırgan DHCP serverın IP adreslerini bitirene kadar DHCP serverı fake DHCPDiscover mesajları ile doldurur. Eğer sunucu gelen bu mesajların hepsine cevap verirse havuzdaki IP paketlerinin hepsini tüketebilir. Ve DHCP server geçerli DHCP isteklerine sunacak daha fazla IP adresi olmadığına inanabilir. Aynı zamanda gerçek bir IP adresi isteyen clientlar kendileri için IP adresi verilmeyeceğini anlar ve bu saldırının üzerine DHCP server gerçek clientların isteklerini reddedebilir. Bundan dolayı clientlar başka bir DHCP server arayabilmektedir. Bu şekilde gerçek bir DHCP server kalmadığı zaman saldırgan kendi DHCP serverına istek atar ve saldırganın sunucu IP paketleri dağıtmaya başlar. Bu DHCP serverı kullanan clientlar artık saldırganın makinesi aracılığıyla yönlendirilmektedir. Hatta Middle in the man saldırısına yol açan alternatif bir DHCP bağlantısı da sağlayabilir. 

![dhcp_starvation](https://user-images.githubusercontent.com/55113204/116831124-2f3f3080-abb6-11eb-98bb-5e478de69e34.PNG)

### DHCP Spoofing Saldırısı
Saldırganların sahte bir DHCP server kurduğu ve bu serverı ağdaki cihazlara fake DHCP yanıtı göndermek için kullanılan saldırıdır. Saldırgan kendisini default gateway veya DNS server olarak göstermeye çalıştığında bu saldırı gerçekleşmiş olur. Bunun sayesinde gerçek bir ağ trafiğine geçmeden önce kullanıcılardan gelen trafiği engelleyebilme veya gerçek bir DHCP serverı IP adresine boğarak cevap dönderemeyecek hale getirebilir. 

![dhcp_spoofing](https://user-images.githubusercontent.com/55113204/116831132-36fed500-abb6-11eb-8ee1-bda0c7d25de8.PNG)


### DHCP Snooping Saldırısı 
DHCP isteğinde bulunan clientlara saldırgan tarafından tahsis edilen bir IP adresi verilir. Client bu cevabı aldığı zaman default gateway olarak bu sahte adresi kullanmaya başlar. Ağ dışındaki bir yere ulaşmak isteyen paketler öncelikle ağ dışına çıkmadan saldırganın makinesinin üstünden geçer daha sonra saldırgan bu paketleri gitmeyi istediği yere yönlendirir. Bu şekilde gelen giden tüm paketleri izleme olanağı bulur. İsterse clientten gelen yönlendirme isteğini istediği servera da gönderebilir. Kendi istediği internet sitesine de yönlendirebilir. Sadece belirli portlar üzerinden DHCP Snoopingin izni ile güvenli yada güvensiz ilan edilebilir. Bu şekilde güvensiz portlardan paket aktarımına izin veirlmez ve buradan gelen DHCP cevapları çöpe atılır.

### DHCP Resource Starvation Saldırısı Nedir?
Bu saldırı fake MAC adresleri ile DHCP requestlerini broadcast yapar. Yeterli sayıda istek gönderirse, bir süre sonra DHCP serverlardaki kullanılabilecek IP adresleri tüketilebilir. Saldırgan daha sonra bu istekleri karşılamak için sahte bir DHCP server kurabilir ve ağdaki DHCP clientlardan gelen requestlere cevap verebilmektedir. Yani DHCP request tüketimi sonucunda sahte bir serverdan DHCP request oluşumunu sağlayan saldırı türüne DHCP Resource Starvation saldırısı denir. Saldırgan ağa bağladığı bu sahte server ile clientlara adresler ve diğer ağ bilgileri sağlayabilmektedir. İstediği yere yönlendirmede yapabilmektedir. Ağın trafiğini izleyip kontrol de edebilir. 

![dhcp_resource_starvation_attack](https://user-images.githubusercontent.com/55113204/116831146-4716b480-abb6-11eb-8547-a52dea399b12.jpg)


## Rouge DHCP Server Deployment Nedir?
Sahte bir DHCP serverın ağı kandırmasıdır. Sahte olan DHCP server gerçek bir DHCP clienttan gelen trafiği yakalayıp yeniden yönlendirebilir. Rouge DHCP serverlar iletişimleri engellemek ve trafiği gizlice dinlemek için kullanılabilir. İsterse bu server sayesinde tüm trafiği bir ağ üzerine de yönlendirebilirler. Rogue DHCP server, DHCP server ile deneme yapan bir client tarafından yanlışlıkla ağa tanıtılan yanlış yapılandırılmış veya yanlış yetkilendirilmiş bir serverdır. Rouge serverlar clientlara yanlış bir IP adresi atadığında clientler geçerli domain controllerları (DC) bulamayabilir bundan dolayıda clientların ağda oturum açılmaları engellenmiş olur. Yada IP kiralamalarının yenileme requestlerini geri çevirebilir. 

## DHCP Saldırılarından Korunma Yöntemleri
DHCP snooping ekipmanları ile güvenilmeyen DHCP serverın trafiğini engelleyebilir. Yada bu DHCP gözetleme ekipmanı ile IP adreslerini, MAC adreslerini veya karşılıklı gelen portları izleyerek yalnızda güvenilir kombinasyonların iletişim kurmasını sağlamaktadır. Ağ spoofing yağmak için birçok araç mevcuttur. Bu araçların bazı DHCP server tarama araçlarının anlık ileti uyarı ve e-posta uyarı yetenekleri vardır. Bu sebeple güvenilmez bir DHCP server buldukları zaman sistem yöneticisini uyarabilmektedirler. BAşka bir yol ise networkun bölümlere ayrılmasıdır. Bu şekilde eğer bir parça sahte bir DHCP server tarafından kandırılıyorsa diğer ağlar bundan etkilenmeyebilir. Son olarak da şüpheli adreslere karşı beklenmeyen bir anda DNS trafiği gibi fake client yapılandırılmasına ait kanıtlar toplamak için ağ trafiği izlenmesidir. Avantajları ise eski bir düzene yeni bir perspektif getiriyor olmasıdır. Bu şekilde etkili olarak tehtid azaltma stratejileri geliştirilebilir.

## DHCP Saldırı Araçları
DHCP Sentry, Roadkil.net's DHCP Find, Dhcploc.exe, dhcp_probe, DHCPig, dstar, DHCP-Starvation.py,OpUtils’ DHCP, yersinia

Yersinia ile bir DHCP saldırsı gerçekleştirecek olursak ilk olarak eth0 hangi IP adresinde ına bakmalıyız.

![1](https://user-images.githubusercontent.com/55113204/116700099-0f99e380-a9cf-11eb-8fc7-7028e564e80e.PNG)

Daha sonra yersinia aracımızı başlatıyoruz.

![2](https://user-images.githubusercontent.com/55113204/116700159-26d8d100-a9cf-11eb-9bbd-2e86089ee669.PNG)

Sonra saldırıyı başlatmak için launch attack basıp DHCP saldırısı yapacağımızı seçip saldırı görevini seçiyoruz.

![3](https://user-images.githubusercontent.com/55113204/116700529-8c2cc200-a9cf-11eb-841b-a796823b5ca6.PNG)

DHCP sunucuna burada DoS saldırısı yapacağız ve farklı IP adreslerinden discover paketleri yollayarak DHCP serverda bulunan IP ve MAC adreslerini bir süre sonra tüketmiş olacağız. Aşağıda da görüldüğü gibi fake discover paketleri DHCP serverlara yollanmıştır.

![6](https://user-images.githubusercontent.com/55113204/116721510-0e27e580-a9e6-11eb-9ec0-4c6026cc49f2.PNG)

Aynı zamanda Wireshark üzerinde de DHCP Spoofing yaptığımızı görebilmekteyiz.

![5](https://user-images.githubusercontent.com/55113204/116722458-13396480-a9e7-11eb-9639-24fffe15d1d0.PNG)



## DNS ve UDP İlişkisi
DNS isim için ise UDP'yi kullanır ve reverse'si sorggulanır. UDP burada küçük bilgi alışverişinde kullanılır. DNS istekleri de genellikle çok küçük olduğundan dolayı bu paketleri kullanır DNS serverda routerın çalışması için tüm UDP paketlerini gelen trafiğin herhangi bir yüksek UDP portuna ulaşmasına izin verilir. UDP çok hızlı olduğu için DNS server bu protokülü tercih etmektedir. Bunun sebebi üçlü el sıkılması yapmamasıdır. UDP ayrıca güvenilir bir protokol değildir ama uygulama katmanına güvenirlik eklenebilir ve yeniden gönderilebilir. DNS 53. porttaki UDP protokolünü kullanır. Bu portu kullanmasının sebebi DNS sprusu yapmasıdır. DNS sorguları, clienttan gelen bir UDP paketine karşılık DNS serverdan da UDP paketiyle bir yanıt oluşur. Gelen cevap paketin boyutu 512 baytı geçtiği zaman ve clientla server EDNS'yi dekteklediği zaman daha büyük UDP paketlerine ihtiyaç duyulur.


## DNS ve TCP İlişkisi
DNS, TCP güvenilir oldupundan dolayı zone transferininde her zaman TCP'nin 53. portunu kullanır. Çünkü transfer yapılırken veriler tutarlı olmalıdır. DNS serverlar arasında bağlantı kurulur ve source ve target DNS server, TCP ACK bitlerini kullanarak verilerin tutarlı olması sağlanmaktadır. DNS sorgularında paket boyutu 512 baytı geçtiği zaman TCP'yi kullanır. TCP güvenilir bir bağlantı olduğundan dolayı LDAP protokolü de her zaman TCP kullanmaktadır. 53. portta bir DNS isim sorgusu yapıldığında ve DNS serverdan bir cevap alınamadığı zaman 3-5 saniye sonra tekrar bir DNS sorgusu sorgusu yapılır ancak bu sefer TCP protokolünü kullanarak yapar.  

![When-does-DNS-use-TCP-or-UDP](https://user-images.githubusercontent.com/55113204/116831169-631a5600-abb6-11eb-8410-06b9a1e94e12.jpg)


## DNS Çalışma Mantığı
Bir DNS server bir ana bilgisayar adını bir IP adresine çevirir. İnternete çıkan tüm cihazlara bir IP adresi verilir ve herhangi bir cihazı bulmak için gereklidir. DNS'i bir telefon rehberine rehberi gibi düşünebiliriz. Yani Bir domain isimlerini bir IP adreslerine eşleştirir. 

![dns](https://user-images.githubusercontent.com/55113204/116831172-6e6d8180-abb6-11eb-84b0-f714e3e22f5f.gif)


## Root DNS
Kök sunucular yani yetkili ad sunucuları dünya üzerinde birçok ülkede bulunana ve altında bir çok sunucudan oluşan bir ağdır. Bir networkun kök bölgesinde bulunan en üst noktadaki çalışan ad sunucularıdır. Bu serverlar köte bulunan ve deoplanan ve önbelleğe alınan sorguları doğrudan yanıtlayabilen ve diğer istekleri TLD servera yönlendirebilen kök sunucularıdır. Bir DNS sorgusu araması kök bölgenden başlar daha sonra bu üst noktadan aşağıya doğru ilerlemektedir. Sorgu ilk olarak Root DNS sonra TLD servera oradan da etki alanı içindeki Yetkili olan Name Servera ulaşana kadar arama yapar ve bunun sonucunda bir IP adresine ulaşılır ve bu IP adresi clienta verilir. 

![ROOT (1)](https://user-images.githubusercontent.com/55113204/116831182-79281680-abb6-11eb-8b4b-46e3b4ff076e.png)


## DNS Sorgu Türleri
3 çeşit DNS sorgulama türleri vardır.
### Recursive Query
Bu sorgu özyinelemeli sorgudur. DNS client bir domain tanımlar ve DNS server bu sorguya yanıt vermek zorundadır. Eğer bu sorgu hakkında böyle bir kaynak yoksa olmadığına dair bilgilendirme mesajı ile geri dönüş yaparak hata mesajı verir. DNS çözümleyici sorgulanmak istenen domain adı hakkında IP adresini ve diğer bilgileri bulana kadar Root DNS Server'dan başlayarak özyinelemeli olarak sorgu yapmaktadır. 


### Iterative Query
Yinelemeli sorgu bir DNS çözümleyi DNS clienta verebileceği en iyi yanıtı gönderir. Eğer DNS çözümleyicisinin önbelleğinde sorgu hakkında bir bilgi varsa bunu kayıtları döndürmektedir. Eğer önbellekte de kayıt yoksa DNS clienti en yakın alakalı DNS zone yada Root DNS Servera yönlendirir. Bu esnada DNS client DNS sorgusunu başvurduğu DNS servera tekrar etmelidir.

![recursive-query](https://user-images.githubusercontent.com/55113204/116831198-8e04aa00-abb6-11eb-9a2a-4f98b6c6b79b.jpg)

### Non-Recursive Query
Özyinelemeli olmayan sorgudur. Bu sorgu DNS çözümleyicisinin bildiği yani sorguyu önbellekte depoladığı için bir DNS kaydı gönderir yada kayıtta yetkili olan bir DNS name serverı sorgular yani istenilen sorgunun IP adresine zaten sahiptir. Bundan dolayı sorgulamaları tekrarlamaya gerek yoktur. Tek seferde zaten istenilen bilgiler elde edilir.

## DNS Server Çeşitleri
3 çeşit DNS Server çeşidi vardır.
### DNS Resolver
Bu server bir domain adı sorgulamasını IP adresine çevirmekten sorumludur. Örneğin www.ornek.com domaininin sorgulanmasında 10.10.0.0 gibi bir IP adresi ve bilgileri dönmektedir.
### DNS Root Server
İlk olarak root serverdan IP adresine kadar uzun bir sorgulama yapar. TLD name serverın ayrıntıları ile sorgulama yapar. Örnek olarak .com, .gov gibi DNS zone sahip alanların ayrıntılarıyla bilgi sağlayacaktır.
### Authoritative DNS Server
Yüksek seviyeli serverlar, ana makine için güncel bilgileri tutmaktadır. Bu server name server sorgusundaki son gidilen duraktır. Sorguyu alır DNS çözümleyiciye döndürür ve IP adresini bulur eğer bulamazsa NXDOMAIN mesajını döndürür.

## DNS Önbellek
Bir makinenin DNS sorgusunun genel bir bilgisini kopyalamak, web browserdaki eski DNS aramaları hakkında bilgilerin geçici olarak saklandığı yada işletim sistemi hakkında bilgilerin depolandğı alandır. Eğer bir DNS sorgusunun kopyası alınırsa tekrar bu sorgu yapıldığı taktirde hızlı bir şekilde domainine karşılık gelen IP'si, işletim sistemi bilgileri, web browser geçmişi çözümlenebilmektedir. Bir DNS sorgusu sırasında ilk önce root server sonra TLD server sorgulanır ve buradan elde edilen bilgiler de önbelleğe kayıt edilmektedir. DNS önbelliği boş olsa bile DNS çözümleyicisi bu bilgileri kendi önbelleğine almış olabilir bundan dolayıı da tam bir DNS sorgulaması yapma ihtiyacı kalmayabilir.
* DNS önbelleği şu bilgileri içerir:

Kaynak verileri (rdata): kaydı tanımlayan veriler, örneğin adres veya ana bilgisayar adı
Kayıt türü : oluşturulan girişin türü, örneğin "A": IPv4 adresi (ondalık değer: 1) veya "AAAA": IPv6 adresi (ondalık değer: 28)
Kayıt adı (isteğe bağlı): DNS girişinin kendisi için oluşturulduğu nesnenin alan adı
Canlı zamanı (opsiyonel): saniye cinsinden kaynak kaydı geçerlilik süresi
Sınıf (isteğe bağlı): RR'nin ait olduğu protokol grubu (esas olarak internet için "IN")
Kaynak veri uzunluğu (isteğe bağlı): kaynak verilerinin uzunluğu için değer
DNS önbelleği, ilgili etki alanları veya ana bilgisayarlar için IP adreslerinin yanı sıra , kaydın geçerlilik süresi veya uygun protokol grubu gibi bunu belirten ek bilgileri de içerir .

## DNS Sorgulamaları için Dig Kullanımı Nasıldır?
Ağ yönetimi komut satırı aracı olan dig (Domain Information Groper) DNS ad sunucularını sorgulamak ve DNS aramalarını yapmak için kullanılmaktadır. 

### A Kaydı
>> Doman ile ilgili A kaydı hakkında genel bir bilgi edinebiliriz.
>> Burada 9.16.13 bize sürüm hakkında bilgi vermektedir.
>> Daha sonra dig gazi.edu.tr den aldığı yanıtı bize döndürmektedir.
>> Bu sorgu sonucunda IN İnternette bir sorgulama olduğunu göstermektedir.
>> 194.27.18.16 IP adresine sahip olduğu bilgisini vermektedir.
>> Bunun bir A kaydı olduğunu söylemektedir. 
>> Server ve tarih hakkında da bizi bilgilendirmektedir.

![dig](https://user-images.githubusercontent.com/55113204/116727003-afb23580-a9ec-11eb-8e6d-b884237af44b.PNG)

### + (Genişletme)
>> Burada sadece bir kayıt türünü değil aynı zamanda istediğimiz bir kayıt türünü de arayabiliriz. İsterseniz IP adresleri de ekleyip farklı IPlerinde DNS bilgileri hakkında ipuculara ulaşabilirsiniz. 
>> İkinci bir örnek olarakta biz burada MX kaydını da aramak istedik. 

![dig2](https://user-images.githubusercontent.com/55113204/116728060-1a17a580-a9ee-11eb-9372-546002136cc7.PNG)

![dig2](https://user-images.githubusercontent.com/55113204/116727797-b2f9f100-a9ed-11eb-99ca-e60981935194.PNG)

### MX Kaydı
>> Burada bir domainin MX kayıtları hakkında bilgi edinebiliriz.
>> Farklı DNS source kayıtlarını sorgulamak için kullanabiliriz. 

![dig mx](https://user-images.githubusercontent.com/55113204/116728250-577c3300-a9ee-11eb-9cb8-2e68efa8083d.PNG)

### SOA Kaydı
>> Bölgelerde tutulan ilk kayıtlardır. bir DNS için bulunduğu bölgeden sorumlu olarak primary DNS olduğunu gösteren kayıttır. 

![dig5](https://user-images.githubusercontent.com/55113204/116729434-d0c85580-a9ef-11eb-96ae-5a4533e18057.PNG)

### TTL kaydı
>> Bir DNS kaydının ne kadar süreliğine önbellekte tutulması gerektiğini saniye cinsinden söyler.

![dig6](https://user-images.githubusercontent.com/55113204/116729891-6ebc2000-a9f0-11eb-98fc-0123da61fa81.PNG)

### Geriye Doğru Sorgulama
>> Dig kullanarak IP adresinden domaine göre sorgu yapabilmekteyiz.

![dig8](https://user-images.githubusercontent.com/55113204/116730889-b2fbf000-a9f1-11eb-980d-5d41466bcdba.PNG)

### Birden Çok Sorgulama
>> Hem gazi.edu.tr hemde google.com domainin MX kayıtlarını aynı anda birden çok sorgulama tekniği ile sorgulayabiliriz.

![dig9](https://user-images.githubusercontent.com/55113204/116731227-1ab23b00-a9f2-11eb-8cea-08901ef29ec4.PNG)


## DNS’e Yönelik Saldırılar

### TCP SYN Floods :
Server ile client arasındaki el sıkışmasını rastgele isteklerle doldurarak kesintiye uğratan bir DDoS saldırısı türüdür. Mevcut açık bağlantıların rezervini tüketmek amacıyla servera, onlara yanıt verebileceğinden daha hızlı bir şekilde senkronize (SYN) mesajları göndererek gerçekleştirir. Client SYN mesajı atar server SYN-ACK mesajı döndürmesi esnasında saldırgan daha hızlı davranarak giderek daha fazla istek üretir ve sonuçta sunucunun çökmesine neden olan yarı açık bağlantıların çoğuyla sonuçlanır.

![syn-flood](https://user-images.githubusercontent.com/55113204/116831320-2c910b00-abb7-11eb-8d4b-3dcc29c688bd.jpg)

### NXDOMAIN attack :
Bir NXDOMAIN saldırısı, DNS sunucusu var olmayan alan adlarına yönelik sorgularla dolup taştığında, yetkili ad sunucusunun önbelleğini doldurduğunda ve meşru DNS isteklerini tamamen durdurduğunda bir DDoS varyantıdır.

![nxdomain](https://user-images.githubusercontent.com/55113204/116831328-331f8280-abb7-11eb-934d-e1a7ae7c56ac.png)

### Phantom domain attack :
Özyinelemeli DNS aramalarını engellemek için yapılır. Yetkili bir ad sunucusuna yönelik bir tür DoS saldırısıdır. DNS isteklerine yanıt vermeyen veya bunu çok yavaş yapan ve iletişimi kesintiye uğratan bir grup DNS sunucusu kurarak yapılır.

### Random subdomain attack :
DNS'den var olmayan bir etki alanı istemek yerine, bu saldırının var olmayan bir alt etki alanı istemesidir. Şöyle anlatmak gerekirse www.asdasdas.com diye bir site düşünelim DNS bunda bize bir cevap döndürecektir ama www yerine asd.asdasdas.com olarak değiştirsek asd dizesini özyinelemeli olarak aramak isteyecektir. Sürekli bu başlığı değiştirirsek her sorgu asdasdas yetkili sunucusuna yönelik özyinelemeli bir sorguyu tetikleyerek, özyinelemeli bağlamları tüketir ve negatif önbelleği doldururacaktır. Bu saldırı özellikle alanın yetkili ad sunucularını hedef alır.

![random](https://user-images.githubusercontent.com/55113204/116831343-42063500-abb7-11eb-9d45-82bb4f449b1f.png)


### Distributed Reflection DoS attack :
Saldırı trafiğini bir mağdura göndermek için potansiyel olarak meşru bir üçüncü taraf bileşenini kullanır ve sonuçta saldırganların kendi kimliğini gizlerler. Bu durumlarda, saldırgan sahte bir kaynak IP'si ile bir DNS, NTP, vb. İstek göndererek sahte adreste bulunan ana bilgisayara daha büyük bir yanıt gönderilmesi amacıyla gönderilebilir. Yani örnek verecek olursak bir IP adresinden bir SYN mesajı alınır ama ana makine yapmamıştır çağrıyı buna karşılık gelen yanıt mesajında ana bilgisayar benden gelmedi bu istek der ve önünü keser bunun üzerine serverın kafası karışır ve ne yapacağını bilemediğinden trafiği kitler.

![tcp-reflect](https://user-images.githubusercontent.com/55113204/116831344-50ece780-abb7-11eb-928b-a687f4b14fc0.gif)

## DNS Kullanılarak Gerçekleştirilen Saldırılar

### DNS Lock-up Attack :
Serverı doğru yanıtı göndermeyip rastgele veri paketleri ile yanıtlayarak meşgul tutar ve mevcut bağlantıların rezervini tüketen (asla gelmeyen) uygun bir yanıt beklemelerini sağlar. Ve istemci arasındaki el sıkışmasını da kesintiye uğratır. Bu saldırı üç yönlü bir TCP el sıkışmasının sonraki aşamasında gerçekleşir. İstemciden ACK mesajının gelmesini beklerken el sıkışmayı kasıtlı olarak yavaşlatır ve saldırgan tarafından ACK mesajlarını geri gönderir.


### DNS rebinding attack :
Web sayfası çalışmadığında yeniden yüklenmesi esnasında saldırgan Walware kullanarak siteye kötü bir yazılım atar ve siz tekrar yüklediğinizde bunu kendi DNS sunucusuna atar. Bu şekilde tekrarlanan aramalar yapmak için DNS önbelleğe almayı ve tarayıcınızı zorlamayı önlemek için arama yanıtına çok kısa bir süre (TTL) verir. Kurban web sitesini yüklediğinde, sitedeki kötü amaçlı komut dosyasını tetiklemiş olur.

![rebinding](https://user-images.githubusercontent.com/55113204/116831353-6bbf5c00-abb7-11eb-8d2e-25f06379a0b2.png)

### DDoS attack :
Saldırganlar genellikle hedefi trafikle bombalamak için botlar kullanır. Yalnızca bir botun kullanıldığı bir durum, Hizmet Reddi (DoS) saldırısı olarak bilinir ve çoğunlukla yerelleştirilir veya minimum etkiye sahiptir. DDoS ise daha geniş bir etkiye sahip ve daha fazla kaynak gerektirecek.


### DNS hijacking :
DNS sorgu sonuçlarını değiştirme yöntemine DNS hijacking denir. Bu değişiliklere phishing denir. Sahte DNS sunucuları domainleri kötü amaçlı IP adreslerine çevirir. DNS korsanlığı olarak bilinen ve Malware gibi kötü yazılım araçları kullanılarak TCP/IP ayarları değiştirilerek saldırganın kontrolü ile kendi belirlediği sahte bir DNS servera yönlendirerek yapılır.

![DNS-Hijacking](https://user-images.githubusercontent.com/55113204/116831364-87c2fd80-abb7-11eb-91cb-83e0596d6df4.png)

### Cache poisoning :
Yanlış DNS önbelleğine yönlendirme olacak şekilde bir DNS önbelleği zehirlenmesi yapılabilmektedir. Bu şekilde saldırganın istediği web sitesine yönlendirilebilirsiniz. Adımları şöyledir. Sahte bir DNS server kurar bir DNS resolveye istekte bulunur gerçek bir DNS name server yanıt vermeden önce DNS resolvera bir şeyler uydurarak cevap verir.

![cache1](https://user-images.githubusercontent.com/55113204/116831372-93162900-abb7-11eb-9a0e-b6c3db1b7edc.png)

## DNS Sunucu Versiyon Bilgisini Belirleme
Birçok DNS sunucusu version.bind, CHAOS sınıfındaki etiket için DNS TXT kayıtlarındaki sürüm bilgileriyle önceden yapılandırılmıştır.
* dig @dns.name.server version.bind chaos txt

## Zone Transfer 
Bölge aktarımı primary DNS serverın o bölgedeki dosyalarını seconder DNS servera kopyalama işlemidir. Bu şekilde kopyalama yaparak herhangi bir hatanın önüne geçilebilmektedir. Eğer bir çözümle esnasında primary DNS server başarız olursa seconder DNS server çözümleme yapmaya devam eder. Ve aynı şekilde seconder DNS serverlar diğer seconder DNS serverlara aktarma yapabildiklerinden DNS çözümlemesi devam eder. 3 Zone Transfer modu vardır.
Tam Aktarım DNS Transfer : Bir bölge için mevcut tüm kaynak kayıtlarını çoğaltmak için tüm bölge bilgilerinin tam aktarımını gerçekleştirir. Eğer yeterli bant genişliği yoksa çok zaman almaktadır. Örnek olarak DNS veritabanına yapılan güncellemelerdir. 
Artımlı DNS Transfer : Primary DNS server ile seconder DNS server kayıtları karşılaştırılır. Zonelar eğer tanımlanmamışsa karşılaştırılma yapılamaz. Eğer primary server seri numarası seconder server seri numarasından yüksek ise delta kaynak kayıtlarının aktarımı başlar. Bu da daha az bant genişliği gerektirir. Bundan dolayı trafik daha az olur ve hızlı bir şekilde biter.
DNS Bildirimi : Bu bir aktarım yöntemi değildir. Seconder DNS serverlardan primary DNS serverların sürekli sorgulanmasını önlemek için bir standart olarak geliştirilmiştir. Tüm seconder DNS serverların IP adresleri, zone güncellemeleri almak için primary DNS serverların bildirim listesine girmektedir.

## DNS Spoofing Nedir?
DNS serverın önbellek veritabanındaki veriler eklenmesi yada değiştirilmesiyle oluşan saldırıdır. Bu saldırı esnasında ağ trafiği ya yanlış yönlendirilir ki bu genellikle saldırganın bilgisayarına yönlendirilerek ağı izlenmek içindir yada yanlış olan IP adresleri döndürülmektedir. Bu saldırıda bir adrese gidilmek istendiğinde saldırgan tarfından yönlendirilen trafikle farklı bir ağa yönlendirilir. Burada ya saldırganın kendi sitesine yönlendirme olur yada bilgisayarın ele geçirebilmesi için virüsler veya zararlı yazılımlar yüklenir. Bu sayede hem kişisel bilgiler elde edilebilir hemde sizi kullanarak arkanıza saklanıp kötü işlere kendisi bulaşmadan sizi kullanabilmektedir.

![dns_spoofing](https://user-images.githubusercontent.com/55113204/116831404-d8d2f180-abb7-11eb-9301-a9d9cc1fc150.jpg)

## DNS Cache Snooping Nedir?
DNS önbellek gözetlemede, DNS server sorgulandığı zaman bu serverın önbelliğine bakarak belirli bir DNS kaydı var mı öğrenmek amacıyla ve bu DNS server yada DNS clientın yakınlarda belirlenmiş bir siteyi ziyaret edilmiş onu öğrenebiliriz. İki şekilde yapılabilir. Birincisi, Yinelemeli olmayan sorguları kullanmadır bunda cevaplar önbellektedir sonra sunucu sorguyu sağlar. İkincisi  ise, Özyinelemeli sorguların kullanılmasıdır. Bunda ise birincisinde yapılan sorgulamanın aynısı yapılır ama serverın cevap vermesi esnasındaki geçen süreye bakarak önbellekten gelen yanıtı sağlar.

![dns cache snooping v](https://user-images.githubusercontent.com/55113204/116831406-dec8d280-abb7-11eb-96b9-b8f59c10bdff.JPG)


## DNS Rebinding
Bir siber saldırı çeşidi olan DNS Rebinding ile kurban bilgisayarın firewallun arkadasındaki sistemlere komutlar göndererek Javascripti çalıştırıp sonra bir alan adıyla ilişkili IP'yi değiştirebilmektedir. Bunu yaparken bir websitesinin yeniden yüklenmesini beklerler. Bunun içinde DNS sunucusuna kısa yanıtlar döndürecek şekilde TTL (yaşam süresini) 10 saniye gibi bir sürede yapılandırılırlar. Misal bir client kötü amaçlı olan badsite.com adlı siteyi açtığında karşı tarafın DNS sunucusu, kötü amaçlı web sitesini barındıran HTTP sunucusunun IP adresiyle yanıt verir. Web server clientın web tarayıcısında çalışan Javascript içeren bir web sayfası döndürür. Javascript kodu daha sonra bazı ek kaynakları indirmek için orijinal alan sahtesite.com'daki orijinal web sitesine erişir. Web tarayıcısı Javascript'i çalıştırdığında, etki alanı için yeni bir DNS isteği gönderir (kısa TTL nedeniyle), ancak saldırganın DNS'si yeni bir IP adresiyle yanıt verir. Örnek olarak saldırganın DNS sunucusu gerceksite.com gerçek dahili bir IP adresiyle yanıt verebilir. Sonuç olarak ise, gerceksite.com yerine sahtesite.com sitesi yüklenmiş olur.

![dns_rebind_general_approach2](https://user-images.githubusercontent.com/55113204/116831741-cbb70200-abb9-11eb-8287-14477ed62818.jpg)


## DNS Tünelleme
Saldırgan, badsite.com gibi bir alanı kaydeder. Etki alanının ad sunucusu, saldırganın kötü amaçlı tünel oluşturan bir programın kurulu olduğu sunucuyu işaret eder.
Saldırgan, genellikle bir şirketin güvenlik duvarının arkasında bulunan bir bilgisayara kötü amaçlı yazılım bulaştırır. DNS isteklerinin her zaman güvenlik duvarına girip çıkmasına izin verildiğinden, etkilenen bilgisayarın DNS çözümleyiciye bir sorgu göndermesine izin verilir. DNS çözümleyici, IP adresi isteklerini kök ve üst düzey etki alanı sunucularına aktaran bir sunucudur.
DNS çözümleyici, sorguyu saldırganın tünelleme programının kurulu olduğu komut ve kontrol sunucusuna yönlendirir. Kurban ile saldırgan arasında DNS çözümleyici aracılığıyla artık bir bağlantı kurulmuştur. Bu tünel, veri hırsızlığı veya başka kötü niyetli amaçlar için kullanılabilir. Saldırgan ile kurban arasında doğrudan bir bağlantı olmadığı için saldırganın bilgisayarının izini sürmek daha zordur.

![tunneling](https://user-images.githubusercontent.com/55113204/116831761-e6897680-abb9-11eb-901f-67b8360059ff.PNG)

## DNS DDoS Saldırıları 
Genel olarak erişilebilen bir domain nameleri manipüle ederek, küçük sorguları kurbanın sunucularını çökertmek için kullanılan çok daha büyük miktarlarda UDP paketleriyle yüklere dönüştürdüğü bir Dağıtılmış Hizmet Reddi ( DDoS ) saldırısıdır. DNS resolverden sahte bir IP adresine bir yanıt elde edilerek gerçekleştirilir. Gönderilen çok sayıda fake sorgu ile aynı anda yanıt veren birkaç DNS Resolver kurbanın ağı çok sayıda DNS yanıtından kolayca etkilenebilir. Saldırgan kimliğini gizlemek için trafik hacmini arttırmak sebebiyle DNS isteklerini bir veya daha fazla botnet aracılığıyla iletir. EDNS0 DNS protokol uzantısı ile DNS mesaj boyutunu artırılarak güçlendirilmek için  DNSSEC ( DNS güvenlik uzantısı) şifreleme özelliği kullanılarak gönderilmektedir . 

![DNS-DDoS-attack-process](https://user-images.githubusercontent.com/55113204/116831777-fe60fa80-abb9-11eb-8350-d2ef6cf0c9b0.png)

## DNS Flood Saldırıları
Saldırganın belirli bir bölgede bir veya birden fazla DNS serverın bölgesinin alt kayıtlarının resolve edilmesini engelleyen bir DDoS saldırı çeşididir. Bu saldırılarla saldırganın amacı, bant genişliği kapasitesini sürekli tüketerek ağı doyurmaktır. DNS flood saldırısı UDP flood saldırısının bir çeşidi olarak kabul edilir. UDP güvenli olmadığından dolayı sahtekarlık daha kolay gerçekleştirilir. Saldırgan, DNS flood bir DNS servera saldırmak için genellikle birden çok serverdan bir komut dosyası çalıştırır. Bu komut dosyaları, sahte IP adreslerinden hatalı biçimlendirilmiş paketler gönderir. DNS flood gibi Katman 7 saldırılarının etkili olması için hiçbir yanıt gerekmediğinden, saldırgan ne doğru ne de yanlış biçimlendirilmiş paketler gönderebilir. Saldırgan, kaynak IP dahil olmak üzere tüm paket bilgilerini yanıltabilir ve saldırının birden çok kaynaktan geliyormuş gibi görünmesini sağlayabilir. Rastgele paket verileri aynı zamanda saldırganın ortak DDoS koruma mekanizmalarından kaçınmasına yardımcı olurken aynı zamanda IP filtrelemeyi (örneğin, Linux IP tablolarını kullanarak) tamamen işe yaramaz hale getirir. DNS flood simetrik DDoS saldırılarıdır. Bir diğer yaygın DNS flood saldırısı türü, DNS NXDOMAIN flood saldırısıdır; burada saldırgan, DNS sunucusunu var olmayan veya geçersiz kayıt talepleriyle doldurur. DNS sunucusu, bu kayıtları arayan tüm kaynaklarını harcar, önbelleği kötü isteklerle dolar ve sonunda meşru isteklere hizmet edecek kaynağı kalmaz.

![dns-flood](https://user-images.githubusercontent.com/55113204/116831768-f43efc00-abb9-11eb-8ac0-878c129af03e.PNG)


## DNSSEC Nedir?
Alan adı sistemi güvenlik uzantıları yani DNSSEC, yetkili bölge verilerini sisteme geldiğinde dijital olarak imzalamak yani kullanıcılara verilerin belirtilen kaynaktan geldiğini ve aktarım sırasında değiştirilmediğini garanti etmeye yardımcı olmak ve ardından hedef yerinde doğrulamak için ortak anahtar şifrelemesini kullanarak internet topluluğunu sahte DNS verilerinden korur. Avantajı DNSSEC'de her bölgenin bir genel / özel anahtar çifti vardır. Bölgenin genel anahtarı DNS kullanılarak yayınlanırken, bölgenin özel anahtarı güvende tutulur ve ideal olarak çevrimdışı saklanır. Üst bölgeden alt bölgeye doğru akan katı bir güven zinciri tarafından yönetilir. DNSSEC ayrıca bir alan adının olmadığını da kanıtlayabilir. Bu işlemin bir sonucu olarak MITM saldırılarından korunmuş olur. Kimlik doğrulama, diğer güvenlik uygulamalarından önce çalışır. DNS verileri için güvenlik sağlayamaması da bir dezavantajıdır. DNSteki veriler topluma açıktır ve hiçbir şifreleme yoktur. Ayrıca DNSSEC, hizmet reddi (denial of service) ve ölü paket (packets of death) gibi DNS sunucusu ataklarını adreslemez.

**¯\\\_(ツ)\_/¯**
