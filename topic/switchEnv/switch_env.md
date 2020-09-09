## apiKey




### config.js
```js
import "define_env.js"

const accessKey = {
  "dev": "{
          }",
  "prod": "{
           }"
};

const config = "accessKey." + env
```

### define_env.js
```js
const env = "dev";

```

### .gitlab-ci.yml
```yaml
job:
  script:
    - sed -i -e "s/'env = \"dev\"'/'env = \"prod\"'/" define_env.js

```


