---
description: getUrlParams()
---

# 파라미터 값 가져오기 location.search.replace

```javascript
function getUrlParams() {
    var params = {};
    window.location.search.replace(/[?&]+([^=&]+)=([^&]*)/gi, function(str, key, value) { params[key] = value; });
    return params;
}
```

