# 클립보드 복사

```javascript
function copyUrl(){
    /** -------------------------------------------
    *   클립보드 복사 플러그인
    <script src="https://cdnjs.cloudflare.com/ajax/libs/clipboard.js/1.7.1/clipboard.min.js"></script>
    
    btn   = .copyUrl_btn
    input = <input type="hidden" id="copyUrl_input">
    --------------------------------------------*/
    $('.copyUrl_btn').click(function(){

        $('.copyUrl_btn').attr('data-clipboard-text', $('#copyUrl_input').val());
        var clipboard = new Clipboard('.copyUrl_btn');
        
        clipboard.on('success',function(e){
            console.log(e);
        });
        
        clipboard.on('error', function(e) {
            console.log(e);
        });
    });
}
```



