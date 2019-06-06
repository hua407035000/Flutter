


1.页面跳转
![在这里插入图片描述](https://img-blog.csdnimg.cn/2019060610350754.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM0OTI3MTE3,size_16,color_FFFFFF,t_70)

1 首先写一个类 A 继承 StatefulWidget{}
2. 再写 class BState extends State<A> {}  , 把刚才创建的类A 放进State里面
3.  然后  onPressed   通过一个私有方法 来实现路由跳转
4.    通过  Navigator.of(context).push(
      new MaterialPageRoute(.....）;）  来实现页面跳转
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190606104222496.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM0OTI3MTE3,size_16,color_FFFFFF,t_70)
完整的代码

```
// Flutter code sample for material.AppBar.actions.1

// This sample shows adding an action to an [AppBar] that opens a shopping cart.
import 'package:flutter/material.dart';
import 'package:english_words/english_words.dart';
void main() => runApp(MyApp());
/// This Widget is the main application widget.
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return new MaterialApp(
      title: 'Welcome to Flutter',
      home: new A(),
    );
  }
}
class A extends StatefulWidget {
  @override
  State<StatefulWidget> createState() {
    return new BState();
  }
}
class BState extends State<A> {
  final _suggestions = <WordPair>[];
  final _saved = new Set<WordPair>();
  @override
  Widget build(BuildContext context) {
    return new Scaffold(
      appBar: AppBar(
        title: Text("开始写"),
        actions: <Widget>[
          new IconButton(icon: new Icon(Icons.list), onPressed: _pushSaved),
        ],
      ),
      body: _getListView(),
    );
  }

  Widget _getListView() {
    return new ListView.builder(
        padding: const EdgeInsets.all(16.0),
        // 对于每个建议的单词对都会调用一次itemBuilder，然后将单词对添加到ListTile行中
        // 在偶数行，该函数会为单词对添加一个ListTile row.
        // 在奇数行，该函数会添加一个分割线widget，来分隔相邻的词对。
        // 注意，在小屏幕上，分割线看起来可能比较吃力。
        itemBuilder: (context, i) {
          // 在每一列之前，添加一个1像素高的分隔线widget
          if (i.isOdd) return new Divider();
          // 语法 "i ~/ 2" 表示i除以2，但返回值是整形（向下取整），比如i为：1, 2, 3, 4, 5
          // 时，结果为0, 1, 1, 2, 2， 这可以计算出ListView中减去分隔线后的实际单词对数量
          final index = i ~/ 2;
          // 如果是建议列表中最后一个单词对
          if (index >= _suggestions.length) {
            // ...接着再生成10个单词对，然后添加到建议列表
            _suggestions.addAll(generateWordPairs().take(10));
          }
          return _buildRow(_suggestions[index]);
        });
  }

  Widget _buildRow(WordPair pair) {
    final aSvaed = _saved.contains(pair);
    return new ListTile(
        title: Text(pair.asPascalCase),
        trailing: new Icon(
          aSvaed ? Icons.favorite : Icons.favorite_border,
          color: aSvaed ? Colors.red : null,
        ),
        onTap: () {
          setState(() {
            if (aSvaed) {
              _saved.remove(pair);
            } else {
              _saved.add(pair);
            }
          });
        });
  }

  void _pushSaved() {
    Navigator.of(context).push(
      new MaterialPageRoute(
        builder: (context) {
          final tiles = _saved.map(
                (w) {
              return new ListTile(
                title: new Text(
                  w.asPascalCase,
                ),
              );
            },
          );
          final divided = ListTile
              .divideTiles(
            context: context,
            tiles: tiles,
          ).toList();

          return new Scaffold(
            appBar: new AppBar(
                title: Text("新界面")
            ),
            body: new ListView(children: divided),
          );
        },
      ),
    );
  }
}
```

