

Way 1

```cs
public static async Task Main(string[] args]
{
  var serviceCollection = new ServiceCollection();
  ConfigureService(serviceCollection);
  
  var serviceProvider = serviceCollection.BuildServiceProvider();
  await serviceProvider.GetService<Program>().Run(args);
}
```

Way 2

```cs
public static async Task Main(string[] args]
{
  var host = Host.CreateDefaultBuilder()
            .ConfigureServices((context, services) =>
            {
              ConfigureService(services);
            })
            .Build();

  var program = ActivatorUtilities.CreateInstance<Program>(host.Services); 
  await program.Run(args);
}
```

With 

```cs
public static void ConfigureService(IServiceCollection services)
{
  services.AddScoped<IEngine,Engine>();
}
```





