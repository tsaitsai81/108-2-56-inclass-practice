# 108-2-56-inclass-practice
 108-2-56節 資料科學程式設計（一） 課堂練習
TSAI
---
title: "Untitled"
output: html_document
---
```{r}

```

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

## R Markdown

This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.

When you click the **Knit** button a document will be generated that includes both content as well as the output of any embedded R code chunks within the document. You can embed an R code chunk like this:

```{r cars}
summary(cars)
```

## Including Plots

You can also embed plots, for example:

```{r pressure, echo=FALSE}
plot(pressure)
```

Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.

```{r}
```


```{r}
library(googlesheets4)
```
```{r}
library(googlesheets4)
install.packages(c("googlesheets4"))
library(dplyr)
library(lubridate)
```

```{r}
install.packages(c("googlesheets4"))
```
```{r}
a <- 2
a = 2 # = 與 <-同義
```
```{r}
3 -> b
```
```{r}
my_108_total_credits <- 15
_108_total_credits <- 15
108.total_credits <- 15
.my_108_total_credits <- 15
my.108.total_credits <- 15
.108.total_credits <- 15 # 隱藏變數
.my.108.total_credits <- 15
我的108學年總學分數 <- 15
`我的108學年總學分數` <- 15 # 特殊名稱處理，`不是名稱的一部份
`.108.total_credits` <- 15
```

```{r}
library(readr)
A02_company_all_public <- read_csv("https://www.dropbox.com/s/rtz2a9na62n3a8l/A02_company_all_public.csv?dl=1")
A02_company_all_public$`候選人` -> candidate
```

```{r}
library(httr)
library(dplyr)
GET("https://api.github.com/repos/tpemartin/108-2-56-inclass-practice/commits") %>%
  content() %>%
  View()
```

```{r}
library(googlesheets4)
`出席狀況表單網址` <- "https://docs.google.com/spreadsheets/d/1EAG49qDKPWWi0ebkVr29TLrvVnoBPfkvxYY-J3xLAHY/edit#gid=458686645" # 缺乏定義值
ss <- as_sheets_id(`出席狀況表單網址`)
homework_sheet <- sheets_read(ss,sheet=1)

```
```{r}
library(googlesheets4)
`出席狀況表單網址` <- "https://github.com/tsaitsai81/108-2-56-inclass-practice" 
ss <- as_sheets_id(`出席狀況表單網址`)
homework_sheet <- sheets_read(ss,sheet=1)
```


```{r}
source("https://www.dropbox.com/s/mk7bxvu6a3lxf79/studentEnvironmentReport.R?dl=1",print.eval = T)

```
```{r}
library(lubridate)
`小明交易1` <- list(
  ymd_hms("2020-03-31T13:40:55Z"), # Date/Time class
  "一芳", # character
  2, # numeric
  "水果茶" # character
)
print(`小明交易1`)
```
```{r}
# list含兩個vectors
`小明108學年課表A` <- list(
  c("108-1","高級會計學","高等統計學"),
  c("108-2","食在拉丁美洲")
)
print(`小明108學年課表A`)
```

```{r}
# list含兩個lists
`小明108學年課表B` <- list(
  list("108-1","高級會計學","高等統計學"),
  list("108-2","食在拉丁美洲")
)
print(`小明108學年課表B`)
```

```{r}
# list含兩個lists, 子層list又各含兩個vectors
`小明108學年課表C` <- list(
  list(
    c("108-1"), # 可只寫 "108-1"
    c("高級會計學","高等統計學")
       ),
  list(
    c("108-2"),
    c("食在拉丁美洲")
  )
)
print(`小明108學年課表C`)
```
```{r}
# list含兩個lists, 子層list又各含兩個vectors
`小明108學年課表C` <- list(
  `108學年第1學期`=list(
    c("108-1"), # 可只寫 "108-1"
    c("高級會計學","高等統計學")
       ),
  `108學年第2學期`=list(
    c("108-2"),
    c("食在拉丁美洲")
  )
)
print(`小明108學年課表C`)
```
```{r}
authorValues <- 
  list( # 由c() 改list(), 元素命名
    name="Martin老師", 
    email="mtlin@gm.ntpu.edu.tw", time="2020-03-25T07:17:40Z"
  )
