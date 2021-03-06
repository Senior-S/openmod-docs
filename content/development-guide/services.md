# Services and Dependency Injection

## Introduction

OpenMod, like other modern .NET projects, uses the dependency injection pattern. This guide aims to simplify it and explain what it means for plugin developers using OpenMod.

Plugins, commands, event listeners and services can automatically get references to any other services provided by OpenMod or plugins just by adding their interfaces to the constructor.  

# Registering your own Services
You can register your own services by implementing the `IServiceConfigurator` or `IContainerConfigurator` interfaces in any class.

## List of built-in OpenMod Services
TODOODODOODODODOODODODODOODODODO

## Dependency Injection Example
Assume you want to access your plugin's instance and configuration from a command. Here is how you could do it:

```c#
//This is now accessible by the execute method
private readonly IConfiguration m_Configuration;
private readonly MyPlugin m_MyPlugin;

public EchoCommand(
    IServiceProvider serviceProvider, 
    MyPlugin myPlugin,
    IConfiguration configuration) : base(serviceProvider)
{
    m_MyPlugin = myPlugin;
    m_Configuration = configuration;
}
```

## Further reading
For more, read the [Dependency injection page on docs.microsoft.com](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection).