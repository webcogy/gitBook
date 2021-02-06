# textarea 최대글자제한

```javascript
function textarea_textcounting(){
	if( $('textarea').length > 0 ){
		var html_wrapper = '<div id="textareaBox"></div>';
		var html_countingBox = '<span id="countingBox">(0 / 최대 500자)</span>';
		
		$('textarea').wrap(html_wrapper);
		$('#textareaBox').append(html_countingBox);
		$('textarea').keyup(function (e){
		    var content = $(this).val();
		    $('#countingBox').html("("+content.length+" / 최대 500자)");    //글자수 실시간 카운팅
		
		    if (content.length > 500){
		        alert("최대 500자까지 입력 가능합니다.");
		        $(this).val(content.substring(0, 500));
		        $('#countingBox').html("(200 / 최대 500자)");
		    }
		});
	}
}
```

