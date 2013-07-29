#SUSY 研究文件
##章節
* ###[概述](#page0)

* ###[基礎設定](#page1)

* ###[基礎函數](#page2)

---

<h3 id="page0">概論</h3>

suzy本身是一套柵格系統框架，可讓你輕鬆製作出RWD及Desktop兩種版本的頁面，跟twitter bootstrap 不一樣是 不提供任何按鈕或是表單等元件。

<h3 id="page1">基礎設定</h3>
`$total-columns`總欄數設定

`$guter-width`欄與欄之間間距

`$grid-padding`最左和最右的間距

<h3 id="page2">基礎函數</h3>
`@include container;`放於最基本DIV底下,將會視為一個容器

`@include border-box-sizing;`將柵欄設定為css的border-box

`@include susy-grid-background;`顯示欄位背景 
- - -
`@include span-columns(<colums>,<parent-colums>);`指派一個 HTML 元素對⿑齊到格線上的欄數

* `<colums>`內指定目前需要欄數不能大於父層的欄數(如果是最後一個設定 需加上omega)
* `<parent-colums>`父層所佔的欄數(或是總欄數)

範例如下：

`@include span-columns(3,12);`

`@include span-columns(9 omega,12);`
- - -
`@include at-breakpoint($media-query)` 設定中斷點(判斷螢幕大小給予不同CSS)
	
* `$medai-query:12`符合最小寬度的時候設為12欄
* `$medai-query:320px 12`小於320px 設為12欄
* `$media-query:320px 12 768px` 當介於320px~768px之間 設為12欄

其他請參照susy-refrence

`@include isolate-grid(1);`如果是一個陣列可以使用此函數去指定他所需要的欄位


***待續...***

