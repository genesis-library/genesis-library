```typescript
import { Controller, Get } from '@nestjs/common';

@Controller('cats')
export class CatsController {
	@Get()
	findAll(@Res({ passthrough: true }) res: Response) {
	  res.status(HttpStatus.OK);
	  return [];
	}
}
```

@Res and @Response are the same.
If you inject it, you must return a json or http server will hang

`@Get()`, `@Post()`, `@Put()`, `@Delete()`, `@Patch()`, `@Options()`, and `@Head()`. 
In addition, `@All()` defines an endpoint that handles all of them.


- Alter HTTP Codes
If your status code isn't static, you must inject using @Res
```typescript
Import `HttpCode` from the `@nestjs/common`
@Post()
@HttpCode(204)
create() {
  return 'This action adds a new cat';
}
```


- Alter Headers
@Header or res.header()
```typescript
@Header('Cache-Control', 'none')
```

- Redirection
```typescript
@Get('docs')
@Redirect('https://docs.nestjs.com', 302)
getDocs(@Query('version') version) {
  if (version && version === '5') {
    return { url: 'https://docs.nestjs.com/v5/' };
  }
}

// https://docs.nestjs.com/v5/ overrides https://docs.nestjs.com/
```



- Route Parameters
```typescript
@Get(':id')
findOne(@Param() params): string {
  console.log(params.id);
  return `This action returns a #${params.id} cat`;
}
```

findOne(@Param('id') id: string):


- Request Payloads
DTO's schema can be determined by interface or class.
Class is preferred because its part of js ES6 standart.
Classes are preserved as real entities in the compiles JS.
TS interfaces removed during the transpilation, Nest can't refer to them at runtime.
This is important because features such as **Pipes** enable additional possibilities when they have access to the metatype of the variable at runtime.

Nestjs has ValidationPipe and in the example below, name, age and breed are whitelisted properties.

```typescript
export class CreateCatDto {
  name: string;
  age: number;
  breed: string;
}


@Post()
async create(@Body() createCatDto: CreateCatDto) {
  return 'This action adds a new cat';
}
```