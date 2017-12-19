
# 前言

# 使用方法



# 表单

## 输入框
参考页 [demo>表单>输入框][1]

### 普通输入框
![][2]
HTML代码

``` html?linenums
<input type="text" class="input-xs" style="" />
```
### 组合输入框
![][3]
```html?linenums
 <div class="input-group input-daterange" >
  	<input class="form-control input-xs"  type="text" placeholder="输入">
  		<span class="input-group-addon addon-xs">
                ~
          </span>
  	<input class="form-control input-xs"  type="text" placeholder="输入">
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
  </ script>
```









  [1]: http://tonyyang.cn/test/oa/main/#demo/form/input
  [2]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513673749252.jpg
  [3]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513673973879.jpg
  [4]: http://tonyyang.cn/test/oa/main/#demo/form/selectorAuto
  [5]: https://www.github.com/codertony/5i5j-document/raw/master/images/1513674183449.jpg