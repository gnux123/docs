#Umall CSS/SCSS/SASS 文件規範
version 1.0 by 2013/07/31 
##章節
* ###[註釋規範](#page_0)
* ###[CSS排版規範](#page_1)
* ###[規則撰寫](#page_2)

	* ####[命名規則](#page_2-1)
	* ####[屬性撰寫順序](#page_2-2)
	* ####[選擇器性能](#page_2-3)
* ###[值類規範](#page_3)
* ###[HACK規範&參考](#page_4)
* ###[Umall CSS文件](#page_5)
* ###[備註](#others)

---

<h2 id="page_0">註釋規範</h2>

1. ####文件註解：
		/*		*desc: 中英文文件說明		*author: 編撰者姓名		*update: 2012-10-17 18:32 		*/
2. ####模組註解：
		/* module: 模組功能 by 人名 */
3. ####行內註解部分：
		單行註解		/* commando line.1 */
		多行註解需寫在css行內
		/*
		command line.1
		command line.2
		*/
4. ####特殊註解：
		標註bug修正部分：
		/* BUGFIX: 修正內容 by 人名 @ 時間 */
		標註待辦事項：
		/* TODO: 待辦內容 by 人名 @ 時間 */
<h2 id="page_1">CSS排版規範</h2>
採用**tab鍵(四個空白字元)**縮排書寫可選擇單行或多行規則書寫方式。

####書寫規則：
1. 每條規則的大括號`{`前後需加上一個空白字元
2. 每個屬性值結束後需加`;`結尾
3. 多個選擇器共用一個樣式集，則必須寫成多行模式，如下範例：
			
		a.foucs,
		a.focus:hover,
		div.focus,
		div.focus:hover { text-decoration:inline; }
		/* 屬性冒號不加空格，那個是偽類 */
4. 每條規則內屬性需與規則起始第一個字元間距一個**tab鍵(四個空白字元)**
		
		a.foucs,
		a.focus:hover {
			text-decoration:inline;
			color:#ccc;
		}
5. CSS3撰寫規則如下，如需加入前綴詞則依照`-webkit- / -moz- / -ms- / -o-`等依序放入
		
		a.focus {
			-webkit-animation: bundle 1s infinite;
			   -moz-animation: bundle 1s infinite;
			    -ms-animation: bundle 1s infinite;
			     -o-animation: bundle 1s infinite;
			        animation: bundle 1s infinite;
		}
		
<h2 id="page_2">規則撰寫</h2>

1. <h3 id="page_2-1">命名規則</h3>
	* 命名規則中不允許下劃線`_`，一律採用小寫及中劃線`-`。
	* 避免使用中文拼音方式，需採用英文單字簡明
	* 避免Class和id命名重複
	* id 必須是唯一，勿隨意建立id命名
	* 盡可能提高CSS模組使用性，樣式需盡量採用組合方式(OOCSS)
	* 除了基礎樣式，禁止直接為html tag加上樣式
		
			div {
				float:left;
				width:100%;
			}
	* 命名規則中不應該包含顏色(red/blue/black)及定位(left/top/right/bottom)等字詞 (待議?)

2. <h3 id="page_2-2">屬性撰寫順序</h3>
	* 顯示屬性： `display/list-style/position/float/clear`
	* 自身屬性(box-model)： `width/height/margin/padding/border`
	* 背景屬性： `bakcground`
	* 行高屬性： `line-height`
	* 文字屬性： 
		
			color/font/text-decoration/text-align/
			text-indent/vertical-align/white-space/content
	* 其他屬性： `cursor/z-index/zoom`
	* CSS3屬性： `transform/transition/animation/box-shadow/border-radius`
	* 連結樣式：依照`:link/vistied/hover/active`

3. <h3 id="page_2-2">選擇器性能</h3>
	* 盡量合併`margin/padding/border/background/font`等屬性，盡量使用縮寫方式。
	* 基於滿足功能性的需求上，減少查找的選擇器節點
	* 禁止於基礎樣式之外，採用`*`來宣告。
	* 除非必要，一般有class或id的，在加上對應的tag
	* 如果沒有邊框 盡量不要寫成`border:0` 而需寫成 `border:none`
	
<h2 id="page_3">值類規範</h2>
<h2 id="page_4">HACK規範&參考</h2>
**盡量減少hack 能不使用就不使用 不允許濫用hack**
