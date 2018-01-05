

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
## 时间选择器 
### 日期选择器组件
![][3]
```html?linenums
  <div class="input-group" style="" >
    <input class="form-control 5i5jdate input-xs"  type="text" placeholder="选择时间"/>
      <span class="input-group-addon addon-xs">
            <i class="fa fa-calendar bigger-110"></i>
      </span>
  </div>
  <script>
     $('.5i5jdate').datepicker({
        todayBtn: "linked",//今天按钮
        clearBtn: true,//清空按钮
        language: "zh-CN",//语言
        autoclose: true,//自动关闭
        todayHighlight: true,//今天高亮
        format: "yyyy-mm-dd",//日期格式，可以不写，直接使用默认的
    })
  </script>
```
### 日期区域选择器
![][4]
```html?linenums
 
  <div class="input-group"  >
        <input class="form-control input-xs" id="monthDate"  type="text" placeholder="选择时间">
        <span class="input-group-addon addon-xs">
       	 	<i class="fa fa-calendar bigger-110"></i>
        </span>
      </div>
  <script>
     $("#monthDate").datepicker({
        todayBtn: "linked",
        language: "zh-CN",
        autoclose: true,
        todayHighlight: true,
        clearBtn: true
        , format: "yyyy-mm",
        enableOnReadonly: false,
        startView: 1,
        minViewMode: 1
      });
  </script>
```
### 日期和时间选择器
![][5]
```html?linenums
<input type="text" class="5i5jDateTime input-xs" style="" placeholder="选择日期和时间" />
  <script>
     $("#5i5jDateTime").datetimepicker({
        locale:  'zh-CN',
        format:'YYYY-MM-DD HH:mm',
        stepping: 1,
        toolbarPlacement: 'top',
        useStrict: true,
        sideBySide:true,
        showClose:true,
        fixPlace:true
        
      })
  </script>
```
## 选择框
[demo>表单>选择框][6]
### 行内小型多选框 
![][7]
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
![][8]
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
[demo>表单>下拉菜单和自动补全][9]
### 自动补全输入框
![][10]


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
![][11]
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
![][12]
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
![][13]
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
[demo>表单>文件上传][14]

![][15]
```html?linenums
<input id="auto" type="text" class="input-xs"/>
 <script>
  $( "#auto" ).autocomplete({
          source: arrayData//数组
        });
</script>
```
## 表单验证
[demo>表单>表单验证][16]
### 外部有星
![][17]
```html?linenums 
	<input vRequired="true" type="text" class="form-control input-xs" placeholder="必填项"/>
	vRequired="true"或者required="outerStar"
```
### 内部有星
![][18]
```html?linenums 
<input vRequired="innerStar" type="text" class="form-control input-xs" placeholder="必填项"/>
```
### 无星
![][19]
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
[demo>表单>隐藏显示的控制 ][20]
### select控制，无js
![][21]
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
![][22]
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

# 页面控件
## 模态弹框
[demo>页面控件>模态弹框][23]

![][24]

```html?linenums 
<button id="buttonId" class="btn btn-primary">模态弹框</button>
<script>
  方法一：
    oaDialogOpen(dialogId,options)

    $("#buttonId").click(function(){
    oaDialogOpen("newModal",//对话框ID，必填，且不能与当前页面的ID重复
        {url:"../demo/grid/gridtest_form.html",//调用页面的url
          title:"我的",//弹框的title
          closeOnEscpe:true,//是否通过escpe关闭弹框
          closeBtn:true,//是否显示关闭按钮
          width:500,//弹框的宽度
          height:"min",//弹框的高度，可以是数字，也可以是"min",子元素撑起；和"auto"或"max"--表示自适应屏幕最大高度。

          
          buttons:{"确定" : function() {//按钮和执行函数
                    $(this).dialog("close");
                    },
                    "取消" : function() {
                    $(this).dialog("close");
                    }
                },
          willOpen:function(){},//弹框打开前的回调函数
          openCall:function(){},//弹框打开后的回调函数
          closeCall:function(){}//弹框关闭后的回调函数
      })
    });
  方法二：
    oaDialogOpen(dialogId,url,title,width,height,buttons,willOpen,openCall,closeCall)

    $("#buttonId2").click(function(){
        oaDialogOpen("newModal",//对话框ID，必填，且不能与当前页面的ID重复
        "../demo/grid/gridtest_form.html",//调用页面的url
        "我的",//弹框的title
        500,//弹框的宽度
        "auto",//弹框的高度，可以是数字，也可以是"min",子元素撑起；和"auto"或"max"--表示自适应屏幕最大高度。
        {"确定" : function() {//按钮和执行函数
          $(this).dialog("close");
            },
          "取消" : function() {
              $(this).dialog("close");
          }
        },
        function(){},//弹框打开前的回调函数
        function(){},//弹框打开后的回调函数
        function(){}//弹框关闭后的回调函数
      )
    });
	
</script>
```
## 弹框页面布局
[demo>页面控件>弹框页面布局][25]

![][26]

```html?linenums 
 <div class="col-xs-6">
        <h3>两列输入：
          <button id="buttonId1" class="btn btn-primary">两列输入</button>
          towColInput.html
        </h3>
    </div>
<script>
$("#buttonId1").click(function(){
                oaDialogOpen("newModal",//对话框ID，必填，且不能与当前页面的ID重复
                "../demo/widget/dialogPages/towColInput.html",//调用页面的url
                "我的",//弹框的title
                500,//弹框的宽度
                "min",//弹框的高度，可以是数字，也可以是"auto",子元素撑起；或者"max"--表示自适应屏幕最大高度。
                  {"确定" : function() {//按钮和执行函数
                    $(this).dialog("close");}
                  }
                )
        });
</script>
```
##  tab切换页面
[demo>页面控件>tab切换页面][27]

![][28]

