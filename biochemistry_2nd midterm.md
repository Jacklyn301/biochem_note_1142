---
title: biochemistry_2nd midterm.md

---

# biochem 2nd midterm
## electron transport, oxidative phosphorylation, oxygen metabolism
### what is mitochondrion
- glycolysis發生在cytoplasm，而pyruvate的氧化、脂肪酸的 $\beta$ -oxydation、胺基酸氧化、檸檬酸循環
- 亞區域包含outer membrane、innermembrane、intermembrane space、matrix，內膜形成cristae
- 這需內膜有嵌入非常多的蛋白質 (內膜7成就是這些蛋白質，3成為脂質)
- 內膜中的蛋白質一半參與電子傳遞鏈跟氧化磷酸化，外膜的蛋白質則是完全度一樣的系統
- 其中電子傳遞鏈一共有五個複合體，以及兩個輔酶

![image alt](https://uw.pressbooks.pub/app/uploads/sites/678/2023/05/Figure-1-ETC-1.jpg)

### 氧化跟能量生成
#### 標準還原電位
- 標準還原電位 ( $E_0 \text{'}$ ) 數值愈正代表愈容易被還原，愈負則代表愈容易失去電子被氧化: 

$$\Delta G^\circ\text{'}=-nF\Delta E_0 \text{'}=-nF(E^0\text{'}_{acceptor}-E^0\text{'}_{donor})$$

- $n$ 是半反應中轉移的電子數， $F$ 為法拉第常數 ( $96485\ J/mol\cdot V$ )
- 電子由低 $E_0 \text{'}$ 往高 $E_0 \text{'}$ 自發性流動
- 當然，這還要取決於反應物濃度，畢竟濃度差別很大的話，依然能自發性反應。假如說 $A$ 是電子受體， $B$ 是電子供體: 

$$
\begin{align}
& A_{ox} + B_{red}\rightarrow A_{red} + B_{ox}\\
& \Delta G=\Delta G^\circ\text{'}+ RT\ln (\frac{[A_{red}][B_{ox}]}{[A_{ox}][B_{red}]})
\end{align}
$$

#### 生物體內的自由能變化
- 以最基礎的氧化還原反應來當例子: 

$$NADH + H^+ + 0.5\ O_2\rightleftharpoons  NAD^+ + H_2O$$

- 在標準條件下，此反應為強放能反應: 

$$\Delta G^\circ\text{'}=-nF\Delta E_0 \text{'} = -2\times 96485\times (0.82 V - (-0.32 V))=-220\ kJ/mol$$

- 而這個反應在身體裡面，約為 $\Delta G = -381\ kJ/mol\ O_2$ ，也就是一對電子-190 kJ: 

$$
\begin{align}
& 50\times 2.5\ ATP=125 kJ\\
& 125/190 = 0.66
\end{align}
$$

> [!Tip]
> 氧化磷酸化在 *in vivo* 狀況下的效率可以到6~7成 🐱

### 電子傳輸
```mermaid
flowchart LR
NADH((NADH)):::carrier
NADH-.->NAD((NAD+)):::carrier
NADH-.->|電子傳遞|FMN

subgraph complex_I [🔴 Complex I]
  FMN([FMN]):::complexI
  FMN-.->FeS1([Fe-S]):::complexI
end

succinate(succinate<br>琥珀酸):::substrate
succinate-.->fumarate(fumarate<br>延胡索酸):::product
succinate-.->|電子傳遞|FAD

subgraph complex_II [🟢 Complex II]
  FAD((FAD)):::complexII
  FAD-.->FeS2([Fe-S]):::complexII
end

FeS1([Fe-S]):::complexI-.->Q(輔酶 Q<br>Coenzyme Q):::coenzyme
FeS2-.->Q

Q-->Cytb

subgraph complex_III [🔵 Complex III]
  Cytb([細胞色素 b<br>Cytochrome b]):::complexIII
  Cytb-.->FeS3([Fe-S]):::complexIII
  FeS3-.->Cytc1([細胞色素 c1<br>Cytochrome c1]):::complexIII
end

Cytc1-.->Cytc(細胞色素 c<br>Cytochrome c):::cytc
Cytc-.->Cyta

subgraph complex_IV [🟣 Complex IV]
  Cyta([細胞色素 a<br>Cytochrome a]):::complexIV
  Cyta-.->Cyta3([細胞色素 a3<br>Cytochrome a3]):::complexIV
end

Cyta3-.->oxygen((O₂)):::oxygen

classDef carrier fill:#fff0b5,stroke:#daa520,stroke-width:2px,color:#000
classDef substrate fill:#ffd966,stroke:#e67e22,stroke-width:2px,color:#000
classDef product fill:#ffe699,stroke:#d4ac0d,stroke-width:2px,color:#000
classDef coenzyme fill:#ffcc80,stroke:#f39c12,stroke-width:2px,color:#000
classDef cytc fill:#a8d8ff,stroke:#2980b9,stroke-width:2px,color:#000
classDef complexI fill:#ffb3b3,stroke:#c0392b,stroke-width:2px,color:#000
classDef complexII fill:#d6f5d6,stroke:#27ae60,stroke-width:2px,color:#000
classDef complexIII fill:#b3d9ff,stroke:#1f4e79,stroke-width:2px,color:#000
classDef complexIV fill:#e0d6ff,stroke:#8e44ad,stroke-width:2px,color:#000
classDef oxygen fill:#d5dbdb,stroke:#7f8c8d,stroke-width:2px,color:#000

```

#### 電子載體
##### 黃素蛋白
- flavoprotein，例如FMN (黃素單核苷酸) 與FAD (黃素腺嘌呤二核苷酸) 都是由維生素B2 (核黃素，riboflavin) 衍生而來的輔酶
- 結構特色在於共同擁有異咯嗪環 (isoalloxazine ring) 作為氧化還原核心

![image alt](https://cf2.ppt-online.org/files2/slide/r/rRfihpQ6DdI7cwo2sgxbqHESaT91FkXMj0zKB8NLuZ/slide-30.jpg)

##### 鐵硫蛋白
- 是一類含有鐵–硫簇（Fe–S cluster）的金屬蛋白
- 鐵–硫簇 (Fe–S cluster) 由鐵離子與硫化物組成，常見形式有: 
  - 2Fe–2S: 菱形結構，常見於鐵氧還蛋白 (ferredoxin)
  - 4Fe–4S: 立方體結構，常見於電子傳遞鏈的複合體 I、II
- 配位基: 大部分由蛋白質中的半胱氨酸硫醇基提供，也可能有組氨酸或天冬氨酸參與

![image alt](https://www.frontiersin.org/files/Articles/735678/fcell-09-735678-HTML/image_m/fcell-09-735678-g001.jpg)

##### 輔酶Q
- 也被稱為ubiquinone (因為太常見了，所以用了 *ubi* 為開頭)，或是被稱為Q10 (其含有10個異戊二烯單元的Q型式)
- 原本quinone分子中有兩個羰基 (C=O)，電子局限在羰基上，整個芳香環的共振被 "打斷"
- 當其接收兩個電子 + 2質子後，羰基被還原成羥基 (–OH)，羥基不再強烈拉電子，芳香環的 $\pi$ 電子可以重新分布，這讓芳香環恢復共振，變成quinol

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/coenzyme_Q_0424.png)

##### 細胞色素
- 含有**血紅素 (heme) 輔基**: 由**卟啉環 + 鐵原子**組成，鐵原子可在還原態( $Fe^{2+}$ )與氧化態( $Fe^{3+}$ )間切換，吸光能力強

> [!Note]
> 可透過偵測吸收光譜，從圖形去猜測可能的型式。不同的cytochromes有不同的吸收光譜

- 大部分細胞色素的血紅素與蛋白質非共價結合，細胞色素c是例外 (血紅素透過半胱氨酸的硫醇基與蛋白質共價結合)
- 常見的細胞色素如下:

|類型|輔基|特徵|常見位置|
|----|----|----|----|
|Cyt a|血紅素 a|卟啉環有甲酰基修飾|複合體 IV (細胞色素c氧化酶)|
|Cyt b|血紅素 b|非共價結合，跨膜蛋白|複合體 III、光合電子鏈|
|Cyt c|血紅素 c|共價結合，水溶性球狀蛋白|粒線體膜外側，電子傳遞鏈中可溶載體|

![image alt](https://pub.mdpi-res.com/cells/cells-09-00579/article_deploy/html/images/cells-09-00579-g001.png?1585750836)

#### 確定電子載體順序
- 把 "NADH被 $O_2$ 氧化" 視為一個一個小步驟來看。但是科學家們是如何確定電子載體的順序的? 🤔

##### 透過吸光光譜
- 無論是NADH、FADH2還是什麼cytochrome，其氧化態跟還原態的吸收光譜都不一樣
- 例如還原態細胞色素c在550nm附近有明顯正吸光值、NADH於340nm處有明顯正吸光值，黃素蛋白在460nm處有明顯負吸光值
- 透過在適當時機給粒線體氧氣，並且觀察吸收光譜的變化，誰變高誰變低，就可以確定不同載體從完全氧化態到部分有還原的 "時間順序"

![image alt](https://journals.physiology.org/cms/10.1152/ajpcell.00223.2006/asset/images/large/zh00120650820003.jpeg)

##### 透過抑制劑以及人工的電子受體
- 有些物質的作用靶點就是載電子傳遞鏈上面，例如: 
  - 魚藤酮 (**rotenone**) 跟異戊巴比妥 (**amytal**): 阻斷鐵硫簇蛋白把電子傳給Q10
  - **antimycin A** (抗黴素A): 抑制細胞色素b傳電子給細胞色素c
  - **cyanide**: 跟氧化態的細胞色素a3反應，阻止其接收電子
  - **一氧化碳**: 跟還原型的細胞色素a3反應，阻止其把辮子傳給氧氣
- 這些抑制位點又被稱為**crossover point** 

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/ETC_and_inhibitors_0424.png)

#### respiratory complex
##### NADH 脫氫酶，complex I
- NADH跟FMN可以可逆的交換電子
- 這種可逆的脫氫反應跟電子透過氫負離子的方式從底物轉移到目標分子

$$\text{reduced substrate}+NAD^+ \leftrightharpoons \text{oxidezed substrate} + NADH + H^+$$

- 整個複合物包含一個FMN + 八個鐵硫簇，然後電子最後會透過complex I轉手給Q10
- 基本上結構在整個進化過程中高度保守，沒啥變化

```mermaid
flowchart LR
t1((第一次<br>轉手)):::transfer
t2((第二次<br>轉手)):::transfer
t3((第三次<br>轉手)):::transfer

NADH([NADH + H⁺]):::reduced_start
NADH-->t1-->|氧化成|NAD([NAD⁺]):::oxidized

FMNo([FMN]):::oxidized-->t1-->|還原成|FMNr([FMNH₂]):::reduced
FMNr-->t2-->|氧化成|FMNo

feso([Fe³⁺-S]):::oxidized-->t2-->|還原成|fesr([Fe²⁺-S]):::reduced
fesr-->t3-->|氧化成|feso

Qo([CoQ]):::oxidized-->t3-->|還原成|Qr([CoQH₂]):::reduced

classDef transfer fill:#d6f5d6,stroke:#27ae60,stroke-width:2px, stroke-dasharray: 5 5,color:#000
classDef reduced fill:#ffb3b3,stroke:#c0392b,stroke-width:2px,color:#000
classDef reduced_start fill:#fff0b5,stroke:#daa520,stroke-width:2px,color:#000
classDef oxidized fill:#b3d9ff,stroke:#1f4e79,stroke-width:2px,color:#000
```
- 雖然鐵硫簇只能攜帶單一電子，但是FMN有兩種還原型式: 兩個電子的完全還原 $FMNH_2$ 以及單一電子的半還原 $FMNH\cdot$ ，因此能穩定的提供一個一個電子給鐵硫簇
- 電子在複合體I內部的傳遞，會造成蛋白質結構的局部能量釋放。這些能量透過蛋白質的 "構象改變" 傳遞到跨膜區域
- 膜區域有四個質子通道模組，當電子流動時，這些通道的氨基酸側鏈發生酸鹼性改變，推動質子跨膜

> [!Important]
> 每傳遞一對電子 (NADH → CoQ)，就會把4個質子從基質側打到膜間腔 🐱

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/NADH_dehydrogenase_structure.jpg)

##### 琥珀酸-輔酶Q還原酶，complex II
- Q10也會從琥珀酸獲取電子，這東西就是之前上TCA cycle時提到的succinate dehydrogenase
- 包含兩個跨膜亞基，兩個親水亞基，FAD-結合亞基，以及三個鐵硫簇
- 不泵出質子

$$succinate + Q\leftrightharpoons fumarate + QH_2$$

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/succinate_dehydrogenase_structure_0424.png)

- 除此之外，脂肪酸做 $\beta$ -氧化的時候產生的反應裡面也有一個酵素跟輔酶Q有關係，就是**ETF-QO** (把fatty acyl-CoA變成fatty enoyl-CoA) 。脂肪醯氧化的電子透過該酵素傳遞給Q10
- **G3P dehydrogenase**催化G3P變成DHAP，這個反應產生的電子最終也會丟給Q10

##### 輔酶Q:細胞色素c氧化還原酶，complex III
- 將ubiquinol的電子轉移給cytochrome c
- 以二聚體的形式存在，每個單體有10或是11個亞基
##### 備註: **Q-cycle**
- 把ubiquinol 的 "兩電子" 分拆成兩條 "單電子路徑"，最後交給只能接收一電子的cytochrome c
  - $QH_2$ 進入 $Q_0$ 位點
  - $QH_2$ 帶著 $2e^- + 2H^+$
  - 兩個質子直接釋放到膜間腔 (intermembrane space)
- 電子分流
  - 第一電子: 傳給**Rieske Fe–S center → cytochrome c1 → cytochrome c (單電子受體)**
  - 第二電子: 傳給**cytochrome bL → cytochrome bH → $Q_i$ 位點的 ubiquinone (Q)**
- 半醌形成
  - Qi位點的ubiquinone先接受一電子，形成 semiquinone ( $Q\cdot ^-$ )
- 第二個 $QH_2$ 進入 $Q_o$ 位點
  - 再次釋放 $2H^+$ 到膜間腔
  - 第一電子再傳給另一個cytochrome c
  - 第二電子再傳給 $Q_i$ 位點的 semiquinone，使它完全還原成 $QH_2$ ，並吸收 $2H^+$ 來自基質側
> [!Note]
> 結果: 每2個 $QH_2$ 在 $Q_o$ 位點被氧化...
> - 釋放 $4H^+$ 到膜間腔
> - 還原 2 個 cytochrome c (各帶走 $1e^-$ )
> - $Q_i$ 位點的 ubiquinone被還原成 $QH_2$ ，完成循環 🐱

$$QH_2 + 2\ cyt\ c_{ox}+2H^+_\text{matrix}\rightarrow Q + 2\ cyt\ c_{red} + 4H^+_\text{intermembrane space}$$

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/Q-cycle_and_complex_III_0427.png)

- 細胞色素c位於內膜靠膜間腔的那一側，也是內在途徑細胞凋亡的核心成員
- 在內原性凋亡途徑中，粒線體外膜的通透性增加，細胞色素e流到細胞質中，和其他蛋白質形成凋亡體，促進級聯反應，導致apoptosis

##### 細胞色素c氧化酶，complex IV
- 13個亞基組成，包含主要三個功能性亞基: I、II、III
- 亞基I包含兩個heme: $a$ 和 $a_3$ ，以及兩個以銅為主的center: $Cu_A$ 跟 $Cu_B$
- 起點: 細胞色素 c
  - 還原態的cytochrome c (攜帶 $1e^-$) 將電子交給Complex IV
  - 每次需要4個cytochrome c，才能完成一次完整的氧還原
- $Cu_A$ 中心
  - 第一個電子先傳到 $Cu_A$ 雙核銅中心， $Cu_A$ 是cytochrome c的主要接受者
- heme $a$
  - 電子再傳到heme $a$ ，作為中繼站
- heme $a_3–Cu_B$ 反應中心
  - 電子最後到達 heme $a_3$ 與 $Cu_B$ 組成的雙金屬中心，這裡是氧分子結合的位點
- 氧還原
  - 需要4電子 + 4質子，才能把一個 $O_2$ 分子完全還原成 $2\ H_2O$
  - **電子來自cytochrome c，質子來自粒線體基質** 

$$4\ cyt\ c_{red}(Fe^{2+}) + O_2 + 8H^+_\text{matrix}\leftrightharpoons 4\ cyt\ c_{ox}(Fe^{3+}) + 2\ H_2O + 4H^+_\text{intermembrane space}$$

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/cytochrome_c_oxidase_structure_0427.png)

##### supercomplex 
- 複合體I、III、IV，可以以1:2:1的比例結合成 "超複合體" ，這種呼吸鏈複合體傳遞電子的樣子，有時候就像一條微型導線似的

### oxidative phosphorylation
#### P/O ratio
- P/O ratio (ATP synthesized/ $O_2$ consumed): **一對電子經過electron transport chain可產生的ATP數目**
- 由於後來進一步發現，P/O ratio的實際值並非整數。例如NADH氧化的P/O ratio為2.5，succinate氧化的P/O ratio為1.5: 

$$NADH + H^+ + \frac{1}{2}O_2 + 2.5\ ADP + 2.5\ Pi \leftrightharpoons NAD^+ + H_2O + 2.5\ ATP$$

- 再次提醒一次，在標準條件下，合成2.5個ATP需要76kJ的能量，而NADH被 $O_2$ 氧化的 $\Delta G$ 為-220kJ，氧化磷酸化效率大概只有35%
- 但是由於身體中的ATP水解 $\Delta G$ 更高一點 (-50kJ/mol)，所以實際上的效率可以到60%到70%

> [!Tip]
> 什麼樣的時候反應能夠允許 "1個NADH產生2.5個ATP" ? 就是電子傳遞鏈跟ATP 合成並沒有直接的化學反應關係，也就是說，**沒有任何所謂的中間體反應物跟ATP的合成偶聯** !! 🐱

#### 驅動ATP合成的氧化反應
- 即使氧化磷酸化跟電子傳遞鏈並沒有完全直接的關係，我們依然可以把電子傳遞鏈弄成三大反應: 
  - $Q$ 搶走NADH的電子
  - 細胞色素c搶走 $QH_2$ 的電子
  - $O_2$ 搶走細胞色素c的電子
- 透過抑制劑跟底物的使用，最終可確定複合體I、III、IV可以形成ATP，但是複合體II不行: 
  - Antimycin A: **阻斷Complex III → cytochrome b還原態累積 → ATP 合成停止 → 證明Complex III是耦合位點**
  - Cyanide: **阻斷Complex IV → cytochrome $a_3$ 還原態累積 → ATP 合成停止 → 證明 Complex IV 是耦合位點**
  - Succinate + Rotenone: **電子只能走Complex II → CoQ → III → IV → ATP合成量比NADH低 → Complex II不泵質子**

#### mechanism of oxidative phosphorylation
- 利用的叫做 "化學滲透偶聯" (chemiosmotic coupling)，基本概念就是:
  - 電子傳遞鏈產生的自由能驅動主動運輸系統
  - 質子從基質泵入膜間腔，產生質子電化學梯度
  - 質子因為熱力學的所傾向的情形，沿著梯度流回基質，促進ATP合成
- 這個過程涉及ATP合成酶 (也就是complex IV)，每四個質子經過，就產生1 ATP

#### 實驗證據
##### 膜建立質子梯度
- 如果你測量膜電位差，內膜兩側的膜電位大概是150~200 mV

> [!Important]
> - 電壓梯度 = 電場強度/距離，由於細胞膜最多5nm厚，所以: 
> 
> $$\frac{0.2V}{5\times 10^-9}=4000000\ V/m$$
>
> - 這跟閃電的電壓是差不多的，慢走不送 🙂

- 根據以前算的電化學梯度公式... 

$$\Delta G=RT\ \ln (\frac{C_2}{C_1}) + ZF\Delta\psi$$

- 我們把pH (質子濃度的對數函數) 丟進去，簡化方程式為: 

$$\Delta G=2.3\ RT\ \Delta pH + F\Delta\psi$$

- 然後我們知道，內膜兩側的pH值差了0.75，在體溫下 (T=310 K)，pH的梯度貢獻大概是: 

$$2.3\times 8.314\times 310\times 0.75 = +4.45\ kJ/mol$$

- 而膜電位的部分貢獻為: 

$$F\cdot \Delta\psi = 96485\times 0.2V = 19.3\ kJ/mol$$

- 整體大概就是 $+23.75\ kJ/mol$ ，這是形成質子梯度時的反應，屬於吸能。所以梯度的釋放就是放能反應，這個放能產生的自由能就用來產生ATP 😏

##### 氧化磷酸化需要完整的內膜
- 當內膜不是連續的 (例如你用超音波震碎了一點，漏電)，電子傳遞依然可以進行，但是無法產生ATP

##### 跨膜蛋白
- 泵質子的蛋白必須是跨膜蛋白，並且接觸膜間腔還有基質。同時，為了確保單向的泵出，蛋白質的結構應該內外不對稱 (例如標記蛋白質的時候只能標記一側)

##### 解偶劑的 "神奇" 之處
- DNP跟FCCP添加到粒線體中時，可以允許質子流入基質，但是不用產生ATP。它可以當質子在膜內外的 "運輸機" 

![image alt](https://mpalmer.heresy.is/webnotes/Metabolism/graphics/dnp-pic-9af07.png)

- **Vanilomycin**
  - 一種 "陽離子載體"，特別是 $K^+/Na^+$ 交換載體
  - 把膜電位 $\Delta\psi$ 消耗掉，因為帶電的陽離子跨膜流動會中和電壓差
> [!Note]
> 結果: 雖然 $\Delta pH$ 可能還在，但 $\Delta\psi$ 被破壞 → PMF 減弱，ATP 合成受阻 🐱

- **Nigericin**
  - 是一種 " $H^+/K^+$ 交換載體"
  - 把質子梯度 $\Delta pH$ 消耗掉，因為 $H^+$ 與 $K^+$ 交換使得pH差消失。
> [!Note]
> 結果: $\Delta pH$ 被破壞，但 $\Delta\psi$ 仍可能存在 → PMF 減弱，ATP 合成受阻 🐱


##### 質子梯度就能夠產生ATP
- 就算沒有電子傳遞鏈，只要有pH的差異，ATP合成酶就能進行
- 將葉綠體在pH=4的地方孕育幾個小時，然後迅速轉移到pH=8的緩衝液，在葉綠體裡面添加ADP跟Pi，ATP就能迅速合成，同時pH梯度消失


#### complex V的結構
- 可以分為: 
- $F_0$ 部分 (膜內馬達)
  - 位於粒線體內膜，形成一個質子通道
  - c-ring: 由10~12個c亞基組成的環狀結構，質子進入後推動它旋轉
  - $a$ 亞基: 質子入口，導引質子進入 c-ring
  - 功能: 把PMF轉換成機械旋轉能
- $F_1$ 部分 (基質側催化頭)
  - 位於基質側，呈球狀
  - $\alpha_3 \beta_3$ 六聚體：三個 $\alpha$ 與三個 $\beta$ 交替排列，每個 $\alpha\beta$ 單體中間都可以塞一個腺嘌呤核甘酸，但 $\beta$ 亞基才是ATP合成的活性位點
  - $\gamma$ 軸：連接 $F_0$ 的旋轉部分與 $F_1$，像 "曲軸" 一樣插入 $\alpha_3 \beta_3$ 中心。中間的stalk除了 $\gamma$ ，還有其他subunits，形成 $\gamma\delta\varepsilon$
  - 功能: 隨著 $\gamma$ 軸旋轉， $\beta$ 亞基依序經歷三種構象 (Open → Loose → Tight)，完成ADP + Pi → ATP的合成

![image alt](https://www.encyclopedie-environnement.org/app/uploads/2020/02/ATP-Synthesis_fig2.png)

- 由於 $\gamma$ 亞基在三個 $\alpha\beta$ 二聚體內部相互作用，讓這三個二聚體每次都呈現出不同構型
##### 運作原理
- 質子流入 $F_0$ → 推動c-ring旋轉
- 旋轉傳到 $\gamma$ 軸 → $\gamma$ 軸在 $\alpha_3 \beta_3$ 中轉動
- $\beta$ 亞基構象改變: 
  - Open: 釋放ATP
  - Loose: 結合ADP + Pi
  - Tight: 催化生成ATP
- 每轉一圈，合成3個ATP

##### 天然狀態下的方向性
- ATP合成酶在沒有運作時，對ATP的親和力非常高
- 如果沒有質子動力勢 (PMF) 驅動，ATP合成酶會牢牢抓住ATP，甚至傾向於水解ATP
- 這就是為什麼它在 "沒有馬達旋轉" 時，ATP 幾乎不會釋放

##### 能量 "逼迫" 釋放ATP
- 在 $F_1$ 部分的 $\beta$ 亞基裡，ATP的結合位點親和力極高
- $\gamma$ 軸旋轉帶來的構象改變 (Open → Loose → Tight) 才是讓ATP被釋放的關鍵
- that is，ATP合成酶不是自發合成ATP，而是利用質子動力勢來 "強制降低對ATP的親和性" 

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/binding_change_model_for_ATP_synthesis_0427.png)

- 一實驗中，人們將 $\beta$ 亞基固定在蓋玻片上面，並將螢光標記的actin固定在 $\gamma$ 蛋白上面，之後加入 $\alpha$ 亞基，使玻片上形成 $F_1$ complex
- 觀察時可以發現，要是加入了ATP，可以刺激這個actin旋轉，而且旋轉方向為逆時針，而在人體中，合成ATP的 $\gamma$ 是順時針旋轉

> [!Important]
> ATP合成酶的 "高ATP親和力" ，代表它本質上是一個**ATP水解酶**，而不是天然的ATP合成器 !! 👀

##### c-ring跟質子
- 每個c亞基上都有一個保守的Asp或Glu側鏈。當質子從膜間腔進入a亞基的通道時，它會質子化這個Asp/Glu殘基
- 質子化的c亞基會隨著c-ring的旋轉移動，直到到達另一側。當Asp/Glu殘基回到基質側的出口通道時，質子被釋放，殘基恢復帶負電狀態，準備再接受下一個質子
- 由於質子只能 "**膜間腔 → 基質側**" 流動，因為 a 亞基的通道設計了 "入口" 與 "出口" 的分工

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/rotation_of_the_c-ring_of_the_F0_component_0427.png)

### resporatory control
#### 底物影響
- 底物會影響ATP合成，包含ADP、Pi、氧氣，以及可以形成NADH或是FADH2的代謝物
- 大部分的時候，ATP的量普遍比ADP的量多4~10倍，當消耗ATP時，ADP會累積，促進呼吸作用並再合成ATP。相反，能量充足的時候，累積很多ATP相當於ADP的量少，底物不足，限制電子傳遞以及產生ATP的速率
- 例如，如果我加上可氧化的底物 (例如glutamate或是malate)，對呼吸作用的影響較小 (氧氣消耗慢)，但當我另外加入ADP，氧氣消耗速率就會大幅增加，直到所有ADP都變成ATP
- 相反，要是我的可氧化底物少，但是ADP很多，我一樣無法產生大量ATP
> [!Note]
> 雖然電子傳遞鏈跟ATP合成在化學反應上是兩碼子事，但是它們會因為底物的消耗情況而互相影響，除非粒線體漏電 (解偶) 🐱

#### 質子動力勢的耦合關係
> 我們能很好理解為什麼電子傳遞鏈抑制，會抑制ATPase (因為他媽沒有質子梯度)，那反過來呢? ATPase可以影響電子傳遞鏈嗎? 🤔🤔

- **oligomycin**屬於氧化磷酸化的抑制劑，直接抑制酵素生成ATP
- 讓我們來做個思想實驗... 通常來說，正常情況下: 
  - ETC把電子傳下去，同時把質子打到膜間腔
  - ATP合成酶讓質子回流，消耗PMF，並合成 ATP，形成一個 "動態平衡": 

$$\text{質子泵出} \leftrightarrow \text{質子回流}$$

- 加入oligomycin
  - ATP合成酶的c-ring被鎖住，質子無法回流
  - 結果: 膜間腔的質子越積越多，PMF ( $\Delta\psi + \Delta pH$ ) 急速上升
- 對 ETC 的影響
  - ETC的質子泵是 "逆壓工作" 當膜電位太高，泵質子需要更多能量
  - 當PMF達到極限，電子傳遞就會被 "反壓" 阻塞。所以ETC的速率下降，氧消耗減少

> [!Tip]
> 這也是為什麼Oligomycin常被用來測試耦合性: **如果ETC和ATP合成酶是耦合的，抑制ATP 合成就會連帶抑制呼吸 !!** 🐱

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/experimental_demonstration_of_respiratory_control_0427.png)

#### 消耗ATP導致的熱力學效果
- 當我開始消耗ATP時，粒線體基質中的ATP下降，使 $\Delta G$ 更有利於磷酸化ADP。此時ATP合成持續進行，質子也會繼續流過 $F_0$ : 

$$\Delta G_\text{ATP合成} + \Delta G_{H^+ \text{重新進入基質}} < 0$$

- 同時，質子重新流入，也會降低電子傳遞在熱力學上的阻礙，反過來又增加電子傳遞，提高呼吸效率: 

$$\Delta G_{e^-\text{的運輸}} + \Delta G_{H^+ \text{的泵入}} < 0$$

#### ATP的水解
- 如果粒線體呼吸受到干擾，PMF低於某個值，且細胞質中還有ATP的存在，**adenine nucleotide translocase** (腺嘌呤核甘酸轉位酶，ANT) 會把ATP帶到粒線體基質裡面，被水解後反向讓ATP合成酶泵入質子，維持PMF
![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/reversibility_of_ATP_synthase_0427.png)
- 但是如果要避免細胞因為缺乏ATP而死給你看 (🙂)，我們有時要想辦法鎖住ATPase反向運行
- $IF_1$ ( $F_1$ **inhibitor protein**) 主要結合在 $F_1$ 的 $\beta$ 亞基附近，阻止 $\gamma$ 軸旋轉所帶來的構象改變。這樣 $\beta$ 亞基就不能進行ATP水解循環
- 這相當於是一種 "安全閥"，確保粒線體在能量危機時不會把ATP反向消耗掉
![image alt](https://www.frontiersin.org/files/Articles/917203/fphys-13-917203-HTML-r2/image_m/fphys-13-917203-g002.jpg)

#### brown adipose tissue
- 棕色脂肪的粒線體富含解偶聯蛋白 (**uncoupling protein, UCP**)，允許解偶聯的發生，脂肪氧化的能量以熱的形式釋放出來。目前哺乳動物至少表達了5種解偶聯蛋白
- 有些植物也有辦法解偶聯，尤其是那些在早春就要萌發的植物

### 粒線體的運輸系統
- 我們知道粒線體內膜有多挑剔，通透受到嚴格限制 (畢竟要避免漏電)，上面就以非常多的蛋白質管控這項系統，這些蛋白多數歸類為粒線體載體家族 (**mitochondrial carrier family, MCF**)

#### 部分MCF介紹
##### adenine nucleotide translocase, ANT
- 等量的交換ATP/ADP: 輸入一個ADP到基質，就輸出一個ATP到細胞質
- 由於ATP帶-4電荷，ADP帶-3電荷，又因為膜間腔電荷較正，因此這個交換不需要能量額外參與

##### phosphate translocase
- 磷酸轉位酶共分為兩種: 同向轉運 (**symport**) 跟反向轉運 (**antiport**)
- 這兩種傳遞方式都是維持電中性，而動力來源是pH值梯度的部分

| 種類 | 運輸方式 | 消耗的PMF成分 | 生物學意義 |
| --- | --- | --- | --- |
| **Symport** | 傳送 $HPO_4^{2-} + 2H^+$ 一起進入基質 | 消耗 $\Delta pH$ (質子梯度) | 直接利用質子<br>動力勢帶入Pi |
| **Antiport** | 傳送 $H_2PO_4^-$ 進入 ↔ $OH^-$ 出去 | 消耗 $\Delta pH$ $OH^-$ 出去相當於 $H^+$ 進來） | 另一種方式維持<br>Pi輸入與電荷平衡 |

- 缺乏這些載體的人，通常都會有運動不耐受、肌肉張力問題、肥厚型心肌病變、乳酸性酸中毒等問題

##### 氧化的底物受體
- pyruvate由**pyruvate transport system**移入基質，跟磷酸根一樣，透過和 $OH^-$ 交換來完成
- 一些兩個 $COOH^-$ 的有機酸底物 (如succinate、fumarate、malate) 可以透過**dicarboxylate transport system**互相換來換去
- 三個 $COOH^-$ 的有機酸底物 (如citrate、isocitrate)，也可以透過**tricarboxylate transport system**互相交換，或是利用兩個 $COOH^-$ 的有機酸、PEP來交換citrate跟isocitrate

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/mitochondrial_inner_membrane_transport_systems_0427.png)

#### 如何確保細胞質中的代謝能繼續?
- 粒線體需要能夠將細胞質還原當量轉運到基質。NADH需要能夠成功氧化，剩下的NAD+才能給糖解作用使用，但是NADH無法直接轉進基質，所以需要特殊的穿梭系統
- 這些穿梭系統並非利用蛋白質直接傳輸NADH，而是用 "交換" 的方式以及酵素的轉換達成

#### DHAP/G3P shuttle
##### 細胞質側
- 由cytosolic glycerol-3-phosphate dehydrogenase催化，把 NADH 的電子轉移到 DHAP，生成 G3P
- G3P可以順利穿過外膜，進入膜間腔

$$NADH + DHAP \rightarrow NAD^+ + G3P$$

##### 粒線體內膜上的反應
- G3P進入靠近內膜的mitochondrial glycerol-3-phosphate dehydrogenase
- 這個酵素含有FAD，會把G3P氧化回DHAP，同時把電子交給 FAD，產生 $FADH_2$
- 然後DHAP穿過外膜，回到細胞質
##### 電子進入ETC
- $FADH_2$ 將電子傳給ubiquinone，形成ubiquinol，進入電子傳遞鏈
##### 特點 
- 電子是以 $FADH_2$ 的形式進入ETC，跳過complex I，所以每個細胞質NADH最多只能產生約1.5 ATP，而不是2.5 ATP
- 這個shuttle系統反應迅速，適合需要快速能量供應的組織，例如大腦和骨骼肌
- 電子一旦進入粒線體，就不會再回到細胞質，不可逆

#### Malate–Aspartate shuttle
##### 細胞質側
- NADH 將OAA透過cytosolic malate dehydrogenase還原成malate
- malate 可以穿過粒線體內膜的轉運蛋白

##### 粒線體基質側
- malate 進入基質後，再被mitochondrial malate dehydrogenase氧化回OAA，並在粒線體內部生成NADH
- 這樣就把細胞質NADH的還原力 "轉移" 到粒線體內的NADH

##### 天冬氨酸迴路
- OAA在基質中不能直接穿膜，所以會先透過轉胺酶 (transaminase) 轉換成aspartate
- aspartate可以穿過膜，回到細胞質後再轉換回OAA，完成循環

##### 特點
- 效率較高，電子是以NADH的形式進入粒線體，能從complex I 開始，完整泵出10個質子，每個NADH約產生2.5 ATP
- 不同於DHAP/G3P shuttle，這個shuttle是可逆的，能根據代謝需要調整方向
- 常見於心臟、肝臟等需要高效率能量轉換的組織

| Shuttle 系統 | 電子進入ETC的位置 | 每個NADH產生 | 常見組織 | 特點 |
| --- | --- | --- | --- | --- |
| **Malate–Aspartate** | Complex I | 2.5 ATP | 心臟、肝臟 | 高效率、可逆 |
| **DHAP/G3P** | Complex II (FAD → Q) | 1.5 ATP | 腦、骨骼肌 | 速度快、不可逆 |

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/shuttles_for_transfer_of_reducing_equivalents_from_cytosol_into_mitochondria_0427.png)

