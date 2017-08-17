# uncrustify-practice

Uncrustify 使用指南

本源仅针对的是Objective-C语言

## 安装

1. 需要最新版HomeBrew, 如果已经安装过, 可以跳过这一步
```
/usr/bin/ruby -e "$(curl -fsSL https:// raw.githubusercontent.com/Homebrew/install/master/install)"
```
2. 执行命令安装
```
brew install uncrustify
```
    请确认安装完的版本号大于等于 0.64, 如果低于这个版本, 请自行删除, 更新HomeBrew后, 重新安装
```
brew remove --force uncrustify
```

3. 执行下面语句, 双击Uncrustify Objective-C文件,安装服务
```
cd ~/Downloads
curl -o Uncrustify_Objective-C.tar https://raw.githubusercontent.com/dominic-lian/uncrustify-practice/master/workflow/Uncrustify_Objective-C.tar
tar -zxvf ~/Downloads/Uncrustify_Objective-C.tar -C ~/Downloads
rm ~/Downloads/Uncrustify_Objective-C.tar
open ~/Downloads/Uncrustify_Objective-C
```

4. 执行下列语句将文件配置文件拷贝进入对应位置
```
curl -o default.cfg.txt --no-check-certificate https://raw.githubusercontent.com/dominic-lian/uncrustify-practice/master/cfg/default.cfg.txt
mv default.cfg.txt ~/.uncrustify_obj_c.cfg
```

## 使用
1. 在XCode的代码编辑器中选中需要格式化的代码, 最好是以整个方法为单位
2. 右键 -> services -> Uncrustify Objective-C
3. 格式化成功后需要再使用 Ctrl + I 让冒号对齐

## 至今存在的问题
1. 文件头会被认为是单行注释被去掉空格
2. 大段的单行注释会被去掉空格

## align_var_def_span变量
1. 这个变量控制声明或创建变量时是否是以*为单位对齐, 好处是@property非常整齐
2. 坏处是代码中其他带*的地方也会被对齐, 请自行决定是否使用
3. 使用下面语句安装align_var_def_span打开的版本,可以与上面版本共存
```
cd ~/Downloads
curl -o Uncrustify_Objective-C_Variable.tar https://raw.githubusercontent.com/dominic-lian/uncrustify-practice/master/workflow/Uncrustify_Objective-C_Variable.tar
tar -zxvf ~/Downloads/Uncrustify_Objective-C_Variable.tar -C ~/Downloads
rm ~/Downloads/Uncrustify_Objective-C_Variable.tar
open ~/Downloads
curl -o default_variable.cfg.txt --no-check-certificate https://raw.githubusercontent.com/dominic-lian/uncrustify-practice/master/cfg/default_variable.cfg.txt
mv default_variable.cfg.txt ~/.uncrustify_obj_c_variable.cfg
```

## 使用快捷键
1. 点屏幕左上角的苹果图标，选 System Preferences – Keyboard – Keyboard Shortcuts – Services
2. 在Text分区里，找到刚添加的服务Uncrustify Objective-C，给这个服务加上快捷键
3. 注意不要和Xcode里其它快捷键冲突，推荐设置为：Cmd+Opt+O, 这样以后在Xcode里，先用Cmd+A全选代码，再用Cmd+Opt+O来格式化代码

## 可视化的修改config文件
[Uncrustify Config](https://cdanu.github.io/uncrustify_config_preview/index.html)


## 参考
[Uncrustify的GitHub主页](https://github.com/uncrustify/uncrustify)


##cfg中的文件为手动修改而成, 请尊重劳动成果

