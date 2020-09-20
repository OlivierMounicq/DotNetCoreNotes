

|   Way 1     | Way 2  |
|------------|--------------------------|
| ```cs 
  var serviceProvider = serviceCollection.BuildServiceProvider(); 
  
  ``` | ```cs var program = ActivatorUtilities.CreateInstance<Program>(host.Services);  ``` |



