# wsl中使用jupyter
wsl下
jptyter notebook
自动跳转，浏览器无法打开。解决

（1）chrome在win的位置C:\Program Files (x86)\Google\Chrome\Application\chrome.exe
在wsl中找到该位置，其实就是在将该路径转换成linux中的路径
注意：所有的空格或者符号前都需要加防转义符‘\’如果和我的路径一样，直接复制下面即可
```
/mnt/c/Program\ Files\ \(x86\)/Google/Chrome/Application/chrome.exe
```
在wsl中键入下面命令尝试访问，如果能正确的打开浏览器，说明路径是对的
```
/mnt/c/Program\ Files\ \(x86\)/Google/Chrome/Application/chrome.exe
```
这个路径太长了，而且手打起来很麻烦，所以我们建立一个软连接
```
sudo ln -s /mnt/c/Program\ Files\ \(x86\)/Google/Chrome/Application/chrome.exe /usr/bin/chrome
```
验证软连接是否成功，看能否成功驱动浏览器

（2）编辑jupyter配置文件
首先我们先生成默认配置文件
```
jupyter notebook --generate-config
```
打开配置文件，更改浏览器的驱动路径
```
nano ~/.jupyter/jupyter_notebook_config.py
```
我们直接在文件的最后面，加上下面这段代码：

## 自定义浏览器
```
import webbrowser
webbrowser.register('chrome',None,webbrowser.GenericBrowser('/usr/bin/chrome'))
c.NotebookApp.browser = 'chrome'
# --------------------------------------------------
```

再设置禁用重定向，否轴浏览器会打开 诸如下面的地址file:///home/mzs/.local/share/jupyter/runtime/nbserver-2289-open.html

在jupyter_notebook_config.py里设置
```
c.NotebookApp.use_redirect_file = False                                                                                                                      #c.NotebookApp.allow_root=True  
```
