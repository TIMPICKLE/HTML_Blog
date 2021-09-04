# 标题为《HTML入门笔记1》

## HTML 是谁发明的
Tim Berners-Lee

## HTML 起手应该写什么
<img width="361" alt="截屏2021-09-03 03 01 19" src="https://user-images.githubusercontent.com/79064198/131901451-dfea239e-a9db-4192-98ce-64e84abe519e.png">

## 常用的表章节的标签有哪些，分别是什么意思（h1~h6、section、article、main、aside 等等）
* h1~h6 标题
* section 章节
* article 文章
* p 段落
* header 头部
* footer 脚部
* main 主要内容
* aside 旁枝内容
* div 划分

## 全局属性有哪些
* class
* contenteditable
* hidden
* id
* style
* tabindex
* title

## 常用的内容标签有哪些，分别是什么意思
```
* <ol><li> order list
* <ul><li>  unorder list
* <dl><dt><dd> description list/term/data
* <pre> 保留回车，空格等操作
* <code> 代码块
* <hr> 分割线
* <br> 换行
* <a> 超链接
* <em> 强调（语气）
* <quote> 引用（行内）
* <blockquote> 引用（块级）
```
## tips
1. 针对一个块内容做样式化，三者并无区别。

2. div section article ，语义是从无到有，逐渐增强的。

3. div 无任何语义，仅仅用作样式化或者脚本化；对于一段主题性的内容，则就适用 section；假如一段主题性内容脱离上下文后仍是完整且独立存在的一段内容，则就适用 article。

div：

定义：文档中的分区或节。

使用场合：作为布局以及样式化时使用（此时三者并无区别,但div更常用）

section：

定义：文档中的节，一般是具有标题性的。

使用场合：文章的章节、标签对话框中的标签页、或者论文中有编号的部分。

article:

定义：独立的自包含内容。一般来说，article会有标题部分( 包含在header内 )，有时也会包含footer。

使用场合：一段内容脱离了所在的语境，仍是完整的、独立的，则应该用article标签。
