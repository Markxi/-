# table Drag
表格列拖拽效果排序
支持列拖拽交换数据，点击标头进行排序。
cells每行单元格的数组cells[idx];
idx每个表头都执行这个方法，并且添加参数也是idx,单元格的下标。
要利用数组的排序，就要把数据添加到数组[]里面tarr；
同一列第二次点击就会调用数组方法反排序reverse();
给个属性赋值就可以了 这个值就是当前点击的列下标。
表格里面排序有可能输数组和字符串。
数组排序用Array.sort();字符串排序用string1.localeCompare(string2);
将排好序的放进一个代码片段里面。然后再添加到tbody里面。
最后给sortCol赋值给当前点击列的小标。如果值等于下标说明之前排序过了。再次点击就是反排序了。

//Drag
onmousedown的时候获取事件对象，列下标，鼠标坐标，当前触发事件对象的宽度（也就是列的宽度）。
把当前列所有数据保存到一个DOM块级元素。
把所有列的left值保存到数组arrn.
onmousemove移动计算鼠标下标，控制DOM元素BOX不溢出，进行判断。
  document.onselectstart=function(){return false};       
  window.getSelection ? window.getSelection().removeAllRanges() : document.selection.empty();  
上面代码在移动的时候不要选中被移动的元素和其他的元素。
onmouseup 也一样的计算坐标 下标 在和arrn进行对比，从而判断是在多少列，进行数据交换。释放事件和清空DOM数组。
