![[Pasted image 20220305085305.png]]

https://medium.com/cloud-and-servers/cap-teoremi-nedir-8673e71c10fc

Consistency: Dağıtık sistemde sunucu farketmeksizin aynı cevabı alabilmek.
Availability: Her zaman erişebilmek.
Partition Tolerance: Bazı sunucuların bağlantısı gitse de hala çalışabilme.

CA: 

CP: Bir bölünme olduğu zaman tutarsız olmayan düğüm erişilmez hale getirilir böylece A'dan vazgeçilir. 

AP: Her zaman available olan bir sistemde iletişimde kopukluk olduğu zaman C elbette sağlanamaz.



CouchDB, trendyolda her zaman aynı şeyi görmeyebiliriz. UDP'ye benzer. 1-2 şeyin o anlık farklı olması sorun çıkarmaz. Eventual consistency

(CP) MongoDB: strict consistency
Write operasyonları master node'a gider. Buradaki değişiklikler secondary nodelara aktarılır.
Primary node fail ederse secondarylerden biri primary olur böylece Partition Tolerance sağlanmış olur.
O zaman A'nın olmama nedeni sadece tek bir yere yazmanın verdiği tıkanıklık mı?

CouchDB: master-master, master-slave



Bankacılık örneği:
CP: ATM'ler arasında bağlantı problemi olduğunda hiçbir işleme izin vermemeli.

VEYA

Deposit: Yes
