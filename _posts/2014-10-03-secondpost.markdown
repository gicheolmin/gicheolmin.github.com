---
layout: post
title:  "Welcome to Jekyll!"
date:   2014-10-03 07:21:41
categories: jekyll update
---

|두번째|포스트|입니당|헤헤|
|------|------|------|----|
|content|content|content|content|



<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">

<html>

    <head>

        <title> sjisbmoc </title>

<script language='javascript' type='text/javascript'>

//<![CDATA[




var fm;

var answer  = new Array();

answer.push('1');

answer.push('2');

answer.push('1');

answer.push('4');

answer.push('3');

answer.push('1');

answer.push('4');

answer.push('3');

answer.push('1');

answer.push('4');




var an_desc = new Array();

an_desc.push('1번 : 1.크리스마스');

an_desc.push('2번 : 2.Korea');

an_desc.push('3번 : 1.후지산');

an_desc.push('4번 : 4.필란드');

an_desc.push('5번 : 3.워싱턴');

an_desc.push('6번 : 1.5월5일');

an_desc.push('7번 : 4.이명박');

an_desc.push('8번 : 3.무궁화');

an_desc.push('9번 : 1.2011년');

an_desc.push('10번 : 4.24');




function fncInit()

{

    fm       = document.frm;

    var name = prompt('이름을 입력해 주세요.','');

    var jumin= prompt('주민번호를 입력해 주세요.\n예) 19900101-1234567','');

    jminlt   = jumin.split('-');

    fm.jumin1.value = jminlt[0];

    fm.jumin2.value = jminlt[1];

    if(fncChkJuminNo())

    {

        document.getElementById('user_name').innerText = name;

        document.getElementById('test').style.display  = 'block';

    }

    else

    {

        alert('주민번호가 잘못됐습니다.');

    }

}




function fncCalc()

{

    var str = '';




    var cnt   = 0;

    for( var i=0; i<answer.length; i++ )

    {

        var obj = fm['rdo'+i];

        for( var j=0; j<obj.length; j++ )

        {

            if( obj[j].checked )

            {

                if( obj[j].value == answer[i] )

                {

                    cnt++;

                }

                else

                {

                    if(str=='') str = an_desc[i];

                    else str += '<br>'+an_desc[i];

                }

            }

        }

    }







    var rlt = document.getElementById('result');




    var grade = cnt/answer.length*100;

    if( grade>=60 )

    {

        rlt.innerHTML = grade+'점 합격';

    }

    else

    {

        rlt.innerHTML = grade+'점 불합격';

    }




    rlt.innerHTML += '<p/>틀린답<p/>'+str;

}




function fncChkJuminNo()

{

    var fm  = document.frm;

    var jno1= fm.jumin1.value; //첫 번째 필드

    var jno2= fm.jumin2.value; //두번째 필드




    if(jno1.length != 0)

    {

        var chk = 0;

        var yy  = jno1.substring(0, 2); //출생년도 추출

        var mm  = jno1.substring(2, 4); //출생월 추출

        var dd  = jno2.substring(4, 6); //출생일 추출

        var sex = jno2.substring(0, 1); //성별 추출




        //첫 번째필드가 6자리가 아니거나 출생월일이 날짜 형식에 위배될때

        if((jno1.length!=6) || (mm<1 || mm>12 || dd<1 || dd>31))

        {

            //frm.jumin1.value='';

            alert('본인 주민번호 첫번째자리 형식이 잘못 되었습니다.');

            //frm.jumin1.focus();

            return false;

        }




        //성별형식이 틀리거나 두 번째 필드가 7자리가 아닐때

        if((jno2.length!=7) || (sex!=1 && sex!=2 && sex!=3 && sex!=4 ))

        {

            alert('본인 주민번호 두번째자리 형식이 잘못 되었습니다.');

            return false;

        }




        //주민등록번호 체크에 관한

        for(i=0; i<=5; i++) chk = chk+((i%8+2)*parseInt(jno1.substring(i, i+1)));




        for(i=6; i<=11; i++) chk = chk+((i%8+2)*parseInt(jno2.substring(i-6, i-5)));

        chk = (11-(chk%11))%10;

        if(chk!=jno2.substring(6, 7))

        {

            alert('주민번호 형식이 잘못 되었습니다.');

            return false;

        }

    }




    return true;

}




//]]>

</script>

<style>

td  { font-size:12px; font-family:굴림체; }

.bd { font-weight:bold; }

.name {font-size:12px; font-family:굴림체; font-weight:bold; }

</style>

    </head>

    <body leftmargin='0' topmargin='0' onload='javascript_:fncInit();'>

<form name='frm'>

