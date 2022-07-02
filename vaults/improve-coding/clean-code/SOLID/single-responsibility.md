Bir ekleme yapmak istediğimizde bir classı modify etmemiz gerekmemeli. Örneğin logging ve repository ayrı olmalı.

take interfaces as constructor arguments
DI: relying on abstractions over concrete classes.
use dependency injection which allows you to use interfaces?
testing gets easier

```
public class GetUsersCommand(){
	private readonly AppDatabase appDatabase;
	public GetUsersCommand(){
		appDatabase = new AppDatabase();
	}
	public User[] Execute() => appDatabase.Users.ToArray();
}
```

```
public class GetUsersCommand(){
	private readonly IAppDatabase appDatabase;
	public GetUsersCommand(IAppDatabase database){
		appDatabase = database
	}
	public User[] Execute() => appDatabase.Users.ToArray();
}
```