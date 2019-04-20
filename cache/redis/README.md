<a href="https://github.com/zhenlei520/System.Extension.Core.Doc/blob/1.0/README.md">回到目录</a>

# 缓存服务 #

在Nuget包市场中搜索`EInfrastructure.Core、EInfrastructure.Core.AutoFac`，并安装1.*.*版本

### Redis缓存 ###
在Nuget包市场中搜索`EInfrastructure.Core.Redis`，并安装1.*.*版本

在Starup中ConfigureServices中添加AutoFac自动注入，实例为：  
    
		public IServiceProvider ConfigureServices(IServiceCollection services)
		{
			services.AddRedis(option=>{
				option.Ip = Configuration.GetSection("RedisConfig")["Ip"];
                option.Port = Configuration.GetSection("RedisConfig")["Port"].ConvertToInt(0);
                option.DataBase = Configuration.GetSection("RedisConfig")["DataBase"].ConvertToInt(0);
                option.Name = Configuration.GetSection("RedisConfig")["Name"];
                option.Password = Configuration.GetSection("RedisConfig")["Password"];
                option.PoolSize = Configuration.GetSection("RedisConfig")["PoolSize"].ConvertToInt(0);
			});

			this._serviceProvider = new AutofacAutoRegister().Build(services,
                (builder) => { });
		}


通过控制器注入的方式可直接得到ICacheService，之后直接调用即可
例如：

			public class TestController{
			private readonly ICacheService _cacheService;
			public TestController(ICacheService cacheService){
				_cacheService=cacheService;
			}

			public void Check()
			{
				_cacheService.StringSet("key","value",30);//设置30秒过期
			}
		} 