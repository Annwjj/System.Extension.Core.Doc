<a href="https://github.com/zhenlei520/System.Extension.Core.Doc/blob/1.0/README.md">回到目录</a>

### 序列化与反序列化

#### 对象的序列化与反序列化


&emsp;&emsp;序列化：
	
		object obj=new {};
		new JsonCommon(EnumJsonMode.Newtonsoft).Serializer(obj,false);//默认使用Newtonsoft进行序列化，其中序列化方式可以不写

&emsp;&emsp;反序列化：
		
		String str="[1,2]";
		new JsonCommon(EnumJsonMode.Newtonsoft).Deserialize<List<int>>(str);//默认使用Newtonsoft进行序列化，其中序列化方式可以不写


#### xml对象的序列化与反序列化

&emsp;&emsp;序列化：
	
		object obj=new {};
		XmlCommon.Serializer(obj);//此方法中有多个参数，需要的可调用使用

&emsp;&emsp;反序列化：
		
		String str="[1,2]";
		XmlCommon.Deserialize<T>("xml字符串","编码格式，默认utf8");