```html?linenums 
<div class="col-xs-12">
    <br/>
    <div class="tabbable tabbable-lightBlue">
      <div class="tab-top-tool">
        <button class="btn btn-xs btn-danger">确定</button>
        <button class="btn btn-xs btn-danger">保存</button>
      </div>
      <ul class="nav nav-tabs" >
        <li class="active">
          <a data-toggle="tab" tabUrl="../demo/widget/tabView_viewValue.html" tabView="#tab-content1">
            <i class="green ace-icon fa fa-home bigger-120"></i>
            键值样例
          </a>
        </li>

        <li>
          <a data-toggle="tab" tabUrl="../demo/widget/tabView_viewtest2.html" tabView="#tab-content1">
            表格样例
            <span class="badge badge-danger">4</span>
          </a>
        </li>

        <li class="dropdown">
          <a data-toggle="dropdown" class="dropdown-toggle" href="#">
            Dropdown &nbsp;
            <i class="ace-icon fa fa-caret-down bigger-110 width-auto"></i>
          </a>

          <ul class="dropdown-menu dropdown-info">
            <li>
              <a data-toggle="tab" tabUrl="../demo/widget/tabView_viewtest3.html" tabView="#tab-content1">
                其他1
              </a>
            </li>

            <li>
              <a data-toggle="tab" tabUrl="../demo/widget/tabView_viewtest4.html" tabView="#tab-content1">
                其他2
              </a>
            </li>
          </ul>
        </li>
      </ul>

      <div class="tab-content" id="tab-content1">

      </div>
    </div>
    <!-- /section:elements.tab -->
  </div>

```
![][29]

```html?linenums 
  <div class="col-xs-12">
    <br/>
    <div class="tabbable tabs-left tabbable-darkBlue">
      <ul class="nav nav-tabs" id="myTab3">
        <li class="active">
          <a data-toggle="tab" tabUrl="../demo/widget/tabView_viewtest1.html" tabView="#tab-content3">
            <i class="pink ace-icon fa fa-tachometer bigger-110"></i>
            第一个页面
          </a>
        </li>

        <li>
          <a data-toggle="tab" tabUrl="../demo/widget/tabView_viewtest2.html" tabView="#tab-content3">
            <i class="blue ace-icon fa fa-user bigger-110"></i>
            第二个页面
          </a>
        </li>

        <li>
          <a data-toggle="tab" tabUrl="../demo/widget/tabView_viewtest3.html" tabView="#tab-content3">
            <i class="ace-icon fa fa-rocket"></i>
            第三个页面
          </a>
        </li>
      </ul>

      <div class="tab-content" id="tab-content3">

      </div>
    </div>

  </div>

```
##  多级复选和收缩框
[demo>页面控件>多级复选和收缩框][30]

![][31]



```html?linenums 
  <div class="panel panel-gray panel-border">
        <div class="checkbox-inline first_header" style="left: 150px;">
          <label>
            <input all-ctrl="#first_check1" name="check1" type="checkbox" class="ace">
            <span class="lbl"> 全选
            </span>
          </label>
        </div>
        <div class="panel-heading">
          <h4 class="panel-title">
            <a href="#first_check1" data-toggle="collapse" class="accordion-toggle">
              <i data-icon-show="ace-icon fa fa-angle-right" data-icon-hide="ace-icon fa fa-angle-down" class="ace-icon fa fa-angle-down bigger-110"></i>
              &nbsp;一、三级多选联动
            </a>
          </h4>
        </div>

        <div id="first_check1" class="panel-collapse collapse in">
          <div class="panel-body">
            <div class="row">
              <div class="col-xs-12">
                <div class="alert alert-gray ">
                  <div class="checkbox second_header">
                    <label>
                      <input all-ctrl="#second_check1" name="check1" type="checkbox" class="ace">
                      <span class="lbl"> 二级菜单aaaaa</span>
                    </label>
                  </div>

                  <div class="row" id="second_check1">
                    <div class="col-sm-12">
                      <ul class="list-inline power_list">
                        <li class="">
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选是打发好的师傅告诉择</span>
                            </label>
                          </div>
                        </li>

                        <li>
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选择打算发放</span>
                            </label>
                          </div>
                        </li>

                        <li>
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选择打算发放</span>
                            </label>
                          </div>
                        </li>

                        <li>
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选择打算发放</span>
                            </label>
                          </div>
                        </li>

                        <li>
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选择打算发放</span>
                            </label>
                          </div>
                        </li>

                        <li>
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选择打算发放</span>
                            </label>
                          </div>
                        </li>

                        <li>
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选择打算发放</span>
                            </label>
                          </div>
                        </li>

                        <li>
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选择打算发放</span>
                            </label>
                          </div>
                        </li>

                        <li>
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选择打算发放</span>
                            </label>
                          </div>
                        </li>
                      </ul>
                    </div>
                  </div>
                </div>
                <div class="alert alert-gray ">
                  <div class="checkbox second_header">
                    <label>
                      <input all-ctrl="#second_check2" name="check1" type="checkbox" class="ace">
                      <span class="lbl"> 二级菜单aaaaa</span>
                    </label>
                  </div>

                  <div class="row" id="second_check2">
                    <div class="col-sm-12">
                      <ul class="list-inline power_list">
                        <li class="">
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选是打发好的师傅告诉择</span>
                            </label>
                          </div>
                        </li>

                        <li>
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选择打算发放</span>
                            </label>
                          </div>
                        </li>

                        <li>
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选择打算发放</span>
                            </label>
                          </div>
                        </li>

                        <li>
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选择打算发放</span>
                            </label>
                          </div>
                        </li>

                        <li>
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选择打算发放</span>
                            </label>
                          </div>
                        </li>

                        <li>
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选择打算发放</span>
                            </label>
                          </div>
                        </li>

                        <li>
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选择打算发放</span>
                            </label>
                          </div>
                        </li>

                        <li>
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选择打算发放</span>
                            </label>
                          </div>
                        </li>

                        <li>
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" class="ace">
                              <span class="lbl"> 三级选择打算发放</span>
                            </label>
                          </div>
                        </li>
                      </ul>
                    </div>
                  </div>
                </div>
                <div class="alert alert-gray ">
                  <div class="checkbox second_header">
                    <label>
                      <input all-ctrl="#second_check3" name="check1" type="checkbox" class="ace">
                      <span class="lbl"> 二级菜单aaaaa</span>
                    </label>
                  </div>

                  <div class="row" id="second_check3">
                    <div class="col-sm-12">
                      <ul class="list-inline power_list">
                        <li class="">
                          <div class="checkbox-inline">
                            <label>
                              <input name="check1" type="checkbox" checked class="ace">
                              <span class="lbl"> 三级选是打发好的师傅告诉择</span>
                            </label>
                          </div>
                        </li>
                      </ul>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
```

