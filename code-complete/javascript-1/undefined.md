# 폼체크 - 다중 라디오 버튼 체크

```javascript

function radio_chkAll(){
    var popup = $(".popup_toast.fixedBottom").eq(0);
    var popupText = $(".popup_toast.fixedBottom p").eq(0);
    
    var typeChk1 = false;
    var typeChk2 = false;
    var typeChk3 = false;
    var typeChk4 = false;
    
    // type1 체크
    for( var i=0; i<3; i++ ){
        if( $('.orderType1').eq(i).prop('checked') ){
            typeChk1 = true;
        }else{
            popupText.text('모발타입을 선택해주세요.');
        }
        
    }
    if( typeChk1 == false ) return false;
    
    // type2 체크
    for( var i=0; i<3; i++ ){
        if( $('.orderType2').eq(i).prop('checked') ){
            typeChk2 = true;
        }else{
            popupText.text('모발굵기를 선택해주세요.');
        }
    }
    if( typeChk2 == false ) return false;
    
    // type3 체크
    for( var i=0; i<3; i++ ){
        if( $('.orderType3').eq(i).prop('checked') ){
            typeChk3 = true;
        }else{
            popupText.text('모발손상정도를 선택해주세요.');
        }
    }
    if( typeChk3 == false ) return false;
    
    // type4 체크
    for( var i=0; i<3; i++ ){
        if( $('.orderType4').eq(i).prop('checked') ){
            typeChk4 = true;
        }else{
            popupText.text('두피타입을 선택해주세요.');
        }
    }
    if( typeChk4 == false ) return false;
    
    
    if( typeChk1 && typeChk2 && typeChk3 && typeChk4 ){
        return true;
    }else{
        return false;
    }
}
```