### 有氧呼吸的代謝總結 🐱
- 先來做總反應式的相加大集合...

#### glycolysis

$$\text{glucose} + 2\ ADP + 2\ Pi + 2\ NAD^+\rightarrow 2\ \text{pyruvate} + 2\ ATP + 2\ NADH + 2\ H_2O + 2\ H^+$$

#### pyruvate dehydrogenase complex (PDC)

$$2\ \text{pyruvate} + 2\ NAD^+ + 2\ \text{CoA-SH}\rightarrow 2\ \text{acetyl-CoA} + 2\ NADH + 2\ CO_2$$

#### citric acid cycle (TCA cycle)

$$2\ \text{acetyl-CoA} + 4\ H_2O + 6\ NAD^+ + 2\ FAD + 2\ ADP + 2\ Pi\rightarrow 4\ CO_2 + 6\ NADH + 2\ FADH_2 + 2\ \text{CoA-SH} + 2\ ATP + 4H^+$$

#### net: 

$$\text{glucose} + 10\ NAD^+ + 2\ FAD + 2\ H_2O + 4\ ADP + 4\ Pi\rightarrow 6\ CO_2 + 10\ NADH + 6H^+ + 2\ FADH_2 + 4\ ATP$$

- 假設P/O ratio如同預期，每莫耳葡萄糖氧化，就會產生: 

