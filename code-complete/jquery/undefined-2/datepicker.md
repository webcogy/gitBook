---
description: 기본 / 옵션 사용법 + input 2개로 시작 - 종료일 설정 + 오늘 날짜 선택하기
---

# datepicker

{% code title="기본 / 옵션 사용법" %}
```javascript
$(function(){
    $.datepicker.regional['ko'] = {
        closeText: '창닫기',
        prevText: '이전달',
        nextText: '다음달',
        currentText: '오늘선택',
        monthNames: ['1월(JAN)','2월(FEB)','3월(MAR)','4월(APR)','5월(MAY)','6월(JUN)',
        '7월(JUL)','8월(AUG)','9월(SEP)','10월(OCT)','11월(NOV)','12월(DEC)'],
        monthNamesShort: ['1월','2월','3월','4월','5월','6월',
        '7월','8월','9월','10월','11월','12월'],
        dayNames: ['일','월','화','수','목','금','토'],
        dayNamesShort: ['일','월','화','수','목','금','토'],
        dayNamesMin: ['일','월','화','수','목','금','토'],
        weekHeader: 'Wk',
        dateFormat: 'yy-mm-dd',
        firstDay: 0,
        isRTL: false,
        showMonthAfterYear: true,
        yearSuffix: '',
        showOtherMonths: true,
        
        //changeMonth: true, // 타이틀 month를 selectBox로 바꾸기
        //changeYear: true, // 타이틀 year를 selectBox로 바꾸기
        //inline: true, // 달력이 화면의 한영역을 잡고 즉시 표시
        //showOn: 'both', // 인라인이 아닐경우, 인풋과 이미지 둘다 표시
    };
    $.datepicker.setDefaults($.datepicker.regional['ko']);



    $('.calendar').datepicker({
        inline:true,
        monthNames: ['. 1','. 2','. 3','. 4','. 5','. 6',
        '. 7','. 8','. 9','. 10','. 11','. 12'],
        monthNamesShort: ['1월','2월','3월','4월','5월','6월',
        '7월','8월','9월','10월','11월','12월'],
    });
});




/* 블로그내용 ↓ */

//altField 
$( ".selector" ).datepicker({
    altField: ".selecter"
}); //선택한 날짜가 해당 폼에 입력된다. 

//altFormat 
$( ".selector" ).datepicker({
    altFormat: "yyyy-mm-dd"
}); 
//altField의 폼에 입력될 날짜의 형식 


//beforeShow 
$( ".selector" ).datepicker({
    beforeShow: function(input, inst) {
        // input은 폼
        // inst는 datepicker의 여러 값이 있던데
        //          아직 쓸모를 찾지 못했다.
    }
}); 
//달력이 그려지기 전에 처리할 일들을 지정할 수 있다. 


//buttonImage 
$( ".selector" ).datepicker({
    buttonImage: "/images/datepicker.gif"
}); 　 

//buttonImageOnly 
$( ".selector" ).datepicker({
    buttonImageOnly: true
}); 　
 
//buttonText 
$( ".selector" ).datepicker({
    buttonText: "선택"
}); 　 

//changeMonth 
$( ".selector" ).datepicker({
    changeMonth: true
}); //셀렉트박스로 월 변경 여부 


//changeYear 
$( ".selector" ).datepicker({
    changeYear: true
}); //셀렉트박스로 연도 변경 여부 


//closeText
$( ".selector" ).datepicker({
    closeText: "닫기"
});


//constrainInput 
$( ".selector" ).datepicker({
    constrainInput: false
}); //형식외 텍스트 입력제한. 디폴트 true 


//currentText
$( ".selector" ).datepicker({
    currentText: "Now" 

});

//dateFormat 
$( ".selector" ).datepicker({
    dateFormat: "yy-mm-dd"
}); 　 

//dayNames 
$( ".selector" ).datepicker({
    dayNames:
        [ "일요일", "월요일", "화요일", "수요일",
        "목요일", "금요일", "토요일" ]
}); 　 

//dayNamesMin 
$( ".selector" ).datepicker({
dayNamesShort:
        [ "S", "M", "T", "W", "T", "F", "Sa" ]
}); 　 

//dayNamesShort 
$( ".selector" ).datepicker({
    dayNamesShort:
        [ "일", "월", "화", "수", "목", "금", "토" ]
}); 　 

//defaultDate 
$( ".selector" ).datepicker({
    defaultDate: +7
}); //달력 기본 출력될때 기준일. Date타입, 숫자, String 다 가능하다. 

//duration 
$( ".selector" ).datepicker({
    duration: "slow"
}); //달력 나타나는 속도, "slow", "normal", "fast" firstDay 


$( ".selector" ).datepicker({
    firstDay: 1
}); //주의 시작일을 일요일로 하려면 0, 월요일은 1 gotoCurrent 


$( ".selector" ).datepicker({
    gotoCurrent: true
}); 　 

//maxDate 
$( ".selector" ).datepicker({
    maxDate: "+1m +1w"
}); 　 

//minDate 
$( ".selector" ).datepicker({
    minDate: new Date(2012, 1 - 1, 1)
}); 　 

//monthNames 
$( ".selector" ).datepicker({
    monthNames:
        [ "1월", "2월", "3월", "4월", "5월", "6월", "7월", "8월", "9월", "10월", "11월", "12월" ]
}); 　 


//monthNamesShort 
$( ".selector" ).datepicker({
    monthNamesShort:
        [ "Jan", "Feb", "Mar", "Apr", "Maj", "Jun",
        "Jul", "Aug", "Sep", "Okt", "Nov", "Dec" ]
}); 　 

//nextText 
$( ".selector" ).datepicker({
    nextText: "차월"
}); 　 

//numberOfMonths 
$( ".selector" ).datepicker({
    numberOfMonths: [ 2, 3 ]
}); //여러개월 달력을 표시 onChangeMonthYear 



$( ".selector" ).datepicker({
    onChangeMonthYear: function(year, month, inst) {
        // year 년도 숫자
        // month 월 숫자
        // inst는 datepicker의 여러 값이 있던데
        //          아직 쓸모를 찾지 못했다.
    }
}); //달력에서 연월을 셀렉트 박스로 바꿀 수 있을때 바꿀때 이벤트 



//onClose 
$( ".selector" ).datepicker({
    onClose: function(dateText, inst) {
        // dateText는 날짜 스트링
        // inst는 datepicker의 여러 값이 있던데
        //          아직 쓸모를 찾지 못했다.
    }
}); 　 


//onSelect 
$( ".selector" ).datepicker({
    onSelect: function(dateText, inst) {
        // dateText는 날짜 스트링
        // inst는 datepicker의 여러 값이 있던데
        //          아직 쓸모를 찾지 못했다.
    }
}); 　 


//prevText 
$( ".selector" ).datepicker({
    prevText: "전월"
}); 　 

//selectOtherMonths 
$( ".selector" ).datepicker({
    selectOtherMonths: true
}); //다른 달도 출력시 선택가능 여부. 디폴트는 false showAnim 


$( ".selector" ).datepicker({
    showAnim: "fold"
}); //달력 에니메이션 효과. show(디폴트), slideDown, fadeIn etc.. 


//showCurrentAtPos 
$( ".selector" ).datepicker({
    showCurrentAtPos: 3
}); //여러 달의 달력을 한꺼번에 띄울 경우 시작월을 현재를 기준으로 달 수. 0이 현재월. -5면 5개월 전, 3이면 3개월 후 

//showOptions 
$( ".selector" ).datepicker({
    showOptions: { direction: "up" }
}); //달력 보여줄때 이벤트 옵션 

//showOtherMonths 
$( ".selector" ).datepicker({
    showOtherMonths: true
}); //월 1일 이전, 월 말일 이후 빈칸에 이전달, 다음달 날짜 출력 여부 

//showWeek 
$( ".selector" ).datepicker({
    showWeek: true
}); //주수 출력 여부 

//stepMonths 
$( ".selector" ).datepicker({
    stepMonths: 3
}); //달력에서 좌우 선택시 이동할 개월 수 

//weekHeader 
$( ".selector" ).datepicker({
    weekHeader: "주"
}); 　 

//yearRange 
$( ".selector" ).datepicker({
    yearRange: "2010:2013"
}); //연도 범위 

//yearSuffix
$( ".selector" ).datepicker({
    yearSuffix: "년"
}); 　

//출처: https://harui.tistory.com/75  []
```
{% endcode %}



