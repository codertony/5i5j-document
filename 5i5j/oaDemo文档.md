

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
[demo>表单>下拉菜单和自动补全][4]
### 自动补全输入框
![][5]


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
![][5]


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


  [1]: http://tonyyang.cn/test/oa/main/#demo/form/input
  [2]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513673973879.jpg
  [3]: http://tonyyang.cn/test/oa/main/#demo/form/checkBox
  [4]: http://tonyyang.cn/test/oa/main/#demo/form/selectorAuto
  [5]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513674183449.jpg