$$4 + (2.5\times 10) + (1.5\times 2)=\boxed{32\ ATP}$$

- 標準狀況下，跟據ATP的水解自由能 ( $\Delta G = -30.5\ kJ/mol$ ) 以及葡萄糖的氧化自由能 ( $\Delta G = -2870\ kJ/mol$ )，運行效率為: 

$$\boxed{\frac{32 \times 30.5}{2870}=34\text{%}}$$

### 補充一下 🧠
#### mitochondrial genome
- 粒線體內部的DNA屬於雙股環狀genome，包含37個基因，編碼13種蛋白質
- 這些蛋白質都屬於電子傳遞鏈複合體的亞基，無論是I、III、IV、V裡面都有mtDNA參一咖
- 當然，大部分的粒腺體蛋白質是由細胞核幫忙編碼的，只是轉錄轉譯後再轉運至粒線體
- mtDNA的突變就會導致電子傳遞鏈方面的缺陷問題，這些缺陷容易影響腦部跟肌肉，因此又被稱為**mitochondrial encephalomyopathies**
- 有些子細胞會同時遺傳突變的mtDNA跟正常的mtDNA，這被稱為**異質性 (heteroplasmic)**
- 而且特定器官往往要有一定數量的突變mtDNA才會發病，這又被稱為**閾值效應 (threshold effect)**

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/mitochondrial_genome_0427.png)

