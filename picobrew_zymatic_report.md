# Picobrew Zymatic測試報告

測試期間：2017/04/14~2017/11/27 約一年，共 22 筆實驗紀錄（有少部分實驗未寫入紀錄）

購入理由：希望藉由Zymatic的高度自動化/標準化，協助我了解原料特性，調整譜面，並節省做實驗的時間

購入通路：代理商 媽媽嘴大丙兄

開發擴充套件

* Pico運作階段自動通知網站 <http://picofollower.anotherdream.tw:81/user/ethen>
* Pico自動化冷卻系統 <https://github.com/sakura26/pico-extension>
* Pico Keg連接器替代零件

**最終測試結果：退坑**

### Short Summary

**整體來說，Zymatic是一台適合一般人的家用級釀酒設備，不過我並不推薦給對成品有要求的玩家使用。**

Zymatic確實實現了相當高度的自動化，在某些條件下可以實現「一鍵Play，晚上投酵母」的愉快體驗，也不失去自釀啤酒的樂趣（Recipe與釀造流程可高度自動化），但是基於某些尚不明朗的原因，這台設備也會在成品中帶入一種專屬於Pico的異常風味，不管是哪一種Recipe或材料都多少可以辨識得出這樣的風味。即便不是每個人都在意或是討厭這個風味，但我覺得這不是一個精釀自釀適合的工具。

### 測試Recipe種類

* Pico Pale ale(官方譜、官方配方包)
* APA
* Cream Ale
* Wheat Beer
* Witbier
* English Northen Brown ale
* Saison
* English Bitter
* kolsch

## Zymatic

Zymatic是一台高度自動化的機器，濃縮了酒廠的自動化機制於一台桌上型設備，可製作多樣的全穀類自釀，具備精確的流程控制與溫度追蹤功能。他本身肩負 多階段醣化、煮花 的功能，只有在水/麥汁加熱到指定溫度才會注入麥芽槽（註1），本身又主打全自動化（註2），乍看之下是相當適合做為量產前的小批量測試的實驗機器，這是我一開始選擇的理由