<input type='hidden' name='jumin1' style='width:80;' maxlength='6'/>

<input type='hidden' name='jumin2' style='width:80;' maxlength='7'/>




        <div id='user_name' class='name'></div>




        <br>




        <table id='test' style='display:none'>

            <tr>

                <td class='bd'>1.12월25일은?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo0' value='1'>크리스마스

                    <input type='radio' name='rdo0' value='2'>석가탄신일

                    <input type='radio' name='rdo0' value='3'>광복절

                    <input type='radio' name='rdo0' value='4'>설날

                </td>

            </tr>

            <tr>

                <td class='bd'>2.한국은?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo1' value='1'>USA

                    <input type='radio' name='rdo1' value='2'>Korea

                    <input type='radio' name='rdo1' value='3'>Japan

                    <input type='radio' name='rdo1' value='4'>China

                </td>

            </tr>

            <tr>

                <td class='bd'>3.한국에 있는산이 아닌것은?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo2' value='1'>후지산

                    <input type='radio' name='rdo2' value='2'>백두산

                    <input type='radio' name='rdo2' value='3'>설악산

                    <input type='radio' name='rdo2' value='4'>지리산

                </td>

            </tr>

            <tr>

                <td class='bd'>4.아시아가 아닌나라</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo3' value='1'>베트남

                    <input type='radio' name='rdo3' value='2'>필리핀

                    <input type='radio' name='rdo3' value='3'>말레이시아

                    <input type='radio' name='rdo3' value='4'>필란드

                </td>

            </tr>

            <tr>

                <td class='bd'>5.미국의 수도는?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo4' value='1'>켈리포니아

                    <input type='radio' name='rdo4' value='2'>뉴욕

                    <input type='radio' name='rdo4' value='3'>워싱턴

                    <input type='radio' name='rdo4' value='4'>알래스카

                </td>

            </tr>

            <tr>

                <td class='bd'>6.어린이날?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo5' value='1'>5월5일

                    <input type='radio' name='rdo5' value='2'>6월5일

                    <input type='radio' name='rdo5' value='3'>7월5일

                    <input type='radio' name='rdo5' value='4'>8월5일

                </td>

            </tr>

            <tr>

                <td class='bd'>7.우리나라 현재 대통령은?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo6' value='1'>부시

                    <input type='radio' name='rdo6' value='2'>김대중

                    <input type='radio' name='rdo6' value='3'>오바마

                    <input type='radio' name='rdo6' value='4'>이명박

                </td>

            </tr>

            <tr>

                <td class='bd'>8.한국의 국화는?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo7' value='1'>장미

                    <input type='radio' name='rdo7' value='2'>벚꽃

                    <input type='radio' name='rdo7' value='3'>무궁화

                    <input type='radio' name='rdo7' value='4'>국화

                </td>

            </tr>

            <tr>

                <td class='bd'>9.내년은 몇년도인가?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo8' value='1'>2011년

                    <input type='radio' name='rdo8' value='2'>2020년

                    <input type='radio' name='rdo8' value='3'>2100년

                    <input type='radio' name='rdo8' value='4'>2999년

                </td>

            </tr>

            <tr>

                <td class='bd'>10.하루는 몇시간?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo9' value='1'>30

                    <input type='radio' name='rdo9' value='2'>31

                    <input type='radio' name='rdo9' value='3'>50

                    <input type='radio' name='rdo9' value='4'>24

                </td>

            </tr>

            <tr>

                <td><input type='button' name='btn' value='체점' onclick='javascript_:fncCalc();'></td>

            </tr>

        </table>




        <div id='result'></div>




</form>

    </body>

</html>







주민번호 체크 제거





<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">

<html>

    <head>

        <title> sjisbmoc </title>

<script language='javascript' type='text/javascript'>

//<![CDATA[




var fm;

var answer  = new Array();

answer.push('1');

answer.push('2');

answer.push('1');

answer.push('4');

answer.push('3');

answer.push('1');

answer.push('4');

answer.push('3');

answer.push('1');

answer.push('4');




var an_desc = new Array();

an_desc.push('1번 : 1.크리스마스');

an_desc.push('2번 : 2.Korea');

an_desc.push('3번 : 1.후지산');

an_desc.push('4번 : 4.필란드');

an_desc.push('5번 : 3.워싱턴');

an_desc.push('6번 : 1.5월5일');

an_desc.push('7번 : 4.이명박');

an_desc.push('8번 : 3.무궁화');

an_desc.push('9번 : 1.2011년');

an_desc.push('10번 : 4.24');




function fncCalc()