#### reactive oxygen species
##### 🔬 superoxide 的來源
- 電子傳遞鏈中，semiquinone偶爾會把電子 "漏" 給氧氣，生成superoxide ( $O_2\cdot^-$ )
- 其他酵素 (如NADPH oxidase) 也能直接把電子傳給 $O_2$ ，產生superoxide
- 如果想要起到抗氧化的作用，就是想方設法找人去接電子，例如**peroxiredoxins**: 

$$ROOH + 2H_2O\rightarrow ROH + H_2O$$

##### 後續命運
- **歧化反應**
  - $2O_2\cdot^- + 2H^+ \rightarrow H_2O_2 + O_2$
  - $2H_2O_2\rightarrow 2H_2O + O_2$
  - 此反應由SOD (**superoxide dismutase**) 執行，迅速轉化成過氧化氫
- **Fenton反應** (dangerous 😱)
  - $H_2O_2 + Fe^{2+} \rightarrow OH\cdot + OH^- + Fe^{3+}$
  - 生成羥基自由基 (**hydroxyl radical**)，屬於最具破壞性的ROS
- **peroxynitrite產生** 
  - $O_2\cdot^- + NO\cdot \rightarrow ONOO^-$



---

## Photosynthesis
- 重點可以寫成以下簡單的形式: 

