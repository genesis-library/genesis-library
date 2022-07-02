Transactional consistency boundary
Her aggregate root bir tane repositoryle konuşur
Aggregateler farklı transactionlarda olmalı atomik olmalı
Aggregate Type 1: Charge
Aggregate Type 2: Refund

Aggregate design rules
1 - Protect 
2 - Design small aggregates
3 - Reference other aggregates by identity only
4 - Update other aggregates using eventual consistency

Anemic Model
Sadece get ve setlerden oluşan model dışarı veri sızdırıyordur.
1.adım atlanmış. Başka katmana leak etmiş olabilir.
Entity lack the behaviour, only for CRUD

Rich Model


Repository pattern
Aggregate tabanlıdır

Domain Service
Stateless
Highly cohesive
May interact with other domain services

infrastructure
database, notification, email, sms, external apis

domain
- service
- model

infrastructure
- port
- adapter





Bir couchdb dökümanı = aggregate
Business'ı kendi başına doğrulayabilecek bir döküman
Contentler tek bir obje içinde olmalı ki bir operasyonla doğrulayabilelim.

Optimistic concurrency control
Bir aggregate i aynı anda bir kişi değiştirebilir.
nosql'de döküman versiyonu var. versiyon arttırarak atomik değişiklik garantiliyoruz.

Aggregate'ler olabildiğince küçük tasarlanmalı.
Küçülttükçe domain doğruluğu azalır, yöntemler karmaşıklaşır (ödünleşme)
Aggregate içerisindeki bir birime çok erişim yapılıyor olabilir, yeniden planlama gerekebilir.

Implementing domain driven design


Aggregate root, aggregate boundary
![[Pasted image 20220426112411.png]]



Customer bu context'in bir parçası değil, başka bir contextin ana objesi olabilir.
![[Pasted image 20220426113001.png]]




Böyle yazıldığı zaman okunduğunda selectedPos gerekmiyor diye düşünebiliriz (yanlış).
Constructor içinde verilmeli ya da factory pattern.
![[Pasted image 20220426113216.png]]



Aggregate in büyüklüğü içindeki datanın büyüklüğüne ve conflict şansına bağlı

JPA sorunu id yerine obje almak
Sadece technical design ile bile TDD biraz yapılabilir.

business tarafında her şey açık açık yazılmalı.
business dilinden uzak oluyorsa sorun vardır.
duplicate etmekten kaçınma.

Implementing Domain Driven Design book

value objectin life cycleı yok.