{

    var str = '';




    var cnt   = 0;

    for( var i=0; i<answer.length; i++ )

    {

        var obj = fm['rdo'+i];

        for( var j=0; j<obj.length; j++ )

        {

            if( obj[j].checked )

            {

                if( obj[j].value == answer[i] )

                {

                    cnt++;

                }

                else

                {

                    if(str=='') str = an_desc[i];

                    else str += '<br>'+an_desc[i];

                }

            }

        }

    }







    var rlt = document.getElementById('result');




    var grade = cnt/answer.length*100;

    if( grade>=60 )

    {

        rlt.innerHTML = grade+'점 합격';

    }

    else

    {

        rlt.innerHTML = grade+'점 불합격';

    }




    rlt.innerHTML += '<p/>틀린답<p/>'+str;

}




//]]>

</script>

<style>

td  { font-size:12px; font-family:굴림체; }

.bd { font-weight:bold; }

.name {font-size:12px; font-family:굴림체; font-weight:bold; }

</style>

    </head>

    <body leftmargin='0' topmargin='0'>

<form name='frm'>

<input type='hidden' name='jumin1' style='width:80;' maxlength='6'/>

<input type='hidden' name='jumin2' style='width:80;' maxlength='7'/>




        <br>




        <table id='test'>

            <tr>

                <td class='bd'>1.12월25일은?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo0' value='1'>크리스마스

                    <input type='radio' name='rdo0' value='2'>석가탄신일

                    <input type='radio' name='rdo0' value='3'>광복절

                    <input type='radio' name='rdo0' value='4'>설날

                </td>

            </tr>

            <tr>

                <td class='bd'>2.한국은?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo1' value='1'>USA

                    <input type='radio' name='rdo1' value='2'>Korea

                    <input type='radio' name='rdo1' value='3'>Japan

                    <input type='radio' name='rdo1' value='4'>China

                </td>

            </tr>

            <tr>

                <td class='bd'>3.한국에 있는산이 아닌것은?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo2' value='1'>후지산

                    <input type='radio' name='rdo2' value='2'>백두산

                    <input type='radio' name='rdo2' value='3'>설악산

                    <input type='radio' name='rdo2' value='4'>지리산

                </td>

            </tr>

            <tr>

                <td class='bd'>4.아시아가 아닌나라</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo3' value='1'>베트남

                    <input type='radio' name='rdo3' value='2'>필리핀

                    <input type='radio' name='rdo3' value='3'>말레이시아

                    <input type='radio' name='rdo3' value='4'>필란드

                </td>

            </tr>

            <tr>

                <td class='bd'>5.미국의 수도는?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo4' value='1'>켈리포니아

                    <input type='radio' name='rdo4' value='2'>뉴욕

                    <input type='radio' name='rdo4' value='3'>워싱턴

                    <input type='radio' name='rdo4' value='4'>알래스카

                </td>

            </tr>

            <tr>

                <td class='bd'>6.어린이날?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo5' value='1'>5월5일

                    <input type='radio' name='rdo5' value='2'>6월5일

                    <input type='radio' name='rdo5' value='3'>7월5일

                    <input type='radio' name='rdo5' value='4'>8월5일

                </td>

            </tr>

            <tr>

                <td class='bd'>7.우리나라 현재 대통령은?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo6' value='1'>부시

                    <input type='radio' name='rdo6' value='2'>김대중

                    <input type='radio' name='rdo6' value='3'>오바마

                    <input type='radio' name='rdo6' value='4'>이명박

                </td>

            </tr>

            <tr>

                <td class='bd'>8.한국의 국화는?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo7' value='1'>장미

                    <input type='radio' name='rdo7' value='2'>벚꽃

                    <input type='radio' name='rdo7' value='3'>무궁화

                    <input type='radio' name='rdo7' value='4'>국화

                </td>

            </tr>

            <tr>

                <td class='bd'>9.내년은 몇년도인가?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo8' value='1'>2011년

                    <input type='radio' name='rdo8' value='2'>2020년

                    <input type='radio' name='rdo8' value='3'>2100년

                    <input type='radio' name='rdo8' value='4'>2999년

                </td>

            </tr>

            <tr>

                <td class='bd'>10.하루는 몇시간?</td>

            </tr>

            <tr>

                <td>

                    <input type='radio' name='rdo9' value='1'>30

                    <input type='radio' name='rdo9' value='2'>31

                    <input type='radio' name='rdo9' value='3'>50

                    <input type='radio' name='rdo9' value='4'>24

                </td>

            </tr>

            <tr>

                <td><input type='button' name='btn' value='체점' onclick='javascript_:fncCalc();'></td>

            </tr>

        </table>




        <div id='result'></div>




</form>

    </body>

</html>