##  图片分组管理
[demo>页面控件>图片分组管理][32]

![][33]

```html?linenums 
<div class="col-xs-12 powerSet">
    <div class="text-center">
      <div class="h3">分组选择</div>
      <label class="checkBtn">
        <input all-ctrl="#first_check2" name="check1" type="checkbox" class="ace">
        <span class="lbl">所有图片</span>
      </label>
      <button id="imgCheckBox-modal" class="btn btn-danger btn-sm">打开弹框</button>
    </div>
    <div id="first_check2">
      <div class="panel panel-gray panel-border">
        <div class="checkbox-inline first_header" style="left: 150px;">
          
        </div>
        <div class="panel-heading">
          <h4 class="panel-title">
            <div class="accordion-toggle">
              <label>
                <input all-ctrl="#second_check21" name="check1" type="checkbox" class="ace">
                <span class="lbl"> 第一组图片</span>
              </label>
            </div>
          </h4>
        </div>
        <div id="second_check21" class="alert alert-gray ">
            <ul class="list-inline power_list">
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/gallery/image-1.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/gallery/image-2.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/paper/scan0011.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/paper/scan0012.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/paper/scan0013.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/paper/scan0014.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/paper/scan0015.jpg" alt="">
                    </span>
                  </label>
                </li>
              </ul>
        </div>
      </div>
      <div class="panel panel-gray panel-border">
        <div class="checkbox-inline first_header" style="left: 150px;">
          
        </div>
        <div class="panel-heading">
          <h4 class="panel-title">
            <div class="accordion-toggle">
              <label>
                <input all-ctrl="#second_check22" name="check1" type="checkbox" class="ace">
                <span class="lbl"> 第一组图片</span>
              </label>
            </div>
          </h4>
        </div>
        <div id="second_check22" class="alert alert-gray ">
            <ul class="list-inline power_list">
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/gallery/image-1.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/gallery/image-2.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/paper/scan0011.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/paper/scan0012.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/paper/scan0013.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/paper/scan0014.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/paper/scan0015.jpg" alt="">
                    </span>
                  </label>
                </li>
              </ul>
        </div>
      </div>
      <div class="panel panel-gray panel-border">
        <div class="checkbox-inline first_header" style="left: 150px;">
          
        </div>
        <div class="panel-heading">
          <h4 class="panel-title">
            <div class="accordion-toggle">
              <label>
                <input all-ctrl="#second_check23" name="check1" type="checkbox" class="ace">
                <span class="lbl"> 第一组图片</span>
              </label>
            </div>
          </h4>
        </div>
        <div id="second_check23" class="alert alert-gray ">
            <ul class="list-inline power_list">
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/gallery/image-1.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/gallery/image-2.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/paper/scan0011.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/paper/scan0012.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/paper/scan0013.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/paper/scan0014.jpg" alt="">
                    </span>
                  </label>
                </li>
                <li class="">
                  <label class="imgCheckBox">
                    <input name="check1" type="checkbox" class="ace">
                    <span class="lbl">
                      <img src="../assets/images/paper/scan0015.jpg" alt="">
                    </span>
                  </label>
                </li>
              </ul>
        </div>
      </div>
      
    </div>
  </div>
 <script>
 $('#imgCheckBox-modal').click(function(){
          oaDialogOpen("imgCheckBox",//对话框ID，必填，且不能与当前页面的ID重复
            {url:"../demo/widget/dialogPages/imgCheckBox.html",//调用页面的url
              title:"批量下载",//弹框的title
              closeOnEscpe:true,//是否通过escpe关闭弹框
              closeBtn:true,//是否显示关闭按钮
              width:850,//弹框的宽度
              height:"max",//弹框的高度，可以是数字，也可以是"min",子元素撑起；和"auto"或"max"--表示自适应屏幕最大高度。
              buttons:{"下载" : function() {//按钮和执行函数
                $(this).dialog("close");
              },
                "取消" : function() {
                  $(this).dialog("close");
                }
              },
            })
        });
 
 </script>
```
##  多级复选框,号码选择
[demo>页面控件>多级复选框,号码选择][34]
![][35]
```html?linenums 
 <div style="width: 600px;">
      <label>
        <input type="checkbox" class="ace" check-all="#websiteList">
        <span class="lbl">全选</span>
      </label>
      <ul class="flexList" id="websiteList" >
        <li>
          <div class="websiteBtnLi dropdown-hover">
            <label class="websiteBtn">
              <input type="checkbox" class="ace" check-all="#websitepop1">
              <!--check-all的值需要和被控制区域的id一直-->
              <span class="lbl">58同城(三网合一) <span class="sl"></span></span>
            </label>
            <ul id="websitepop1" class="dropdown-menu dropdown-caret websitepop">
              <li>
                <label>
                  <input type="checkbox" class="ace">
                  <span class="lbl">1111111111111</span>
                </label>
              </li>
              <li>
                <label>
                  <input type="checkbox" class="ace">
                  <span class="lbl">1111111111111</span>
                </label>
              </li>
              <li>
                <label>
                  <input type="checkbox" class="ace">
                  <span class="lbl">1111111111111</span>
                </label>
              </li>
              <li>
                <label>
                  <input type="checkbox" class="_qxBox ace">
                  <span class="lbl">1111111111111</span>
                </label>
              </li>
            </ul>
          </div>
        </li>
        ...
      </ul>
    </div>
<script>
 $('.websiteBtnLi').each(function () {
        var $this = $(this),
          $sl = $this.find('.sl'),
          $websitepopCheck =  $this.find('.websitepop').find(':checkbox');
        function slReady () {
         if($websitepopCheck.filter(':checked').length>0) {
           $sl.addClass('orange').html('['+$websitepopCheck.filter(':checked').length+']');
         }else {
           $sl.removeClass('orange').html('['+$websitepopCheck.length+']');
         }
        }
        slReady()
        $websitepopCheck.click(function () {
          slReady()
        })
      })
    
</script>
```
 ##  灯箱控件
 
 [demo>页面控件>灯箱控件][36]
 
 ![][37]
 ```html?linenums 
  单张图的例子，要保证lightBox值唯一：
<a href="../assets/images/gallery/image-1.jpg" title="你好吗" lightBox="single1" class="inline">
  <img width="200" height="200" alt="图片路径不对" src="../assets/images/gallery/thumb-1.jpg"/>
</a>
多张图的例子，注意lightBox的值要一样：
<ul class="ace-thumbnails clearfix">
  <li>
    <a href="../assets/images/gallery/image-1.jpg" title="Photo Title" lightBox="colorBox">
      <img width="150" height="150" alt="150x150" src="../assets/images/gallery/thumb-1.jpg"/>
    </a>
    <div class="tags">
      <span class="label-holder">
        <span class="label label-info">breakfast</span>
      </span>

      <span class="label-holder">
        <span class="label label-danger">fruits</span>
      </span>

      <span class="label-holder">
        <span class="label label-success">toast</span>
      </span>

      <span class="label-holder">
        <span class="label label-warning arrowed-in">diet</span>
      </span>
    </div>

    <div class="tools">
      <a href="#">
        <i class="ace-icon fa fa-link"></i>
      </a>

      <a href="#">
        <i class="ace-icon fa fa-paperclip"></i>
      </a>

      <a href="#">
        <i class="ace-icon fa fa-pencil"></i>
      </a>

      <a href="#">
        <i class="ace-icon fa fa-times red"></i>
      </a>
    </div>
  </li>

  <li>
    <div>
      <img width="150" height="150" alt="150x150" src="../assets/images/gallery/thumb-5.jpg"/>

      <div class="text">
        <div class="inner">
          <span>Some Title!</span>

          <br/>
          <a href="../assets/images/gallery/image-5.jpg" lightBox="colorbox">
            <i class="ace-icon fa fa-search-plus"></i>
          </a>

          <a href="#">
            <i class="ace-icon fa fa-user"></i>
          </a>

          <a href="#">
            <i class="ace-icon fa fa-share"></i>
          </a>
        </div>
      </div>
    </div>
  </li>

   ....
</ul>

```

