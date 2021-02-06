# 평점 별반개도 표시 \(보여줄 경우\)

```javascript
<div class="grade-box result" data-grade="2.5">
     <i class="i_star"></i>
     <i class="i_star"></i>
     <i class="i_star"></i>
     <i class="i_star"></i>
     <i class="i_star"></i>
			<strong>3.5</strong>
</div>
```

```javascript
$('.grade-box.result').each(function(i){
            _grade = $(this).attr('data-grade');

            if( _grade.length == 3 ){ // 소수점
                var _int = _grade.substr(0,1);
                var _decimal = _grade.substr(2,1);

                //정수 별점 넣기
                $(this).find('.i_star').css({background:'url(./img/common/ico_grade_lg_off.png) 50% /20px no-repeat'});
                $(this).find('.i_star:lt('+_int+')').css({background:'url(./img/common/ico_grade_lg_on.png) 50% /20px no-repeat'});
                
                if( _decimal > '4' ){
                    $(this).find('.i_star:eq('+_int+')').css({background:'url(./img/common/ico_grade_off_half.png) 50% /20px no-repeat'});
                }else{
                    $(this).find('.i_star:eq('+_int+')').css({background:'url(./img/common/ico_grade_lg_off.png) 50% /20px no-repeat'});
                }
            }else if( _grade.length == 1 ){ // 정수
                //정수 별점 넣기
                $(this).find('.i_star').css({background:'url(./img/common/ico_grade_lg_off.png) 50% /20px no-repeat'});
                $(this).find('.i_star:lt('+_grade+')').css({background:'url(./img/common/ico_grade_lg_on.png) 50% /20px no-repeat'});
            }

            console.log(_grade.substr(0,1), _grade.substr(2,1));

            if( $(this).find('strong').length ){
                $(this).find('strong').text(_grade);
            }
        });
```

