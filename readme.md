# Running K6 load testing on Docker
Visit https://k6.io/ for more information.

## Create a load testing script
```
vi script.js
```
```
import http from 'k6/http';
import { sleep } from 'k6';

export default function() {
  http.get('https://www.radarhack.com');
  sleep(1);
}
```

## Run K6 load tester
```
docker run -i  loadimpact/k6 run \
  --vus 10 \
  --duration 30s \
  --insecure-skip-tls-verify   \
  -<~/k6/script.js
  ```
