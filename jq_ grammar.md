## JQuery

JS 快速，小巧，功能丰富的 类库

优势： 操作DOM  事件处理 动画 AJAX 

版本： 1.72 兼容所有浏览器

http://www.jquery.com/    官网

DOM 就是清晰的操作，了解DOM树

只要加了下标 如：[0] jq对象就会变成原生对象

jq 第i个 要用 eq(i)

如果你要使用 jq 的方法，那么必须保证，前面那个对象是JQ对象

互转：
    
       JQ对象转原生对象 使用下标即可
    
       原生对象转JQ对象 使用$() 包一下即可
  
    innerHTML   ->  html()
    style.css/cssText    ->  css()
    innerText   ->  text()
    value  ->  val()

    attr 属性 -> getAttribute + setAttribute

    removeAttr 删除行间属性

   $('#box').html('78910jQk');
  
   $('#box').html('<p>pppp</p>'); //写操作

   $('#box').html() //读操作

   $('#box').text('<p>pppp</p>');//专门获取文本的

   $('input').val('我是文本');
   
   
         prop:专门用来操作表单元素属性的（比如:checked）。
   
    因为直接使用attr('checked')为undefined

    例如：
    
    $('input[type="button"]').click(()=>{
    
        let inputs = $('input[type="checkbox"]');

        for(var i=0;i<inputs.length;i++){
          if(inputs.eq(i).prop('checked')){
            inputs.eq(i).prop('checked',false);
          }else{
            inputs.eq(i).prop('checked',true);
          }
        }
    });
    
    
    JQ.each():
      JQ的循环,里面有个回调函数
      function (i,e){}  ,i->index  e->element
      
         $('li').each((i,e)=>{
            $(e).click(function(){
                $('li').eq(i).css({
                    background:'red'
                });
                $(this).css({
                    background:'red'
                })
            });
        });
        
    添加class  addClass()
    删除class  removeClass()
    
    找到当前元素所在的位置（在父级同级兄弟元素中的位置）
    JQ.index(可以选填范围)
    
    hide:隐藏  -> display:none
    show:显示  -> display:block

    parent() -> parentNode
    children()  -> chilren;
        
    $('a').click(function(){
        $(this).parent().hide();
    });
    
    closest():
      closest会首先检查当前元素是否匹配，如果匹配则直接返回元素本身
      如果不匹配则向上查找父元素，一层一层往上，直到找到匹
      配选择器的元素。
      如果什么都没找到则返回一个空的jQuery对象。
      
    