$$CO_2 + H_2O\xrightarrow[]{light\ energy} [CH_2O] + O_2$$

- 由於有些細菌使用的是不同還原劑 (不一定是水)，所以反應是也可以改寫成: 

$$CO_2 + 2H_2A \xrightarrow[]{light\ energy} [CH_2O] + H_2O + 2A$$

- 分為兩個子過程: 
  - 光反應，水分子進行光化學氧化後，還原NADP變成NADPH，並釋放出氧氣。而且能量將ADP磷酸化成ATP
  - 固碳反應，又稱為碳同化反應 (carbon assimilation reaction)，將二氧化碳跟水透過光反應產生的ATP和NADPH，形成碳水化合物

### Chloroplast: photosynthetic organelle
- 有三層膜，外膜 (**outer membrane**) 、內膜 (**inner membrane**)、類囊體膜 (**thylakoids**)，多個類囊體疊起來形成**granum**，空腔內為**lumen**，基質為**stroma**，葉綠餅中間的連絲被稱為**lamella**

> 這邊我們就音速帶過囉~ 🙂

![image alt](https://cdn.britannica.com/76/53076-050-BB83032D/stacks-membrane-vesicles-stroma-matrix-chlorophyll-membranes.jpg)

### 光反應簡介

```mermaid
graph LR
  H2O((2 H2O)):::water
  H2O-.->|透過|OEC(水分解酶複合體<br>Oxygen Evolving Complex):::water_splitting
  P1((photon)):::photon-.->|激發|P680
  OEC-.->|產生|oxygen((O2)):::oxygen
  OEC-.->|釋放|H1((4H+)):::proton
 
subgraph PSII [PSII, 光系統II]
  direction TB
  OEC-.->|透過|Yz(tyrosine殘基<br>作為電子中介):::electron_carrier
  Yz-->P680[P680 → P680*<br>電子激發]:::psii
  P680-->ph(pheophytin<br>脫鎂葉綠素a):::psii_carrier
  ph-->Qa((質體醌A)):::psii_carrier
  Qa-->Qb((質體醌B)):::psii_carrier
end

  Qb==>QH2([游離的<br>plastoquinone])
  QH2==>cytb6f[紅藻素複合體<br>Cyt b₆f complex]:::cytochromes
  cytb6f-.->|釋放|H2((8H+)):::proton
  cytb6f==>PC(plastocyanin<br>質體藍素):::plastocyanin
  PC==>P700[P700 → P700*<br>電子激發]:::psi
  P2((photon)):::photon-.->|激發|P700

subgraph PSI [PSI, 光系統I]
  direction TB
  P700-->A0(A0，初級電子受體<br>葉黃素or葉綠素):::psi_carrier
  A0-->A1(A1，次級電子受體<br>葉綠醌為主):::psi_carrier
  A1-->Fx([Fx, Fe-S cluster]):::fe_s
  Fx-->Fa_Fb([Fa/Fb, <br>Fe-S cluster]):::fe_s
end

  Fa_Fb==>Fd(ferredoxin<br>鐵氧還蛋白)
  Fd==>FNR[ferredoxin-NADP⁺<br>reductase]:::fnr
  Fd==>|循環電子<br>路徑|cytb6f
  NADP([2 NADP+]):::nadp-.->|透過|FNR
  FNR-.->|形成|NADPH([2 NADPH]):::nadph


classDef water fill:#a8d8ff,stroke:#2980b9,stroke-width:2px,color:#000
classDef water_splitting fill:#d6eaff,stroke:#3498db,stroke-width:2px,color:#000
classDef oxygen fill:#7fb3d5,stroke:#1f4e79,stroke-width:2px,color:#000
classDef proton fill:#99ccff,stroke:#2471a3,stroke-width:2px,stroke-dasharray:3 3,color:#000
classDef photon fill:#fff0b5,stroke:#daa520,stroke-width:2px,color:#000, stroke-dasharray:3 3
classDef psii fill:#ffb3b3,stroke:#c0392b,stroke-width:2.5px,color:#000
classDef psii_carrier fill:#ffcccc,stroke:#e74c3c,stroke-width:2px,color:#000
classDef electron_carrier fill:#ffd6d6,stroke:#e74c3c,stroke-width:2px,color:#000
classDef cytochromes fill:#d6f5d6,stroke:#27ae60,stroke-width:2px,color:#000
classDef plastocyanin fill:#a9dfbf,stroke:#1e8449,stroke-width:2px,color:#000
classDef psi fill:#e0d6ff,stroke:#8e44ad,stroke-width:2.5px,color:#000
classDef psi_carrier fill:#e8daef,stroke:#7d3c98,stroke-width:2px,color:#000
classDef fe_s fill:#d2b4de,stroke:#6c3483,stroke-width:2px,color:#000
classDef fnr fill:#ffd966,stroke:#e67e22,stroke-width:2px,color:#000
classDef nadp fill:#ffe0b3,stroke:#f39c12,stroke-width:2px,color:#000
classDef nadph fill:#ffcc80,stroke:#d35400,stroke-width:2px,color:#000
  
```

### 光捕獲系統
#### 光的能量
- 我們已經知道光有波動性跟粒子性 (波粒二象性，wave-particle duality)，我們可以用波長 ( $\lambda$ ) 跟頻率 ( $\nu$ ) 形容特定類型的輻射
- 根據普郎克定律，光子的能量跟其光的頻率成正比 ( $h$ 為普郎克常數)

$$E=h\nu =\frac{hc}{\lambda}$$

- 因此，就等量的光子來看，要能破壞共價鍵，你勢必要有波長較短，頻率較高的光線才辦得到，如果你只是遠紅外線，那頂多分子震動 (產生熱)，無法產生化學反應

#### 色素種類
- 有些色素是負責吸收光的，他們又被稱為**chromophores**
- 不同色素有不同的吸收光譜，這些chromophores幾乎都覆蓋了整個可見光譜的範圍

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/absorption_spectra_of_plant%20pigments_0427.png)

- 🌱 **chlorophylls**
  - 結構: 卟啉環 (**porphyrin ring**) 為核心，中央配位一個 $Mg^{2+}$ ，並帶有一條長的phytol脂肪鏈
  - 主要吸收藍光與紅光，反射綠光，因此呈現綠色；是光合作用的主要能量捕捉分子
  - 結構類似血紅素 (heme)，但中心金屬是鎂而非鐵
- 🥕 $\beta$ **-carotene**
  - 結構: 由 **40 個碳**組成的長鏈多烯烴，含有**共軛雙鍵系統**，兩端各有一個 $\beta$ -環 (cyclohexenyl ring)
  - 主要吸收藍光與綠光，呈現橙紅色；在動物體內可轉化為**維生素 A**
  - 屬於類胡蘿蔔素 (carotenoids)，在植物中常與葉綠素共存，幫助光能捕捉並保護葉綠素免受光氧化
