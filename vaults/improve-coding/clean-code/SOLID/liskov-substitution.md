- design by contact

if S is subtype of T, T objects may be replaced with S objects.

Sometimes it doesn't fit like natural language "square is a rectangle"
not a "is a" relationship for programming

```
// bad example, Ostrich cannot fly
public class Bird{
    public void fly(){}
}
public class Duck extends Bird{}
public class Ostrich extends Bird{}
```

```
public class Bird{}
public class FlyingBirds extends Bird{
    public void fly(){}
}
public class Duck extends FlyingBirds{}
public class Ostrich extends Bird{} 
```

- Alt tipler ön şartları güçlendiremez. Kısıtlama getiremez.

- Rectangle - Square örneği
Square, Rectangle'dan daha kısıtlıdır. 2 ayrıtının eşit olması kuralı vardır.

LSP'ye göre Rectangle kullanan kişi Square'ı da aynı şekilde kullanabilmelidir.
Fakat aşağıdaki örneğe bakıldığında öyle olamadığı ortaya çıkıyor.

```
class Rectangle{
	setShortLength(int shortLength){this.shortLength = shortLength}
	setShortLength(int longLength){this.longLength = longLength}
}

class Square extends Rectangle{
	@Override
	setShortLength(int newShortLength){
		shortLength = newShortLength
		longLength = newShortLength
	}
}

main(){
	Rectangle rectangle = new Rectangle()
	rectangle.setShortLength(5)
	rectangle.setLongLength(10)
	rectangle.area(10) // will give us 50 as expected.

	Square square = new Rectangle()
	square.setShortLength(5)
	square.setLongLength(10)
	square.area(10) // will give us 100 since square has a constraint.
}
```


- Kodun kötü olduğu nasıl anlaşılır?
Yukarıdaki kodda main() içerisinde mecburen **instance of** kullanmak zorundayız.
Rectangle için kullandığımız kod square için çalışmaz. Bu durum hatalı, polymorphism'e uygun değil.

