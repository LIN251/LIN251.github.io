---
layout:     post
title:      Python中Flask框架的使用(随笔)
subtitle:   
date:       2020-05-01
author:     Linz
header-img: img/about_bg.jpg
catalog: true
tags:
    - 服务器
---

## Python中Flask框架的使用

### Flask的目录结构
```
| - projectName
	| - app  //程序包
		| - templates //jinjia2模板
		|- static //css,js 图片等静态文件
		| - main  //py程序包 ，可以有多个这种包，每个对应不同的功能
			| - __init__.py
			|- errors.py
			|- forms.py
			|- views.py
		|- __init__.py
		|- email.py //邮件处理程序
		|- models.py //数据库模型
	|- migrations //数据迁移文件夹
	| - tests  //单元测试
		|- __init__.py
		|- test*.py //单元测试程序，可以包含多个对应不同的功能点测试
	|- venv  //虚拟环境
	|- requirements.txt //列出了所有依赖包以及版本号，方便在其他位置生成相同的虚拟环境以及依赖
	|- config.py //全局配置文件，配置全局变量
	|- manage.py //启动程序
```

### Flask在不同页面间传递参数

**session** 只要设置，在任意请求中都能拿到，无论你拿多少次
```
session.pop('username', None) //从session中移除username，如果存在的话

```

**flash** 一旦设置，可在任意一次请求中获取，但是只能取一次
```

```
**g** 在A路由中设置设置，只能在A路由请求中请求中获取，其它的请求都不能获取
```

```

### API接入
Ensembl API例子

``` Python
// Ensembl API的接入. 如何构建URL.
@app.route('/Ensembl', methods=['GET', 'POST'])
def index():
    server = "http://rest.ensembl.org"
    ext = "/archive/id/ENSG00000157764?"

    r = requests.get(server + ext, headers={"Content-Type": "application/json"})

    if not r.ok:
        r.raise_for_status()
        sys.exit()

    decoded = r.json()
    //返回打印json文件到网页
    return json.dumps(decoded ,ensure_ascii=False)
```

### 重定向

多个URL对应一个function, 转到新的html (render_template)

``` python
@app.route('/hello/')
@app.route('/hello/<name>')
def hello(name=None):
    return render_template('hello.html', name=name)
```

### 读取URL中值作为输入
``` Python
//String
@app.route('/user/<username>')
def show_user_profile(username):
    # show the user profile for that user
    return 'User %s' % username

//Int
@app.route('/post/<int:post_id>')
def show_post(post_id):
    # show the post with the given id, the id is an integer
    return 'Post %d' % post_id

//以URL的值作为传递方法
@app.route('/upload', methods=['POST', 'GET'])
def upload():
    filename = 'NewFile'
    return redirect(url_for('show', filename=filename))
@app.route('/show?filename=<filename>')
def show(filename):
    return filename
```



### Debug模式

注意在Pycharm中需要手动开启debug模式
```
-- Run/Debug Configurations
      FLASK_DEBUG 打勾
```    
``` Python
if __name__ == '__main__':
    app.debug = True
    app.run()
```
