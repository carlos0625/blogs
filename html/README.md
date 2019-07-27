# HTML基础

## 标签

### 标题与段落

`<h1></h1>`到`<h6></h6>` : 分别表示1~6级标题

`<p></p>` : 段落标签

### 文本修饰标签

`<strong></strong>` : 加粗

`<em></em>`、`<i></i>` : 斜体

`<sup></sup>` : 上标

`<sub></sub>` : 下标

`<ins></ins>` : 下划线

`<del></del>` : 删除线

### 图片标签与图片属性

`<img/>` : 图片标签。属性如下:
* `src` : 图片的位置
* `alt` : 加载不出来应该显示的提示信息
* `title` : 当鼠标移动到标签上时提示的信息。所有标签都有的属性。
* `width` : 图片的宽度
* `height` : 图片的高度

### 引入文件的地址

* 绝对路径

 * Windows: `盘符:/目录1/...`
 * Linux/Unix: `/目录1/目录2/...`

* 相对路径: 相对于当前文件来引入的

  * `.`: 当前目录
  * `..`: 上一级目录

### 跳转链接

`<a></a>`: 链接标签。常用属性:

* `href`: 链接的地址
* `target`: 
  * `_self`: 当前页直接跳转
  * `_blank`: 新建一个标签页

`<base/>`: 改变`<a></a>`标签的默认行为，通常写在`<head></head>`中，`<base target="_blank"/>`，使得所有的`<a></a>`标签都是新建新标签页实现跳转。

### 跳转锚点

跳转锚点指在页面内部进行跳转。实现方式两种:

* `<a></a>` `#` + id
* `<a></a>` + `#` + `<a></a>` + name

### 特殊字符

常用特殊字符:

特殊字符 | 含义 | 代码
-- | -- | --
` `| 空格 | `&nbsp;`
© | 版权 | `&copy;`
® | 注册商标 | `&reg;`
< | 小于号 | `&lt;`
`>` | 大于号 | `&gt;`
& | 和号 | `&amp;`
￥ | 人民币 | `&yen;`
° | 摄氏度 | `&deg;`

### 无序列表

`<ul></ul>`、`<li></li>`

`type`属性: `square`、`circle`等等，改变前面的标记。

### 有序列表

`<ol></ol>`、`<li></li>`

`type`属性: `1`、`a`、`i`等等，改变前面的标记。

### 定义列表

* `dl`: 定义列表
* `dt`: 标题
* `dd`: 列表项

列表之间可以互相嵌套，形成多层级的列表。

### 表格标签

`table`、`tr`、`td`、`th`、`caption`

语义化标签: `<tHead></tHead>`、`<tBody></tBody>`、 `<tFood></tFood>`，`tHead`和`tFood`在一个`table`中只能出现一次，而`tBody`可以出现多次。

#### 表格的属性

* `border`: 边框

* `cellpadding`: 单元格内的填充空间

* `cellspacing`: 单元格间的空间

* `colspan` : 合并列单元格

* `rowspan` : 合并行单元格

* `align` : 左右对齐方式， left, center, right

* `valign` : 上下对齐方式，top, center, bottom

### 表单标签

`<form></form>` 和 `<input />`

属性`type`: text、password、reset、submit、button、checkbox、radio、file

`<textarea></textarea>` 多行文本框

`<selcet></selcet>` 下拉菜单，配合`<option></option>`使用，属性`size`为显示几个选项

`<label></label>`: 辅助标签

`<div></div>`块标签: 做一个区域划分的块

`<span></span>`: 内联标签，用于修饰文字