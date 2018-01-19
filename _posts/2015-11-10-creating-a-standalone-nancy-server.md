---
layout: post
title: Creating a standalone Nancy server
---
Something I tend to be doing more often, is creating a standalone Nancy server and with each of them, I setup a lot of the same boilerplate code. So I thought I would put together what that setup looks like and throw the code up on GitHub.

This is an opinionated setup using the following packages: Nancy, Autofac, Serilog, ConfigInjector

**Getting Started**  

Starting with a new empty web application in Visual Studio 2015:

![nancy]({{ site.baseurl }}public/images/nancy.png){:width="244px" :height="191px" }

Then add the initial nuget packages:

```
Install-Package Nancy.Hosting.Aspnet
Install-Package Nancy.Bootstrappers.Autofac
```

Next, implement the Autofac Bootstrapper for Nancy by adding a class called Bootstrapper.cs and implement the AutofacNancyBootstrapper:

```csharp
public class Bootstrapper : AutofacNancyBootstrapper
{        
    protected override void ConfigureApplicationContainer(ILifetimeScope existingContainer)
        {           
            var builder = new ContainerBuilder();
            builder.RegisterAssemblyModules(Assembly.GetAssembly(typeof(Bootstrapper)));
            builder.Update(existingContainer.ComponentRegistry);
        }
}
```

Finally create a NancyModule class for the endpoint:

```csharp
public class SampleEndpoint : NancyModule
{
    public SampleEndpoint() : base(&quot;/sample&quot;)
    {
        Get[&quot;/&quot;] = _ =&gt; GetSampleData();
    }
    
    private Response GetSampleData()
    {
        return &quot;hello world&quot;;
    }
}

```

Now if you run up the application, and navigate to the sample endpoint, you should get the hello world response.

![nancy3]({{ site.baseurl }}public/images/nancy3.png){:width="450px" :height="351px" }

