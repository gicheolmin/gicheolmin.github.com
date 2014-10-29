<style type="text/css">
 .tbl { border-top:2px solid #999999; border-left:1px solid #dddddd; }
 .tbl th { background-color:#eeeeee; border-bottom:1px solid #dddddd; border-right:1px solid #dddddd; padding:2px; }
 .tbl td { border-bottom:1px solid #dddddd; border-right:1px solid #dddddd; padding:2px; }
 </style>
 <script type="text/javascript">
 var dap = 5;
 var answer_check = function(el) {
  var result = document.getElementById("result");
  if(dap==el.value) {
   result.innerHTML = '정답';
   result.style.color = 'blue';
   // : alert('정답'); // : 경고창으로 띄울때
 } else {
   result.innerHTML = '틀림';
   result.style.color = 'red';
   // : alert('틀림'); // : 경고창으로 띄울때
 }
 }
 </script>
 <div>정답체크 : <span id="result" name="result">정답을 체크해주세요</span></div>
 <table border="0" cellspacing="0" cellpadding="0" class="tbl">
 <tr>
  <th>다음중 남자연예인은?</th>
 </tr>
 <tr>
  <td><input type="radio" name="answer" id="answer_1" value="1" onClick="answer_check(this)" /><label for="answer_1">한가인</label></td>
 </tr>
 <tr>
  <td><input type="radio" name="answer" id="answer_2" value="2" onClick="answer_check(this)" /><label for="answer_2">박시연</label></td>
 </tr>
 <tr>
  <td><input type="radio" name="answer" id="answer_3" value="3" onClick="answer_check(this)" /><label for="answer_3">김태희</label></td>
 </tr>
 <tr>
  <td><input type="radio" name="answer" id="answer_4" value="4" onClick="answer_check(this)" /><label for="answer_4">신민아</label></td>
 </tr>
 <tr>
  <td><input type="radio" name="answer" id="answer_5" value="5" onClick="answer_check(this)" /><label for="answer_5">김수현</label></td>
 </tr>
 </table>
