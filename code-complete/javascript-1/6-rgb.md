---
description: hexToRgb()
---

# 컬러 6자리→RGB로 바꾸기

```javascript
var pointColor = hexToRgb("#E91E63"); /*메인 포인트 컬러*/
var subColor = hexToRgb("#4DA1FF");  /*서브 포인트 컬러*/

$(".menu_link a.on").css('background-color','rgb('+pointColor+')');


			function hexToRgb(hex) {
          // Expand shorthand form (e.g. "03F") to full form (e.g. "0033FF")
          var shorthandRegex = /^#?([a-f\d])([a-f\d])([a-f\d])$/i;
          hex = hex.replace(shorthandRegex, function(m, r, g, b) {
              return r + r + g + g + b + b;
          });

          var result = /^#?([a-f\d]{2})([a-f\d]{2})([a-f\d]{2})$/i.exec(hex);
          return result ? parseInt(result[1], 16)+','+parseInt(result[2], 16)+','+parseInt(result[3], 16) : null;
      }
```

