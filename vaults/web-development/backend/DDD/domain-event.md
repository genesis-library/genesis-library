Yapılan işi özetleyen payload
Fat event modeli

olabildiğince az api call yapılmalı.

kaybolan eventler?

at-most once:
at-least once: ack supportları verenler var. kafka, rabbitmq
exactly once: aşırı kompleksite katıyor

at-least once kullanılacaksa idempotency desteklenmesi gerekiyor.
downstream idemponent davranmalı. (downstream ne?)
- versiyon kontrolü 
- outbox pattern - outbox performansı için ne kullanılıyor kaçırdım... rebesium? loglara bakıyor, kowl
- event sourcing - eksileri var. eventleri yıllarca saklamak gerekiyor. çok yük getiriyor.


saga pattern
routing slip pattern
orchestration vs choreography



![[Pasted image 20220426140344.png]]



charge implementasyonu değişebilir.
![[Pasted image 20220426141416.png]]