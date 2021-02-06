# input value 클립보드 복사 document.execCommand\(\)

```javascript
function btn_accountCopy(){
    var textField = document.getElementById('input_account');
    textField.select();
    document.execCommand("copy");
    alert('계좌번호가 복사되었습니다');
}


<button onclick="btn_accountCopy()">
<input type="text" id="input_account" value="복사할 글자" readonly>
```