## 滑动边框
[demo>页面控件>滑动边框][38]

![][39]
```html?linenums 
   <div id="abc" class="modal aside">
            <div class="modal-dialog">
                <div class="modal-content">
                    <div class="modal-header no-padding">
                        <div class="table-header">
                            <button type="button" class="close" data-dismiss="modal" aria-hidden="true">
                                <span class="white">&times;</span>
                            </button>
                            Based on Modal boxes
                        </div>
                    </div>

                    <div class="modal-body">
                        <h3 class="lighter">Custom Elements and Content</h3>

                        <br/>
                        With no modal backdrop
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        1
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        2
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        <br/>
                        3
                    </div>
                </div>
                <!-- /.modal-content -->

                <button style="top: 50px;" class="aside-trigger btn btn-info btn-app btn-xs ace-settings-btn" data-target="#abc"
                        data-toggle="modal" type="button">
                    <i data-icon1="fa-plus" data-icon2="fa-minus" class="ace-icon fa fa-plus bigger-110 icon-only"></i>
                </button>
            </div>
            <!-- /.modal-dialog -->
        </div>
<script>
 $("#abc").ace_aside({
                placement: 'right',
                backdrop:false,
                fixed:false,
                background: false,
                offset: false,
                body_scroll: false,
            });

</script>
```
## 目录树treeview
[demo>页面控件>目录树treeview][40]


![][41]

```html?linenums 
  <div class="col-sm-4">
        <h2>zTree</h2>
        <div class="checkbox">
            <label>
                <input id="ztreeCheckAll" type="checkbox" class="ace">
                <span class="lbl">全选</span>
            </label>
        </div>
        <ul id="treeDemo" class="ztree noUnderline"></ul>
    </div>
<script>
 $("#ztreeCheckAll").change(function(){
            treeObj.checkAllNodes($(this).is(":checked"));
            treeObj.expandAll($(this).is(":checked"));
          });

</script>
```
#  自定义控件
##  图片预览管理控件
[demo>自定义控件>图片预览管理控件][42]

![][43]


```html?linenums 
 <div id="picM"> </div>
<script>
  var img=[
    "../assets/images/gallery/image-1.jpg",
    "../assets/images/gallery/image-2.jpg"
  ];
  var picM=$("#picM").pmCtrBox({
    img:img,//图片src数组,或者是由包含imgUrl的对象所组成的数组。
    method:"click",//切换方式，默认click也可以选择hover
    width:600,//控件宽度
    height:300,//大图显示宽度
    imgReady:function(imgLi){},//每张小图加载完毕时回调函数
    singleLine:false,//小图预览是否单行显示,默认false
    sortBack:function(){},//排序完毕后的毁掉函数
    ableClose:function(a){return true},
    //判断是否确认删除图片，函数返回ture则返回删除，返回false则不删除
    imgChangeBack:function(a){}
      //当图片切换时的事件，a为当前图片li对象，通过a.data('imgData')获取储存数据。
    imgCloseBack:function(dom){},//图片删除后的回调函数
    emptyImg:""//图片为空时大图的url，
    onlyRead:true,//只读模式
    largeImg:true,//是否出现大图预览
    smallToLarge:false//这个可以是false和true;也可以是function(a){},a为小图的url
  });

  /*没有大图预览且制度模式*/
  var picM1=$("#picM1").pmCtrBox({
    img:img,//图片src数组
    width:550,//控件宽度
    height:500,//控件高度
    rowNumber:3,//每行图片的个数
    largeImg:false,//是否出现大图预览
    onlyRead:true//只读模式
  });
  /*方法*/
  picM.imgLoad(imgs);//图片载入方法,imgs为图片数组
  picM.addImg(img);//img可以是图片url也可以是数组
  picM.nmSort();//图片序号重新排列
  picM.imgPutOut();//图片导出方法，到处当前图片src数组
  picM.destroy();//销毁控件
  picM.rotateRight();//右转图片
  picM.rotateLeft();//左转图片
  picM.largeShow();//大图预览
</script>
```
##  轮播控件
[demo>自定义控件> 轮播控件][44]

