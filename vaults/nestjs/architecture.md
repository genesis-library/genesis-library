layered vs hexagonal

0 533 655 6166

distributed yapılarda gecikmeler var (latency)
bandwith is not infinite
network is not reliable

fiziksel layer: tier

3 tier: client, middle, database

4 layer:
presentation
business
persistence
database

antipattern: business ve persistence'ın iç içe geçmesi.
presentation ile business'ın iç içe geçmesi.

model: business
view: presentation

layerlar kendi içlerinde kohezyonu yüksek.
layerların arayüzünde facade'lar vardır.

bütün layerlar close olmalıdır.
Close: kısa devreye izin vermemek, presentation layerı persistence'a atlayamaz.

fast lane reader pattern
çok kişi olanlar hızlı gidebilir.

Örnek: %80 inde CRUD kalanında business logicleri varsa fast lane e izin verilmeli closed olmamalı.

EĞER
- scale etmek için 3 tane makine kurulabilir fakat ya business katmanı daha fazla yük alıyorsa? o halde layer yerine tier olmalıydı.
- bazı businesslar daha fazla yük alıyor olabilir, burada işe microservice'ler giriyor.

SOA: Büyük şirketler küçük şirketleri alabilir, aralarında orkestrasyon kurmak gerekebilir. o zaman SOA olur. Service bus gerekli. Aralarında bağımlılık var. XML

4+1 deployment view
logical
implementation
process
deployment
and scenarios