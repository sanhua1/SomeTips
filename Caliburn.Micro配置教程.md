# Caliburn.Micro配置教程

修改`App.xaml`：

```xaml
<Application
    x:Class="项目名称.App"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="clr-namespace:FollowupManager">
    <Application.Resources>
    <ResourceDictionary>
        <ResourceDictionary.MergedDictionaries>
            <ResourceDictionary>
                <local:Bootstrapper x:Key="bootstrapper" />
            </ResourceDictionary>
        </ResourceDictionary.MergedDictionaries>
    </ResourceDictionary>
</Application.Resources>
</Application>
```

项目中添加Bootsrapper.cs

```c#
internal class Bootstrapper : BootstrapperBase
{
    public Bootstrapper() 
    {
        Initialize();
    }
    private SimpleContainer _container;

    protected override void Configure()
    {
        this._container = new SimpleContainer();
        this._container.Instance(this._container);

        this._container.Singleton<IWindowManager, WindowManager>();


        this._container.PerRequest<HomePageViewModel>();

    }

    // 启动
    protected override async void OnStartup(object sender, StartupEventArgs e)
    {
        await DisplayRootViewForAsync<HomePageViewModel>();
    }

    protected override object GetInstance(Type service, string key)
    {
        var instance = _container.GetInstance(service, key);
        if (instance != null)
        {
            return instance;
        }

        throw new InvalidOperationException($"Could not locate any instances of {service}.");
    }
    protected override IEnumerable<object> GetAllInstances(Type service)
    {
        return _container.GetAllInstances(service);
    }

    protected override void BuildUp(object instance)
    {
        _container.BuildUp(instance);
    }
}
```