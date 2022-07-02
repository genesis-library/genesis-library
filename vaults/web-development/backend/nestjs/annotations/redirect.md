@Redirect('/swagger', HttpStatus.MOVED_PERMANENTLY)

corsOptions'ı almak için this.application.get<CorsConfig>(CorsConfig) yapıyor.

CorsConfig bir class, fakat implementasyonu yok sadece fieldları var
```
export class CorsConfig {  
  public origin: string | string[];  
  public allowedHeaders: string;  
}
```

ConfigurationModule içerisinde:







------ 
Happens when application bootstrapping
Dependencies can have dependencies too, bottom up. No need to care
Dependency Injection
- Constructor based

@Injectable() decorator marks service as a provider.
// declares class as a class that can be managed by the Nest IoC container.
// Controller declares a dependency on service token with constructor injection.
// on module file, registering the token service with service class.

- When Nest IoC container instantiates controller, it looks for dependencies (like in constructor)
- Finds service as a dependency, performs a lookup on this service token
- Returns service class 
- Nest will create an instance of service and cache it or use it from cache.



Custom providers
You want to create a custom instance instead of having Nest instantiate a class.
- reuse an existing class in a second dependency
- 