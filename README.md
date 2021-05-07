一、加解密算法
1、SM4
1.1、ECB、PKCS5PADDING模式
加密（密文采用HEX转码）：

var encryptStr = encryptBySM4(“数据”,”密钥”)
解密：

var decryptStr = decryptBySM4(“数据”,”密钥”)

例：
//定义明文数据，可以为 utf8 串或字节数组
var msg = "李镒彤";    
//定义密钥，可以为 16 进制串或字节数组，要求为 128 比特
var key = "abcdefgh12345678abcdefgh12345678";   
//加密
var encryptStr = encryptBySM4(msg,key);
console.log(encryptStr);
//解密
var decryptStr = decryptBySM4(encryptStr,key);
console.log(decryptStr);

控制台响应结果










2、SM2
生成密钥对儿：
var keyPair = generateKeyPairBySM2();
var publicKey = keyPair.publicKey;
var privateKey = keyPair.privateKey;
加密（密文采用HEX转码）：
var encryptStr = encryptBySM2(“数据”,“公钥”);
解密：
var decryptStr = decryptBySM2(“数据”,“私钥”);

例：
//获取SM2公私钥对儿
var keyPair = generateKeyPairBySM2();
var publicKey = keyPair.publicKey;
console.log(“公钥:”+publicKey);
var privateKey = keyPair.privateKey;
console.log(“私钥:”+privateKey);
//加密，生成16进制的密文
var data = "李镒彤";
var encryptStr = encryptBySM2(data,publicKey);
console.log(encryptStr);
//解密
var decryptStr =decryptBySM2(encryptStr,privateKey);
console.log(decryptStr);

控制台响应结果
















3、AES
3.1、ECB、PKCS7PADDING模式
加密（密文采用Base64转码）：
var encryptStr = encryptByAES(“数据”,“密钥”,“ECB”);
解密：
var decryptStr = decryptByAES(“数据”,“密钥”,“ECB”);

例：
var data = "李镒彤";
//加密，密文采用Base64转码
var encryptStr = encryptByAES(data,"1234567812345678","ECB");
console.log(encryptStr);
//解密
var decryptStr = decryptByAES(encryptStr,"1234567812345678","ECB");
console.log(decryptStr);

控制台响应结果

3.2、CBC、PKCS7PADDING模式
加密（密文采用Base64转码）：
var encryptStr = encryptByAES(“数据”,“密钥”,“CBC”，“IV向量”);
解密：
var decryptStr = decryptByAES(“数据”,“密钥”,“CBC”，“IV向量”);

例：
var data = "李镒彤";
//加密
var encryptStr = encryptByAES(data,"1234567812345678","CBC","1234567812345678");
console.log(encryptStr);
//解密
var decryptStr = decryptByAES(encryptStr,"1234567812345678","CBC","1234567812345678");
console.log(decryptStr);

控制台响应结果
































4、RSA
//支持64、128、256字节以及HEX、Base64转码格式的公私钥对儿
加密（密文采用Base64转码）：
var encryptStr = encryptByRSA(“数据”,“公钥”);
解密：
var decryptStr = decryptByRSA(“数据”,“私钥”);

例：
var msg = "李镒彤";
var publicKey = 
"305c300d06092a864886f70d0101010500034b003048024100c2283fa10b9a874e28f5aed0559803db410f32eabed0ca248dd09ba71499d005f685815e1a2b6a0e7e76613f592ce6c7e0a7f08050d158a33c15c247846e6ed70203010001";
var privateKey = 
"30820154020100300d06092a864886f70d01010105000482013e3082013a020100024100c2283fa10b9a874e28f5aed0559803db410f32eabed0ca248dd09ba71499d005f685815e1a2b6a0e7e76613f592ce6c7e0a7f08050d158a33c15c247846e6ed702030100010240253a3e690ca6868710077b8b6abe090f433c3cd111e14ac113880a30511ce4ebc9cc41c1e60f525bbe725624ef744ded79af80c5858d0bfd0ae4063233e85371022100f7f40aa1419f8602291efccb70c04e6a057074f66193180fe9f4c346d7d46e6b022100c8754705b390e4d763ae9309fabbf022b3e0c4a7abf639865895e9673a1904450220182efd3a6d2419f5ebfcd1bb25ec1bb9cb7e046a6369ed56e002b7691973e6b10220248f874999eb96615673f3ab81489fcea4821d3bfb9827fbc1d26dc47f0b2b0502210089abc56d67925855ac8d5774bb57ddf2a18ea3b09077e421238114c29ba26df8";
//加密
var encryptStr = encryptByRSA(msg,publicKey);
console.log(encryptStr);
//解密
var decryptStr = decryptByRSA(encryptStr,privateKey);
console.log(decryptStr);

控制台响应结果


二、摘要算法
1、SM3
加密(采用HEX编码)：
var hashValue = hashBySM3(data);

例：
var data = "李镒彤";
var hashValue = hashBySM3(data);
console.log(hashValue);

控制台响应结果：


2、MD5
加密(采用HEX编码)：
var hashData = hashByMD5(data);

例：
var data = "李镒彤";
var hashData = hashByMD5(data);
console.log(hashData);

控制台响应结果：


3、SHA-1
加密(采用HEX编码)：
var hashData = hashBySHA1(data);

例：
var data = "李镒彤";
var hashData = hashBySHA1(data);
console.log(hashData);

控制台响应结果


4、SHA-256
加密(采用HEX编码)：
var hashData = hashBySHA256(data);

例：
var data = "李镒彤";
var hashData = hashBySHA256(data);
console.log(hashData);

控制台响应结果







三、转码
1、字符串转HEX
var str = "李镒彤";
var strToUtf8 = toUtf8(str);
//字符串转HEX
console.log(stringToHex(strToUtf8));
2、字符串转Base64
var str = "李镒彤";
var strToUtf8 = toUtf8(str);
//字符串转Base64
console.log(stringToBase64(strToUtf8));
3、Hex转Base64
var str = "李镒彤";
var strToUtf8 = toUtf8(str);
var hex = stringToHex(strToUtf8);
//hex转Base64
console.log(hexToBase64(hex));
4、Base64转HEX
var str = "李镒彤";
var strToUtf8 = toUtf8(str);
var base64 = stringToBase64(strToUtf8);
//base64转hex
console.log(base64ToHex(base64));
