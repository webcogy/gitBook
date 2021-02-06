# 쿠키, 추가/제거 Cookies.set\('name', '', 606024\*30\)

```javascript
// 쿠키 넣을 
Cookies.set('name', '', 60*60*24*30);
Cookies.set('name', '1', 60*60*24*30);
```

```javascript
// 쿠키 있는지 체크
if( document.cookie.indexOf("name=1") == -1 ){ // -1
        // 없으면 -1
}else{ // 136
        // 있으면 그 외
}
```

```javascript
var Cookies = 
{
    
    /**
     * Cookie 생성 함수
     * 
     * @memberOf Cookies
     * @param {String} name Cookie 이름
     * @param {String} value Cookie 값
     * @param {Date} expires Cookie 기간 (option) 60*60*24*30 = 한달
     * @param {String} path 경로 (option)
     * @param {String} domain 도메인 (option)
     * @param {boolean} secure (option)
     */ 
    set : function(name, value)
    {
        var argv = arguments;
        var argc = arguments.length;
        var expires = (argc > 2) ? (argv[2])*1000 : null;
        var path = (argc > 3) ? argv[3] : '/';
        var domain = (argc > 4) ? argv[4] : null;
        var secure = (argc > 5) ? argv[5] : false;
        
        
        var today = new Date();
        today.setTime( today.getTime() );
        var expires_date = new Date( today.getTime() + (expires) );
        
        document.cookie = name + "=" + escape (value) +
            ((expires == null) ? "" : ("; expires=" + expires_date.toGMTString())) +
            ((path == null) ? "" : ("; path=" + path)) +
            ((domain == null) ? "" : ("; domain=" + domain)) +
            ((secure == true) ? "; secure" : "");
    },
    
    /**
     * Cookie 값을 얻는 함수
     * 
     * @param {String} name
     * @return {Object} Returns a Cookie value
     */
    get : function(name)
    {
        var arg = name + "=";
        var alen = arg.length;
        var clen = document.cookie.length;
        var i = 0;
        var j = 0;
        
        while(i < clen){
            
            j = i + alen;
            if (document.cookie.substring(i, j) == arg)
                return Cookies.getCookieVal(j);
            i = document.cookie.indexOf(" ", i) + 1;
            if(i == 0)
                break;
        }
        return null;
    },
    /**
     * Cookie 값을 얻기 위한 내부 함수
     * 
     * @param {int} offset
     */
    getCookieVal : function(offset)
    {
        var endstr = document.cookie.indexOf(";", offset);
        if(endstr == -1){
            endstr = document.cookie.length;
        }
        return unescape(document.cookie.substring(offset, endstr));
    },
    /**
     * Cookie 삭제 함수
     * 
     * @param {String} name
     */
    clear : function(name) 
    {
        if(Cookies.get(name))
        {
            document.cookie = name + "=" +"; expires=Thu, 01-Jan-70 00:00:01 GMT";
        }
    }
};
```

