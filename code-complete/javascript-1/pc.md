---
description: isMobile()
---

# 모바일,PC 구분 접속 체크

```javascript
function isMobile(){
    var UserAgent = navigator.userAgent;
    if (UserAgent.match(/iPhone|iPod|Android|Windows CE|BlackBerry|Symbian|Windows Phone|webOS|Opera Mini|Opera Mobi|POLARIS|IEMobile|lgtelecom|nokia|SonyEricsson/i) != null || UserAgent.match(/LG|SAMSUNG|Samsung/) != null)
{
        return true;
    }else{
        return false;
    }
}
if(isMobile()){
    location.href = "/mobile/index.html";   //모바일페이지
}else{
    location.href = "/main.html";       //PC용 페이지
}
```

