 1. 文本组件：Text
 2. 图片组件：Image
 3. 容器组件：Container
 4. 列表组件：ListView：水平列表、垂直列表、长列表、矩阵式列表
 5. 表单组件：From

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190602153420961.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM0OTI3MTE3,size_16,color_FFFFFF,t_70)
一、文本控件

```
        new Text(
                  //文本内容
                  'flutter  中划线 是 lineThrough',
                  //文本样式
                  style: new TextStyle(
                  // 文字颜色
                  color: Colors.orange,
                  //文字颜色
                  fontSize: 25,
                  //中划线
                  decoration: TextDecoration.lineThrough,
                  //下划线
                  //decoration: TextDecoration.underline,
                  // 斜体
                  fontStyle: FontStyle.italic,‘
                  // 加粗	
                  fontWeight: FontWeight.bold,
                  //间隔
                  letterSpacing: 6,
                  //中划线的颜色
                  decorationColor: Colors.blue,
                ),
              ),
              
```

二：长列表

```
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
        title: 'flutter控件展示',
        home: Scaffold(
          appBar: AppBar(
           //标题栏
            title: Text('flutter 控件展示'),
          ),
          //body  ListView
          body: new ListView(
            // 视图组 【】
            children: <Widget>[
              ListTile(
               // 图片
                leading: Icon(Icons.arrow_back),
                title: Text('文本标题3'),
              ),
              ListTile(
                leading: Icon(Icons.arrow_back),
                title: Text('文本标题4'),
              ),
              ListTile(
                leading: Icon(Icons.arrow_back),
                title: Text('文本标题3'),
              ),
              ListTile(
                leading: Icon(Icons.arrow_back),
                title: Text('文本标题4'),
              ),
              ListTile(
                leading: Icon(Icons.arrow_back),
                title: Text('文本标题5'),
              ),
              ListTile(
                leading: Icon(Icons.arrow_back),
                title: Text('文本标题6'),
              ),
              ListTile(
                leading: Icon(Icons.arrow_back),
                title: Text('文本标题7'),
              ),
            ],
          ),
        )
    );
  }
}
```

水平列表：

```
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
        title: 'flutter控件展示',
        home: Scaffold(
          appBar: AppBar(
            title: Text('flutter 控件展示'),
          ),
          body: new Container(
            margin: EdgeInsets.symmetric(vertical: 20),
            height: 200,
            child: ListView(
              //水平方向
              scrollDirection: Axis.horizontal,
              children: <Widget>[
                Container(
                  width: 160,
                  color: Colors.deepOrange,
                  child: Column(
                    children: <Widget>[
                      Text(
                        'aaa',
                      ),
                      Text(
                        'bbb',
                      ),
                    ],
                  ),
                ),

                Container(
                  width: 160,
                  color: Colors.deepPurple,
                  child: Column(
                    children: <Widget>[
                      Text(
                        'aaa',
                      ),
                      Text(
                        'bbb',
                      ),
                    ],
                  ),
                ),
               Container(
                 width: 180,
                 color: Colors.amberAccent,       
               ),    
              ],
                        
            ),
          ),
        )
    );
  }
}
```

三、网格列表
默认垂直

```
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
        title: 'flutter控件展示',
        home: Scaffold(
          appBar: AppBar(
            title: Text('flutter 控件展示'),
          ),
          //构建网格
          body: new GridView.count(
            primary: false,
            //四周的间距
            padding: const EdgeInsets.all(20),
            //横轴间隔
            crossAxisSpacing: 30,
            //横轴的最大长度
            //maxCrossAxisExtent: 180.0,
            //主轴间隔
            mainAxisSpacing: 4.0,
            //一行几列
            crossAxisCount: 3,
            //数据
            children: <Widget>[
              const Text('1'),
              const Text('1'),
              const Text('1'),
              const Text('1'),
              const Text('1'),
              const Text('1'),
              const Text('1'),
              const Text('1'),
              const Text('1'),
              const Text('1'),
              const Text('1'),
            ],
          ),
        )
    );
  }
}
```
四、图片

```
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
 
    return new MaterialApp(
      title: 'Flutter base UI Widget',
      home: new Scaffold(
        appBar: new AppBar(
          title: new Text('Flutter base UI Widget'),
        ),
        body: new ListView(
          children: <Widget>[
            //add code
            new Text('Hello World', style: new TextStyle(fontSize: 32.0)),
            new Image.asset('images/lake.jpeg', width: 200.0,height: 200.0, fit: BoxFit.cover),
            new Icon(Icons.star, color: Colors.red[500])
          ],
        ),
      ),
    );
  }
  }

```

