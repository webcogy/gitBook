---
description: numberWithCommas()
---

# 숫자 3자리 콤마 찍기 toString\(\).replace

```javascript
function numberWithCommas(x) {
	return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
}
```

