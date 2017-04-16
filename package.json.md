# package.json
最简单的package.json文件，项目名称和项目版本不可缺，不要把node或者js放在名字中

```json
{
  "name" : "xxx",
  "version" : "0.0.0",
}
```
更完整的package.json
```json
{
	"name": "Hello World",
	"version": "0.0.1",
	"author": "张三",
	"description": "第一个node.js程序",
	"keywords":["node.js","javascript"],ß
	"repository": {
		"type": "git",
		"url": "https://path/to/url"
	},
	"license":"MIT",
	"engines": {"node": "0.10.x"},
	"bugs":{"url":"http://path/to/bug","email":"bug@example.com"},
	"contributors":[{"name":"李四","email":"lisi@example.com"}],
	"scripts": {
		"start": "node index.js"
	},
	"dependencies": {
		"express": "latest",
		"mongoose": "~3.8.3",
		"handlebars-runtime": "~1.0.12",
		"express3-handlebars": "~0.5.0",
		"MD5": "~1.2.0"
	},
	"devDependencies": {
		"bower": "~1.2.8",
		"grunt": "~0.4.1",
		"grunt-contrib-concat": "~0.3.0",
		"grunt-contrib-jshint": "~0.7.2",
		"grunt-contrib-uglify": "~0.2.7",
		"grunt-contrib-clean": "~0.5.0",
		"browserify": "2.36.1",
		"grunt-browserify": "~1.3.0",
	}
}
```

`author` `description` `keywords` `contributors`
`main` : 指定了加载的入口文件
`engines`:  指明了该项目所需要的node.js版本，引擎
`homepage`：项目官网的url
`repository`：指定你的代码存放的地方
`license`：许可证，让人知道使用的权利和限制（BSD或者MIT，通用）
`bugs`：你项目的提交问题的url和（或）邮件地址
`script`: 指定了运行脚本命令的npm命令行缩写,` npm run+ * `自动执行*默认命令
- 如上，start 指定了运行`npm run start`时，所要执行的命令为`node index.js` 

`devdependence`: 指定项目开发所需要的模块
`dependence`: 指定了项目运行所依赖的模块
 - devdependence ,dependence指向同一个目录,该对象的各个成员，分别由模块名和对应的版本要求组成，表示依赖的模块及其版本范围。
 - 版本范围（遵循“大版本.次要版本.小版本”的格式规定）：
	 - 指定版本 ： 1.2.2
	 - 波浪号（tilde）+指定版本 ：~1.2.2  - 小版本的最新版本，不小于2
	 - 插入号（caret）+指定版本： ˆ1.2.2 - 次要版本最新， 1.x.x的最新版本，不低于1.2.2
	 - latest：安装最新版本

`bin`: 用来指定各个内部命令对应的可执行文件的位置
```json
"bin": {
  "someTool": "./bin/someTool.js"
}
scripts: {  
  start: 'someTool build'
}
```
 
#### 其他：
1. package.json文件可以手工编写，也可以使用`npm init`命令自动生成
2. 有了package.json文件，直接使用`npm install`命令，就会在当前目录中安装所需要的模块。
3. 单独安装模块, `--save`: 将该模块写入package.json的`dependencies`属性，`--save-dev`表示将该模块写入`devDependencies`
```javascript
$ npm install express --save
$ npm install express --save-dev
```


[阮一峰 - package.json](http://javascript.ruanyifeng.com/nodejs/packagejson.html#toc2)