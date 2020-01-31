# JD-Bot-Python3

基于 GitHub 上一个 Python2 的项目: https://github.com/Adyzng/jd-autobuy

Credit to Adyzng

Python爬虫，扫码登录京东网站，查询商品库存，价格，显示购物车详情等。

可以指定抢购商品，自动下单，最后手动付款完成购买。

## 注意事项

### 获取地区代码即 area_id 的方法：

使用可以检查网页元素的浏览器如 Chrome 或 Firefox，将鼠标移到商品页面 配送至xxxx地区 的位置。

右键，点击检查/审查，复制 data-id 中的内容，如 1_72_2799_0 即代表北京地区。

将其中的 _ 替换成 - 即可得到 area_id：1_72_2799_0 ==> 1-72-2799-0

### 获取商品代码即 good_ID 的方法：

打开需要购买的商品，复制其链接，如：https://item.jd.com/38704750307.html

商品链接即 item.jd.com/ 后的数字串：38704750307


## 运行环境
Python 3

## 环境配置

在安装完 Python3 后需要检查环境是否配置，运行以下命令配置环境。

``` Python
pip install requests
pip install bs4
pip install lxml
```

## 基础使用方法

### Windows:

##### 打开系统命令提示符

ctrl + R ==>输入 cmd ==> 回车

##### 获取 JDspider.py 的路径

右键 JDspider.py，点击属性，复制位置后的路径。

以 E:\downloads\JD-Bot-Python3 为例。在 cmd 中输入

```cmd
cd \
e:
cd E:\downloads\JD-Bot-Python3
```

##### 最终输入

获取帮助

```cmd
python3 JDspider.py -h 
```

或直接开始下单

```cmd
python3 JDspider.py -a 地区ID -g 商品ID
```

### macOS

##### 打开终端

command + space ==> Terminal ==> 回车

##### 获取 JDspider.py 的路径

选中 JDspider.py, 按下 option + command + c

在终端中输入

```cmd
cd 复制刚才的路径并去掉末尾的 JDspider.py
```

##### 最终输入

获取帮助

```cmd
python3 JDspider.py -h 
```

或直接开始下单

```cmd
python3 JDspider.py -a 地区ID -g 商品ID
```

### 

## 帮助

``` cmd
> python JDspider.py -h
JDspider.py [-h] [-a AREA] [-g GOOD] [-c COUNT] [-w WAIT] [-f] [-s]

Simulate to login Jing Dong, and buy good automatically

optional arguments:
  -h, --help            show this help message and exit
  -a AREA, --area AREA  Area ID, like: 1_72_2799_0 for Beijing
  -g GOOD, --good GOOD  Good ID, copy the link of the good, the id is the
                        string after item.jd.com/
  -c COUNT, --count COUNT
                        The quantity to buy
  -w WAIT, --wait WAIT  Flush time interval, unit MS. Too small may cause
                        problem.
  -f, --flush           Continue flash if good out of stock, default True.
  -s, --submit          Submit the order to Jing Dong, default True. By adding
                        this argument, set the progrom to not submit order
```

