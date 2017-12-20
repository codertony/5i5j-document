

1. [前言](#前言)
2. [使用方法](#使用方法)
3. [表单](#表单)
	1. [输入框](#输入框)
		1. [普通输入框](#普通输入框)
		2. [组合输入框](#组合输入框)
	2. [下拉菜单和自动补全](#下拉菜单和自动补全)
		3. [自动补全输入框](#自动补全输入框)

# 前言

# 使用方法

# 表单

## 输入框
参考页 [demo>表单>输入框][1]
### 普通输入框

HTML代码

``` html?linenums
<input type="text" class="input-xs" style="" />
```
### 组合输入框
![][2]
```html?linenums
 <div class="input-group input-daterange" >
  	<input class="form-control input-xs"  type="text" placeholder="输入">
  		<span class="input-group-addon addon-xs">
                ~
          </span>
  	<input class="form-control input-xs"  type="text" placeholder="输入">
</div>
```

## 选择框
[demo>表单>选择框][3]
### 行内小型多选框 
![][4]
``` html?linenums
	<div class="checkbox-inline input-xs">
    <label>
      <input name="check1" type="checkbox" class="ace">
      <span class="lbl"> choice 5</span>
    </label>
  </div>
  <div class="checkbox-inline input-xs">
    <label>
      <input name="check1" type="checkbox" class="ace">
      <span class="lbl"> choice 6</span>
    </label>
  </div>
  <div class="checkbox-inline input-xs">
    <label>
      <input name="check1" type="checkbox" class="ace">
      <span class="lbl"> choice 7</span>
    </label>
  </div>
  
```
### 行内小单选框
![][5]
``` html?linenums
	<div class="checkbox-inline input-xs">
    <label>
      <input name="check1" type="checkbox" class="ace">
      <span class="lbl"> choice 5</span>
    </label>
  </div>
  <div class="checkbox-inline input-xs">
    <label>
      <input name="check1" type="checkbox" class="ace">
      <span class="lbl"> choice 6</span>
    </label>
  </div>
  <div class="checkbox-inline input-xs">
    <label>
      <input name="check1" type="checkbox" class="ace">
      <span class="lbl"> choice 7</span>
    </label>
  </div>
  
```

## 下拉菜单和自动补全
[demo>表单>下拉菜单和自动补全][6]
### 自动补全输入框
![][7]


``` html?linenums
<input id="auto" class="input-xs" type="text" listWidth="300" mustAuto="false"/>
   //通过设置 mustAuto为"false"或者"true",来设置可否任意填写
   //如果mustAuto="false"则说明输入框可以任意填写，默认为true
   //listWidth属性表示下拉列表的宽度。

 <script>
	  $( "#auto" ).autocomplete({
		source: arrayData,//数组
		focus:function(event, ui){},//下拉菜单聚焦
		select:function(event, ui){},//下拉菜单选择
		open:function(event, ui){},//下拉菜单打开
		close:function(event, ui){}//下拉菜单关闭
	  });
</script>
```

### 自动补全+多个标签
![][8]
``` html?linenums
<div class="input-group blueTags" >
  <input type="text" name="tags" id="form-field-tags" value="mytag1,mytag2" >
</div >

 <script>
	  var tag_input = $('#form-field-tags');
      try {
        tag_input.tag({
          mustAuto:true,
          placeholder: "请输入",
          //source: ['tag 1', 'tag 2'],//静态数组
          source: autoSource
          //或者从数据库获取数据, 获取匹配query的数据
          /*source: function(query, process) {//远程数据传入方法
           $.ajax({
           url: 'remote_source.php?q='+encodeURIComponent(query),
           dataType:"json"
           })
           .done(function(result_items){
           process(result_items);
           });
           }*/
        });
        tag_input.data('tag').add('手动添加');//手动添加标签方法
        tag_input.data('tag').disable()//禁用
        tag_input.data('tag').able()//恢复
        tag_input.parent().width('auto');//宽度设定
        
      }
      catch (e) { //对ie的8以下不支持，ie8以上不稳定}
        
</script>
```
### 数组载入下拉菜单
![][9]
``` html?linenums
<select name="" id="selectReady"<>/select>

 <script>
	  var abc=[123,
          "abc",{
          name:"11",
          value:"33"
        },{
          name:"666",
          value:"888",
          data:{
            type:"银行"
          }
        },{
          value:"999",
          data:{
            type:"非银行"
          }
        },
      ];
      数组单元可以是数字，字符串，对象。
      对象必须有value属性,如果显示值和value值不一样，可以设置属性name;
            还可以设置属性data,
            选中后可以通过$('#selectReady').data('selectData')获得选中的option的data。
  $("#selectReady").selectReady(abc,'自定义空选择项').change(function(){
            console.log($(this).data('selectData'))
          });
       //默认空为"请选择"，如果不需要可以设置为false
</script>
```
### 多级联动下拉选择
![][10]
``` html?linenums
  <div id="element_id">
    <select class="province input-xs form-control" data-value="浙江省"></select>
    <select class="city input-xs form-control"></select>
    <select class="area input-xs form-control"></select>
  </div>
  
 <script>
	   $('#element_id').cxSelect({
     url: '../demo/dataText/cityData.json', // 如果服务器不支持 .json 类型文件，请将文件改为 .js 文件
      selects: ['province', 'city', 'area'],  // 数组，请注意顺序
      emptyStyle: 'none'
    });
</script>
```
## 文件上传
[demo>表单>文件上传][11]

![][12]
```html?linenums
<input id="auto" type="text" class="input-xs"/>
 <script>
  $( "#auto" ).autocomplete({
          source: arrayData//数组
        });
</script>
```
## 表单验证
[demo>表单>表单验证][13]
### 外部有星
![][14]
```html?linenums 
	<input vRequired="true" type="text" class="form-control input-xs" placeholder="必填项"/>
	vRequired="true"或者required="outerStar"
```
### 内部有星
![][15]
```html?linenums 
<input vRequired="innerStar" type="text" class="form-control input-xs" placeholder="必填项"/>
```
### 无星
![][16]
```html?linenums 
<input vRequired="noStar" type="text" class="form-control input-xs" placeholder="必填项"/>
```
### 日期
```html?linenums 
<input type="text" vType="date" class="form-control input-xs" placeholder="日期"/>
```
### 固定电话

```html?linenums 
<input type="text" vType="phone" class="form-control input-xs" placeholder="固定电话"/>
```
### 手机

```html?linenums 
	<input type="text" vType="mobile"  class="form-control input-xs" placeholder="手机"/>
```
### 邮箱

```html?linenums 
	<input type="text" vType="email" class="form-control input-xs" placeholder="邮箱"/>
```
### 银行卡号

```html?linenums 
<input type="text" vType="bankId" class="form-control input-xs" placeholder="银行卡号"/>
```
### 中文

```html?linenums 
<input type="text" vType="chinese" class="form-control input-xs" placeholder="只能输入中文"/>
```
### 数字
```html?linenums 
<input type="text" vType="number" class="form-control input-xs" placeholder="数字"/>
```
### 整数
```html?linenums 
<input type="text" vType="integer" class="form-control input-xs" placeholder="整数"/>
```
### 正数
```html?linenums 
 <input type="text" vType="plus" class="form-control input-xs" placeholder="正数"/>
```
### 非零正数 
```html?linenums 
 <input type="text" vType="plusNotZero" class="form-control input-xs" placeholder="非零正数"/>
```
### 字母 
```html?linenums 
 <input type="text" vType="plusNotZero" class="form-control input-xs" placeholder="非零正数"/>
```
### 金额 
```html?linenums 
 <input type="text" vType="money" class="form-control input-xs" placeholder="金额"/>
      最多保留小数点后两位  
```
### 手机和电话
```html?linenums 
<input type="text" vType="mobile"  class="form-control input-xs" placeholder="手机"/>  
```
### 数字和字母
```html?linenums 
<input type="text" vType="onlyLetterNumber" class="form-control input-xs" placeholder="数字和字母"/>
```
### 身份证
```html?linenums 
 <input type="text" class="form-control input-xs" vTypeFunc="chinaId" placeholder="身份证">
```
### 保留不同位的小数
```html?linenums 
 <input type="text" vType="decimal1" class="form-control input-xs" placeholder="保留一位小数"/>
 decimal1,2,3,4,5分别表示不同位的小数
```
### 字符长短匹配
```html?linenums 
<input minSize=5 vType="date" class="form-control input-xs" placeholder="最少5个字符"/>
<input maxSize=6 vType="date" class="form-control input-xs" placeholder="最多6个字符"/>
```
### mask 方法
```html?linenums 
 <input id="maskTest" type="text" placeholder="必填" name="name" class="input-xs" />
<script>
 $("#maskTest").mask("999-9999-99999", {placeholder: "aaa/bbbb/ccccc"});
</script>
```
##  隐藏显示的控制 
[demo>表单>隐藏显示的控制 ][17]
### select控制，无js
![][18]
```html?linenums 
 <select id="Ctrl1" showControl="#showArea1" showState="显示" class="form-control input-xs">
  ...
</select>
<div id="showArea1">
  我是一个被控制的区域。
</div>
showControl=控制对象的选择器，
 showState=显示条件，hideState=隐藏条件，这两个条件只能二选一。
```
### input(checkbox或radio)控制，无js
![][19]
```html?linenums 
<input type="checkbox" id="Ctrl2" showControl="#showArea2" showState=true />
    控制器
  <div id="showArea2" >
    我是一个被控制的区域。
  </div>
showControl=控制对象的选择器，
 showState=显示条件，选中为true,不选中为false
```
### select控制，有js

```html?linenums 
<div class="ctrSelect">
  <select class="ctr3 form-control input-xs">
    ...
  </select>
  <div class="showArea30">
    我是一个被控制的区域。
  </div>
  <div class="showArea31">
    我是一个被控制的区域。
  </div>
  <div class="showArea32">
    我是一个被控制的区域。
  </div>
</div>
<script>
$(".ctrSelect").showControl({//作用对象为包含控制器和被控制区域
    controlHandle:".ctr3",//控制器，可以是input和checkbox和radio
    controlFor:$(".showArea30"),//控制对象，可以是jquery对象，也可以是选择器(字符串)
    /*showState: "显示",*/  //显示条件
    hideState:"区域1隐藏", //隐藏条件
    willShowCall:function(){},//显示前的的回调函数
    showCall:function(){},//显示后的回电函数
    willHideCall:function(){},//隐藏前的的回调函数
    hideCall:function(){}//隐藏后的回调函数
  },{
    controlHandle:".ctr3",//控制器，可以是input和checkbox和radio
    controlFor:$(".showArea31"),//控制对象，可以是jquery对象，也可以是选择器(字符串)
    showState: "区域2显示",  //显示条件
  },{
    controlHandle:".ctr3",//控制器，可以是input和checkbox和radio
    controlFor:$(".showArea32"),//控制对象，可以是jquery对象，也可以是选择器(字符串)
    showState: "区域3显示",  //显示条件
  }
})
</script>
```
### input(checkbox或radio)控制，有js

```html?linenums 
<div id="ctrInput">
  <input type="checkbox" id="ctrl4" />
  控制器
  <div id="showArea4" >
    我是一个被控制的区域。
  </div>
</div>
<script>
$("#ctrInput").showControl({//作用对象为包含控制器和被控制区域
  controlHandle:"#ctr4",//控制器，可以是input和checkbox和radio
  controlFor:$("#showArea4"),//控制对象
//可以是jquery对象，也可以是选择器(字符串),例如：controlFor:"#showArea4"
  showState: false,//显示条件
  willShowCall:function(){},//显示前的的回调函数
  showCall:function(){},//显示后的回电函数
  willHideCall:function(){},//隐藏前的的回调函数
  hideCall:function(){}//隐藏后的回调函数
})
</script>
```
#  页面控件 






  [1]: http://tonyyang.cn/test/oa/main/#demo/form/input
  [2]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513673973879.jpg
  [3]: http://tonyyang.cn/test/oa/main/#demo/form/checkBox
  [4]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513735288195.jpg
  [5]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513735345416.jpg
  [6]: http://tonyyang.cn/test/oa/main/#demo/form/selectorAuto
  [7]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513674183449.jpg
  [8]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513735492671.jpg
  [9]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513735556846.jpg
  [10]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513735772850.jpg
  [11]: http://tonyyang.cn/test/oa/main/#demo/form/upload
  [12]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513736537624.jpg
  [13]: http://tonyyang.cn/test/oa/main/#demo/form/validate
  [14]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513739525840.jpg
  [15]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513739674143.jpg
  [16]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513739837563.jpg
  [17]: http://tonyyang.cn/test/oa/main/#demo/form/showControl
  [18]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513754002014.jpg
  [19]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513754023445.jpg