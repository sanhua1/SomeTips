scrollviewer中嵌套datagrid/listbox等内部自带滚动的控件时，scrollviewer的滚动事件会被子控件拦截，鼠标无法在内部滚动整个容器。

类似：

```xaml
<ScrollViewer>
    <DataGrid/>
</ScrollViewer>
```

解决方案如下：

`xaml`

```
<DataGrid PreviewMouseWheel="HandlePreviewMouseWheel">
```

`xaml.cs`

```c#
private void HandlePreviewMouseWheel(object sender, MouseWheelEventArgs e) {
    if (!e.Handled) {
        e.Handled = true;
        var eventArg = new MouseWheelEventArgs(e.MouseDevice, e.Timestamp, e.Delta);
        eventArg.RoutedEvent = UIElement.MouseWheelEvent;
        eventArg.Source = sender;
        var parent = ((Control)sender).Parent as UIElement;
        parent.RaiseEvent(eventArg);
    }
}
```

