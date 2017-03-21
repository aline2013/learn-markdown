# 时间处理（Date）

### 基本用法
```javascript
//获取当前时间： 北京时间 2017.3.21 22:14:43 
var now = new Date();  // Tue Mar 21 2017 22:14:43 GMT+0800 (CST); 
typeof now;			// object
a instanceof Date;  // true; Date对象

// 获取 年／月／日／时／分／秒／毫秒 星期 
now.getFullYear();		// 2017
now.getMonth(); 		// 2 (0~11)	
now.getDate();			// 21
now.getHours();			// 22
now.getMinutes();		// 14
now.getSeconds();		// 43
now.getMilliseconds();  // 777 (0~999)
now.getDay();			// 2 （即星期二，0~6)

// 根据世界时，得到各数据
now.getUTC[FullYear|Month|Date|Hours|Minutes|Seconds|Milliseconds|Day]()
// 北京时间和世界时相差8h
now.getUTCHours();		// 14
// 返回本地时间与格林威治标准时间 (GMT) 的分钟差
now.getTimezoneOffset();	// -480

// 获取时间戳
now = now.getTime();		// 1490105683777
// 将时间戳变为Date对象,now = 1490105683777
now = new Date(now);    // Tue Mar 21 2017 22:14:43 GMT+0800 (CST)
// 返回1970年1月1日午夜到指定日期（字符串）的毫秒数
now = Date.parse(now);		// 1490105683000(
精准到秒)
// 返回 Date 对象的原始值
now.valueOf();		// 1490105683777
+new Date(now);		// 1490105683777
// 转为Date对象
new Date(2009,1,1);
new Date("2009/1/1");
var strTime="2011-04-16";    //字符串日期格式           
var date= new Date(Date.parse(strTime.replace(/-/g,  "/")));      // Thu Jan 01 2009 00:00:00 GMT+0800 (CST)

// 转为string类型
now = now.toString();  // "Tue Mar 21 2017 22:14:43 GMT+0800 (CST)"
// 日期部分转换为字符串
no.toDateString();		// "Tue Mar 21 2017"
// 时间部分转换为字符串
now.toTimeString();		// "22:14:43 GMT+0800 (CST)"
// 根据世界时，把 Date 对象转换为字符串
now.toUTCString();		// "Tue, 21 Mar 2017 14:14:43 GMT"
now.toISOString();		// "2017-03-21T14:14:43.777Z"
// 根据本地时间格式
// ,把 Date 对象转换为字符串
now.toLocaleString();	// "2017/3/21 下午10:14:43"
// ,日期部分转换为字符串
now.toLocaleDateString(); // "2017/3/21"
// ,时间部分转换为字符串
now.toLocaleTimeString();	// "下午10:14:43"

// 设置时间参数, 年／月／日／时／分／秒／毫秒
now.set[FullYear|Month|Date|Hours|Minutes|Seconds|Milliseconds]()
```

- 时间戳有 10位／13位，即秒级和毫秒级，转换 *1000 或 ／1000，可通过转为string后进行判断和处理

