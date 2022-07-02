S: Bir ekleme yapmak istediğimizde bir classı modify etmemiz gerekmemeli. Örneğin logging ve repository ayrı olmalı.
O: Allow extensions, not modifications. Çiğnendiği yerlerde genelde alt alta if'ler olur. Factory class ile polymorphism yapabiliriz. Ya da fonksiyon tutan hashmap kullanılabilir.
L:
I: 
D: kohezyon sağlar, araya soyut bir katmak ekleyerek sınıfın bağımlılığını kaldırıyoruz.


https://gokhana.medium.com/solid-nedir-solid-yaz%C4%B1l%C4%B1m-prensipleri-nelerdir-40fb9450408e



## “The number of classes explodes with every refactor your make!”

This might be one objection you have to my refactoring approach.

Remember refactoring is not about minimizing code or even necessarily about making things “simpler”. It’s about changing your code to match your application’s complexity and making your code easier to work with.

Simple != easy.