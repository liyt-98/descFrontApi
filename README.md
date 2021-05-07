一、加解密算法

1、SM4

1.1、ECB、PKCS5PADDING模式

加密（密文采用HEX转码）：

var encryptStr = encryptBySM4(“数据”,”密钥”)

解密：

var decryptStr = decryptBySM4(“数据”,”密钥”)


2、SM2

生成密钥对儿：

var keyPair = generateKeyPairBySM2();

var publicKey = keyPair.publicKey;

var privateKey = keyPair.privateKey;

加密（密文采用HEX转码）：

var encryptStr = encryptBySM2(“数据”,“公钥”);

解密：

var decryptStr = decryptBySM2(“数据”,“私钥”);


3、AES

3.1、ECB、PKCS7PADDING模式

加密（密文采用Base64转码）：

var encryptStr = encryptByAES(“数据”,“密钥”,“ECB”);

解密：

var decryptStr = decryptByAES(“数据”,“密钥”,“ECB”);

3.2、CBC、PKCS7PADDING模式

加密（密文采用Base64转码）：

var encryptStr = encryptByAES(“数据”,“密钥”,“CBC”，“IV向量”);

解密：

var decryptStr = decryptByAES(“数据”,“密钥”,“CBC”，“IV向量”);


4、RSA

//支持64、128、256字节以及HEX、Base64转码格式的公私钥对儿

加密（密文采用Base64转码）：

var encryptStr = encryptByRSA(“数据”,“公钥”);

解密：

var decryptStr = decryptByRSA(“数据”,“私钥”);


二、摘要算法

1、SM3

加密(采用HEX编码)：

var hashValue = hashBySM3(data);

2、MD5

加密(采用HEX编码)：

var hashData = hashByMD5(data);


3、SHA-1

加密(采用HEX编码)：

var hashData = hashBySHA1(data);


4、SHA-256

加密(采用HEX编码)：

var hashData = hashBySHA256(data);

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
