[TOC]

# Lecture 1

## Questions
### 什麼是多變量分析? 為什麼使用?
- 又稱 Multivariate Data Analysis，指涉所有同時分析複數個變數(例如關於個體的量測)的統計方法。
- 所有變數一定要是隨機且變數之間要存在互相關聯(不然就要分成兩個問題)
- 個別效應難以被有意義地分開詮釋
- 為什麼：解釋與預測；幫助決策；假說驗證


### 多變量分析步驟
1. 特定出概念、背後理論；概念模型不需要太複雜或有太多細節
2. 分析規劃
    - 例如，需要至少或大概什麼規模的sample size、接受什麼樣型別的變數、估計方法等
3. underlying assumption: e.g. normality, linearity... and two more (see ppt)
4. estimate the multivariate model and assess overall model fit
    - statistical and practical significance
    - 結果是否過分地受單一/極少數觀測所影響?
5. Interpret the variate(s)
    - reveals multivariate relationships 
      - I.V.s: estimated coefficients 
      - variate(s) [D.V.(s)]: underlying dimensions of association
    - identify the empirical evidence of multivariate relationships in the sample data that can be generalized to the total population 在可被概化至母體的資料中是否能發現/看到與得到之多變量模型之經驗上的證據
6. Validate
    - 診斷性分析評估概化能力(generalizability)
    - can be generalized to the population?


### 其他問題
Why are scales of measurement important for data analysis?
- Each of the four scales (i.e., nominal, ordinal, interval, and ratio) provides a different type of information. ... Measurement refers to the assignment of numbers in a meaningful way, and understanding measurement scales is important to interpreting the numbers assigned to people, objects, and events.

