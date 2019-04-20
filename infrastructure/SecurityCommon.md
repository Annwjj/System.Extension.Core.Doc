<a href="https://github.com/zhenlei520/System.Extension.Core.Doc/blob/1.0/README.md">回到目录</a>

### 加密帮助类

&emsp;&emsp;字符串转换为泛型集合：

        string param="";//待加密的字符串
        string decrptParam="";//待解密的字符串


&emsp;&emsp;Aes加密与解密 

        string key="";//AesKey
        SecurityCommon.AesEncrypt(param,key);
        SecurityCommon.Decrypt(decrptParam,key);

&emsp;&emsp;MD5加密

        SecurityCommon.GetMd5Hash(param);//默认编码格式：UTF8
	
&emsp;&emsp;Des加密与解密

        SecurityCommon.DesEncrypt(param,key,iv);//其中key为秘钥，iv为偏移量
        SecurityCommon.DesDecrypt(decrptParam,key,iv);//其中key为秘钥，iv为偏移量

&emsp;&emsp;Sha加密

        SecurityCommon.Sha1(param);
        SecurityCommon.Sha256(param);
        SecurityCommon.Sha384(param);
        SecurityCommon.Sha512(param);

&emsp;&emsp;HMacSha1加密

        SecurityCommon.HMacSha1(param,key);//其中key为秘钥

&emsp;&emsp;JS Aes 加密与解密

        SecurityCommon.JsAesEncrypt(param,key,iv);//其中key为秘钥，iv为偏移量
        SecurityCommon.JsAesDecrypt(param,key,iv);//其中key为秘钥，iv为偏移量