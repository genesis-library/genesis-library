entity and value types

Identifier equality
Reference equality
Structural equality

Entity
kendi başına var olabilir.
fieldları değişebilir, değişmeli
public setterlar olmadan davranış üzerinden değişmeli.
entity ismi değişiyorsa setName() degil changeName() gibi

Value Objects
Idleri yok
Kendi başlarına hayatta kalamazlar
Eşitlik için bütün fieldları kontrol edilmeli.
Interchangeable
entity e bağlı olmalı
değeri değişmeyeceği için validasyon başta yapılır.
Side effect yok çünkü mutation yok.


benefits of value object
- ör email için value object yerine string değer tutabilirdik
- fakat stringin validasyonunu ayrı ayrı her yerde yapmak gerekiyor.
- primitive obsession olur.
- emailin tipini biliyoruz artık
- constraint koymak istediğimizde tek bir yerde yapabiliyoruz.
- Hashing (hash kodları eşitse eşitler)

id - reference : entity object
reference - structure equality : value object






- id int yerine guid
id generate ettirdiğimiz zaman oradaki mimariye dependent olmuş oluyor.
çünkü dbye kaydettiğimiz zaman db yapar ve bize id döner
IDOR atak

- guid yerine string
<hizmetTipi>-<lineId> concurrency sağlar.

Anemic Model encapsulation'a uymaz.
Anemic Model ile test etmek de zorlaşır ve sızıntılar olur.





















