[[why-kotlin]]
[[nullable]]
[[extension-functions]]
[[resources]]
[[functions]]

```
????
expect fun measureTime(action: () -> Unit): Duration
actual fun measureTime(action: () -> Unit): Duration{

}
```
open class Base 
open yazmazsan final olarak sayar ve inherit edemezsin.

data class Employee

object MyCompany{
	const val name: String = "MyCompany" // singleton
}

String, Instant

fun Instant.toPromotionApiFormat(): LocalDateTime {
}

mutableListOf
listOf dediğimizde add yapamıyoruz.
val çünkü değeri bir kere oluşur.
class UserController(private val userService : UserService)



CQRS Pattern
.net core mediator

Yazma ve okuma işlemlerini ayırmaya yönelik
W/R ayrılması eventually consistency olarak çalışıyor.

- W/R ayrılması gerekebilir

- Pesimist lock koymanız gerekebilir

- Read tarafını scale etmek istiyorsanız - Write 1 : Read 1000
Index eklerseniz write tarafındaki response yükselir.


Event Sourcing

Command: Sonuç döndürmez

suspend fun? - suspend nonblocking yapıyor