![][45]

```html?linenums
<div id="picM"> </div>
<script>
var img=[
    "../assets/images/gallery/image-1.jpg",
    "../assets/images/gallery/image-2.jpg"
  ];
  var picM=$("#picM").pmCtrBox({
    img:img,//图片src数组
    imgListPlace:'bottom',//图片列表位置，可以是left，top，bottom。
    sliderTime:500,//轮播图，轮播时间，0则没有轮播
    method:"mouseover",//切换方式，默认click,也可以选择"mouseover"
    width:800,//控件宽度
    height:500,//控件高度
    rowNumber:2,//每行图片的个数
    ableClose:function(){return window.confirm("确认删除吗？")},//是否允许删除
    sortBack:function(){},//排序完毕后的毁掉函数
    largeImg:true,//是否出现大图预览
    onlyRead:true,//只读模式
    small:false,//如果使用阿里缩略图，则为ture
    smallImgClick :function(a){
      console.log(a.data('imgData'))
    }
  });
          
  /*方法*/
  picM.imgLoad(imgs);//图片载入方法,imgs为图片数组
  picM.addImg(img);//img可以是图片url也可以是数组
  picM.nmSort();//图片序号重新排列
  picM.imgPutOut();//图片导出方法，到处当前图片src数组
  picM.destroy();//销毁控件
  picM.rotateRight();//右转图片
  picM.rotateLeft();//左转图片
  picM.largeShow();//大图预览
</script>
```
##  简单文件管理控件
[demo>自定义控件> 简单文件管理控件][46]

![][47]

```html?linenums
<div id="file1"> </div>
<script>
/*没有大图预览且制度模式*/
  var file1=$("#file1").fileCtr({
    files:[],
    addFileCallBack:null,//添加每一个文件后的回调函数
    willDelete:null,//删除文件前的回调函数
    Deleted:null,////删除文件后的回调函数
    ableDelete:function(){return window.confirm("确认删除吗？")},//判断是否确认删除文件
    deleteBtn:true,//是否显示删除按钮
    downLoadBtn:true//是否显示下载按钮
  });
  /*方法*/
  picM.loadFiles(files);//文件载入方法,files为图片数组，或者可以是字符串
  picM.addFiles(files);//文件方法,files为图片数组，或者可以是字符串
  picM.destroy();//销毁对象

</script>
```
##  图片编辑器
[demo>自定义控件> 图片编辑器][48]

![][49]

![][50]

```html?linenums
<button id="open1" class="btn btn-primary">图片1</button>
<script>
  $("#open1").click(function(){
       $.markupModalOpen({
          img:"",//边界图片的url
          tools:{//工具加载设置，如果为0则表示不显示
                select:1,
                rectangle:1,
                ellipse:1,
                line:1,
                arrow:1,
                pen:1,
                text:1,
                erase:1,
                color:1,
                lineSize:1,
                fontSize:1,
                clearAll:1,
                undo:1,
                redo:1,
                saveAs:1,
                upLoad:1,
                rotateLeft:1,
                rotateRight:1,
                rotate180:1
          },
          color:['#000000','#ffffff', '#123456', '#ccc333', '#764575','pink', 'yellow', 'green', 'blue', ],
          //画笔和文字颜色参数
          lineSize:[1,2,3,4,5],//画笔粗细参数
          fontSize:[10,15,20,25,30,35,40,50],//文字大小参数
          defaultSet:{lineSize:3,
                      fontSize:20,
                      color:"red"
          },
          downImgName:"编辑图片.jpg",//图片下载时的名称
          upLoadUrl:"",//上传的url
          upLoadCall:function(data){},//上传成功的回调，data是返回的数据
          willClose:function(){}//图片编辑器关闭时的回调
        })
      });
</script>
```

##   克隆按钮
[demo>自定义控件> 克隆按钮][51]

![][52]
```html?linenums
<button class="btn btn-sm" cloneTarget="#table1"
        clone="#pd0" >克隆按钮</button>
   clone=克隆对象的ID;
   cloneTarget=克隆位置的ID;
   class为cloneList的dom节点位数字，会自动增加

默认添加行，如果为可删除的，则在行标签上添加class="hasDelete"
      <tr id="pd1" class="hasDelete">
      ......
      </tr>
```
![][53]
```html?linenums
<button class="btn btn-sm"  >克隆公式</button>
<script>
$('#cloneFun').click(function(){
  cloneDom({
    dom:$("#tr0"),//克隆对象
    target:$("#table2"),//克隆位置
    loadBefore: null,
    callBack: function(a){console.log(a)},
          //克隆后的回调函数，a为克隆完成后的html对象
    willDelete: function(a){console.log(a)},//删除前回调函数
    deleteBack: function(a){console.log(a)},//删除后回调函数
    deleteNoId: false,//航对象是否有ID
    allDelete:false//是否允许全部删除
})
  cloneDom()返回的对象为克隆完成后的html对象
```
##   预约验件时间
[demo>自定义控件> 预约验件时间][54]

![][55]