committerValues <- 
  list( # 由c() 改list(), 元素命名
    name="emilyluckey", 
    email="emily007@gmail.com", time="2020-03-26T08:18:40Z"
  )

commit <- list(
  author=authorValues,
  commmitter=committerValues,
  message="update"
)

print(commit)
```
```{r}
library(lubridate)
authorValues <- 
  list(
    name="Martin老師",  
    email="mtlin@gm.ntpu.edu.tw",
    time=ymd_hms("2020-03-25T07:17:40Z")
  )
committerValues <- 
  list(
    name="emilyluckey", 
    email="emily007@gmail.com",
    time=ymd_hms("2020-03-26T08:18:40Z")
  )

commit <- list(
  author=authorValues,
  commmitter=committerValues,
  message="update"
)

print(commit)
```

```{r}
# 108-1 
course1_1081 <- 
  list(
    name="個體經濟學",
    teacher="Alice",
    grade=85
  )
course2_1081 <-
  list(
    name="總體經濟學",
    teacher="Mark",
    grade=78
  )
`108-1修課記錄` <- 
  list(
    course1_1081,
    course2_1081
  )

# 108-2
course1_1082 <- 
  list(
    name="作業研究",
    teacher="Jason",
    grade=90
  )
`108-2修課記錄` <- 
  list(
    course1_1082
  )

# 整合兩學期
`每學期修課記錄` <- list(
  `108-1`=`108-1修課記錄`,
  `108-2`=`108-2修課記錄`
)

# 完成記錄
`小明的修課記錄` <- 
  list(
    name="小明",
    semesters=`每學期修課記錄`
  )
```
```{r}
`小明的修課記錄` <- 
  list(
    name="小明",
    semesters=
      list(
        `108-1`=
          list(
            year=108,
            semester=1,
            courses=
              list(
                list(
                  name="個體經濟學",
                  teacher="Alice",
                  grade=85
                ),
                list(
                  name="總體經濟學",
                  teacher="Mark",
                  grade=78
                )
              )
            ),
        `108-2`=
          list(
            year=108,
            semester=2,
            courses=
              list(
                list(
                  name="作業研究",
                  teacher="Jason",
                  grade=90
                )
              )
            )
      ) 
    )
```

```{r}
library(jsonlite)
fromJSON("https://opendata.cwb.gov.tw/fileapi/v1/opendataapi/F-C0032-001?Authorization=rdec-key-123-45678-011121314&format=JSON") ->
  weather_next36hours
```
```{r}
object1 <- c(2,5)
object2 <- ymd_hms(
  c("2015-03-22 12:28:42","2017-12-22 15:33:48"),
  tz="Asia/Taipei"
)
object3 <- list(2, FALSE, c("a","b","c"))
save(object1, object2, object3, file="threeObjects.Rda")
```
```{r}
library(lubridate)
list1 <- 
  list(
    list(
      name="Jack",
      birthday=ymd("1998-03-21"),
      status=c(height=177, weight=80)
    )
  )

str(list1)
```
```{r}
# 更改日期
list1[[1]]$birthday <- ymd("1997-03-21")

# 新增資料
list1[[2]] <- list(
  name="Mary",
  birthday=ymd("1998-08-24")
)

str(list1)
```

```{r}
list1[[2]]$status <- c(height=163, weight=45)
list1[[1]]$status[["height"]] <- 176
str(list1)
```


#4-3
```{r}
a <- c(2, 3, 5)
b <- c(4,-1, 3)
```

```{r}
#會第一個對第一個向量做加減乘除
a+b
a-b
a*b
a/b
```

```{r}
a %%  #餘數
a ** b#次方
```
```{r}
sequenceNums <- c(11, 6, 8, 11, 12, 11, 3, 7, 10, 8)
print(sequenceNums)

