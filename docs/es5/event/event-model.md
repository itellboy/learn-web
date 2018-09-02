# 事件模型

浏览器的事件模型，就是通过监听函数响应事件。事件发生后，浏览器监听到了这个时间，然后执行对应的监听函数，这是事件驱动编程模式的主要编程方式。

JavaScript 有三种方式为事件绑定监听函数

* 设置 HTML 元素的`on-`属性
* 元素节点的事件属性
* 通过节点的`addEventListener()`添加事件

**this 的指向**

监听函数内部的`this`指向触发事件的那个元素节点

**事件的传播**

一个事件发生后，会在子元素和父元素之间传播 (propagation)，分为三个阶段

* 第一阶段：从`window`对象传导到目标节点（上层传底层），称为捕获阶段 (capture phase)
* 第二阶段：从目标节点向上触发，称为目标阶段 (target phase)
* 第三阶段：从目标阶段传导回`window`（从底层传回上层），称为冒泡阶段 (bubbling phase)

**事件的代理**

由于事件在传播的过程中会冒泡到父节点，因此可以把子节点的监听函数定义到父节点上面，由父节点统一监听处理多个子元素的事件，这种方式称为事件的代理

可以通过`Event.stopPropagation()`方法阻止事件继续向下传播

## 参考

[网道（WangDoc.com）是一个文档网站，提供互联网开发文档](https://wangdoc.com/javascript/events/model.html)