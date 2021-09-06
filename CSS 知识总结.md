# 浏览器渲染原理
1. 根据HTML构建HTML树（DOM）
2. 根据CSS来构建CSS树（CSSDOM）
3. 将两棵树合并成一棵渲染树（render tree）
4. Layout布局（文档流，盒子模型，计算大小和位置）、
5. Paint绘制（边框颜色，文字颜色，阴影等画出来）
6. Compose合成（层叠关系）
# CSS 动画的两种做法（transition 和 animation）
1. Transition 过度
* 作用是补充中间帧
* ![831630951869_ pic](https://user-images.githubusercontent.com/79064198/132251583-94f8e376-3a82-4f30-b602-ed700ff16f63.jpg)
* dispaly和visiblity区别是：
``` 
是否占据空间
display:none，该元素不占据任何空间，在文档渲染时，该元素如同不存在（但依然存在文档对象模型树中）。
visibility:hidden，该元素空间依旧存在。
即一个（display:none）不会在渲染树中出现，一个（visibility :hidden）会。 

是否渲染
display:none，会触发reflow（回流），进行渲染。
visibility:hidden，只会触发repaint（重绘），因为没有发现位置变化，不进行渲染。

是否是继承属性
display:none，display不是继承属性，元素及其子元素都会消失。
visibility:hidden，visibility是继承属性，若子元素使用了visibility:visible，则不继承，这个子孙元素又会显现出来。

读屏器是否读取
读屏器不会读取display：none的元素内容，而会读取visibility：hidden的元素内容。 
```

# Animation 动画
* 用法：关键帧
* ![841630952086_ pic](https://user-images.githubusercontent.com/79064198/132251795-5a145f68-c719-4849-b362-3fe60daaf9c3.jpg)

# 三种更新方式
* ![851630952387_ pic](https://user-images.githubusercontent.com/79064198/132252055-4b1070b0-0825-46a5-80c6-e48f0a222d62.jpg)
