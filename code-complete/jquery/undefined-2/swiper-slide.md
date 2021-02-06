---
description: 슬라이딩페이지 숫자표기 +  video control +
---

# swiper slide



```javascript
 
    // 스위퍼 API
    https://www.tutorialdocs.com/tutorial/swiper/api-autoplay.html 
    
    
    var NCswiper = new Swiper('.swiper-container01',{
        pagination:{
             el: '.swiper-pagination01',
             clickable:true // 클릭하면 화면이 넘어가게 할지 선택
        },
        navigation:false,
        autoplay:{ 
            delay:3000 
        },
        loop:true, // 자동 슬라이드 무한 루프
        autoplayDisableOnInteraction:false, // 마우스로 autoplay 정지 막음
        renderBullet: function (index, className) { // 불릿 만들기 
            return '<span class="' + className + '">' + (index + 1) + '</span>';
        },
        on: {
            slideChangeTransitionEnd: function(){ // 현재 페이지 숫자표기
                //alert(this.activeIndex);
                SetPageNumber(this.activeIndex+1);
            },
        },

    });
    function SetPageNumber(nPageNumber){
        document.getElementById("page_number").innerHTML = nPageNumber;
        //출처: https://doolyit.tistory.com/121 [동해둘리의 IT Study]
    }

    
    <div class="swiper-slide" data-swiper-autoplay="2000"> // video 재생시간이 모두 끝난 후 넘기려면 inline으로 값을 던져주면 된다.
```

