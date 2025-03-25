Use webwoker like a regular function

example:
  ```ts
  import {easyWebworker} from "easy-webworker"
const { onError, onMessage, postMessage, terminate, worker } = easyWebworker()
onMessage(data => {
  console.log("result is ...", data)
})

function ComplexCalculations(outCount: number, innerCount: number) {
  let result = 0
  for (let i = 0; i < outCount; i++) {
    for (let j = 0; j < innerCount; j++) {
      result += i + j
    }
  }
  return result
}

postMessage(ComplexCalculations, 100000, 100000)
  
```
