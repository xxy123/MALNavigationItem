MALNavigationItem
=================

可定制的navagationitem
    当我们使用系统的方法设置navigationItem的leftItem或者rightItem时，我们会
发现item位置会有偏差(左边的偏右，右边的偏左)。当设置navigationItem的titleView时，
会发现图片被拉伸。因此我对系统的设置方法做了一个简单的封装，可以方便的设置navigationItem
的leftItem，titleView,rightItem并可以自主控制item的偏移量。

<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: Menlo;"><span style="line-height: 1.5; font-family: 'Heiti SC Light';">使用方法</span><span style="line-height: 1.5;">:</span></p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: Menlo;"><span style="font-family: 'Heiti SC Light';">一、将</span>demo<span style="font-family: 'Heiti SC Light';">里的</span>customBarItem<span style="font-family: 'Heiti SC Light';">文件夹加入工程。</span></p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: Menlo;"><span style="font-family: 'Heiti SC Light';">二、在要设置的文件里加入头文件</span>#import "UINavigationItem+CustomItem.h"</p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: 'Heiti SC Light';">三、设置</p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: Menlo;">&nbsp; &nbsp; 1<span style="font-family: 'Heiti SC Light';">、通过文字设置</span>item</p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: Menlo; color: rgb(209, 47, 27);"><span style="color: #000000">&nbsp; &nbsp; </span>[self.navigationItem setItemWithTitle:@"<span style="font-family: 'Heiti SC Light';">自定义</span>item" textColor:[UIColor redColor]<span style="color: #000000"> fontSize:16 itemType:center];</span></p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: 'Heiti SC Light';"><span style="font-family: Menlo;">&nbsp; &nbsp; </span>参数说明：①、文字内容<span style="font-family: Menlo;"> </span>②、文字颜色<span style="font-family: Menlo;"> </span>③、字体大小<span style="font-family: Menlo;">&nbsp;</span></p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: Menlo;">&nbsp; &nbsp; <span style="font-family: 'Heiti SC Light';">④、</span>item<span style="font-family: 'Heiti SC Light';">的格式</span> left<span style="font-family: 'Heiti SC Light';">对应</span>leftItem&nbsp; center<span style="font-family: 'Heiti SC Light';">对应</span>titleView &nbsp; right<span style="font-family: 'Heiti SC Light';">对应</span>rightItem</p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: Menlo;">&nbsp; &nbsp; 2<span style="font-family: 'Heiti SC Light';">、通过图片设置</span>item</p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: Menlo; color: rgb(209, 47, 27);"><span style="color: #000000">&nbsp;&nbsp; &nbsp; </span>[self.navigationItem setItemWithImage:@"test1.png" size:CGSizeMake(48/2, 26/2) itemType:left]<span style="color: #000000">;</span></p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: 'Heiti SC Light';"><span style="font-family: Menlo;">&nbsp; &nbsp; </span>参数说明：①、图片名称<span style="font-family: Menlo;"> </span>②、图片尺寸<span style="font-family: Menlo;"> </span>③、同上</p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: Menlo;">&nbsp; &nbsp; 3<span style="font-family: 'Heiti SC Light';">、为</span>item<span style="font-family: 'Heiti SC Light';">添加点击事件</span></p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: 'Heiti SC Light';"><span style="font-family: Menlo;">&nbsp;&nbsp; &nbsp; &nbsp; 1</span>、<span style="font-family: Menlo;">2</span>两种设置方法均会返回一个<span style="font-family: Menlo;">CustomBarItem</span>实例，获得这个实例进行事件添加</p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: Menlo; color: rgb(209, 47, 27);"><span style="color: #000000">&nbsp; &nbsp; &nbsp; CustomBarItem *rightItem = </span>[self.navigationItem setItemWithImage:@"test.png" size:CGSizeMake(39/2, 40/2) itemType:right]<span style="color: #000000">;</span></p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: Menlo; color: rgb(209, 47, 27);"><span style="color: #000000">&nbsp; &nbsp; &nbsp; </span>[rightItem addTarget:self selector:@selector(search) event:(UIControlEventTouchUpInside)]<span style="color: #000000">;</span></p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: Menlo;">&nbsp; &nbsp; 4<span style="font-family: 'Heiti SC Light';">、设置</span>item<span style="font-family: 'Heiti SC Light';">偏移量</span></p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: Menlo;">&nbsp;&nbsp; &nbsp; &nbsp; <span style="font-family: 'Heiti SC Light';">同</span>3<span style="font-family: 'Heiti SC Light';">先拿到</span>CustomBarItem<span style="font-family: 'Heiti SC Light';">实例然后进行设置</span></p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: Menlo;">&nbsp;&nbsp; &nbsp; &nbsp; <span style="color: #d12f1b">[rightItem setOffset:10]</span>;//<span style="font-family: 'Heiti SC Light';">数值越大，则</span>leftItem<span style="font-family: 'Heiti SC Light';">越靠左</span>&nbsp; rightItem<span style="font-family: 'Heiti SC Light';">越靠右</span>&nbsp; <span style="font-family: 'Heiti SC Light';">默认值为</span>10</p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: Menlo;">&nbsp; &nbsp; 5<span style="font-family: 'Heiti SC Light';">、当用文字设置</span>item<span style="font-family: 'Heiti SC Light';">时设置</span>item<span style="font-family: 'Heiti SC Light';">的尺寸</span></p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: Menlo; color: rgb(209, 47, 27);"><span style="color: #000000">&nbsp;&nbsp; &nbsp; &nbsp; </span>[rightItem setTitleViewSize:CGSizeMake(width, height)]<span style="color: #000000">;</span></p>
<p style="margin: 0px; font-size: 11px; line-height: normal; font-family: 'Heiti SC Light';">四、<span style="font-family: Menlo;">demo</span>里有具体的例子相信大家一看就明白了。<span id="_editor_bookmark_start_0" style="display: none; line-height: 0px;">‍</span></p>