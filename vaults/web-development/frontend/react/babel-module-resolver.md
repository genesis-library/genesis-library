FINAL RESULT

```
// old way to import
import { CheckIcon } from '../components/icons'
import CancelIcon from '../components/icons/CancelIcon'

// new way to import
import { CheckIcon } from '@icons'
import CancelIcon from '@icons/CancelIcon'
```

----- 


```
npm install babel-plugin-module-resolver --save-dev
```

.babelrc:
```
{
  ...
  "plugins": [
  
    [
      "module-resolver",
      {
        "alias": {
          "@icons": "./src/components/icons"
        }
      }
    ]
  ],
  ...
}
```





## BABEL MODULE RESOLVER WITH ESLINT
.eslintrc
```
{
  ...
  "extends": [
    "plugin:import/errors",
    "plugin:import/warnings"

  ],
  "settings": {
    "import/resolver": {
      "babel-module": {}
    }
  },
  ...
}
```


tsconfig.json
```
{
  "compilerOptions": {
    ...
    "baseUrl": ".",
    "paths": {
      "@components/*": ["./src/components/*"],
      "@constants/*": ["./src/constants/*"]
    }
  },
  ...
}
```