## apiKey


### config.js
```js
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

### indes.html
```html
<script src="define_env.js"></script>
<script src="config.js"></script>


```


