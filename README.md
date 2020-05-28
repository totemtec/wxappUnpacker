
# 说明
- 来自网友基于 [wxappUnpacker](https://github.com/qwerty472123/wxappUnpacker "wxappUnpacker") 改进的开源项目。

# 安装
```
npm install
```

# 安装依赖
```
npm install esprima
    
npm install css-tree
    
npm install cssbeautify
    
npm install vm2
    
npm install uglify-es
    
npm install js-beautify
```

# 分包功能

当检测到 wxapkg 为子包时, 添加-s 参数指定主包源码路径即可自动将子包的 wxss,wxml,js 解析到主包的对应位置下. 完整流程大致如下: 
1. 获取主包和若干子包
2. 解包主包 `./bingo.sh testpkg/master-xxx.wxapkg`
3. 解包子包 `./bingo.sh testpkg/sub-1-xxx.wxapkg -s=../master-xxx`

TIP
> -s 参数可为相对路径或绝对路径, 推荐使用绝对路径, 因为相对路径的起点不是当前目录 而是子包解包后的目录

```
├── testpkg
│   ├── sub-1-xxx.wxapkg #被解析子包
│   └── sub-1-xxx               #相对路径的起点
│       ├── app-service.js
│   ├── master-xxx.wxapkg
│   └── master-xxx             # ../master-xxx 就是这个目录
│       ├── app.json
```

# 注意事项
1. 获取小程序的wxapkg文件不要用PC版微信，否则反编译时提示：Error: Magic number is not correct!
   要使用手机root后读取，root嫌麻烦可以用模拟器，网上推荐的的夜神真坑啊，最后用了网易mumu模拟器，好用速度快
2. 因为我的客户丢失了乙方，所以我做了乙方，想拿回源代码。
   万幸从微信小程序管理后台能拿到map文件，使用下面工具，混淆后的Javascript文件都能还原回来
   
https://github.com/paazmaya/shuji
