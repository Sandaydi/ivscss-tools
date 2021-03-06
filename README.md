# ivscss-tools
## 🖖 简介
ivscss-tools是scss的一个工具库。
The ivscss-tools is a tool library of scss.

它提供了scss原生没有的一些接口。
It provides some interface, but native scss does not.

例如，scss不允许类型转换。工具库提供了可让字符串转换为数值的**ivs-s-parseNum()**.<br>
For instance, convert a string type into a number type in scss is not allowed, and 'ivs-s-parseNum' of ivscss-tools can do it. 

如果你觉得总是要确认使用哪个类型接口很麻烦，别担心，工具库还提供了集合版接口**ivs-toNum()**，你只需要传值即可，无需进行判断该传入的值该是字符串还是列表。

❗ 小提示：
这个工具库使用的是node-sass而非dart-sass，若你是使用**[dart-sass](https://sass.bootcss.com/dart-sass)**，可以去官网上了解如何兼容此文件。

## 安装
```shell
npm i ivscss-tools
```

## 🛠 API
✔ 详细使用方法介绍，已经放到语雀上啦。<br>
请戳这里 **[ivscss-api](https://www.yuque.com/sanday/vq00su/pzv6z9)**

以下是所有接口及文件介绍：

### ⭐_core.scss
> 核心接口：一些集合版的接口

- [ivs-toNum($val)](https://www.yuque.com/sanday/vq00su/cs72hb)
	- 转数值
		- list ✔
		- string ✔
	- 若是列表则会将列表项连接起来
	- 返回一个数值
- [ivs-toStr($val)](https://www.yuque.com/sanday/vq00su/zpl1f3)
	- 转字符串
		- list ✔
		- number ✔
	- 若是列表则会将列表项连接起来
	- 返回一个字符串
- [ivs-toList($str)](https://www.yuque.com/sanday/vq00su/kmex31)
	- 转列表
		- string ✔
		- number ✔
		- map ✔
	- map是获取所有value值
	- 字符串和数值会进行分割
	- 返回处理后的值
- [ivs-reverse($val)](https://www.yuque.com/sanday/vq00su/ki9sfo)
	- 翻转字符串、列表、数值
		- list ✔
		- string ✔
		- number ✔
	- 返回处理后的值
- [ivs-remove($val, $idx)](https://www.yuque.com/sanday/vq00su/hyg3rr)
	- 通过索引删除某元素
		- list ✔
		- string ✔
		- number ✔
		- map ✔
	- map是根据key值
	- 返回处理后的值
- [ivs-remove-v($val, $v, $q)](https://www.yuque.com/sanday/vq00su/oprilz)
	- 通过删除某个值，$q为多少个
		- list ✔
		- string ✔
		- number ✔
	- 返回处理后的值
- [ivs-splice($val, $start, $end)](https://www.yuque.com/sanday/vq00su/plen5d)
	- 剪切
	- $start起始点（含） $end终止点（含）
		- string ✔
		- list ✔
	- 返回列表
		- 剪切后的左边片段
		- 右边片段
		- 被剪切的片段
- [ivs-splice-q($val, $start, $q)](https://www.yuque.com/sanday/vq00su/tnk1gn)
	- 和上面区别在于$0q是多少个
		- string ✔
		- list ✔
	- 返回列表
		- 剪切后的左边片段
		- 右边片段
		- 被剪切的片段

### list
[戳链接](https://www.yuque.com/sanday/vq00su/lqs4m1)


> **Tip** 丨 因为scss里列表的特殊性，所以只要是传列表值。都是放最后面。

- ivs-l-parseNum($list);
	- 列表转数值
- ivs-l-parseStr($list);
	- 列表转字符串
- ivs-l-mergeMultiple($list);
	- 合并多个列表
- ivs-l-strToNum($list);
	- 字符串列表转为数值列表
- ivs-l-removeItemByIndex($idx, $list);
	- 通过索引值删除某个列表项
- ivs-l-removeFirstItem($list);
	- 删除列表的第一项
- ivs-l-removeLastItem($list);
	- 删除列表的末尾项
- ivs-l-removeItemByValue($v, $q, $list);
	- 删除列表中的某个值
- ivs-l-reverse($list)
	- 翻转列表
- ivs-l-splice($list)
	- 剪切列表

### map
[戳链接](https://www.yuque.com/sanday/vq00su/nyibpm)
- ivs-m-handle($way, $map, $params)
	- 映射的连续操作
	- $way可选项:get/has
- ivs-m-merge($map, ...)
	- 合并多个map 
	- 返回一个map
- ivs-m-remove($val)
	- 删除含有某个val值项
	- 返回一个新的map

### number
[戳链接](https://www.yuque.com/sanday/vq00su/dvmarc)
- ivs-n-parseList($num)
	- 数值转列表
- ivs-n-parseStr($str)
	- 数值转字符串
	- （没什么技术含量）
- ivs-n-removeItemByIndex($num, $idx)
	- 通过索引值删除数值
	- （有点没意义）
- ivs-n-removeItemByVal($num, $v, $q)
	- 删除一个或多个数值中某个数字
	- （有点没意义）

### math
[戳链接](https://www.yuque.com/sanday/vq00su/sf6s4p)
- ivs-math-pow($num, $q)
	- 数值的几次幂

### string
[戳链接](https://www.yuque.com/sanday/vq00su/foxxs0)
- ivs-s-removeItemByIndex($str, $idx)
	- 通过索引值删除字符串的字段
- ivs-s-removeItemByValue($str, $v, $q:1)
	- 通过索引值删除一次或多次字符串出现的某个单词
- ivs-s-reverse($str)
	- 翻转字符串
- ivs-s-splice($str, $start, $end)
	- 剪切字符串
- ivs-s-splice-q($str, $start, $q)
	- 剪切字符串
- ivs-s-parseList($str)
	- 分割字符串转列表
- ivs-s-parseNum($str)
	- 分割字符串转数值

### _error.scss
[error](https://www.yuque.com/sanday/vq00su/xvagbe)
- ivs-error($code)
	- 错误匹配器

### _config.scss
[config](https://www.yuque.com/sanday/vq00su/lz6wdx)
- 配置某些信息，如错误提示

### _comm.scss
[comm](https://www.yuque.com/sanday/vq00su/qxodo5)
- ivs-isDualList($list...)
	- 双重列表清除
	- 当你的列表出现难以传值的错误时，可以加上，在你传值那列表要写成$list...形式

### ivscss-tools.scss
[ivscss-tools](https://www.yuque.com/sanday/vq00su/os82lr)


## 🌠 后记
以上便是所有接口啦，祝君使用愉快~

今后有空会继续完善的~

我的另一个开源scss函数库。<br>
This is my another project.
**ivcss** 让sass书写更简单的小型函数库。Writing scss code more ease.
→
[ivcss](https://github.com/Sandaydi/ivcss)