- 🔵 **phycocyanin**
  - 結構: 屬於藻膽蛋白 (**phycobiliproteins**)，是一種蛋白質，結合開鏈四吡咯色素 (**phycocyanobilin**) 作為發色團
  - 常常存在於藍綠菌 (cyanobacteria) 與紅藻
  - 主要吸收橙紅光，呈現鮮藍色；在光合作用中作為輔助色素，將能量傳遞給葉綠素

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/photosynthetic_pigments_0427.png)

- 光合作用的第一步是LHC，每一個LHC都是一個多亞基的蛋白複合體，裡面包含多個天線色素 (antenna pigment) 以及一對作為反應中心的葉綠素分子
- 這些色素捕獲能量之後的反應，可分為共振能量傳遞以及電子傳遞
#### resonance transfer
- 沒有電子真正移動，只是激發態能量在分子之間 "傳遞"
- 供體分子的激發態電子傳遞能量，回到基態，受體電子反而變成激發態
> [!Important]
> ##### 條件：
> - 供體分子處於激發態
> - 受體分子的吸收光譜與供體的發射光譜有重疊
> - 分子距離通常在 1–10 nm 之間

![image alt](https://edin.b-cdn.net/wp-content/uploads/2024/05/Quenching_FRET_Blog_Feature_Image.png)

#### electron transfer
  - 電子真的從供體傳遞給受體，這屬於氧化還原反應

| 特徵 | Resonance Transfer | Electron Transfer |
| --- | --- | --- |
| **是否有電子移動** | ❌ 沒有，只有能量傳遞 | ✅ 有，電子跨分子移動 |
| **化學本質** | 激發態能量共振 | 氧化還原反應 |
| **距離範圍** | 1–10 nm，靠偶極耦合 | 分子接觸或共價連接 |
| **光合作用角色** | **天線色素 → 反應中心** | **反應中心 → 電子傳遞鏈** |

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/resonance_and_electron_transfer_in_chloroplast_0416.png)

- 通常在反應之後的極短時間內 ( $<10^{-10}$ ) ，能量就會從天線色素傳到反應中心的葉綠素分子
- 至於為何反應中心的葉綠素接收到能量不是變成激發態，而是成為釋放電子的還原劑，是因為: 
  - 反應中心的葉綠素並不是孤立存在，而是嵌在蛋白質複合體裡
  - 蛋白質環境改變了葉綠素的 氧化還原電位，讓它在激發態時成為一個 "超強還原劑" 
  - 這種設計使得它的激發電子更容易被鄰近的電子受體接走

>[!Important]
> 記得，**大部分的葉綠素分子並不直接參與化學過程，而是做為天線分子行resonance transfer** !! 👀


#### 光系統的原理
- Hill reaction揭示了葉綠體在光照下能夠釋放氧氣，即使沒有完整的碳固定循環
- 研究人員把分離的葉綠體懸浮液暴露在光下，並加入一個人工電子受體 (如ferricyanide)，在光照下，葉綠體能把水分解，釋放 $O_2$ ，並把電子交給人工受體
- 這證明了光合作用的 "光反應本身" 就能驅動水的氧化與氧氣釋放，不需要碳固定: 

$$4\ Fe(CN)_6^{3-} + 2H_2O \xrightarrow[]{light\ energy} 4\ Fe(CN)_6^{4-} + 4H^+ + O_2$$

- 量子效率 (Q，quantum efficiency) 是指釋放的氧氣分子數根吸收的光子數的比，研究發現當光的波長逐漸超過680nm之後，Q值大幅下降，但是700nm附近的波長範圍內還是有很強的吸收，因此認為有兩種光系統
- 吸收波長達到700nm的光系統被稱為PSI (葉綠素被稱為P700)，而吸收波長在680nm以下的光系統叫做PSII (葉綠素被稱為P680)
- 在兩個光系統中，第一步是將激發態的電子從反應中心傳遞到電子傳遞鏈
- 電子的最主要來源是水分子，而終點是NADP分子。而電子傳遞的過程中，質子會被釋放到類囊腔，其中，質子一部份來自於水，一部份來自於基質
- 電子的傳遞跟其所含的能量在光系統中呈現出**Z-scheme**的形式