```html?linenums
<div id="orderTime2"> </div>
<script>
var orderTime = $('#orderTime2').oderTime({
      data:[{timeRange:'08:30--09:30',
        timeNumber: 5
      },{timeRange:'09:30--10:30',
        timeNumber: 5
      },{timeRange:'10:30--11:30',
        timeNumber: 10
      },{timeRange:'11:30--12:00',
        timeNumber: 0
      },{timeRange:'13:00--13:30',
        timeNumber: 5
      },{timeRange:'13:00--13:30',
        timeNumber: 5
      },{timeRange:'13:00--13:30',
        timeNumber: 7
      }],//数据列表
      maxTimeNumber: 8,//最大预约数
      selectTime:'11:30--12:00',//默认选中时间
      changeBack:function(){}//改变时的回调函数
    })
	// 改变时间
	$("#changeData").click(function () {
      orderTime.changeData([{timeRange:'08:30--09:30',
        timeNumber: 1
      },{timeRange:'10:30--11:30',
        timeNumber: 0
      },{timeRange:'11:30--12:00',
        timeNumber: 1
      },{timeRange:'13:00--13:30',
        timeNumber: 2
      },{timeRange:'13:00--13:30',
        timeNumber: 5
      },{timeRange:'13:00--13:30',
        timeNumber: 7
      },{timeRange:'13:00--13:30',
        timeNumber: 8
      }])
    })
	 方法：
     orderTime.getSelectTime();//获取当前选中时间段
     orderTime.getTimeList();//获取时间当前数据列表
     orderTime.changeData(data);改变当前的数据列表
```
##    工作日日历设置
[demo>自定义控件>  工作日日历设置][56]

![][57]

```html?linenums
  <div id="workDay"> </div>
<script>
 var workDay = $("#workDay").workCalendar({
      setDay:{
        workday:['2017-05-06','2017-05-07'],
        freeday:['2017-05-08','2017-05-09','2017-05-10','2018-05-11']
      },
      cellClick : function(td,dateStr, isworkday) {
        console.log("单击日期:"+dateStr+','+isworkday);
        if(isworkday){
          $(td).addClass('freeday');
          $(td).removeClass('workday');
        }else {
          $(td).addClass('workday');
          $(td).removeClass('freeday');
        }
      },
      headerBtn:{
        "测试":{
          id: 1,
          click:function(){
            this.reset();
            console.log(this)
          },
           icon: ''
        }
      },
      yearChange:function (self,year) {//self位控件自身，year为当前年份
        console.log(self)
        console.log(year)
      }
    });
          
    方法：
     workDay.setWorkDay('2017-08-09',true);//将某一天这只为工作日，如果第二个参数为false，则设置为非工作日
     workDay.reset();//重置
```
# 表格
##  jqGrid-单独表格
[demo>表格> jqGrid-单独表格][58]

![][59]


```html?linenums
   <table id="jqGrid"></table>
<script>
 $("#jqGrid").jqGrid({
                url: '../demo/grid/Data.json',
                datatype: "json",
                colModel: [
                    { label: '用户名称', name: 'CategoryName', width: 100,formatter:divBlock},
                    { label: '产品名称', name: 'ProductName', width: 100 },
                    { label: '国家', name: 'Country', width: 100},
                    { label: '小数', name: 'Price', width: 500, align:'right',formatter: 'number', formatoptions: {decimalPlaces: 2}},
                    { label: '货币', name: 'Price', width: 500, align:'right',formatter: 'currency', formatoptions: {decimalPlaces: 2,prefix:'￥ '}},

                    // sorttype is used only if the data is loaded locally or loadonce is set to true
                    { label: '整数', name: 'Quantity', width:500, editable:true,edittype:'text',sorttype: 'number',align:'right' ,formatter: 'integer', formatoptions: {thousandsSeparator:','}},
                    {name:'editBtn',classes:'realTax', width:100,label:'编辑',sortable:false,formatter:editBtn}
                    
                ],
                multiselect: true,
                onSelectRow: function (rowId, status, e) {
                    var rowIds = jQuery("#jqGrid").jqGrid('getGridParam', 'selarrrow');//2、获取选中行的id
                    var rowDataNames = [] ;
                    $(rowIds).each(function(i,rowId){
                        rowDataNames.push($("#jqGrid").jqGrid('getRowData',rowId).Price) //获取选择的行的数据
                    });
                },
                viewrecords: true,
                autowidth:false,
                height: 400,
                rowNum: 30,
                loadonce: true,
                pager: "#jqGridPager",
                gridComplete: function () {
                    $(this).find(".editBtn").each(function(){
                        $(this).click(function(){
                            var row=$(this).attr("data-row");
                            console.log(row);
                            jQuery("#jqGrid").jqGrid("editRow",row);
                        })
                    });
                    $(this).find(".saveBtn1").each(function(){
                        $(this).click(function(){
                            var row=$(this).attr("data-row");
                            console.log(row);
                            jQuery("#jqGrid").jqGrid("saveRow",row,function(){
                                return true
                            });
                        })
                    });
                }
             });
    
```

## jqGrid-多行input与单行input

[demo>表格> jqGrid-多行input][60]

[demo>表格> jqGrid-单行input][61]

![][62]

![][63]
```html?linenums
//代码与单独表格类似，表格上方有一些input
	<table id="jqGrid"></table>
	<script>
    $("#jqGrid").jqGrid({
        url: '../demo/grid/Data.json',
        datatype: "json",
        colModel: [
          {label: '用户名称', name: 'CategoryName', width: 600,classes:'td-auto-height'},
          {label: '产品名称', name: 'ProductName', width: 600,formatter:function(val){
            return '<a class="blue">'+val+'</a>'
          }},
          {label: '国家', name: 'Country', width: 600},
          {label: '价格', name: 'Price', width: 600, sorttype: 'integer'},
          // sorttype is used only if the data is loaded locally or loadonce is set to true
          {
            label: '购买数量', name: 'Quantity', width: 600, sorttype: 'number',
            editable: true,
            editoptions: {},
            dataUrl: "0.php"
          }
        ],
        shrinkToFit:true,
        autoScroll: false,
        multiselect: true,
        //multikey: "ctrlKey",
        multiboxonly: true,
        onSelectRow: function (rowId, status, e) {
          var rowIds = jQuery("#jqGrid").jqGrid('getGridParam', 'selarrrow');
          var rowDataNames = [];
          $(rowIds).each(function (i, rowId) {
            rowDataNames.push($("#jqGrid").jqGrid('getRowData', rowId).CategoryName)
          });
          console.log(rowDataNames);
        },
        cellEdit: true,
        viewrecords: true, // show the current page, data rang and total records on the toolbar
        autowidth: true,
        rowNum: 50,
        editurl: "1.php",
        cellurl: "2.php",
        loadonce: true, // this is just for the demo
        pager: "#jqGridPager"
      });
	  </script>
```

