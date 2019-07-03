<a href="https://github.com/zhenlei520/System.Extension.Core.Doc/tree/2.0/README.md">回到目录</a>

### 时间帮助类
&emsp;&emsp;格式化时间：

		DateTime.Now.Format("yyyy-MM-dd");//输出结果：2019-01-01


&emsp;&emsp;将时间格式化成 年月日 的形式,如果时间为null，返回当前系统时间：

		DateTime.Now.GetFormatDate("/");//输出结果：2019/01/01


&emsp;&emsp;把秒转换成分钟：

		DateTime.Now.SecondToMinute(80);//输出结果：2


&emsp;&emsp;格式化时间：

		TimeCommon.GetMonthLastDate(2019,1);//输出结果：31


&emsp;&emsp;返回时间差：

		DateTime.Parse("2019-01-01 12:00:00").DateDiff(DateTime.Now);//输出结果：n月n日或者n小时前或者n分钟前

&emsp;&emsp;获得两个日期的间隔：

		DateTime.Now.DateDiff2(DateTime.Parse('2019-01-01 12:00:00'));


&emsp;&emsp;格式化日期时间：

		DateTime.Now.FormatDate();//默认yyyy-MM-dd HH:mm:ss

&emsp;&emsp;得到随机日期（间隔日期之间的 随机日期）：

		DateTime.Now.GetRandomTime(DateTime.Parse('2019-01-01 12:00:00'));


&emsp;&emsp;得到随机日期（间隔日期之间的 随机日期）：

		string firstDay,string lastDay;
		TimeCommon.ReturnDateFormat(12,out firstDay.out lastDay);//可以得到12月份的第一天和最后一天


&emsp;&emsp;得到据当前多远时间：
		
		DateTime.Now.GetAccordingToCurrent();//得到距离当前多远时间 


&emsp;&emsp;得到月初与月末时间：
		
		DateTime.Now.Get(TimeType.StartMonth);//得到月初/月末/本周一/本周日/本季初/本季末/年初/年末时间 


&emsp;&emsp;得到前N秒的时间：

		TimeCommon.FindASecondsAgo();//默认300秒


&emsp;&emsp;得到13位时间戳：

		DateTime.Now.GetTimeSpan();

&emsp;&emsp;DateTime时间格式转换为10位不带毫秒的Unix时间戳：

		DateTime.Now.ConvertDateTimeInt();

&emsp;&emsp;将当前Utc时间转换为总秒数：

		DateTime.Now.ToUnixTimestamp();

&emsp;&emsp;将10位时间戳转时间：
		
		long i=1550558491;
		i.UnixTimeStampToDateTime();

&emsp;&emsp;将13位时间戳转为时间：

		long i=1550558491000;
		i.JsTimeStampToDateTime();


&emsp;&emsp;获得总秒数：

		TimeCommon.CurrentTimeMillis();//默认从1970年1月1日 0点0分到现在的总时间