![image alt](https://cdn.britannica.com/80/3480-050-897EEB7C/Flow-electrons-reactions-reaction-stage-photosynthesis-Arrows.jpg)

### 光反應前半段
#### PSII
- 光合作用的第一步是 "光捕獲系統吸收光子" ，傳遞時天線色素回到基態釋放的光子，這個光子會促進P680釋放電子
- 釋放完電子之後，P680形成強氧化劑，促進 $H_2O$ 的裂解

![image alt](https://www.agrisera.com/dokument/bibliotek/Image/10.-PSII_cofactors.png)

##### OEC
- 放氧複合體 (**oxygen evolving complex**)，屬於PSII的一個亞基，含有 $Mn_4CaO_5$ 簇，以及酪胺酸殘基 (Yz，把OEC電子給P680+)
- 共有四種氧化態: $S_1$ 、 $S_2$ 、 $S_3$ 、 $S_4$ ，每一次都是Yz被抽走一個電子，累積其還原力，同時在其重新還原回 $S_0$ 時，裂解兩分子水
- 同時，裂解水產生的質子會被釋放到類囊體腔。這整個過程被稱為**S-state cycle**

![image alt](https://frenchbic.cnrs.fr/wp-content/uploads/2020/06/PSII.png)

#### quinone的差別
- 在電子傳遞鏈上，氧化磷酸化用的是ubiquinone (泛醌，Q10)，光合磷酸化用的是plastoquinone (質體醌)，當然植物有不同的質體醌 (包含光系統內的 $Q_A$ 跟 $Q_B$ )
- 同樣，ubiquinone還原後會變成ubiquinol，plastoquinone還原後會變成plastoquinol

![image alt](https://www.frontiersin.org/files/Articles/219304/fpls-07-01898-HTML/image_m/fpls-07-01898-g001.jpg)

#### cytochrome $b_6 f$ complex
- 包含細胞色素 $f$ (含有c-type血基質)、細胞色素 $b_6$ (含有兩個b-type血基質)、跟Rieske鐵硫簇蛋白
- 該複合物類似於粒線體中的complex III，也會催化類似的Q-cycle

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/cytochrome_b6f_complex_0428.png)

### 光反應後半段
#### PSI
- 一樣包含天線色素跟反應中心的葉綠素P700，電子激發後會經過一系列的傳遞鏈，包含: $A_0$ (特殊的葉黃素或是葉綠素)、 $A_1$ (葉綠醌，也就是維生素K)、三個鐵硫簇分子 ( $F_X$ 、 $F_B$ 、 $F_A$ )

![image alt](https://www.agrisera.com/dokument/bibliotek/Image/2.-PSI_cofactors.png)

#### ferredoxin and FNR
- 鐵氧還蛋白存在於葉綠體基質中，透過ferredoxin: $NADP^+$ oxidoreductase反應，把電子給 $NADP^+$ :

$$2\ Fd_{red} + H^+ + NADP^+ \xrightarrow[Fd-NADP^+\ reductase]{} 2\ Fd_{ox} + NADPH$$

### 小總結
#### ATP synthesis
- 光系統II的總反應如下: 

$$2\ H_2O\xrightarrow[]{+4h\nu} 4H^+ + 4e^- + O_2$$
 
- 光系統II的總反應如下: 

$$4e^- + 2H^+ + 2\ NADP^+ \xrightarrow[]{+4h\nu} 2\ NADPH$$

- 所以總反應就變成: 

$$2\ H_2O + 2\ NADP^+ \xrightarrow[]{+8h\nu} 2H^+ + O_2 + 2\ NADPH$$

- 與粒線體內膜不同的是，葉綠體的類囊膜可以對其它離子有通透性 (如 $Mg^{2+}$ 和 $Cl^-$ )，因此大部分的膜電位都會被中和掉，唯一能決定質子動力勢的東西主要就是質子的濃度梯度。通常，類囊體膜兩側產生的pH差可以非常大 
- 與粒線體中的ATP生成類似，這些質子只能透過ATP合成酶複合體穿過類囊膜，這複合體被稱為 $CF_0-CF_1$ (粒線體的ATPase被稱為 $F_0-F_1$ )
- 每三個質子經過 $CF_0-CF_1$ ，就會生成1ATP ( $F_0-F_1$ 產生一個ATP需要4個質子)，這樣來看，根據產生一個 $O_2$ 會得到12個 $H^+$ ，這樣會產生4個ATP

#### 蛋白質的不均勻分布
- PSII主要位於疊片的內側 (grana stacks)，而PSI主要位於基質片 (stroma lamellae) 或是類囊體外側
- ATPase由於同時要和基質和類囊腔接觸，所以一律在類囊腔外側

![image alt](https://image.slideserve.com/1491515/arrangement-of-photosystems-in-thylakoid-membrane-l.jpg)

#### 循環電子途徑
- 當鐵氧還蛋白接收到電子之後，可以選擇不去和FNR反應，而是把電子轉給cytochrome $b_6 f$ complex，這樣子就有辦法再泵出一次質子。而該複合體的電子後來會被質體藍素接收，再去補充PCI的電子，如此往復
- 這種狀況在NADPH很多，沒有還原劑可以接電子時，依然有辦法讓葉綠體產生ATP
- 在此過程中，沒有氧氣被釋放，也沒有NADPH的產生
![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/cyclic_electron_flow_in_light_reaction_0427.png)

### 固碳反應簡介

```mermaid
flowchart LR

CO2((6 CO2)):::co2
CO2==>|透過|rubisco(RuBisCo<br>二磷酸核酮醣羧化酶):::rubisco
RuBP([6個 RuBP<br>1,5-二磷酸核酮醣]):::rubp==>|透過|rubisco
rubisco==>|形成|C6[6個<br>6碳化合物]:::c6
C6==>|裂解成|3PGA([12個 3-PGA<br>3-磷酸甘油酸]):::pga
3PGA==>|形成|13BPG([12個 1,3-BPG<br>1,3-二磷酸甘油酸]):::bpg
12ATP((12 ATP)):::atp-.->|加入|13BPG
13BPG==>G3P([12個GAP +<br>12個DHAP]):::g3p
13BPG-.->|剩下|12ADP((12 ADP)):::adp
NADPH([12 NADPH]):::nadph-.->|加入|G3P
G3P-.->|水解|Pi((12 Pi)):::pi
G3P==>|拉出|1G3P([3個GAP +<br>3個DHAP]):::g3p_out
G3P-.->|剩餘|NADP([12 NADP+]):::nadp
1G3P==>|形成|FBP([3個 F16BP]):::fbp
FBP==>3F6P([3個 F6P]):::f6p
3F6P==>|拉出|1F6P:::f6p_out
3F6P==>|其餘重生RuBP|2F6P([2個 F6P]):::f6p
FBP-.->|水解|3Pi((3 Pi)):::pi

1F6P([1個 F6P]):::f6p_out==>G6P([1個 G6P]):::g6p

G6P==>G1P([1個 G1P]):::g1p
G1P==>result{產生<br>直鏈澱粉}:::starch
1ATP((1 ATP)):::atp-.->|被水解|result
result-.->|剩餘|1Pi((1 Pi)):::pi
result-.->|剩餘|1ADP((1 ADP)):::adp

2F6P==>|形成|RuP

G3P==>|其餘重生RuBP|5G3P([4個GAP +<br>2個DHAP]):::g3p_regen
5G3P==>|形成|RuP([6個 Ru5P<br>5-磷酸核酮糖]):::ru5p
RuP==>|形成|RuBP
3ATP((3 ATP)):::atp-.->|加入|RuBP
RuBP-.->|剩下|3ADP((3 ADP)):::adp

classDef co2 fill:#d6f5d6,stroke:#27ae60,stroke-width:2px,color:#000
classDef rubisco fill:#a9dfbf,stroke:#1e8449,stroke-width:2px,color:#000
classDef rubp fill:#c8e6c9,stroke:#2e7d32,stroke-width:2px,color:#000
classDef c6 fill:#b9f6ca,stroke:#00c853,stroke-width:2px,color:#000
classDef pga fill:#a5d6a7,stroke:#2e7d32,stroke-width:2px,color:#000
classDef atp fill:#ffb3b3,stroke:#c0392b,stroke-width:2px,color:#000
classDef adp fill:#ffcccc,stroke:#e74c3c,stroke-width:2px,color:#000
classDef nadph fill:#ffd6d6,stroke:#e74c3c,stroke-width:2px,color:#000
classDef nadp fill:#ffe0e0,stroke:#e74c3c,stroke-width:2px,color:#000
classDef pi fill:#f5c6c6,stroke:#c0392b,stroke-width:1.5px,stroke-dasharray:3 3,color:#000
classDef bpg fill:#b3d9ff,stroke:#1f4e79,stroke-width:2px,color:#000
classDef g3p fill:#99ccff,stroke:#2980b9,stroke-width:2px,color:#000
classDef fbp fill:#7fb3d5,stroke:#1f4e79,stroke-width:2px,color:#000
classDef f6p fill:#a8d8ff,stroke:#2980b9,stroke-width:2px,color:#000
classDef g6p fill:#85c1e9,stroke:#2471a3,stroke-width:2px,color:#000
classDef g1p fill:#5dade2,stroke:#1a5276,stroke-width:2px,color:#000
classDef g3p_out fill:#d6eaff,stroke:#3498db,stroke-width:2px,color:#000
classDef f6p_out fill:#d6eaff,stroke:#3498db,stroke-width:2px,color:#000
classDef g3p_regen fill:#e0d6ff,stroke:#8e44ad,stroke-width:2px,color:#000
classDef ru5p fill:#d2b4de,stroke:#7d3c98,stroke-width:2px,color:#000
classDef starch fill:#fff0b5,stroke:#daa520,stroke-width:2.5px,color:#000

```

- 通常發生在葉綠體基質中，或是光合細菌的細胞質中，功能就是將大氣中的二氧化碳固定為碳水化合物
- 卡爾文等人利用小球藻 (*Chlorella*) 跟柵藻 (*Scenedesmus*) 培養於 $^{14}C$ 標記的二氧化碳裡面幾秒鐘後，殺死細胞，用二維紙層析技術分析萃取物，並把色譜圖曝光於X-ray膠片，檢測放射性化合物
- 以此獲得循環的第一個產物3-PGA，逐一找出整個循環圖徑
#### 二氧化碳固定跟糖生成
##### RuBisCo
- 二氧化碳的接收分子為1,5-二磷酸核酮醣 (**ribulose-1,5-bisphosphate, RuBP**)，二氧化擴散到葉綠體基質後，添加到RuBP的羰基碳上
- 該反應由二磷酸核酮醣羧化酶 (ribulose-1,5-bisphosphate carboxylase, **RuBisCo**) 催化，可謂是生物圈中最豐富的酵素之一 (真的很多)

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/RuBisCo_reaction_0427.png)

- 此反應基本上是不可逆的 ( $\Delta G^\circ\text{'}= -35.1\ kJ/mol$ )，酵素作用結束後，二氧化碳已被固定成碳水化合物了

##### GAP生成
- 3-PG透過兩個酵素變成GAP，這個反應跟糖質新生的一部份反應幾乎一模一樣，只是糖質新生中使用的NADH變成NADPH而已，其餘酵素反應機制基本一模一樣，很簡單吧 🐱

$$\text{3-phosphoglycerate}\xrightarrow[phosphoglycerate\ kinase]{+ATP} \text{1,3-bisphosphoglycerate}\xrightarrow[GAP\ dehydrogenase]{+NADPH} \text{glyceraldehyde-3-phosphate}$$

##### 己糖生成
- 基本上非常類似糖質新生途徑。假如說我是固定六個碳，在最終生成的物質裡面 (12 GAP + 12 DHAP)，會有三個GAP + DHAP形成三個F6P，而只有其中一個F6P會繼續走糖質新生途徑，而另外兩個會用別的酵素再次回到重生RuBP的路徑。F6P異構化成G1P後，會去合成澱粉。只是不同於肝糖生成使用UTP，植物使用ATP: 

$$
\begin{align}
& \text{glucose-1-phosphate} + ATP \rightarrow ADP\text{-glucose} + PP_i\\
& ADP\text{-glucose} + \text{(glucose)}_n \rightarrow \text{(glucose)}_{n+1} + ADP
\end{align}
$$

- 如果是改合成蔗糖，反應式有所不同: 

$$
\begin{align}
& UTP + \text{glucose-1-P}\rightarrow UDP\text{-glucose} + PP_i\\
& UDP\text{-glucose} + \text{frcutose-6-P}\rightarrow UDP + \text{sucrose-6-P}\\
& \text{sucrose-6-P} + H_2O\rightarrow \text{sucrose} + P_i
\end{align}
$$

#### 再合成受質
```mermaid
flowchart LR

GAP1([2 GAP<br>6C]):::intermediate
DHAP([2 DHAP<br>6C]):::intermediate
GAP2([2 GAP<br>6C]):::intermediate

F6P([2 F6P<br>12C]):::intermediate
F6P-->|透過|E1(Transketolase):::enzyme
GAP1-->|透過|E1

E1-->|形成|A1([2 xylulose-5-P<br>木酮糖-5-磷酸<br>10C]):::intermediate
E1-->|形成|A2([2 erythrose-4-P<br>赤藻糖-4-磷酸<br>8C]):::intermediate

A2-->|透過|E2(Transaldolase):::enzyme
DHAP-->|透過|E2

E2-->|形成|A3([2 sedoheptulose-BP<br>景天庚酮糖二磷酸<br>14C]):::intermediate

A3-->|透過|E3(Phosphatase):::phosphatase
E3-->|形成|A4(2 sedoheptulose-7-P<br>景天庚酮糖-7-磷酸<br>14C):::intermediate
E3-->|水解出|2Pi((2 Pi))

A4-->|透過|E4(Transketolase):::enzyme
GAP2-->|透過|E4

E4-->|形成|A5([2 xylulose-5-P<br>木酮糖-5-磷酸<br>10C]):::intermediate
E4-->|形成|A6([2 ribose-5-P<br>核糖-5-磷酸<br>10C]):::intermediate

A1-->|轉變成|B1([2 ribulose-5-P<br>核酮糖-5-磷酸<br>10C]):::ribulose
A5-->|轉變成|B2([2 ribulose-5-P<br>核酮糖-5-磷酸<br>10C]):::ribulose
A6-->|轉變成|B3([2 ribulose-5-P<br>核酮糖-5-磷酸<br>10C]):::ribulose

B1-->|消耗<br>2 ATP|result{6 RuBP<br>1,5-二磷酸核酮糖<br>30C}:::rubp
B2-->|消耗<br>2 ATP|result
B3-->|消耗<br>2 ATP|result

classDef enzyme fill:#ffb3b3,stroke:#c0392b,stroke-width:2px,color:#000
classDef phosphatase fill:#ffcccc,stroke:#e74c3c,stroke-width:2px,color:#000
classDef intermediate fill:#b3d9ff,stroke:#1f4e79,stroke-width:2px,color:#000
classDef ribulose fill:#d6eaff,stroke:#3498db,stroke-width:2px,color:#000
classDef rubp fill:#fff0b5,stroke:#daa520,stroke-width:2.5px,color:#000
```

- 要記得反應的分子種類相對來說更加複雜: 
  - 轉移到再生途徑的6個GAP中，是以 "**2 DHAP + 4 GAP**" 的形式反應的
  - 其中還有兩個F6P分子反應，F6P來自 "**1 DHAP + 1 GAP**"
  - 這些分子在反應時，經過多次的重排反應
- 再生反應的最後一步驟是將R5P變成RuBP，每再生成一個RuBP，就要消耗一分子ATP

### 來做個大總結
- 我們知道12個NADPH才能生成一個六碳的糖，我們將ATP的反應一塊記下，光反應反應如下: 

$$
\begin{align}
& 12\ H_2O + 12\ NADP^+\rightarrow 12\ H^+ + 12\ NADPH + 6\ O_2\\
& 18\ ADP + 18\ Pi + 18\ H^+\rightarrow 18\ ATP + 18\ H_2O\\
\Rightarrow & 12\ NADP^+ + 18\ ADP + 18\ P_i + 6\ H^+ \rightarrow 18\ ATP + 6H_2O + 12\ NADPH + 6O_2
\end{align}
$$

- 而暗反應的部分，根據剛才在卡爾文循環的反應式，如下:

$$
\begin{align}
& 6\ CO_2 + 12\ NADPH + 12\ H^+ \rightarrow C_6 H_{12} O_6 + 12\ NADP^+ + 6\ H_2O\\
& 18\ ATP + 18\ H_2O \rightarrow 18\ ADP + 18\ P_i + 18\ H^+\\
\Rightarrow & 6\ CO_2 + 18\ ATP + 12\ NADPH + 12\ H_2O\rightarrow C_6 H_{12} O_6 + 18\ ADP + 18\ P_i + 12\ NADP^+ + 6\ H^+
\end{align}
$$

- 兩個反應式加在一起，得到: 

$$6\ H_2O +6\ CO_2 \xrightarrow[]{+48h\nu} C_6 H_{12} O_6 + 6\ O_2\quad \Delta G^\circ \text{'} = +2870\ kJ/mol$$

- 假如說我們使用了650nm的光線，那麼48莫耳的光子相當於有: 

$$\frac{hc}{\lambda}\times N_A = \frac{(6.63\times 10^{-34})(3\times 10^8)}{650\times 10^{-9}} \times (6.03\times 10^{23})\times 48 \approx 8857\ kJ/mol$$

- 那光系統的效率在標準狀況下大概是: 

$$\frac{2870}{8857} = \boxed{32\text{%}}$$

#### 光合作用的調控
- Rubisco對多種糖類化合物敏感，這些化合物可以做為長細抑制劑，例如xylulose-1,5-biphosphate、2-carboxy-D-arabinitol-1-phosphate (CA1P)、以及底物RuBP本身
- CA1P是最有效的Rubisco抑制劑之一，在黑暗中於葉綠體合成，導致Rubisco活性在黑暗中下降
- 同時，Rubisco也受Rubisco activase 調控。activase需要ATP，並且受光反應產生的能量影響
- 當光照充足時，activase會因為來自光反應的電子，以及一系列的電子傳遞被活化，從而導致Rubisco的活化

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/CA1P_and_rubisco_activase_0427.png)

| 分子 | 全名 | 功能 | 狀態 |
| --- | --- | --- | --- |
| **CA1P** | 2-carboxy-D-arabinitol-1-phosphate | 抑制 RuBisCO 活性 | 夜間或光照不足時存在 |
| **RuBisCO activase** | RuBisCO 活化酶 | 移除 CA1P，恢復 RuBisCO 活性 | 白天光照充足時作用 |

### photorespiration and $C_4$ cycle
- 光呼吸是植物在光照下進行的一種副反應，它跟Calvin cycle緊密相關，但會導致能量和碳的浪費

#### Rubisco的雙重活性
- Rubisco不只會固定 $CO_2$，還能錯誤地結合 $O_2$
- 當Rubisco把 $O_2$ 加到RuBP上時，產生的是3-phosphoglycerate (3-PGA) 和 2-phosphoglycolate (2-PG)，2-PG無法直接進入Calvin cycle，必須經過一系列 "回收途徑" 
- 這會導致碳的損失 (因為釋放了 $CO_2$ ，只有四分之三的二氧化碳回到了葉綠體)，而且需要ATP與還原力來回收副產物，而且期間會釋放 $NH_3$ ，需要再同化
- 途徑簡介如下: 
  - 葉綠體: Rubisco產生2-PG → 轉成glycolate (乙醇酸)
  - 過氧化體: glycolate → glyoxylate (乙醛酸) → 轉胺作用 → glycine (甘胺酸)
  - 粒線體: 兩個glycine → serine (絲胺酸) + $CO_2$ + $NH_3$
  - 回到葉綠體: serine → hydroxypyruvate → glycerate → 消耗ATP → 3-PGA，重新進入Calvin cycle

![image alt](https://raw.githubusercontent.com/Jacklyn301/image_bank/main/photorespiration_0427.png)

- 光呼吸雖然 "浪費" ，但也有保護作用，在高光、低 $CO_2$ 的情況下，Rubisco更容易結合 $O_2$ ，也能能避免電子過度積累，減少ROS生成，幫助植物維持代謝平衡

#### $C_4$ 循環
- 為了盡量減少光呼吸， $C_4$ 植物會在葉肉細胞 (mesophyll) 先把 $CO_2$ 固定成四碳化合物，再運送到維管束鞘細胞 (bundle sheath)，讓Rubisco在高濃度 $CO_2$ 環境下工作，減少光呼吸
- 將碳固定成 $C_4$ 化合物的循環中，每一個循環就需要額外消耗2ATP，但是減少碳被浪費的機率
- 由於維管束鞘細胞裡面的氧含量不能太多，因此通常該細胞裡面缺乏能裂解氧氣的OEC
- 通常來說，固定 $CO_2$ 的酵素 (PEP carboxylase) 作用底物為 $HCO_3^-$ ( $CO_2$ 的水溶形式)，PEP carboxylase對 $HCO_3^-$ 的**親和力非常高 (Km值低)**，比Rubisco對 $CO_2$ 的親和力強得多

```mermaid
flowchart LR
CO21((CO₂)):::CO2-.->|進入葉肉|PEPC(PEP carboxylase):::enzyme_mesophyll

subgraph 葉肉細胞 [🌿 葉肉細胞 Mesophyll Cell]
  Py2([pyruvate<br>丙酮酸, 3C]):::malate_meso
  Py2==>PEP([phosphoenolpyruvate<br>磷酸烯醇丙酮酸, 3C]):::pep
  ATP([ATP + Pi]):::atp-.->|利用於形成|PEP
  PEP-.->|產生|AMP([AMP + PPi]):::amp
  PEP==>PEPC
  PEPC==>OAA([oxaloacetate<br>草醯乙酸, 4C]):::oaa
  PEPC-.->|水解|Pi((Pi)):::pi
  OAA-->M1([malate<br>蘋果酸, 4C]):::malate_meso
  NADPH1([NADPH]):::nadph==>|被用來形成|M1
  M1-.->|產生|NADP1([NADP+]):::nadp
end

M1==>|進入維管束鞘|M2([malate<br>蘋果酸, 4C]):::malate_bs

subgraph 維管束鞘細胞 [🌾 維管束鞘細胞 Bundle Sheath Cell]
  M2==>Me(malic enzyme):::enzyme_bs
  Me==>Py1([pyruvate<br>丙酮酸, 3C]):::malate_bs
  NADP2([NADP+]):::nadp-.->Me
  Me-.->|釋放|CO22((CO₂)):::CO2-.->CC{進入<br>Calvin cycle}:::calvin
  Me-.->|釋放|NADPH2([NADPH]):::nadph-.->CC
end

Py1==>|回到葉肉細胞|Py2

classDef CO2 fill: #cecece, stroke: #5a5a5a, stroke-dasharrow: 3 3, color: #000
classDef enzyme_mesophyll fill:#b9f6ca,stroke:#00c853,stroke-width:2px,color:#000
classDef pep fill:#c8e6c9,stroke:#2e7d32,stroke-width:2px,color:#000
classDef oaa fill:#a5d6a7,stroke:#2e7d32,stroke-width:2px,color:#000
classDef malate_meso fill:#81c784,stroke:#1b5e20,stroke-width:2px,color:#fff
classDef enzyme_bs fill:#b3d9ff,stroke:#1f4e79,stroke-width:2px,color:#000
classDef malate_bs fill:#7fb3d5,stroke:#2471a3,stroke-width:2px,color:#fff
classDef calvin fill:#a8d8ff,stroke:#2980b9,stroke-width:2px,color:#000
classDef atp fill:#ffb3b3,stroke:#c0392b,stroke-width:2px,color:#000
classDef amp fill:#ffcccc,stroke:#e74c3c,stroke-width:2px,color:#000
classDef nadph fill:#ffd6d6,stroke:#e74c3c,stroke-width:2px,color:#000
classDef nadp fill:#ffe0e0,stroke:#e74c3c,stroke-width:2px,color:#000
classDef pi fill:#f5c6c6,stroke:#c0392b,stroke-width:1.5px,stroke-dasharray:3 3,color:#000
```
