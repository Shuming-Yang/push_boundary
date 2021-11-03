#### Mermaid語法－圖形繪製



程式撰寫者無論在設計階段亦或是文檔整理與程式流程的細節補充上，最容易讓人明瞭的方式，就是圖形表達了。單靠文字的說明，很難讓閱讀者透過*想像*的方式來理解設計者的理念與實作方式，更何況是從中檢視到是否存在邏輯或是系統錯誤了。有時候，不好的表達方式，會讓好的設計被埋沒，而過於會修飾的表達方式，則又讓有風險的設計被認可而實作出來。所以，使用圖行化的表達方式，加上文字來做細節的說明，會是極佳的方式，讓閱讀者能夠更清晰明確的理解程式撰寫者的理念與想法。

在markdown編輯器中，大多數常用的編輯器都支援Mermaid語法，這邊在編輯器[Typora](editor_typora.md)中，也有列舉出許多的例子來做為參考範例。在這個篇章，我們將其常用的一些描述語法，做更多的說明。讓大家在使用的時候，能夠有更完整的參考資料來源。

而mermaid也有提供[在線編輯器](https://mermaid-js.github.io/mermaid-live-editor/edit#eyJjb2RlIjoiZ3JhcGggVERcbkFbQ2hyaXN0bWFzXSAtLT58R2V0IG1vbmV5fCBCKEdvIHNob3BwaW5nKVxuQiAtLT4gQ3tMZXQgbWUgdGhpbmt9XG5DIC0tPnxPbmV8IERbTGFwdG9wXVxuQyAtLT58VHdvfCBFW2lQaG9uZV1cbkMgLS0-fFRocmVlfCBGW2ZhOmZhLWNhciBDYXJdXG4iLCJtZXJtYWlkIjoie1xuICBcInRoZW1lXCI6IFwiZGVmYXVsdFwiXG59IiwidXBkYXRlRWRpdG9yIjpmYWxzZSwiYXV0b1N5bmMiOnRydWUsInVwZGF0ZURpYWdyYW0iOnRydWV9)，可以讓使用者快速的編寫跟驗證自己的語法內容與確認跟調整顯示的結果。



[回到上一頁](markdown.md)

---

##### 流程圖

流程圖以***graph***關鍵字來做宣告，其後可以帶著以下子句來做進階顯示指定

graph LR

* TB : 從上到下 (Top Buttom)
* BT : 從下到上 (Buttom Top)
* LR : 從左到右 (Left Right)
* RL : 從右到左 (Right Left)
* TD : 跟 TB 同

若是沒有指定的話，預設值為TB





