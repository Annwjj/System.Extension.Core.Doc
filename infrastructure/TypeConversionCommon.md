<a href="https://github.com/zhenlei520/System.Extension.Core.Doc/tree/2.0/README.md">回到目录</a>

# 类型转换 #
	
&emsp;&emsp;类型转换统一格式：ConvertTo

	示例：
		int i=obj.ConvertToInt(0);//object类型强转为int类型，如果转换失败，默认为0
		int?i=obj.ConvertToInt();//object类型强转为可空的int类型，如果转换失败，默认为Null

		decimal i=obj.ConvertToDecimal(0m);//object类型强转为decimal类型，如果转换失败，默认为0
		int?i=obj.ConvertToInt();//object类型强转为可空的decimal类型，如果转换失败，默认为Null

	所有类型转换均参考此格式。

&emsp;&emsp;文件类型转换  
	
	示例：
		转为byte数组
			byte[]tem=Stream.ConvertToByteArray(); //Stream转为byte数组
			byte[]tem=String.ConvertToByteArray();//String转为byte数组

		转为Stream
			Stream stream=byte[].ConvertToStream();//byte数组转为Stream

		byte数组转换为string
			String str=byte[].ConvertToString();//byte数组转换为string

		字符串base64转byte数组
			byte[]tem=base64.ConvertToByte();

		byte数组转换为base64
			string base64=byte[].ConvertToBase64();

		Stream转换为base64
			string base64=Stream.ConvertToBase64();

&emsp;&emsp;清除小数点后0  
		
		String.ClearDecimal();//其中String为要待去除的字符串

得到n为长度的特殊符号  
		
		TypeConversionCommon.GetContentByEncryption('*', 6);//输出结果：******
		TypeConversionCommon.GetContentByEncryption("*", 6);//输出结果：******

值互换(左边最小值,右边最大值)，方法支持类型有：int，decimal，DateTime，byte，float，double  

		int x=2,y=1;
		TypeConversionCommon.ChangeResult(ref x,ref y);//输入结果：x=1,y=2;

		decimal x=5.2m,y=1.5m;
		TypeConversionCommon.ChangeResult(ref x,ref y);//输入结果：x=1.5m,y=5.2m;

		
		