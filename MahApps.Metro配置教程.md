# MahApps.Metro配置教程

`App.xaml`添加：

```xaml
<ResourceDictionary Source="pack://application:,,,/MahApps.Metro;component/Styles/Controls.xaml" />
<ResourceDictionary Source="pack://application:,,,/MahApps.Metro;component/Styles/Fonts.xaml" />
<!--  Theme setting  -->
<ResourceDictionary Source="pack://application:,,,/MahApps.Metro;component/Styles/Themes/Light.Blue.xaml" />
```

`View.xaml`引入:

```xaml
xmlns:mah="http://metro.mahapps.com/winfx/xaml/controls"
```

将

```
<Window>

</Window>
```

修改为

```
<mah:MetroWindoe>

</mah:MetroWindoe>
```



`View.xaml.cs`中删除继承的`Window`或继承`MetroWindow`

