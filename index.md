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


## Corpus Building

### Part 1
The document issued by the Central Committee of the Communist Party of China and the State Council in March 2015, "Several Opinions on Further Deepening the Reform of the Electric Power System" (also been called, "the No.9 Document"), and six supporting documents issued six months later, marked the beginning of this round of electricity industry reform. The No.9 Document itself, clarified the main direction and spirit of the reform, whilst the six supporting documents clarified more detailed implementation plans. These documents are considered constructed the basic direction and the framework of the reform. That is the reason why we started from these six documents below.

In all, we inspected 79 national-level documents on electricity reform from 2015 to 2020. All the original materials come from the official website of Chinese government, as well as the Electricity Reform Policy Document Catalog compiled by Polaris Power Grid.

Manually, we build up the corresponding corpus. We annotated the year, title and body content of the literature as features, deleted all the format including space and lines with [online tools](http://www.esjson.com/delSpace.html), and excluded irrelevant documents. Limited by our capacity, we are not including documents issued from 2021 to 2022.

We used an R package named [jiebaR](https://github.com/qinwf/jiebaR) for Chinese text mining. The default setting of the tokenizer, worker(), includes word segmentation engine "MixSegment", as "type = 'mix'", which is a mix of "MPSegment" (Maximum Probability segmentation procedure) and "HMMSegment" (A hidden Markov model segmentation procedure); a default Chinese word segmentation lexicon, as "dict = "inst/dict/jieba.dict.utf8", which can be supplemented by a user customized terms segmentation lexicon, using "user =" argument; a default setting of segmenting a string, so if want to apply it to a data frame, then need to turn the "bylines = TRUE".

We customized a Chinese word segmentation lexicons and a Chinese stop word list. For the lexicon, we downloaded the electricity industry topic cell lexicons from an official website of an Chinese input software [Sougou](https://pinyin.sogou.com/dict/search/search_list/%B5%E7%C1%A6/normal/), and manually added tens of electricity industry reform terms, by converting the .scel format lexicon to .txt format through an open source converter [ShenLan](https://github.com/studyzy/imewlconverter). For the stop words, we downloaded the list from [GitHub](https://github.com/YueYongDev/stopwords), and manually added about a hundred stop words due to the output in the project.


## Results and Reports

To see our full report, please click [here](add links)

## Authors

Xiyu Zhang, @ShaeChang

Jinli Wu @jw1935

## Reference