註一：雖然他會將水溫加熱到指定溫度才注入到麥芽槽，但由於缺乏攪拌與對流，實際上麥芽槽的升溫速度依然差了很多很多，溫度會低於設定4-6度，請參照實驗 [171230](https://github.com/sakura26/ethanol/blob/master/brewingHistory/171230-ethen-pico-creamale.md)

註二：由於冷卻並不包含於自動化的範圍內，所以依然無法實現無人值守釀造，這個部分我是靠開發了自動冷卻系統與通知系統來補完實現。

### 優點

* 高度自動化（冷卻除外）
* 高度客製化
* 全程皆有溫度紀錄（僅紀錄注入前的加熱溫度）
* 可線上關注系統運作狀態
* 全程處於半封閉系統，感染機率降至最低
* 蒸發量穩定，沒有DMS玉米味的問題，最終成品OG與產量預估容易
* 機體結構相對穩定，不容易出問題
* 台灣代理商對於故障排除有經驗，有維修能力

### 缺點

* 無法攪拌導致極低的糖化效率，約為BIAB等級
  * Pico 49\~56%，對比GrainFather約為60\~86%低了很多，使用 [BrewersFriend](https://www.brewersfriend.com/) 計算
* 依然需要守在前面做手動降溫，因為升溫階段的時間不一定，所以回來做冷卻的時間也不一定。如果沒有及時冷卻有可能造成IBU高於預期
  * 這個問題由專案 Pico自動化冷卻系統 <https://github.com/sakura26/pico-extension> 解決
* 高度特製的壓克力麥芽槽結構設計會因為應力集中造成自然的裂痕，且更換價格昂貴
* 精確度不如給人預期的高，大約僅有BIAB等級 參照實驗 [171230](https://github.com/sakura26/ethanol/blob/master/brewingHistory/171230-ethen-pico-creamale.md)
* Keg堵塞問題，由於麥渣依然可能隨著管線流動，走到白頭注入回keg時會累積不少殘渣，甚至堵塞系統導致溢出
  * 可以藉由增加回流管過濾裝置，或拆除白頭與Keg端彈簧解決
* 清潔並不如描述中的簡單，實際測試官方提供的清潔流程並沒有辦法真正徹底清潔管線，參見實驗 [171108](https://github.com/sakura26/ethanol/blob/master/brewingHistory/171108-ethen-creamale.md)
* **意料之外的Pico味**


## Pico味

### 定義

目前為止所有的釀造紀錄中，僅有使用Pico Zymatic時會發生一種共通的風味，這個風味不是很好描述，有人說橡膠塑膠、油耗味，有的人認為是一種醇類，也有人喝不出來，甚至有人喜歡。在我個人的描述，嗅覺會有一股略為刺鼻的苦味，入口是銳利的苦味，到了喉嚨後方則出現一種高級酯類的氣味，令人不適

除了自己品飲，也請前來自釀聚會的朋友一起喝給意見，多數人喝了幾次之後就有能力識別這個味道。以下是目前收集的評語

* 不自然的化學味
* 油ㄏㄠ味
* 電線走火味
* 塑膠味
* 寶特瓶加了熱水冷卻之後的味道
* 有朋友 釀過芒果  我後來都隱約 喝到芒果味
* 矽膠管加熱的味道
* 電線皮跟加熱塑膠管的辣味 喉嚨刺刺的

### 目前掌握的規則

* 第一次使用機器釀造時Pico味強到炸表（整桶倒了），本來以為是矽膠管沒洗想說希望以後會比較好，不過之後的批次之後還是有相同的問題
* 所有配方都一樣，唯獨使用小麥酵母（澳洲Y-1433/Safale WB-06）的測試都沒有這個味道出現（有人推測酵母會吃掉阿魏酸造成的）
* 機器的有機物殘留無法被徹底清除（測試：經過Deep Clean+30L的清水沖洗後，用清水10L空機跑釀酒流程，出來的水是淡黃色的清水，經過兩個月的沈澱出現明顯的沈澱與懸浮物）

### 問題成因推測

* 製程：冷卻速度不及時造成酒花的風味異常
  * 排除，參見 [Pico自動化冷卻系統](https://github.com/sakura26/pico-extension)
* 原料：酵母
  * [Witbier + Y1433](https://github.com/sakura26/ethanol/blob/master/brewingHistory/170720-ethen-witbier.md)
    * 結果：極淡的Pico味，幾乎難以感知
  * [Witbier + WB-06](https://github.com/sakura26/ethanol/blob/master/brewingHistory/171127-ethen-gf-bw_witbier.md)
    * 結果：幾乎難以感知
  * [Weissbier + Y1433](https://github.com/sakura26/ethanol/blob/master/brewingHistory/171127-ethen-wheat.md)
    * 結果：幾乎難以感知
  * [使用小麥酵母的CreamAle](https://github.com/sakura26/ethanol/blob/master/brewingHistory/171108-ethen-creamale.md)
    * 依然可以嚐到Pico味，但削減了很多，跟對照組S-04相比確實有效
* 製程：阿魏酸開蓋測試（壓克力蓋版可能阻礙阿魏酸的逸散）（高級酸＋醇＝高級酯）
  * 此項目尚未測試。雖然確認小麥酵母可以大幅削減Pico味，但產生的香蕉酯香氣也沒有特別強（若有大量的阿魏酸理論上會提高香蕉酯的生成），所以我認為機率不大。
* 材料：可能我使用的材料來源跟Pico八字不合
  * 排除，與經銷商大丙約定進行AB Test實驗，使用原廠配方與原廠Recipe，結果依然相同，參見實驗 [171120](https://github.com/sakura26/ethanol/blob/master/brewingHistory/171120-ethen-picopaleale.md)
* 配方設計：可能因為酒花利用率較高所以應降低酒花使用量
  * 部分同意：較低酒花用量的酒譜風味影響確實較低
* 設備特性：不同設備的溫升不全然相同
  * 不同意：投入溫度感測頭於麥芽槽中，發現有巨大的溫差存在，但對Pico提高溫度與對GF的降低溫度做的交叉測試中，並沒有降低Pico味，或是在GF的實驗中造出類似的味道
  * 實驗：Pico提高溫度 [171230-Pico-CreamAle](https://github.com/sakura26/ethanol/blob/master/brewingHistory/171230-ethen-pico-creamale.md)
  * 實驗：GF降低溫度 [171230-GF-CreamAle](https://github.com/sakura26/ethanol/blob/master/brewingHistory/171230-ethen-gf-creamale.md)
* 設備特性：矽膠/熱板交換器無法被徹底清潔，或需要強化清潔方式
  * 同意：目前確實沒有找到一個可以徹底清潔的方法，矽膠管確實會吃味道，而單純的酸鹼洗劑可能無法徹底清理，我想更換管線可能會是比較好的實驗，但管線的更換本身工程浩大，真要幹不如自己土炮三槽式設備
  * 原廠建議清潔的最大程度是 85gPBW + 4L熱水，但經過連續清潔，空機跑釀酒行程出來的水依舊有顏色，且長時間放置會發生有機物沈澱，參見實驗 [171108](https://github.com/sakura26/ethanol/blob/master/brewingHistory/171108-ethen-creamale.md)
  * Pico原廠清潔指示： <https://www.youtube.com/watch?v=eC1yYt8mc2c>
  * 經過多次測試，每次使用後皆使用PBW進行深度清潔，確實略微改善異常風味，但是依然存在，尤其對於高酒花使用量的酒。
  * 需要注意的是，Pico即便有多重過濾設施，但麥芽渣依然會順著管線進入Keg, 並堵塞在白頭/In端。建議每次清潔前都使用扳手與一字起子拆卸白頭/IN端進行清理。（為了排除變數，本篇所有測試每次測試前都有拆卸所有元件進行清潔）（Out端大概是因為我有剪管的關係，沒有累積殘渣的紀錄，不過依舊建議每次使用後清潔Out端的Filter）
  * 有趣的是，拆機看管線顏色雖然有改變，但並不嚴重
* 設備特性：矽膠管/泵浦不適合被加熱
  * 不確定。與泵浦的原始廠商SEAFLO與亞洲經銷商聯絡，對方表示泵浦是食品級的，溫度60度的限制僅代表泵浦在高於此溫度壽命會大幅縮短，但依然可以使用
  * [原廠提供之食品級文件](opt/FDA_Report_for_SEAFLO_Water_Pump_B70611638.pdf)
  * 符合食品級，並不代表不會釋出/抓住物質於液體中
* 人品：抽到籤王（？），搞不好是我手上這台有缺陷
  * 與經銷商大丙約定進行AB Test實驗，但釀造完成後始終無法與大丙約定時間完成AB Test。參見實驗 [171120](https://github.com/sakura26/ethanol/blob/master/brewingHistory/171120-ethen-picopaleale.md)


## 結論

雖然當時我是已經看了拆機圖，理解Pico的運作原理，也喝了大丙的Stout之後才決定購買的，所以發現Pico味這個問題的時候整個就是黑人問號，以為我搞錯了些什麼。但經過這一年的時候，各種可能性都試過了，剩下更換全機管線的測試也超出我所能負擔的程度。雖然大丙兄一開始也幫了不少忙，例如在壓克力麥芽槽發生漏水問題時免費提供了一個新的替換，但是後期看起來他也很忙碌，無暇協助測試，我想我的停損點也差不多該在此告一段落了。畢竟我購買這一台的目的除了實驗，也是為了節省我的時間，但現在看起來，這兩點期待似乎都無法滿足，我只好回頭去用GrainFather了。

雖然這台並沒有辦法滿足我個人對自釀的要求，但對於一般的使用者來說，也許並不是問題。他確實解決了自釀最大的問題：感染機率最小化，同時釀造出來的成品也有一定程度的水準。**如果你有考慮購買Pico Zymatic，請不要看到這篇就被嚇跑了，因為我的要求確實比較高**，還是建議您親身體會一下再做決定。

另一方面，美國Picobrew原廠看起來的發展方向也很明確：讓他成為一個家用級，人人可用的膠囊咖啡機，而非注重於風味上。這一點可以從Pico C系列的膠囊訂閱制度可以看出：更漂亮的外觀、容量縮減為5L一個批次，改成紙盒糖化效率進一步降低，官方隨附的酒花新鮮度不佳有起司味，麥芽沒有充分真空 可以略知一二（可以去關注一下Picobrew非公開社團 <https://www.facebook.com/groups/Picobrewers/> ）。因此我想我關注的議題可能不會被解決，但是方便性肯定是會繼續被加強的。能夠每個月有人寄兩個膠囊給你，塞進去就能自動感應搞定剩下一切，只要等酒喝就好，聽起來確實滿爽的 :p

P.S. 台灣目前的代理方向，也不再以釀酒為主打，而是以舒肥與氮氣咖啡為主。對於這一台造價高昂的機器來說，是有點可惜的。

最後，我們自釀也常常使用矽膠管，雖然使用比重不會像Pico那樣一直跑一直跑，但矽膠管卡味道卡顏色的問題確實也是我們要留意的

感謝你看到這邊，我想你應該也是一個自釀狂熱份子才看得了這麼落落長的怪實驗:p 如果你覺得有任何疑惑，或是發現我的盲點，請務必與我聯絡。對我來說，既然選擇了這台機器，也相信他的架構是ok的，我還是很期待能夠搞定他 

ethen @ anotherdream . tw


## Reference

### 釀造紀錄列表

* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170414-ethen-pico_pale_ale.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170424-ethen-creamale.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170425-ethen-creamale.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170425-ethen-fox.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170514-ethen-creamale.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170614-ethen-creamale.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170616-ethen-creamale.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170618-ethen-%E7%A7%91%E9%9A%86.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170619-ethen-%E7%A7%91%E9%9A%86.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170718-ethen-englishnorthenbrown.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170720-ethen-saison.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170720-ethen-witbier.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170723-ethen-creamale.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170725-ethen-englishnorthenbrown.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170729-ethen-englishnorthenbrown.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170730-ethen-englishbitter.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170730-ethen-%E7%A7%91%E9%9A%86.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170730-ethen-%E9%BA%A5%E6%B1%81.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/170731-ethen-rayapa.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/171108-ethen-creamale.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/171120-ethen-picopaleale.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/171127-ethen-bw_witbier.md>
* <https://github.com/sakura26/ethanol/blob/master/brewingHistory/171127-ethen-wheat.md>


