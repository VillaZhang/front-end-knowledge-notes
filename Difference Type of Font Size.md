##　Html 字体大小单位 px em pt
网页上定义字体大小有常见三种单位，px、em、pt

**px**

px是pixel缩写，是基于像素的单位.在浏览网页过程中，屏幕上的文字、图片等会随屏幕的分辨率变化而变化，一个100px宽度大小的图片，在800×600分辨率下，要占屏幕宽度的1/8，但在1024×768下，则只占约1/10。所以如果在定义字体大小时，使用px作为单位，那一旦用户改变显示器分辨率从800到1024，用户实际看到的文字就要变“小”（自然长度单位），甚至会看不清，影响浏览。 

**em**

em：即％，是相对单位，是一个相对长度单位，最初是指字母M的宽度，故名em。现指的是字符宽度的倍数，用法类似百分比，如：0.8em, 1.2em,2em等。通常1em=16px。，一般用来测量长度的通用单位(例如元素周转的页边空白和填充),当用于指定字体大小时,em单位是指父元素的字体大小。

在一个页面上给定了一个父元素的字体大小,这样就可以通过调整一个元素来成比例的改变所有元素大小.它可以自由缩放,比如用来制作可伸缩的样式表。

**pt**

PT是point(磅)缩写，是一种固定长度的度量单位,大小为1/72英寸。如果在web上使用pt做单位的文字，字体的大小在不同屏幕（同样分辨率）下一样，这样可能会对排版有影响，但在Word中使用pt相当方便。因为使用Word主要目的都不是为了屏幕浏览，而是输出打印。当打印到实体时，pt作为一个自然长度单位就方便实用了：比如Word中普通的文档都用“宋体 9pt”，标题用“黑体 16pt”等等，无论电脑怎么设置，打印出来永远就是这么大。

**转换**
 
浏览器的默认字体高都是16px，所以未经调整的浏览器在显示1em=16px，也就是说1px=0.0625em。为了简化font-size的换算，可以在css中的body中先全局声明font-size=62.5%，也就是定义了默认字体大小为16px*0.625=10px,子元素会继承父级元素的字体大小，于是1em=10px，所以12px=1.2em。px与em的转换通过10就可以得来。但是定义font-size=0.625em或者直接定义12px，这是没有效果的，


此外有一点必须要注意，IE处理汉字时，对于浮点的取值精确度有限，由以上方法得到的12px(1.2em)大小的汉字在IE中并不等于直接用12px定义的字体大小，而是稍大一点。只要将62.5%换成63%就可以了。
 
pt和px的换算公式也比较简单，pt=px乘以3/4。
