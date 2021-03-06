# 讓所有人秒懂的數據解讀方法-台科大EMBA最經典商用分析案例 （附贈Python程式碼）
> 行銷資料科學

[原文連結](https://medium.com/marketingdatascience/b1c13ed708b4)

[大量交易資料，卻不知如何找出商業價值？點我了解！](https://tmrgood.kktix.cc/events/python0to1)

現今越來越多企業將會導入數據分析，希望透過數據驅動的方式輔助公司實行重要決策。各家企業紛紛開打搶才人的戰爭。專業社交網站LinkedIn於2018年12月13日公布了2018年的美國新興職缺報告[1]，指出在今年新興的15大職缺中與人工智慧相關的就佔了6項。Data Scientist是今年成長最快的職缺之一。

> 能有商業價值的分析才是企業最需要的關鍵。

但在企業組建分析團隊的過程中，資料科學家的導入時常伴隨著溝通衝突。資料科學家努力的想解釋重大的發現，管理者卻無法理解複雜演算法模型產生的分析結果。讓許多高價值的資訊傳遞緩慢，大大浪費企業的資源。
- - -

而以下案例來自台科大EMBA場場爆滿的研究方法課程。透過簡單的圖表案例，就可以影響整體行銷包裝策略。更讓許多不論是工商背景台科大EMBA瞬間理解商業分析概念與背後的商業價值。

對於擁有良好健康知識的現在代人來說，如果詢問維他命 c 的攝取量究竟是吃到基本單位就好，多吃無益？還是要吃到一定的量以上，而且多多益善？相信聰明的讀者一定會回答基本單位就好。畢竟對於人體任何東西攝取過多都不是一件好事。

但如果實驗出來的結果不同呢？
以下資料集為模擬保健食品廠測試每單位維他命c對於抵抗力增加的實驗資料。

> 特別注意本文維他命只是虛擬案例。為了讓讀者理解概念。任何維他命攝取過多對身體反而有害，尤其是油性維他命。請依照醫師建議攝取量。

### 資料集
* Pr ：抵抗力的增量。
* type：攝取曲線名稱。
* unit：維他命c攝取單位。
假設我們現在將 A 與 B 兩種維他命c攝取曲線繪製出來。可以看出在 A 攝取曲線上維他命 c 每攝取單位越多抵抗力增量才會顯著的提昇。而在 B 攝取曲線中維他命 c 只要攝取少數單位就會顯著增加，越多則抵抗每單位增加則越來越少。

![](https://cdn-images-1.medium.com/max/1000/1*w6B9-6rYRgYkSpxi85GuTA.png)

雖然本案例是模擬的，卻是很典型的數據分析案例。假設人類抵抗力只需要達到一個固定值就足，我們將上圖紅色線畫出標準線。這對廠商來說會有什麼包裝策略的影響呢？

![](https://cdn-images-1.medium.com/max/1000/1*OTf7RPgDZojxOCfGe5LJUQ.png)

由上圖可以看出如果是 A 線是實際的攝取曲線的話，廠商的包裝每單位就會只包裝在少量單顆上。就如同一般的感冒藥一般，只要一般的塑膠鋁箔包裝就可以。但如果是 B 線的話，一定要吃到一定攝取量才會有足夠的效果。廠商的包裝就會改成一次一大罐，說不定連外包裝都會採用玻璃瓶。就如同知名胃藥哇咖OO一樣。一次攝取量就需要多單位才足夠。這不僅影響包裝的成本，更會影響包材的方式。

且 B 線顛覆全人類對於維他命C的認知。
以上案例的就是以4P中的產品為主軸，分析概念可以應用到膠水、水泥、廣告投放、串流媒體…等許多真實商品之中。絕對是商業分析結果展現的重要概念。而且我們也相信只要善用數據分析，所有各行各業可以找出屬於自己公司的商業價值。數據分析絕對不是只有科技業才有的優勢。

### 想了手把手學習商業實戰案例嗎？
[大量交易資料，卻不知如何找出商業價值？點我了解！](https://tmrgood.kktix.cc/events/python0to1)

### 附上完整程式碼：
main.py

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns


# ----------pic1---------------
# 讀取資料
vitamin = pd.read_csv('vitamin.csv')

# 產生圖表
sns.lineplot(x='unit', y='Pr', hue = 'type', data = vitamin);
# 設定圖表參數
plt.title('vitamin')
plt.xlabel('unit')
plt.ylabel('Pr')
plt.yticks([])
plt.show()


# -----------pic2--------------

# 產生圖表
sns.lineplot(x='unit', y='Pr', hue = 'type', data = vitamin);

# 標準線
x = range(1,25)
y4 = [6]*24
plt.plot(x, y4, linestyle='--', c = 'red')

# 產生圖表
y4 = range(0,7)
x1 = [7.3]*7
x2 = [21.8]*7
plt.plot(x1, y4, linestyle='--', c = 'red')
plt.plot(x2, y4, linestyle='--', c = 'red')

# 設定圖表參數
plt.title('vitamin')
plt.xlabel('unit')
plt.ylabel('Pr')
plt.yticks([])
plt.show()
```

參考資料：

[1]2018年的美國新興職缺報告：https://economicgraph.linkedin.com/en-us/research/linkedin-2018-emerging-jobs-report

>本案案例為台科大研究方法課程授課內容，以獲得台科大企管系林孟彥教授同意轉載。
> 作者：林建興（TMR技術長）

* 歡迎加入我們的Line@獲取即時訊息！[https://line.me/R/ti/p/%40cde8265r](https://line.me/R/ti/p/%40cde8265r)
* [WebSite](http://tmrmds.co/)
