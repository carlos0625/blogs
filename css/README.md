# CSS重点知识

### 颜色表示法

* 单词表示法

* RGB表示法: `rgb(x, y, z)`，x、y、z的范围为0~255

* 十六进制表示法: `#xxxxxx`，x为十六进制数

### CSS选择器

关于CSS选择器，可以参考掘金上的一篇文章，[点击这里](https://juejin.im/entry/587c458d128fe1006b002fe9).

#### ID选择器

通过id属性找到映射关系。语法: `#id { ... }`。id值在一个页面中是唯一的。id的命名要求只能由数字、字母、下划线、-组成，而且不能以数字开头，命名方式可以采用驼峰式、下划线式、短线写法(W3C推荐)。

#### 类选择器

通过class属性来映射一组标签。语法: `.class-name { ... }`。如果某个标签有多个class，使用空格来分隔。

#### 标签选择器

通过标签名来映射一组标签。语法: `标签名 { ... }`。又叫元素选择器。使用场景:

* 去掉某些标签的默认样式

* 复杂的选择器，如层次选择器`ul li {...}`

#### 群组选择器

可以通过添加逗号的方式给多个不同的选择器设置相同的样式，达到代码的复用。语法: `选择器1, 选择器2, 选择器3, ... { ... }`

#### 通配选择器

通配选择器即所有标签，语法: `* { ... }`。尽量避免使用通配选择器，因为会给所有的标签添加样式。应用场景:

* 去掉所有标签的默认样式

#### 层次选择器

* 后代选择器，如`ul li { ... }`、`#list li { ... }`，这样会对所有的后代都会生效。

    ```html
    <ul>
        <li>
            <ol>
                <li></li>
                <li></li>
            </ol>
        </li>
        <li></li>
        <li></li>
    </ul>

    <ol>
        <li></li>
        <li></li>
    </ol>
    ```

    ```css
    ul li {
        border: 1px red solid;
    }
    ```

    `ul`中的所有`li`包括`li`中的`li`都会被选中。

* 父子选择器，如`ul > li { ... }`

    ```css
    ul > li {
        border: 1px red solid;
    }
    ```

    只有`ul`的下一层中的`li`会被选中

* 兄弟选择器，如`ul ~ ol { ... }`，找到`ul`同一层的下面的所有`ol`标签，若`ol`标签在`ul`标签前面，则不会被选中。

* 相邻选择器，如`ul + ol { ... }`，只会找`ul`同一层下面的相邻的`ol`标签，如果与`ul`相邻的不是`ol`则没有用

#### 属性选择器

寻找带有特定属性的标签，使用属性选择器: `标签[属性名] { ... }`。如`div[class] {...}`就是选择所有带有class属性的div标签。

* 精确匹配: `标签[属性名=属性值] { ... }`，如`div[class=search] {...}`

* 开始匹配: `标签[属性名*=属性值] { ... }`，如`div[class*=search] {...}`

* 结束匹配: `标签[属性名$=属性值] { ... }`，如`div[class$=search] {...}`

* 组合属性: `标签[属性名1=属性值][属性名2=属性值] { ... }`，如`div[class][id] {...}`

#### 伪类选择器

语法: `标签名:伪类 {...}`。两个冒号代表伪元素。

* `:link`: 访问前的样式(只能给`<a></a>`标签加)

* `:visited`: 访问后的样式(只能给`<a></a>`标签加)

* `:hover`: 鼠标移入时的样式(可以给所有的标签加)

* `:active`: 鼠标按下时的样式(可以给所有的标签加)

* `:after`、`before`: 同通过伪类的方式给元素添加一些文本内容。与`content`样式结合使用。

* `:checked`、`:disabled`、`focus`: 用于表单元素

* 结构性伪类选择器: `标签:伪类 { ... }`

    * nth-of-type() : 括号中可以写0~n，1代表第一个，2代表第二个，n代表所有，2n+1代表奇数行，2n代表偶数行，渲染所有所用标签的选中项。

    * first-of-type : 第一个

    * last-of-type : 最后一个

    * only-of-type : 如果元素唯一，即只有一个，则会应用样式。

    * nth-child() : 括号中可以写一个数值，在所用标签的集合中，如果标签和数值对应的标签是一致的，那么才能渲染出来。

一般网站都只会对`a`标签设置`a {}`和`a:hover {}`。

### 选择器优先级

参考[这篇博客](https://www.cnblogs.com/my--sunshine/p/6872224.html)，CSS选择器的优先级如下：

`@important` > `内联样式表` > `id选择器` > `属性、类、伪类选择器` > `标签` > `通配符` > `继承`

### 背景样式

* `background-color` : 背景颜色

* `background-image` : 背景图片, `url(...)`

* `background-repeat` : 背景图片的平铺方式

    * `repeat-x`
    * `repeat-y`
    * `repeat`
    * `no-repeat`

* `background-position` : 背景图片的位置

    * x: 数值 | left, center, right | 百分比
    * y: 数值 | top, center, bottom | 百分比

* `background-attachment` : 背景图片的滚动方式

    * scroll : 随着元素滚动。(背景位置随元素偏移)
    * fixed : 与浏览器偏移量固定，不滚动。(背景位置随浏览器偏移)

### 边框样式

* `border-style` : 边框的样式

  * 虚线: dashed
  * 实线: solid
  * 双边: double
  * 点线: dotted

* `border-width` : 边框的宽度

* `border-color` : 边框的颜色

当然也可以为某一条边设置：`border-left`、`border-right`、`border-top`、`border-bottom`

透明颜色: `transparent`

### 字体

#### font-family

* 英文字体: Arial, 'Time New Roman`

* 中文字体: 宋体，微软雅黑

中文字体可以作用于中文和英文，而英文字体只作用于英文，对中文无效。

衬线体和非衬线体。

设置多字体是为了防止计算机操作系统中不支持某些字体，使用逗号隔开多个字体，将会从前到后进行识别，如果不能识别就向后识别，直到可以识别并作为网页的默认字体。而是否使用引号，则取决于该字体的名称中是否有空格。

#### font-size

* 单词表示法: xx-small、x-small、small、medium、large、x-large、xx-large，不推荐使用

* 像素表示法: 16px、32px，一般设置为偶数大小。

#### font-weight

* 单词表示法: lighter、normal、bold、bolder

* 数值表示法: 100 ~ 900

#### font-style

* 正常模式: normal

* 斜体: italic、oblique(用的比较少)。区别在于italic表示所有带有倾斜属性的字体可以设置，而oblique在没有倾斜属性的字体也可以设置。

### 段落样式

* text-decoration : 文本修饰

    * underline: 下划线
    * overline: 上划线
    * line-through: 删除线
    * none: 没有样式

    可以添加多个值，使用空格隔开，如将下划线、上划线、删除线全部加上: `text-decoration: overline line-through underline`

* text-transform : 大小写(针对英文)

    * lowercase : 小写 
    * uppercase : 大写
    * capitalize : 首字母大写

* text-indent : 文本缩进

    首行缩进。可以使用em作为单位，这是一个相对单位，与一个字的单位相同。当有英文时，很难对齐。

* text-align : 文本对齐

    * left : 左对齐
    * center : 居中
    * right : 右对齐
    * justify : 两端对齐

* line-height : 定义行高

    行高由三部分组成: 上边距、字体大小、下边距。默认行高不是固定值，而是变化的，根据当前字体的大小在不断地变化。值可以是像素，也可以是比例，跟文字大小成比例。

* letter-spacing : 字体间距

* word-spacing : 词的间距(针对英文而言，对中文没有用。)

* 强制折行(针对英文)

    当一个英文单词或者数字太长，长度大于容器宽度，默认不会进行折行。

    * word-break: break-all (非常强烈的折行)

    * word-wrap: break-word (不是那么强烈的折行)

### 复合样式

* background: background-color background-image background-repeat background-position background-attachment

* border: border-size border-color border-style

* border-left, border-right, border-top, border-bottom

* font: font-weight font-style font-size(/line-height) font-family

    至少包含font-size和font-family，而且要保证二者的顺序。

要么写单一样式，要么写符合样式。如果混合使用，则需要先写复合样式，再写单一样式。

### CSS样式继承

默认情况下，文字相关的样式可以被继承，布局相关的样式不能被继承。如果想让样式继承，可以使用inherit属性值。

### CSS优先级

#### 相同样式优先级

当设置相同样式时，后面设置的优先级高，但不建议重复设置同一样式。

#### 内部样式与外部样式

内部样式与外部样式优先级相同，如果都设置了相同样式，那么后写的引入方式优先级高。先后顺序看style标签的先后顺序。

#### 单一样式优先级

内联样式 > id选择器 > 类选择器 > 元素选择器(标签) > * > 继承

样式/选择器 | 权重
-- | --
内联样式 | 1000
id | 100
class | 10
tag | 1

#### !important

提升样式到最高优先级，非规范方式，不建议使用。**但是不能针对继承的属性提高优先级**。

#### 群组选择器优先级

群组选择器优先级看书写的先后顺序。

#### 层次选择器优先级

### CSS盒模型

CSS盒模型共有个内容，分别是内容、内边距、边框和外边距

* 内容，这个部分由`width`和`height`定义大小

* 内边距，这个部分由`padding`定义，包含四个方向即上下左右，其中各个方向都可以有自己的定义，即`padding-top`、`padding-bottom`、`padding-left`、`padding-right`。对于`padding`，这是一个复合样式，可以写一个值，两个值或四个值:

    * 一个值: `padding: value(上下左右)`
    * 两个值: `padding: value1(上下) value2(左右)`
    * 四个值: `padding: top right bottom left`

* 边框，这个部分由`border`定义。`border`是一个复合样式，可以分为三个小的样式: `border-width`、`border-color`、`border-style`。同样，包含上下左右四块: `border-left`、`border-right`、`border-top`、`border-bottom`。

* 外边距，这个部分由`margin`定义，包含上下左右四个方向，即`margin-top`、`margin-bottom`、`margin-left`、`margin-right`。对于`margin`，这是一个复合样式，可以写一个值，两个值或四个值:

    * 一个值: `margin: value(上下左右)`
    * 两个值: `margin: value1(上下) value2(左右)`
    * 四个值: `margin: top(上) right(右) bottom(下) left(左)`

注意事项:

* 背景色会填充到除margin以内的区域，即包含border、padding、content。背景图片可以修改填充位置。

* 文字只能在content区域。

* padding不能为负数，而margin可以为负数。

#### box-sizing

盒尺寸，可以改变盒子模型的展示形态。取值:

* content-box(默认值): 使得width和height作用与content部分

* border-box: width和height作用于content、padding、border

应用场景:

* 不用再去计算一些值

* 解决一些百分比的问题

#### margin叠加

当给两个盒子同时添加上下外边距时，就会出现叠加问题，只有上下边距有，而左右边距不会出现。上面盒子的下边距和下面盒子的上边距会进行叠加，而不是累加，取二者中的大者作为叠加的边距。

解决方案:

* BFC规范

* 想办法只给一个元素添加间距

#### margin传递

margin传递问题只会出现在嵌套的结构中，且只有margin-top会有传递的问题，其他三个方向是没有传递问题的。

解决方案:

* BFC规范

* 给父容器加上边框

* 给父容器加padding，而不是给子元素加margin，并修改父元素的height

在嵌套结构中，内部元素的margin值是指内部元素的border针对父元素的content进行拉开间距。

#### margin自适应

使用`margin-left: auto`和`margin-right: auto`实现左右居中。无法实现上下居中。

在宽高不设置的时候对盒子模型的影响。对于div这类标签，在不设置宽度的时候，总是会充满父容器，而且是margin、border、padding、content四个加起来充满父容器。但是不设置高度，一般只会包含到标签里的实际内容的高度。

### 标签分类

#### 按类型分类

1. `block`: 块(`div`, `p`, `ul`, `li`, `h1`~`h6`, ...)
    * 独占一行
    * 支持所有的样式
    * 不写`width`属性时宽度和父元素相等。
    * 所占区域是一个矩形

2. `inline`: 内联(`span`, `a`, `em`, `strong`, `img`, ...)
    * 挨在一行
    * 有些样式不支持，如`width`、`height`、`margin`、`padding`
    * 不写宽度时宽度由内容决定
    * 所占不一定是一个矩形
    * 内联标签之间会有空隙，由换行或空格产生，可以通过设置`body`的`font-size`为`0`以及内联标签的`font-size`不为零，就可以将空隙删除。

3. `inline-block`: 内联块(`input`, `select`, `checkbox`, ...)
    * 保持矩形结构，但是不独占一行
    * 标签之间有空隙
    * 支持宽高等样式

#### 按内容分类

1. Flow: 流内容

2. Metadata: 元数据

3. Sectioning: 分区

4. Heading: 标题

5. Phrasing: 措辞

6. Embededded: 嵌入的

7. Interactive: 互动的

#### 按显示分类

1. 替换元素: 浏览器根据元素的标签和属性，来决定元素的具体显示内容。如`img`、`input`，通过属性的方式来确定显示的内容。

2. 非替换元素: 将内容直接告诉浏览器，将其显示出来。

### 显示框类型

显示框类型通过`display`样式来设置:

* block

* inline

* inline-block

* none: 隐藏

注意，`display: none;`于`visibility: true;`是有区别的。前者是不占空间的隐藏，而后者虽然隐藏，但是仍然占着空间。

### 标签嵌套规范

#### 组合规范

* ul, li

* dl, dt, dd

* table, tr, td

#### 通用规范

* 块标签可以嵌套内联标签。

* 块标签不一定能嵌套块标签，绝大多数情况下可以，但有一些特殊情况。如`p`标签内不能再嵌套块标签，只能嵌套内联标签。

    ```html
    <p>
        <div></div>  <!--这是错误的-->
    </p>
    ```

* 内联标签不能嵌套块标签。但是也有特殊的，如`a`标签内可以嵌套块标签。注意，`a`标签中不能再嵌套`a`标签。

    ```html
    <a href="#">
        <div></div>
    </a>
    ```

### 溢出隐藏

overflow的取值:

* visible: 默认值，内容多时直接超出容器显示

* hidden: 隐藏，到了边界进行裁切

* scroll: 出现纵向和横向滚动条，当内容溢出可以进行滚动显示

* auto: 自适应，当内容多的时候出现滚动条，内容少时不显示滚动条

可以分x轴和y轴去写，即`overflow-x`和`overflow-y`。

### 透明度与手势

* `opacity`: 透明度, 0(透明) ~ 1(不透明)，所有子内容也会透明。

* `background: rgba(red, green, blue, opacity)`，只让背景透明。

* `cursor`: 手势

    * default: 默认箭头
    * 鼠标手势(pointer, help, move, ...)
    * 自定义手势: 准备图片(`.cur`、`.ico`), 使用样式: `cursor: url(...), auto;`来定义。

### 最大最小宽高

`min-width`,`min-height`: 设置的值为value，效果为当内容没有溢出的时候，宽度或高度为value，当溢出的时候width或height随内容的增加而增加。即可以理解为`>=value`。

`max-width`,`max-height`: 设置的值为value，效果为当内容没有溢出的时候，宽度或高度为随内容的增加而增加，当溢出的时候width或height值不变，等于value。即可以理解为`<=value`。

注意，百分比单位是用父容器的大小来计算的，不是根据祖先元素来换算的。

### CSS默认样式

有些标签有默认样式，而有些标签没有默认样式。

没有默认样式的标签: `div`、`span`、...

有默认样式的标签:

* `body`: `margin: 8px;`
* `h1`: `margin: 21.440px 0; font-weight: bold;`
* `p`: `margin: 16px 0`
* `ul`: `margin: 16px 0; padding-left: 40px; list-style: disc`
* `a`: `text-decoration: underline;`
* ...

取消默认样式，重置默认样式：

* `* { margin: 0; padding: 0; }`。不用考虑哪些标签有默认的`margin`和`padding`。性能上有一点点影响。
* `ul { list-style: none; }`
* `a { text-decoration: none; color: #999 }; a:hover { text-decoration: underline; color: red; }`
* `img { vertical-align: bottom; }`。图片默认是一个inline标签。下方对齐对的是文字的基线，而不是文字的底线，因此图片跟容器的底部有一些空隙。当然还可以使用: `img { display: block; }`。

### float浮动

**文档流**: 文档中可显示对象在排列时所占用的位置。

**float特性**: 加浮动的元素，会脱离文档流，会延迟父容器靠左或靠右排列，如果之前已经有浮动的元素，会挨着浮动的元素进行排列。

float取值: `left`、`right`、`none(默认)`。

**浮动的注意事项**

* 只会影响后面的元素

* 内容默认提升半层

* 默认宽度根据内容决定

* 换行排列

* 主要给块元素添加，也可以用于内联元素。

**清除浮动**

清除浮动使用`clear`属性。

标签上下书写:

* left
* right
* both

标签嵌套书写: 内部浮动，脱离文档流，导致父容器中没有子元素占空间，然后就瘪了。

* 固定宽高: 不推荐。将父元素的高度写死。
* 父元素浮动: 不推荐。会影响父容器后的元素。
* `overflow: hidden`: BFC规范，如果有子元素想溢出，会截掉溢出的部分。
* `display: inline-block`: BFC规范，但是会影响父元素后面的元素
* 使用定位: 不推荐
* 在父容器中再写一个空元素，并设置宽高来撑开父元素。不推荐
* :after : 推荐，是空标签的加强版，目前各大公司的做法。给父容器加上伪类选择器`:after`，并加入样式`{ content: ""; clear: both; display: block; }`。之所以加上`display: block;`是因为添加的内容是一个内联的内容，而`clear`标签对内联的样式不起任何作用，只对块标签起作用。