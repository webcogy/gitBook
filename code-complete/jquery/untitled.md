# 위치고정 fixPos\(\)

```javascript
function fixPos(){
    if($(".fix").length){
        $(window).scroll(function(){
            var fixTop = $(".fix").attr("data-top");
            var scTop = $(window).scrollTop();
            if (scTop >= fixTop) $(".fix").addClass("fixOn");
            else $(".fix").removeClass("fixOn");
        });
    }
};
```