## jqGrid-多级表格1

[demo>表格> jqGrid-多级表格1][64]

![][65]

```html?linenums
	<table id="jqGrid"></table>
	<script>
   $("#jqGrid").jqGrid({
        url: '../demo/grid/multilevelData.json',
        datatype : "json",
        height : 200,
        colNames : [ 'Inv No', 'Date', 'Client', 'Amount', 'Tax','Total', 'Notes' ],
        colModel : [
          {name : 'id',index : 'id',width : 55},
          {name : 'invdate',index : 'invdate',width : 90},
          {name : 'name',index : 'name',width : 100},
          {name : 'amount',index : 'amount',width : 80,align : "right"},
          {name : 'tax',index : 'tax',width : 80,align : "right"},
          {name : 'total',index : 'total',width : 80,align : "right"},
          {name : 'note',index : 'note',width : 150,sortable : false}
        ],
        rowNum : 10,
        rowList : [ 10, 20, 30 ],
        sortname : 'id',
        viewrecords : true,
        sortorder : "desc",
        multiselect : false,
        subGrid : true,
        subGridUrl : "../demo/grid/subData.json",
        subGridModel : [ {
          name : [ 'No', 'Item', 'Qty', 'Unit', 'Line Total' ],
          width : [ 55, 200, 80, 80, 80 ]
        } ],
        pager: "#jqGridPager"
      });
	  </script>
```
## jqGrid-多级表格2
[demo>表格> jqGrid-多级表格2][66]

![][67]

```html?linenums
	<table id="jqGrid"></table>
	<script>
    $("#jqGrid").jqGrid({
        url: '../demo/grid/multilevelData.json',
        datatype : "json",
        height : 200,
        colNames : [ 'Inv No', 'Date', 'Client', 'Amount', 'Tax','Total', 'Notes' ],
        colModel : [
          {name : 'id',index : 'id',width : 55,classes:'subAble'},
          {name : 'invdate',index : 'invdate',width : 90},
          {name : 'name',index : 'name',width : 100},
          {name : 'amount',index : 'amount',width : 80,align : "right"},
          {name : 'tax',index : 'tax',width : 80,align : "right"},
          {name : 'total',index : 'total',width : 80,align : "right"},
          {name : 'note',index : 'note',width : 150,sortable : false}
          ],
        shrinkToFit:false,
        rowNum : 10,
        rowList : [ 15, 25, 35 ,45,55,100],
        sortname : 'id',
        viewrecords : true,
        sortorder : "desc",
        multiselect : false,
        subGrid : true,
        subGridRowExpanded : function(subgrid_id, row_id) {
          var subgrid_table_id, pager_id;
          subgrid_table_id = subgrid_id + "_t";
          pager_id = "p_" + subgrid_table_id;
          $("#" + subgrid_id).html("<table id='" + subgrid_table_id + "' class='scroll'></table>");
          jQuery("#" + subgrid_table_id).jqGrid({
            url: "../demo/grid/multilevelData.json?q=2&id=" + row_id,
            datatype: "json",
            colNames : [ 'Inv No', 'Date', 'Client', 'Amount', 'Tax','Total', 'Notes' ],
            colModel : [
              {name : 'id',index : 'id',width : 55},
              {name : 'invdate',index : 'invdate',width : 90},
              {name : 'name',index : 'name',width : 100},
              {name : 'amount',index : 'amount',width : 80,align : "right"},
              {name : 'tax',index : 'tax',width : 80,align : "right"},
              {name : 'total',index : 'total',width : 80,align : "right"},
              {name : 'note',index : 'note',width : 150,sortable : false}
            ],
            shrinkToFit:false,
//            rownumbers:false,
            rowNum: 20,
            height: 'auto',
            beforeRequest:function(){
              $("#" + subgrid_id).find('.ui-jqgrid-hbox').hide();
            }
          });
        },
        gridComplete:function () {
          $('.subAble').each(function () {
            if(+$(this).html() >8){
              $(this).prevAll('.sgcollapsed').empty().removeClass('sgcollapsed');
            }
          });
        },
        pager: "#jqGridPager"
      });
	  </script>
```
## jqGrid-表格树
[demo>表格> jqGrid-表格树][68]

![][69]

```html?linenums
	<table id="jqGrid"></table>
	<script>
     $("#jqGrid").jqGrid({
        url: '../demo/grid/treeData.json',
        treeGrid: true,
        treeGridModel: 'adjacency', //treeGrid模式，跟json元數據有關 ,adjacency/nested
        ExpandColumn : 'username',
        treeIcons: {leaf:'ui-icon-document-b'},//树的图标
        datatype: 'json',
        colNames:['編號','姓名','密碼','年齡','地址','出生日期'],
        colModel:[
          {name:'id',index:'id', width:90,sorttype:"int"},
          {name:'username',index:'username', width:110,sorttype:"int"},
          {name:'password',index:'password', width:80},
          {name:'age',index:'age', width:80},
          {name:'address',index:'address', width:80},
          {name:'time',index:'time', width:80,sorttype:"date"}
        ],
        sortname: 'id',
        sortorder: "desc",
        jsonReader: {
          root: "rows",
          repeatitems : false // 如果设为false，则jqGrid在解析json时，会根据name来搜索对应的数据元素（即可以json中元素可以不按顺序）；而所使用的name是来自于colModel中的name设定。
        },
        treeReader : {
          level_field: "level",//菜单级别
          parent_id_field: "parent",//值必须为父级菜单的id值。
          leaf_field: "isLeaf",
          expanded_field: "expanded"
        },
        height: "auto",    // 設为具體數值則會根據實際記錄數出現垂直滾動條
        rowNum : 10,     // 顯示全部記錄
        shrinkToFit:false,  // 控制水平滾動條
        pager:'#jqGridPager'
      });
	  </script>
```
##  jqGrid-tab页
[demo>表格> jqGrid-tab页][70]

