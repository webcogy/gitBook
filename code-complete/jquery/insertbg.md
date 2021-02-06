---
description: "갤러리등\_이미지를\_부모의\_BG로\_깔아버리고\_안\_보이게\_하기"
---

# insertBg\(\)

```javascript
function insertBg(){
    /** -------------------------------------------
    *   갤러리등 이미지를 부모의 BG로 깔아버리고 안 보이게 하기
    *   @example 부모에 .insertBg 추가 (여기에 data-ratioH 비율 맞춰 사용), .img에 background-image 깔리고 자식 img 숨김
    --------------------------------------------*/
    if($(".insertBg").length > 0 ){
        $(".insertBg img").css({display:"none"});//실제 img는 안보이게 처리
        $(".insertBg .img").each(function(){//이미지를 배경으로 집어 넣기
            //$(this).css({backgroundImage:"url('"+$(this).find("img").attr("src")+"')"});
            //위 방식에서 아래 방식으로 변경함. 프린트 상황에서 배경이미지가 노출되는 문제 해결했음.
            $(this).attr('style','background-image:url("'+$(this).find('img').attr('src')+'") !important');
        });
        $(".insertBg").each(function(idx){//한 페이지에 다수의 insertBg가 있을 수 있으므로 개별적으로 처리함.
            if($(this).attr("data-ratioH")){
                $(window).resize(function(){ //리사이즈에 대응
                    setTimeout(set,100);
                });
                function set(){
                    var ratio = $(".insertBg:eq("+idx+")").attr("data-ratioH");//세로비율 찾고
                    var imgW = $(".insertBg:eq("+idx+") .img:first").width();
                    $(".insertBg:eq("+idx+") .img").css({height:parseInt(imgW*(ratio/100))+"px"});
                }
            }
        });
        $(".insertBg .img").css({//모든 img클래스에 동일한 스타일
            display:"block",overflow:"hidden",
            backgroundRepeat:"no-repeat",backgroundPosition:"center",backgroundSize:"cover"
        });

        //목록 이미지 업로드 하지 않았을때 적용
        $(".insertBg .img").each(function(idx){ //목록이미지 없으면
            if(0<$(".insertBg .img:eq("+idx+") img.nonImg").length){
                $(".insertBg .img:eq("+idx+")").css({//모든 img클래스에 동일한 스타일
                    display:"block",overflow:"hidden",
                    backgroundRepeat:"no-repeat",backgroundPosition:"center"
                });
            }else{
                $(".insertBg .img:eq("+idx+")").css({ //모든 img클래스에 동일한 스타일
                    display:"block",overflow:"hidden",
                    backgroundRepeat:"no-repeat",backgroundPosition:"center",backgroundSize:"cover"
                });
            }
        });
    };
}
```

