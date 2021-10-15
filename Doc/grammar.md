# 語法

本篇簡述了一些markdown的語法應用，搭配這些語法應用，可以讓我們在書寫文件時，更容易產出期待的內容與表現方式。

| 項目                                  |
| ------------------------------------- |
| [插入符號](#插入符號)                 |
| [分隔線](#分隔線)                     |
| [特殊字元自動轉換](#特殊字元自動轉換) |
| [網頁語法](#網頁語法)                 |
| [連結](#連結)                         |
| [圖片](#圖片)                         |
| [程式碼區塊](#程式碼區塊)s            |



[回到上一頁](markdown.md)

---

## 插入符號

markdown支援在符號前面加上反斜線來作符號的顯示，列表如下：

```tex
\   反斜線
`   反引號
*   星號
_   底線
{}  大括號
[]  方括號
()  括號
#   井字號
+   加號
-   減號
.   英文句點
!   驚嘆號
```



[回到頁首](#語法)

---

## 分隔線

用三個或以上的星號、減號、底線來建立分隔線。

```tex
***
---
___
```



[回到頁首](#語法)



---

## 特殊字元自動轉換

在HTML文件中，有兩個字元需要特殊處理：`<`和`&`。`<`符號用於起始標籤`&`符號則用於標記HTML實體，如果你只是想要使用這些符號，你必須要使用實體的形式，像是`<`和`&`。

`&` 符號其實很容易讓寫作網路文件的人感到困擾，如果你要打「AT&T」 ，你必須要寫成「`AT&T`」 ，還得轉換網址內的 `&` 符號，如果你要連結到：

```
http://images.google.com/images?num=30&q=larry+bird
```

你必須要把網址轉成：

```
http://images.google.com/images?num=30&amp;q=larry+bird
```

才能放到連結標籤的`href`屬性裡。

**本章節為網路資訊，出處：https://markdown.tw/**

[回到頁首](#語法)

---

## 網頁語法

行間\<abbr title="Hypertext Markup Language">HTML\</abbr>亦支援：<abbr title="Hypertext Markup Language">HTML</abbr>。

不同於HTML是一種樣式發布格式，markdown是一種文件書寫格式，markdown的格式語法只涵蓋純文字範圍。不在markdown涵蓋範圍的標籤都可以在文件裡面用HTML撰寫。不需要額外標註這是HTML或是Markdown；只要直接加標籤就可以了。
只有區塊元素：如`<div>`、`<table>`、`<pre>`、`<p>`等標籤，必需在前後加上空行，以利與純文字內容做區隔。而且這些（區塊元素）的開始與結尾標籤，不可以用tab或是空白來縮排。markdown的產生器可以避免在區塊標籤前後加上沒有必要的`<p>`標籤。

由於以上的特性，加上markdown的表格功能並不支援合併儲存格的書寫方式。我們可以利用以下幾個例子，來達到合併儲存格的效果。可以參考與修改以下的例子來達到不同的應用表示需求。

*NOTE*：

1. 由於使用HTML在markdown文件中，由於添加了大量標籤，雖然可以達到期待的顯示效果，但是文本源碼卻因此變得相當複雜，犧牲了其可讀性：建議遇到此情形時，先思考是否有其他表達方式可以達成需求的表現效果，以此來避免產生讓文檔中存在大量的HTML標籤的缺點。

2. markdown語法在HTML區塊標籤中將不會被進行處理，無法在HTML區塊內使用markdown形式。
3. HTML的區段標籤如`<span>`、`<cite>`、`<del>`則不受限制，可以在Markdown的段落、清單或是標題裡任意使用。依照個人習慣，甚至可以不用Markdown格式，而採用HTML標籤來格式化。舉例說明：如果比較喜歡HTML的 `<a>`或`<img>`標籤，可以直接使用這些標籤，而不用Markdown提供的連結或是影像標示語法。



* **Example 1**

```html
<table>
  <tr>
    <th>項目1</th>
    <th>項目2</th>
    <th>項目3</th>
  </tr>
  <tr>
    <td>Ａ1</td>
    <td colspan="2">Ａ2</td>
  </tr>
  <tr>
    <td rowspan="2">Ｂ1</td>
    <td>Ｂ2</td>
    <td>Ｂ3</td>
  </tr>
  <tr>
    <td>Ｃ2</td>
    <td>Ｃ3</td>
  </tr>
</table>
```

顯示出來的效果如下：

<table>
  <tr>
    <th>項目1</th>
    <th>項目2</th>
    <th>項目3</th>
  </tr>
  <tr>
    <td>Ａ1</td>
    <td colspan="2">Ａ2</td>
  </tr>
  <tr>
    <td rowspan="2">Ｂ1</td>
    <td>Ｂ2</td>
    <td>Ｂ3</td>
  </tr>
  <tr>
    <td>Ｃ2</td>
    <td>Ｃ3</td>
  </tr>
</table>

[回到頁首](#語法)



* **Example 2**

```html
<table>
	<tr>
		<td rowspan="4" bgcolor=#836FFF> 合併多行<br/>
		                 rowspan="n"，跨n行合併<br/>
		</td>
	<td bgcolor=#8B5A00>ITEM</td>
	<td bgcolor=#8B5A00>VALUE</td>
	</tr>
	<tr>
		<td bgcolor=#0000EE>TO-DO</td>
		<td bgcolor=#8E8E8E>5</td>
	</tr>
	<tr>
		<td bgcolor=#228B22>DONE</td>
		<td bgcolor=#8E8E8E>6</td>
	</tr>
	<tr>
		<td bgcolor=#FF3030>REJECT</td>
		<td bgcolor=#8E8E8E>7</td>
	</tr>
	<tr>
		<td colspan="3" bgcolor=#4B0082>RESERVED</td>
	</tr>
</table>
```

顯示出來效果如下：

<table>
	<tr>
		<td rowspan="4" bgcolor=#836FFF> 合併多行<br/>
		                 rowspan="n"，跨n行合併<br/>
		</td>
	<td bgcolor=#8B5A00>ITEM</td>
	<td bgcolor=#8B5A00>VALUE</td>
	</tr>
	<tr>
		<td bgcolor=#0000EE>TO-DO</td>
		<td bgcolor=#8E8E8E>5</td>
	</tr>
	<tr>
		<td bgcolor=#228B22>DONE</td>
		<td bgcolor=#8E8E8E>6</td>
	</tr>
	<tr>
		<td bgcolor=#FF3030>REJECT</td>
		<td bgcolor=#8E8E8E>7</td>
	</tr>
	<tr>
		<td colspan="3" bgcolor=#4B0082>RESERVED</td>
	</tr>
</table>


[回到頁首](#語法)

---

## 連結

markdown也有支援產生連結的語法，此語法不但可以產生外部連結，也可以產生文件內的標籤連結。

```tex
1. [對外連結到https://shuming-yang.github.io/push_boundary/](https://shuming-yang.github.io/push_boundary/)

2. [網站內連結到首頁](../index.md)

3. [連結到當前頁面標籤](#語法)
```

以上可以看到在連結的路經（）內容中的寫法不同，即可產生不同的連結標的，以下為結果顯示：

1. [對外連結到https://shuming-yang.github.io/push_boundary/](https://shuming-yang.github.io/push_boundary/)

2. [網站內連結到首頁](../index.md)

3. [連結到當前頁面標籤](#語法)



[回到頁首](#語法)

---

## 圖片

與前述的[連結](#連結)語法相類似（前面加上一個驚嘆號為前導開頭符號），插入圖片的語法如下，在此就直接提供語法描述替代顯示範例。

```tex
![圖片的替代文字](圖片的路徑)

![圖片的替代文字](圖片的路徑 "圖片的title文字，此為非必需選項")
```

當沒有圖片可以顯示時，將顯示圖片的替代文字

1. ![找不到圖片](nopic.png)
2. ![找不到圖片含title](nopic.png "No picture!!!")



[回到頁首](#語法)

---

## 程式碼區塊

markdown可以使用\```來區塊化出特定的程式碼區塊，在普遍的編輯器中使用\```=<語言名稱>，可以自動產生出針對特定程式碼的區塊顯示。此功能細節，我們在markdown編輯工具介紹中會有進一步的介紹。在此，以下為一些簡單的範例。

1. 使用\```建立文字內程式碼區塊

```tex
當要表示初始值為```a=1;```在執行++的遞增運算```a=a++;```時，寫法如此範例。
```

​		顯示結果為：
​		當要表示初始值為```a=1```在執行++的遞增運算```a=a++;```時，寫法如此範例。

1. 使用\```建立整段獨立的程式碼區塊

````tex
當要表示初始值遞增函數運算時，寫法如此範例（以c語言為例）
```c
void function_opt(void){
	int a = 1;
	a++;
}
```
````

​		顯示結果為：

```c
void function_opt(void){
	int a = 1;
	a++;
}
```



````tex
以下範例用來表示撰寫一個while迴圈應用（以SWIFT語言為例）
```swift
import UIKit

var number = 10

repeat{
	print("\(number)")
	numner -= 1
}while(number > 0)
```
````

顯示結果為：

```swift
import UIKit

var number = 10

repeat{
	print("\(number)")
	numner -= 1
}while(number > 0)
```

由此兩個寫法的顯示結果範例可以看到，markdown編輯器可以根據不同的程式語言，轉譯成易讀的顯示結果，詳細的細節我們將在markdown的編輯工具介紹中描述.



[回到頁首](#語法)

---

[回到上一頁](markdown.md)

