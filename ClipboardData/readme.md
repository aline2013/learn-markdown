

# 剪切板处理


## event.clipboardData

-  返回一个 `DataTransfer`对象

### dataTransfer
1.	与`cut`,`copy`,`paste`，`drop`等事件相关的剪切板数据
2. 方法 
    - 方法1： ` setData(format, data)` 设置放入剪切板的数据,拖放事件
    - 方法2： `getData(format)` 获得剪切板的数据
    - 方法3： `clearData(format)`删除与给定类型关联的数据

1. IE下，window.ClipboardData
2. 其他， event.clipboardData || event.originalEvent.clipboardData;