sequenceNums %% 2 # 餘數為1則是奇數，0則是偶數
```

```{r}
# a+b 即等於
c(2+4, 3+(-1), 5+3)
# a**b 即等於
c(2**4, 3**(-1), 5**3)
```
```{r}
5*c(1,3,4)+7
# 其實是
c(5)*c(1,3,4)+c(7)

## 對向量5，向量7進行recycle==一直重複到向量都等長:
c(5,5,5)*c(1,3,4)+c(7,7,7)
## Recycle等長後才進行elementwise operation:
c(5*1+7, 5*3+7, 5*4+7)
```

```{r}
# 狀況一: 堆疊一定倍數剛好一樣長
c(2,3)/c(-2,-13,10,22)
c(2,3,2,3)/c(-2,-13,10,22)
```


```{r}
# 狀況二: 倍數堆疊一定會超過，只好截斷 ==會顯示出沒有相等 但是一樣可做出來
c(2,3)/c(-2,-13,10)
c(2,3,2)/c(-2,-13,10)
```

```{r}
paste0(
  c("我叫"), c("小明","小美")
)
```


```{r}
paste0(
  c("我叫","我叫"), c("小明","小美")
)
```

```{r}
paste0(
  c("他叫","我叫"), c("小明","小美","大雄") #第三個補成"他叫"
)
```

```{r}
example <- list(
  name=c("小明","小花","小新","美美"),
  height=c(175,166,170,160),
  weight=c(77,NA,60,43),
  birthday=lubridate::ymd(c("1998-03-11","1999-12-22","1995-08-22","2001-10-10")),
  hobby=c("美食 旅遊","旅遊 時尚","3C 美食","音樂 旅遊"),
  residence=c("Taipei","New Taipei","Taichung","Kaohsiung"),
  allowance=factor(c("0-1000","1001-2000","2000+","1001-2000")),
  bloodType=c("A","B","B","O")
)
```

```{r}
str(example[c("name","height")]) #中括號是因為有很多項目要比

pick_above170 <- example$height >= 170
example$name[pick_above170]
```

```{r transcript100to103}
source("https://www.dropbox.com/s/qsrw069n94k61lj/transcript100to103_list.R?dl=1")
```
```{r}
transcript100to103 <-source("https://www.dropbox.com/s/qsrw069n94k61lj/transcript100to103_list.R?dl=1")
```

```{r}
str(transcript100to103)
```

```{r}
# 只要成績大於85的
pick_above85 <-
  transcript100to103$`成績` > 85
```

```{r}
# 各學屆2年級人數
table(transcript100to103$學屆)
# 各學屆2年級成績大於85年數
table(transcript100to103$`學屆`[pick_above85])
```

```{r}
print(example[c("name","birthday")])

pick_after98 <- example$birthday >= lubridate::ymd("1998-01-01")
example$name[pick_after98]
```
```{r}
source("https://www.dropbox.com/s/16h6ggua6qtydci/exchangeRate.R?dl=1")
```

```{r}
str(exchangeRate)
```

```{r}
# 只要1998年1月（含）以後的
library(lubridate)
pick_after98_01 <-
  exchangeRate$`期間` >= ymd("1998-01-01")
```

```{r}
exchangeRate_after98 <-
  list(
    `期間`=exchangeRate$`期間`[pick_after98_01],
    `幣別`=exchangeRate$`幣別`[pick_after98_01],
    `匯率`=exchangeRate$`匯率`[pick_after98_01]
    
  )
```


```{r}
example$allowance <- 
  ordered(example$allowance)
```

```{r}
print(example[c("name","allowance")])

pick_allowanceOver1000 <- example$allowance >= "1001-2000"
example$name[pick_allowanceOver1000]
```

```{r} 
#方法2
example$allowance <-
  factor(
    example$allowance,
    levels=c("0-1000", "1001-2000", "2000+"),
    ordered = T # 設定為可排序factor
  )
