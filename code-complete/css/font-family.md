# font-family 한글,영문 다르게 적용

[https://feel5ny.github.io/2019/09/08/CSS\_02/](https://youngkeol.tistory.com/92)

모든 폰트가 "Noto Sans KR"에서 영문과 숫자만 "Roboto"로 바꿔야 하는 경우가 있었습니다. 클래스를 따로 만들지 않고 @font-face에서 unicode-range을 이용하여 폰트를 변경했습니다. unicode-range는 특정 범위가 글꼴만 불러와 사용할 수 있도록 설정하는 방법입니다. "Roboto"폰트는 영문과 숫자만 불러오고 나머지 폰트는 "Noto Sans KR"로 적용했습니다.



```css
body {font-family:'Roboto' ,'Noto Sans KR', 'sans-serif';}

@font-face {
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 300;
    src: local('※'),
    url('../fonts/Roboto-Regular.eot'),
    url('../fonts/Roboto-Regular.eot#iefix') format('embedded-opentype')
    url('../fonts/Roboto-Regular.woff') format('woff'),
    url('../fonts/Roboto-Regular.otf') format('opentype'),
    url('../fonts/Roboto-Regular.ttf') format('truetype');
    unicode-range:U+0041-005A, U+0061-007A, U+0030-0039;
}
 

유니코드 범위
영문 (대문자) : U+0041-005A

영문 (소문자) : U+0061-007A

숫자 : U+0030-0039

한글 : U+AC00-U+D7A3
```

