# 108-2-56-inclass-practice
 108-2-56節 資料科學程式設計（一） 課堂練習
TSAI
```{r}
# 10位學生的主系
majors10_char <- c('經濟學系','社會學系','社會學系','經濟學系','經濟學系','社會學系','經濟學系','經濟學系','經濟學系','社會學系')

typeof(majors10_char)
class(majors10_char)
```

```{r}
majors10_factor <- factor(majors10_char)
# 或
majors10_factor <- factor(
  c('經濟學系','社會學系','社會學系','經濟學系','經濟學系','社會學系','經濟學系','經濟學系','經濟學系','社會學系')
)

typeof(majors10_factor)
class(majors10_factor)
```
```{r}
majors10_char
```
```
```{r}
majors10_factor
```


```{r}
studentId <- c(410773002, 410773015)
```

```{r}
a <-c(410773002, 410773015)
as.character(a}
as.character.(c(10773002,410773015))
class(a)
```





```{r}
library(lubridate)
```


```{r}
tpeTime <- ymd_hms("2020-03-18 13:52:40",  
        tz="Asia/Taipei")
```


```{r}
pgTime <- mdy_hms("Mar.18, 2020, 05:52:40",
                  tz="Europe/Lisbon")
```

```{r}
with_tz(tpeTime, tzone="UTC")
with_tz(pgTime, tzone="UTC")
```
```{r}

```
```{r}

```
```{r}

```
```{r}

```
```{r}

```
```{r}

```




















