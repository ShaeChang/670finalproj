# China electricity industry reform: Insights with text analysis

## Description

There are two questions drove our project:

To what extent, did the array of policy concepts brought up at 2015 still seems feasible and even successful? To what extent, on the contrary, these concepts were already abandoned and substituted by other new concepts?
Real social science analysis in Chinese context, given the technical threshold?

## Problem Defination

### Part 1

China's electricity system reform is an important part of China's economic reform process. In 2015, a new round of power system reform formulated the institutional framework naming “controlling the middle and liberalizing the two ends”. This means limiting the monopoly power of the grid company occupying the "middle" part, and liberalize the users side and the generation side, which are the "two ends", and once have been regulated by the generation and consumption plan made by the government. In the power industry, China is gradually transitioning from a planned economy to a market economy. 

This process has been driven by a series of detailed policies. In recent years, China's electric power reform has certain achievements, but many policies are far from successful. For example, the theme of one of the six supporting documents of "the No.9 Document", the pilot reform of incremental power distribution, by the end of 2020, only one fifth of the pilots survived to obtain operational qualification. In this context, our core concern is: to what extent, did the array of policy concepts brought up at 2015 still seems feasible and even successful? To what extent, on the contrary, these concepts were already abandoned and substituted by other new concepts?

This part of the study will inspect a series of national-level policy documents issued by the government from 2015 to 2020, using a set of techniques of text mining.

### Part 2

As an effort to go beyond the scope of content on text analysis covered in class, we explored sentiment analysis and applied the techniques to the area of China’s electricity reforms to demonstrate the potential of its applications.

The questions in this section is less driven by our research question, but more driven by the methods: How can we apply certain techniques to a topic/field, and what insights we can get from that.

In this section, we answered questions such as: Do journal articles use more positive words or negative words. Does sentiment remain consistent throughout the paper? What are the words that people use when they talk positively or negatively about electricity reforms in China? Does taking into account negations (e.g., not good) change our findings?


## Corpus Building

### Part 1
The document issued by the Central Committee of the Communist Party of China and the State Council in March 2015, "Several Opinions on Further Deepening the Reform of the Electric Power System" (also been called, "the No.9 Document"), and six supporting documents issued six months later, marked the beginning of this round of electricity industry reform. The No.9 Document itself, clarified the main direction and spirit of the reform, whilst the six supporting documents clarified more detailed implementation plans. These documents are considered constructed the basic direction and the framework of the reform. That is the reason why we started from these six documents below.

In all, we inspected 79 national-level documents on electricity reform from 2015 to 2020. All the original materials come from the official website of Chinese government, as well as the Electricity Reform Policy Document Catalog compiled by Polaris Power Grid.

Manually, we build up the corresponding corpus. We annotated the year, title and body content of the literature as features, deleted all the format including space and lines with [online tools](http://www.esjson.com/delSpace.html), and excluded irrelevant documents. Limited by our capacity, we are not including documents issued from 2021 to 2022.

We used an R package named [jiebaR](https://github.com/qinwf/jiebaR) for Chinese text mining. The default setting of the tokenizer, worker(), includes word segmentation engine "MixSegment", as "type = 'mix'", which is a mix of "MPSegment" (Maximum Probability segmentation procedure) and "HMMSegment" (A hidden Markov model segmentation procedure); a default Chinese word segmentation lexicon, as "dict = "inst/dict/jieba.dict.utf8", which can be supplemented by a user customized terms segmentation lexicon, using "user =" argument; a default setting of segmenting a string, so if want to apply it to a data frame, then need to turn the "bylines = TRUE".

We customized a Chinese word segmentation lexicons and a Chinese stop word list. For the lexicon, we downloaded the electricity industry topic cell lexicons from an official website of an Chinese input software [Sougou](https://pinyin.sogou.com/dict/search/search_list/%B5%E7%C1%A6/normal/), and manually added tens of electricity industry reform terms, by converting the .scel format lexicon to .txt format through an open source converter [ShenLan](https://github.com/studyzy/imewlconverter). For the stop words, we downloaded the list from [GitHub](https://github.com/YueYongDev/stopwords), and manually added about a hundred stop words due to the output in the project.

### Part 2
For sentiment analysis, our corpus consists of published journal papers in both English and Chinese languages. We chose journal papers for a series of analyses in this section for two reasons: 1) there is an abundance of journal papers in both Chinese and English languages, allowing us to apply both Chinese and English sentiment lexicons; 2) it is interesting to compare attitudents/sentiments of scholars toward China’s elecricity reform differ in Chinese-speaking versus English-speaking scholarly contexts, which will likely different due to the social, political, ideological, and cultural differences proxied by the two different languages.

For journal articles in English, we searched for the key words, “China electricity reform”, using Google Scholar. We filter the date of publications to only include papers that are published after 2016, which marks the very start of electricity reform. We adopted two exclusionary criteria: 1) books were excluded because we wanted to focus on journal articles; 2) articles with low relevancy to electricity reform in China were excluded (e.g., an article on the topic of “analysis of electricity consumption in China” was excluded because it did not focus on electricity reform). The search results are sorted by relevance. We selected the first 50 articles using these inclusionary and exclusionary criteria. Amongst these 50 articles, we furtehr excluded those that could not be fully accessed online using Georgetown librart service. These procedures resulted in a total of 43 journal articles in English to be analyzed with sentiment analysis.