What basic issues need to be examined when using multivariate analysis?
- Prediction of relations between variables is not an easy task. Each model has its assumptions. The most important assumptions underlying multivariate analysis are **normality, homoscedasticity, linearity**, and **the absence of correlated errors**. 
- See [Four important statistical assumptions](#four-important-statistical-assumptions)

## 多變量分析
Big Data
- Volume (量大)
- Variety (多樣性)、高速 (velocity)、真實性 (veracity)、快速變動性(variability)、價值(value)
- 樣本越大，統計推論的需求就越少；直接處理母體，沒有統計推論的需求(e.g., 就不用管例如confidence level那些)。
- 工具主義：只要能夠預測，不管為什麼/原理。
- 無法提供學理上的解釋
- 衝擊
  - 組織決策與學術研究
  - 分析方法與分析者: 處理看似無限量的資料


資料分析的兩支 Two distinctive approach
- Statistical/data model
  - 重點在解釋
  - 模型基於理論 > 分析資料 > 檢驗理論
  - 統計推論(樣本推母體數量特徵)以及用統計檢定檢驗模型的概化能力
  - 特定模型的建立: e.g. dependent variables and independent variables to be analyzed by the general linear model
- Datamining/Algorithmic model 
  - 重點在預測的精確度
  - 模型基於算法(例如 神經網路、決策樹)
  - 分析資料> 得到關係(模型)
  - 不重解釋與統計推論

**Also see:** 投影片表格!

Causal Inference 因果關係
- 在不做實驗的情況下得到超越統計推論的「原因-後果(cause-effect) 的論述」

Variate
- a linear combination of variables with empirically determined weight
- $Y = W_1X_1+W_2X_2+W_3X_3+...+W_nX_n$
  - e.g., $X_1=$ income; $X_2=$ education;...

| $Y$ | $X_1$ | $X_2$ | ... | $X_n$ |
| --- | ----- | ----- | --- | ----- |
| ... | ...   | ...   | ... | ...   |
| ... | ...   | ...   | ... | ...   |
| ... | ...   | ...   | ... | ...   |

### Measurement scale
- Non-metric (qualitative) scale
  - (1st level) nominal, categorical, i.e., 類別的、無序(編號與順序或量化值無關)。
  - (2nd level) ordinal, e.g., 10%-20%...; 前10%...; 順序代表測量到的特徵強弱，但不能反映強多少/弱多少。例如：非常喜歡-喜歡-普通-討厭-非常討厭
  - 不可轉成metric scale
- Metric scale: numerical, quantitative
  - (3rd level) Interval：例如溫度，有序(數值能夠比較)、等距(10$^\circ$C-20$^\circ$C區間與20$^\circ$C-30$^\circ$C)；沒有絕對的零(true zero value)
  - (4th level) Ratio: Having all properties that interval scales have and in addition a natural zero point. Ratio scale has absolute zero, hence does not have negative values.
  - 可轉成Non-metric scale
- [Difference between ratio and interval scale](https://www.questionpro.com/blog/ratio-scale-vs-interval-scale/): measurements using interval scale don’t provide any sense of ratio between one another. E.g., you can say 32$^\circ$C is hotter than 16$^\circ$C, but it is nonsense to say "it is twice as hot than 16$^\circ$C".
- Also see https://www.questionpro.com/blog/nominal-ordinal-interval-ratio/
  

![](fig/MeasurementScale_tree.png)


### Validity and Reliability
See [this](https://www.scribbr.com/methodology/reliability-vs-validity/) and ppt.

### TF table

![](fig/TFtable.png)
| "假設" \ "實際上"         | $H_0$ true (沒關係) | $H_0$ false (有關係)    |
| ------------------------- | ------------------- | ----------------------- |
| not reject $H_0$ (沒關係) | $1-\alpha$          | $\beta$ [type II]       |
| reject $H_0$ (有關係)     | $\alpha$ [type I]   | $1 - \beta$ **"Power"** |

> $H_0$ true: 虛無假設是正確的，即**沒有關係**
> $H_0$ false: 虛無假設(沒有關係)是錯的，即**有關係**
> Type I error: 沒有關係說成有關係的機率
> Type II error: 有關係說成沒關係的機率



### Statistical power
[“Statistical significance helps quantify whether a result is likely due to chance or to some factor of interest”](https://hbr.org/2016/02/a-refresher-on-statistical-significance)
![](fig/SampSzPower.png)
![](fig/SampSzPowerTb.png)
<!-- <center>
<img src="fig/SampSzPower.png" width=300><img src="fig/SampSzPowerTb.png" width=300>
</center> -->
- Sample Size太大的時候，一點小影響/差異/變化都可能會是統計顯著。**不能用於Big Data**。
- 要觀察的影響(effect size)很小的時候，則需增加Sample Size以達到足夠的Power。$\Rightarrow$ power 的增加通常是 sample size 變大造成的。

- what is effect size?
- large sample size, what increases?
- small sample size, prone to?
- power too strong, prone to?
- power too weak, prone to?
- 



Dependence Techniques
- MANOVA
  - 多個 dependent variables: Multiple (metric) = Multiple (nonmetric)
- ANOVA
  - 單個 dependent variables: Single (metric) = Multiple (nonmetric)
- Multiple Discriminant Analysis
  - 跟cluster analysis 有異曲同工之妙。
- 結構方程
  - 具有多個方程式；每個方程式(模型)都要被滿足。
  - 同時估計不同假說下的模型。


Interdependence techniques
- Factor analysis
- Cluster analysis

### Problems
- 不能取代理論的建立
- 產生指引(guidelines)

### Guidelines for multivariate analysis
- 建立實務(practical) 顯著性：(?)需較高的 effect size
- 追求簡約(parsimony)：找到少數關鍵的因子(變數)。理論(概念模型^[cpt])是限制研究範圍的重要的工具。


[^cpt]: See "Strive for Model Parsimony", p35 of Lecture Ch1

### Validate Your Result
越複雜的模型(關係/interrelationships)，常常意味著這個模型只適合特定的樣本群，難以概化(generalizable)。
  - 改善：增加每個估計的觀測資料、分割資料集、...

"分析樣本回推母體"：
- 目標是建立一個能描述母體(the population as a whole)的模型(model)，並非找到"best fit"。
- 樣本需對母體要有代表性。




### statistical and practical significance
[What’s the difference between statistical and practical significance?](https://www.scribbr.com/frequently-asked-questions/statistical-significance-vs-practical-significance/)

While statistical significance shows that an effect exists in a study, practical significance shows that the effect is large enough to be meaningful in the real world.

Statistical significance is denoted by p-values whereas practical significance is represented by effect sizes.

# Lecture 2
## Questions
What are the principal aspects of data that need to be examined?


What approaches would you use in examining each aspect?
- preliminary understanding of your data: 
  - univariate profiling (shape/distribution)
  - bivariate profiling 
    - relationships between variables
    - group differences (根據某一變數分群，看各群體的統計值。例如 分男女看成績)
- graphical examination: see shape using histogram; see relationships using scatterplot
- identify and evaluate missing values
- identify and deal with outliers
- check statistical assumptions
## Examine your data

### Missing data
key:
- random or systematic
- researcher's concern:
  - patterns and relationships underlying
  - maintain as close to the original distribution when any remedy is applied

impact:
- reduced sample size
- distort results


#### Four steps:
##### 1. the type and levels of missingness
ignorable missing data:
- expected and part of research design
- the missing data process is random
- censored data (還沒辦法被觀測到的，例如關於存活率的資料收集)

not ignorable:
- known process
  - procedural (e.g., data management)
- unknown process
  - 受試者個人因素


Three levels
- item level (獨立變數的遺失e.g., 某人有幾題未回答導致)
- construct level (e.g., 不知道或拒答)
- personal level: 關於受試者意願或回答之能力 (e.g. 願意填答者都是績效較好的、填答不誠實)


##### 2. extent of missing data (資料缺損的程度)
基本問題：
- 程度是否輕微到即使缺失值非隨機也不影響結果?

levels of analysis (百分比)
- by variable (從直行看缺值比例)
- by case (從橫列看缺值比例)

Guide:
- 10% 以下
- 處治手段(remedy)要確保sample size足夠
- 通常缺 D.V. 就直接整筆刪掉
- 若缺 I.V.，要確保有其他可替代的指標(反映原本變數的意圖，例如有4題都是評估同一項指標，則一題缺答可接受)
- 分析刪或不刪對結果的影響。

##### 3. Diagnose the randomness 
缺失值的隨機性質
- MAR: 缺值與 X 相依，但與 Y 無關；無bias。例如分析 X=企業規模 與 Y=績效 的關係，小企業缺值嚴重，還是可以進行有意義的分析(可剔除小企業)，但分析結果僅適用大企業。
- MCAR: 完全隨機 :thumbsup:
- NMAR (Not missing at random): 有bias。 e.g. 整份拒答 e.g. 績效差的公司缺值嚴重(不願意填答)。

診斷：
- t-test: 根據是否缺值分類，然後測試其他變數。例如，缺X1的一組，沒缺X1的一組，看其他變數(X234...)分布是否有差異。若有，MAR；若無，MCAR。
- Little's MCAR test "是不是足夠接近MCAR"

##### 4. Select the imputation method

策略：
- MCAR: 直接刪掉有缺值得資料 👌
- 整筆(case)刪掉或刪掉某變數(variable): 依據理論考量以及憑經驗
- 估計缺失值: imputation 

補缺值的方法
- case substitution
- mean substitution: 用平均值取代；造成離散程度被低估
- deck imputation: 用既有(hot)或外部(cold)和缺值類似的取代
- regression imputation: 把缺值根據回歸線補上；強化原有關係、低估離散程度
- model-based procedure: see [Handling “Missing Data” Like a Pro](https://towardsdatascience.com/handling-missing-data-like-a-pro-part-3-model-based-multiple-imputation-methods-bdfe85f93087)

方法偏好
- 10%以下：刪除全部缺值
- 10-20%
  - MCAR: hot deck case substitution & regression methods are preferred
  - MAR: model-based methods are necessary
- over 20%
  - MCAR: regression methods are preferred
  - MAR: model-based methods
- In general, model-based methods are preferred for both MCAR and MAR, though for MCAR any imputation methods produce unbiased results.


### Outlier
- a unique combination or extraordinary value
- is the observation/response representative of the population? 這個觀測是真的假的

一般來說(ppt p43)
- univariate: 2.5 std
- bivariate: 看關係是否特別(例如身高體輕)；scatterplot w/ confidence intervals
- multivariate methods: D2/df measure should be very conservative (0.005 or 0.001)
- D2: multivariate detection

Dealing with outliers
- 除非證明有誤，不然保留
- 包含/不包含outlier分別產生結果

#### impact
- 真實的仍須納入
- 扭曲結果；衝擊概化能力
- 常用方法「自我設限」(e.g. 因為無法辨真假，一律剔除)："我的研究結果並不及於被排除的少數群體"
### dummy variable
- non-metric I.V.
- two or more levels that are coded 0 and 1

e.g. 
| Category  | X1  | X2  |
| --------- | --- | --- |
| Physician | 1   | 0   |
| Attorney  | 0   | 1   |
| Professor | 0   | 0   |
### Four important statistical assumptions
Normality (常態性)
- 若是資料呈現常態分配 (normal distribution)，則誤差項也會呈現同樣的分配
- 統計推論(從樣本到母體)的基礎

Homoscedasticity/equality of variance (誤差項的變異數相等)
- 自變數的誤差項除了需要呈現常態性分配外，其變異數也需要相等，變異數的不相等(heteroscedasticity)會導致自變數無法有效的估計應變數
> 殘差值的分配具有相同變異數(common variance)；亦即，每個殘差值所構成的次數分配都具有相同的變異數，這項假定稱作「等分散性」(homoscedasticity)

Linearity
- 例如單位自變數變化的應變數變化是固定的(即斜率為常數)

Non-correlated errors 誤差項的獨立性(interdependence of error terms)
- 自變數的誤差項，相互之間應該是獨立的，也就是誤差項與誤差項之間没有相互關係


# Lecture 3
## Questions



## Exploratory Factor analysis