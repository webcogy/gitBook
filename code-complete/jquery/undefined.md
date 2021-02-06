# 첨부파일 이미지 미리보기\(반응형고려\)

```javascript
/* #q5 start
    <ul class="file_attach">
        <li>
            <div>
                <input type="file" id="imgInp1">
                <img id="foo1" src="#">
            </div>
        </li>
        <li>
            <div>
                <input type="file" id="imgInp2">
                <img id="foo2" src="#">
            </div>
        </li>
        <li>
            <div>
                <input type="file" id="imgInp3">
                <img id="foo3" src="#">
            </div>
        </li>
    </ul>
 */
function readURL1(input) {
    if (input.files && input.files[0]) {
        var reader = new FileReader();

        reader.onload = function(e) {
            if( e.target.result.indexOf('image') == 5 ){ // 이미지 올릴경우
                $('#foo1').attr('src', e.target.result)
                          .show();
                $('#foo1').parent('div').addClass('on');
            }else if( e.target.result.indexOf('video') == 5 ){ // 비디오 올릴경우
                $('#foo1').attr('src', '../images/common/file_video_on.png')
                          .show();
                $('#foo1').parent('div').addClass('on');
            }else{
                return false;
            }
        }
        reader.readAsDataURL(input.files[0]);
    }
}
function readURL2(input) {
    if (input.files && input.files[0]) {
        var reader = new FileReader();
        reader.onload = function(e) {
            if( e.target.result.indexOf('image') == 5 ){ // 이미지 올릴경우
                $('#foo2').attr('src', e.target.result)
                          .show();
                $('#foo2').parent('div').addClass('on');
            }else if( e.target.result.indexOf('video') == 5 ){ // 비디오 올릴경우
                $('#foo2').attr('src', '../images/common/file_video_on.png')
                          .show();
                $('#foo2').parent('div').addClass('on');
            }else{
                return false;
            }
        }
        reader.readAsDataURL(input.files[0]);
    }
}
function readURL3(input) {
    if (input.files && input.files[0]) {
        var reader = new FileReader();
        reader.onload = function(e) {
            if( e.target.result.indexOf('image') == 5 ){ // 이미지 올릴경우
                $('#foo3').attr('src', e.target.result)
                          .show();
                $('#foo3').parent('div').addClass('on');
            }else if( e.target.result.indexOf('video') == 5 ){ // 비디오 올릴경우
                $('#foo3').attr('src', '../images/common/file_video_on.png')
                          .show();
                $('#foo3').parent('div').addClass('on');
            }else{
                return false;
            }
        }
        reader.readAsDataURL(input.files[0]);
    }
}
$("#imgInp1").change(function() {
    readURL1(this);
    // console.log($("#imgInp1").val());
});
$("#imgInp2").change(function() {
    readURL2(this);
});
$("#imgInp3").change(function() {
    readURL3(this);
});
$("*[id^='imgInp'").on('click',function() {
    $(this).next('img').hide();
    $(this).parent('div').removeClass('on');
});


function fileBox_ratio(){
    var divW = $("*[id^='imgInp'").parent('div').width();
    $("*[id^='imgInp'").parent('div').height(divW);
}fileBox_ratio();
$(window).resize(function(){
    fileBox_ratio();
});
```