For journal articles in Chinese, we searched for the key words, “中国电力改革” which directly translates to “China electricity reform”, using Zhi Wang (知网；a Chinese database for journal articles that function in a similar way to Google Scholar). We adopted the same inclusionary and exclusionary criteria. The search results are sorted by the number of times being cited, which helped us locate publications that are of high quality and are influential in the field. We selected the first 50 articles. Amongst these 50 articles, we furtehr excluded those that could not be fully accessed online using Georgetown librart service. These procedures resulted in a total of _____ journal articles in Chinese to be analyzed with sentiment analysis.

## Results 

Please click [here](https://github.com/ShaeChang/670finalproj/blob/main/Final_repot.html) for our final report

## Authors

Xiyu Zhang, @ShaeChang

Jinli Wu @jw1935

## Reference
Robinson, D., & Silge Julia. Text mining with R: A tidy approach. retrieved from: https://www.tidytextmining.com/

Silge J, Robinson D (2016). “tidytext: Text Mining and Analysis Using Tidy Data Principles in R.” _JOSS_,*1*(3). doi: 10.21105/joss.00037 (URL: https://doi.org/10.21105/joss.00037), <URL:http://dx.doi.org/10.21105/joss.00037>.

词库搜索_ “电力” 搜索结果_搜狗输入法词库. (n.d.). Retrieved May 7, 2022, from https://pinyin.sogou.com/dict/search/search_list/%B5%E7%C1%A6/normal/

郎大为. (2016, August). 可能是目前最好的词云解决方案 wordcloud2 | 统计之都. https://cosx.org/2016/08/wordcloud2

Barbara. (2019, March 3). 如何用R语言做中文词云 – Seedhk. https://www.seedhk.org/2019/03/03/r-for-wordcloud/

Devin. (2022). 深蓝词库转换 [C#]. https://github.com/studyzy/imewlconverter (Original work published 2012)

YueYong. (2022). 中文常用停用词表. https://github.com/YueYongDev/stopwords (Original work published 2019)

LUOJIZ. (n.d.). R语言绘制词云图（中文&英文）_LUOJIZ1的博客-CSDN博客_r语言词云图. Retrieved May 7, 2022, from https://blog.csdn.net/qq_38865429/article/details/89407493

Qin Wenfeng and Wu Yanyi (2019). jiebaR: Chinese Text Segmentation. R package
  version 0.11. https://CRAN.R-project.org/package=jiebaR
  
Rinker, T. W. (2021). sentimentr: Calculate Text Polarity Sentiment version
  2.9.0. https://github.com/trinker/sentimentr
  
Ku, L. W., Liang, Y. T., & Chen, H. H. (2006, March). Opinion Extraction, Summarization and Tracking in News and Blog Corpora. In AAAI spring symposium: Computational approaches to analyzing weblogs.

Min, K., Ma, C., Zhao, T., & Li, H. (2015). BosonNLP: An ensemble approach for word segmentation and POS tagging. In Natural language processing and Chinese computing (pp. 520-526). Springer, Cham.

