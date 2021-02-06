---
description: 'isAlphabet, isKorean, isNumber'
---

# 한글, 영어, 숫자인지 체크 charCodeAt

```javascript
/* --------------------------------------------------
알파벳인지 체크
------------------------------------------------*/
function isAlphabet(ch) {
        var numUnicode = ch.charCodeAt(0);     // number of the decimal Unicode
        if ( 65 <= numUnicode && numUnicode <= 90 ) return true;            // 대문자
        if ( 97 <= numUnicode && numUnicode <= 122 ) return true;            // 소문자
        return false;
}

/* --------------------------------------------------
한글인지 체크
------------------------------------------------*/
function isKorean(ch) {
        var numUnicode = ch.charCodeAt(0);                                                                                   
        if ( 44032 <= numUnicode && numUnicode <= 55203 ) return true;           
        return false;
}

/* --------------------------------------------------
숫자인지 체크
------------------------------------------------*/
function isNumber(ch) {
        var numUnicode = ch.charCodeAt(0);                                                                                   
        if ( 48 <= numUnicode && numUnicode <= 57 ) return true;           
        return false;
}

출처: https://aladdin76.tistory.com/593 [Aladdin's Land]
```