```

```{r}
pick_allowanceOver1000 <- example$allowance >= "1001-2000"
example$name[pick_allowanceOver1000]
```

```{r}
jsonlite::fromJSON("https://www.dropbox.com/s/3uijub7xheib405/list_victimAges_female.json?dl=1", simplifyDataFrame = F) -> list_victimAges_female
```

```{r}
list_victimAges_female$`數目` <-
  as.integer(list_victimAges_female$`數目`)
list_victimAges_female$`年齡層` <- 
  as.factor(list_victimAges_female$`年齡層`)
```
```{r}
levels(list_victimAges_female$`年齡層`) -> levels_ages
print(levels_ages)
```
```{r}
levels_new <- c(levels_ages[c(12,13,1,8,2:7,9:11)])
levels(list_victimAges_female$`年齡層`) <- levels_new
```
```{r}
pick_above30 <- 
  list_victimAges_female$`年齡層` >= "30_39歲"
```

```{r}
sum(list_victimAges_female$`數目`, na.rm=T)
sum(list_victimAges_female$`數目`[pick_above30], na.rm = T)
```

```{r}
load()
```

```{r}
library(stringr)
```

```{r}
print(example[c("name","bloodType")])

pick_bloodB <- example$bloodType == "B"
example$name[pick_bloodB]
```

```{r}
sequenceNums <- c(11, 6, 8, 11, 12, 11, 3, 7, 10, 8)
```

```{r}
x <- c(1,5,8)
y <- c(5,8)

# x裡的元素值是不是屬於y集合
x %in% y
```
```{r}
print(example[c("name","residence")])

set_TaipeiMetro <- c("Taipei","New Taipei")
pick_fromTaipeiMetro <- example$residence %in% set_TaipeiMetro
example$name[pick_fromTaipeiMetro]
```

```{r}
str(transcript100to103)
```
```{r}
set_LawBusiness<-c("法學院","商學院")
pick_LawBusiness<- transcript100to103$`學院`%in%(set_LawBusiness)
print(pick_LawBusiness)
```
```{r}

example$name[pick_fromTaipeiMetro]
example$name[pick_not_fromTaipeiMetro]
```


```{r}
pick_not_fromTaipeiMetro <- ! pick_fromTaipeiMetro
# 或
pick_not_fromTaipeiMetro <- !(example$residence %in% set_TaipeiMetro) # (..) 裡面會先運算完才做外面!的處理
```

```{r}
x2 <- c(1,NA,10)
y2 <- c(-1,NA,20)

x3 <- c(NA,"小花")
y3 <- c(NA,"小華")
```

```{r}
is.na(x2)
```
```{r}
print(example[c("name","weight")])

pick_na <- is.na(example$weight)
example$name[pick_na]
```
```{r}
0/0
```
```{r}
list_victimAges_female$`數目` <- as.integer(list_victimAges_female$`數目`)
```

```{r}
print(example[c("name","hobby")])

pick_loveFood <- stringr::str_detect(example$hobby,"美食")
example$name[pick_loveFood]
```

```{r}
jsonlite::fromJSON("https://data.ntpc.gov.tw/od/data/api/EDC3AD26-8AE7-4916-A00B-BC6048D19BF8?$format=json") ->
  garbageRoutes
```
```{r}
str(garbageRoutes)
```
```{r}
#  1 用typeof()函數查詢電腦實質上如何看待garbageRoutes。
typeof(garbageRoutes)  
#  2 用class()函數查詢電腦把它能進行的操作運算歸屬於哪一類型。
#"data.frame"是LIST衍生出來的所以LIST可以做DATA FRAME也可以
class(garbageRoutes)
```
```{r}
# 由linename元素判斷垃圾車有幾條路線。
garbageRoutes$linename %>% factor() -> garbageRoutes$linename
levels(garbageRoutes$linename)
  
# 由linename創造： 可篩選出下午路線的「要/不要」向量pick_afternoonRoutes。
pick_afternoonRoutes <-
  stringr::str_detect(
    garbageRoutes$linename,
    "下午")
```

```{r}
levels(garbageRoutes$linename)
  
```


```{r}
unique(garbageRoutes$linename)
  
```