![][71]
```html?linenums
	<ul class="nav nav-tabs padding-20" >
    <li class="active">
      <a data-toggle="tab" tabUrl="../demo/widget/dialogPages/tab_jqgridMore.html" tabView="#tab-content10">
        <i class="green ace-icon fa fa-home bigger-120"></i>
        键值样例
      </a>
    </li>
    
    <li>
      <a data-toggle="tab" tabUrl="../demo/widget/dialogPages/tab_jqgridSingle.html" tabView="#tab-content10">
        表格样例
        <span class="badge badge-danger">4</span>
      </a>
    </li>
    
    <li class="dropdown">
      <a data-toggle="dropdown" class="dropdown-toggle" href="#">
        Dropdown &nbsp;
        <i class="ace-icon fa fa-caret-down bigger-110 width-auto"></i>
      </a>
      
      <ul class="dropdown-menu dropdown-info">
        <li>
          <a data-toggle="tab" tabView="#tab-content10">
            其他1
          </a>
        </li>
        
        <li>
          <a data-toggle="tab" tabView="#tab-content10">
            其他2
          </a>
        </li>
      </ul>
    </li>
  </ul>
	 
```


  [1]: http://tonyyang.cn/test/oa/main/#demo/form/input
  [2]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513673973879.jpg
  [3]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513769477215.jpg
  [4]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513769512077.jpg
  [5]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513769911930.jpg
  [6]: http://tonyyang.cn/test/oa/main/#demo/form/checkBox
  [7]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513735288195.jpg
  [8]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513735345416.jpg
  [9]: http://tonyyang.cn/test/oa/main/#demo/form/selectorAuto
  [10]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513674183449.jpg
  [11]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513735492671.jpg
  [12]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513735556846.jpg
  [13]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513735772850.jpg
  [14]: http://tonyyang.cn/test/oa/main/#demo/form/upload
  [15]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513736537624.jpg
  [16]: http://tonyyang.cn/test/oa/main/#demo/form/validate
  [17]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513739525840.jpg
  [18]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513739674143.jpg
  [19]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513739837563.jpg
  [20]: http://tonyyang.cn/test/oa/main/#demo/form/showControl
  [21]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513754002014.jpg
  [22]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513754023445.jpg
  [23]: http://tonyyang.cn/test/oa/main/#demo/widget/dialog
  [24]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515148703323.jpg
  [25]: http://tonyyang.cn/test/oa/main/#demo/widget/windowPages
  [26]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515149241812.jpg
  [27]: http://tonyyang.cn/test/oa/main/#demo/widget/tabView
  [28]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515149528121.jpg
  [29]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515150040681.jpg
  [30]: http://tonyyang.cn/test/oa/main/#demo/widget/checkSet
  [31]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515150751719.jpg
  [32]: http://tonyyang.cn/test/oa/main/#demo/widget/imgGroup
  [33]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515151672404.jpg
  [34]: http://tonyyang.cn/test/oa/main/#demo/widget/checkSetNumber
  [35]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515151791141.jpg
  [36]: http://tonyyang.cn/test/oa/main/#demo/widget/lightBox
  [37]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515152043292.jpg
  [38]: http://tonyyang.cn/test/oa/main/#demo/widget/content-slider
  [39]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515152353359.jpg
  [40]: http://tonyyang.cn/test/oa/main/#demo/widget/treeview
  [41]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515152612701.jpg
  [42]: http://tonyyang.cn/test/oa/main/#demo/myWidget/picM
  [43]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513850388323.jpg
  [44]: http://tonyyang.cn/test/oa/main/#demo/myWidget/carousel
  [45]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515140167158.jpg
  [46]: http://tonyyang.cn/test/oa/main/#demo/myWidget/fileCtr
  [47]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515140477874.jpg
  [48]: http://tonyyang.cn/test/oa/main/#demo/myWidget/markupModal
  [49]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515141149657.jpg
  [50]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515141103836.jpg
  [51]: http://tonyyang.cn/test/oa/main/#demo/myWidget/cloneBtn
  [52]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515142050805.jpg
  [53]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515142142195.jpg
  [54]: http://tonyyang.cn/test/oa/main/#demo/myWidget/orderTime
  [55]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515142599942.jpg
  [56]: http://tonyyang.cn/test/oa/main/#demo/myWidget/workCalendar
  [57]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515143030718.jpg
  [58]: http://tonyyang.cn/test/oa/main/#demo/grid/jqGrid_only
  [59]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515143848579.jpg
  [60]: http://tonyyang.cn/test/oa/main/#demo/grid/jqGrid_more
  [61]: http://tonyyang.cn/test/oa/main/#demo/grid/jqGrid_single
  [62]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515144491999.jpg
  [63]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515145145317.jpg
  [64]: http://tonyyang.cn/test/oa/main/#demo/grid/jqGrid_multievel
  [65]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515145906189.jpg
  [66]: http://tonyyang.cn/test/oa/main/#demo/grid/jqGrid_multievel2
  [67]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515146937416.jpg
  [68]: http://tonyyang.cn/test/oa/main/#demo/grid/jqGrid_treegrid
  [69]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515147334200.jpg
  [70]: http://tonyyang.cn/test/oa/main/#demo/grid/jqGrid_tab
  [71]: https://www.github.com/codertony/5i5j-document/raw/master/images/1515148202678.jpg