bucket 
128mb memory kullanıyor - resident %100


döküman hashlenerek virtual bucket
1 bucket - 1024 virtual bucket

![[Pasted image 20220427092332.png]]



couchbase'de sorgu atabilek için index gerekiyor
primary index: for full scan
secondary: index based on attribute
- composite: birden fazla attribute indexi
- partial: bir attribute'u belli bir değerle olanını indexle
- covering: indcexteki alanlar selectteki alanlar kapsıyorsa


![[Pasted image 20220427093636.png]]




cluster has nodes
node types:
coordinated
master
data 


shard veriyi böler
bölünen verilerin replikaları mevcut

segmentler en küçük yapıtaşı ve immutable

partial update yapılamaz. cunku locking mekanizması yok.
update: yeni döküman yaratılıyor, eski döküman deleted olarak işaretleniyor



uygulama üzerinden
db'ye yazılan kaydın elastic'e yazılması - couchbase elasticsearch connector
elasticsearch 1.db olarak kullanılamaz.
index değişeceği zaman update

cbes: java uygulaması

DCP: Her işlemi loglar. couchbase'de her işlemin logu dinlenebiliyor. vbucket'lara yazılıyor.
cbes, DCP'yi dinliyor.

logstash checkpoint takip edemiyor, couchbase plugini yok. bu yüzden cbes kullanılıyor.
elastic'te her an reindex yapılması gerekebilir.

elasticsearch'te aynı 2 ürün nasıl karşılaştırılıyor?





outbox pattern
![[Pasted image 20220427170946.png]]

connector read operasyonu yapmıyor.
diğer türlü outbox tablosuna select sorgusu atılıp update gerekiyordu.