{% code title="input 2개로 시작 ~ 종료일 설정" %}
```javascript
<script type="text/javascript">
$(document).ready(function () {
$.datepicker.setDefaults($.datepicker.regional['ko']);
$( "#startDate" ).datepicker({
changeMonth: true,
changeYear: true,
nextText: '다음 달',
prevText: '이전 달',
dayNames: ['일요일', '월요일', '화요일', '수요일', '목요일', '금요일', '토요일'],
dayNamesMin: ['일', '월', '화', '수', '목', '금', '토'],
monthNamesShort: ['1월','2월','3월','4월','5월','6월','7월','8월','9월','10월','11월','12월'],
monthNames: ['1월','2월','3월','4월','5월','6월','7월','8월','9월','10월','11월','12월'],
dateFormat: "yymmdd",
maxDate: 0, // 선택할수있는 최소날짜, ( 0 : 오늘 이후 날짜 선택 불가)
onClose: function( selectedDate ) {
//시작일(startDate) datepicker가 닫힐때
//종료일(endDate)의 선택할수있는 최소 날짜(minDate)를 선택한 시작일로 지정
$("#endDate").datepicker( "option", "minDate", selectedDate );
}
});
$( "#endDate" ).datepicker({
changeMonth: true,
changeYear: true,
nextText: '다음 달',
prevText: '이전 달',
dayNames: ['일요일', '월요일', '화요일', '수요일', '목요일', '금요일', '토요일'],
dayNamesMin: ['일', '월', '화', '수', '목', '금', '토'],
monthNamesShort: ['1월','2월','3월','4월','5월','6월','7월','8월','9월','10월','11월','12월'],
monthNames: ['1월','2월','3월','4월','5월','6월','7월','8월','9월','10월','11월','12월'],
dateFormat: "yymmdd",
maxDate: 0, // 선택할수있는 최대날짜, ( 0 : 오늘 이후 날짜 선택 불가)
onClose: function( selectedDate ) {
// 종료일(endDate) datepicker가 닫힐때
// 시작일(startDate)의 선택할수있는 최대 날짜(maxDate)를 선택한 시작일로 지정
$("#startDate").datepicker( "option", "maxDate", selectedDate );
}
});
});
</script>
```
{% endcode %}



{% code title="오늘 날짜 선택하기" %}
```javascript
    $('.btn_today').click(function(){
        $(".calendar").datepicker().datepicker("setDate", new Date()); // 오늘날짜선택
        var currentDay = $(".calendar").find('.ui-state-active').text();
        var currentMonth = $(".calendar").find('.ui-datepicker-month').text();
            currentMonth = currentMonth.substring(currentMonth.length-1, currentMonth.length);

        dateText = currentMonth + "월 " + currentDay + "일로 제조 요청하기";
        $('.get_cal').addClass('on').val(dateText);
    });
```
{% endcode %}

