---
layout: article
title: "The most famous cuisine in the world (on Wikipedia)"
lang: en
ref: cuisines-correlation-heatmap
date: 2020-10-06
---

Some time has passed since the [last post](https://albertosantagostino.github.io/blog/2020/06/28/servicehandler_en). In the meanwhile some interesting projects were born[^1]

Between the [draft of a recipe book](https://albertosantagostino.github.io/ricettario/) created to organize some notes and the [computation of Sardinia geographical centroid](https://github.com/albertosantagostino/sardinia-geographical-centroid) (improvised after the holidays), while reading on Wikipedia some pages on foreign cuisines, I wondered:

{:refdef: .centerbig}
<u>What is the most "famous" cuisine in the world (on Wikipedia)?</u> [^2] [^3]
{: refdef}

Put it like this, it's a vague question. In detail:

* **Cuisine**: I mean national cuisines, ignoring regional ones
* **Famous**: define the popularity of a Wikipedia page is not easy[^4]. I used the page length (in characters) in this analysis[^5]
* **Wikipedia**: there are **303** active [Wikipedias](https://en.wikipedia.org/wiki/List_of_Wikipedias) in multiple languages. The same cuisine, well documented in a language, may be only a [stub](https://en.wikipedia.org/wiki/Wikipedia:Stub) (like a draft) in another one

In brief: I've tried to correlate cuisine page lengths (written in multiple languages) and to create an intuitive, easy-to-read visualization

Before discussing the technical side let's see the results! :)  
*(Every graph is also available as interactive version, through the dedicated link. Best viewing on PC)*

## Heatmap (correlation matrix) of Wikipedia cuisines

{: style="text-align: center;"}
<img src="{{site.url | append: '/media/20200922/correlation_heatmap.jpg'}}" title="Result: correlation matrix (heatmap)" class="responsive" onclick="window.open(this.src)">
<a href="{{site.url | append: '/media/20200922/correlation_heatmap.html'}}" target="_blank" rel="noopener noreferrer">↬ Link to the interactive version ↫</a>

There are a lot of things to say on this graph! Before explaining how it was made, let's see how to read it and what it means!

* Every **column** represents the cuisine of a specific country[^6]
* Every **row** indicates a language (in which a Wikipedia exists)[^6]
* Every **cell** corresponds to the Wikipedia cuisine page indicated by the column, written in the language indicated by the row ("Italian cuisine in English" indicates the Italian cuisine voice in the English Wikipedia)
* The **color** of every cell represents the length of the page (the color bar on the right is the key)
* The **white dots** in some cells highlight what in a pure correlation matrix (1:1) would be the diagonal: cells representing cuisines of the country **X** written in the main language of **X**[^7]

Let's consider a small part of the matrix obtained zooming it (using the [interactive version]({{site.url | append: '/media/20200922/correlation_heatmap.html'}})):

{: style="text-align: center; padding: 0 10%;"}
<img src="{{site.url | append: '/media/20200922/correlaton_heatmap_zoom.png'}}" title="A part of the correlation matrix" class="responsive" onclick="window.open(this.src)">

A couple of interesting things can be observed only from the color: the page on the [Italian cuisine in Korean](https://ko.wikipedia.org/wiki/%EC%9D%B4%ED%83%88%EB%A6%AC%EC%95%84_%EC%9A%94%EB%A6%AC) is quite long, as the page on the [Israeli cuisine in Indonesian](https://id.wikipedia.org/wiki/Hidangan_Israel)!

#### Unexpected famous cuisines

Exploring the heatmap, strange cuisine-language combinations can be found. For example:

* The page on the [Greek cuisine in Greek](https://el.wikipedia.org/wiki/%CE%95%CE%BB%CE%BB%CE%B7%CE%BD%CE%B9%CE%BA%CE%AE_%CE%BA%CE%BF%CF%85%CE%B6%CE%AF%CE%BD%CE%B1) (a "diagonal" entry) has a length of 25000 characters (more or less 7 A4 sheets printed using font size 12), but the page on the [German cuisine in Greek](https://el.wikipedia.org/wiki/%CE%93%CE%B5%CF%81%CE%BC%CE%B1%CE%BD%CE%B9%CE%BA%CE%AE_%CE%BA%CE%BF%CF%85%CE%B6%CE%AF%CE%BD%CE%B1) is 93000 characters long! Maybe Greeks love German cuisine so much that they are not interested in their own?[^8] `¯\_(ツ)_/¯`
* The page on the [Dutch cuisine in Polish](https://pl.wikipedia.org/wiki/Kuchnia_holenderska) is really long (130000 characters)!
* The page on the [American (USA) cuisine in French](https://fr.wikipedia.org/wiki/Cuisine_des_%C3%89tats-Unis) (218000 characters) is three times longer than the page on the [French cuisine in French](https://fr.wikipedia.org/wiki/Cuisine_fran%C3%A7aise)! (70000 characters)

### Remarks and disclaimers

* It goes without saying that the length of a Wikipedia page does not represent the sentiment of an entire country towards something. This analysis is clearly limited to Wikipedia. Also, there are some other factors to take into account:
  * Some Wikipedias are [more active than others](https://meta.wikimedia.org/wiki/List_of_Wikipedias#All_Wikipedias_ordered_by_number_of_articles) and have (on average) longer articles
  * Some voices are only simple lists, cases that best exemplify how the length is not an effective and absolute criterion
  * Refining this analysis, the number of characters might be normalized over the average length of a voice in a specific Wikipedia. However, to know at a glance "how much a cuisine page is long", I consider this normalization step not needed. I leave it to the curious reader to implement
* In total there are **167** national cuisines[^9] and **119** languages[^10]. The heatmap above is a filtered/reduced version (53×36)[^11]. The entire correlation matrix is nice to look at but not quite readable. For those who are curious, the complete matrix (167×119) is the following:

{: style="text-align: center; padding: 0 10%;"}
<a href="{{site.url | append: '/media/20200922/correlation_heatmap_full.html'}}" target="_blank" rel="noopener noreferrer">↬ Link to interactive version (with labeled axes) ↫</a>[^12]
<img src="{{site.url | append: '/media/20200922/correlation_heatmap_full.jpg'}}" title="The enormous entire correlation matrix" class="responsive" onclick="window.open(this.src)">

## Statistics and podium 🏆

The following statistics are computed using the entire version of the dataset, without excluding voices or national languages (regional and local dialects were ignored)[^13]

### Most "famous" cuisines of the world (cumulative, on all languages)

{: style="text-align: center;"}
<a href="{{site.url | append: '/media/20200922/cumulative_cuisines_length.html'}}" target="_blank" rel="noopener noreferrer">↬ Link to the interactive version ↫</a>
<img src="{{site.url | append: '/media/20200922/cumulative_cuisines_length.jpg'}}" title="Overall length of every national cuisine, obtained as a sum of the lengths in all languages" class="responsive" onclick="window.open(this.src)">

Adding up the page lengths of every cuisine for all considered languages, the following rankings are obtained:

{: style="margin: auto;"}

|      | Cuisine                                                                | Length              |
| ---- | :--------------------------------------------------------------------- | ------------------- |
| 1 🥇 | 🇮🇹 **[Italian](https://en.wikipedia.org/wiki/Italian_cuisine)**        | 1263679             |
| 2 🥈 | 🇩🇪 **[German](https://en.wikipedia.org/wiki/German_cuisine)**          | 1016720             |
| 3 🥉 | 🇯🇵 **[Japanese](https://en.wikipedia.org/wiki/Japanese_cuisine)**      | 981386              |
| 4    | 🇰🇷 **[Korean](https://en.wikipedia.org/wiki/Korean_cuisine)**          | 912384              |
| 4    | 🇺🇸 **[American](https://en.wikipedia.org/wiki/American_cuisine)**      | 893520              |
| 6    | 🇫🇷 **[French](https://en.wikipedia.org/wiki/French_cuisine)**          | 874603              |
| 7    | 🇮🇩 **[Indonesian](https://en.wikipedia.org/wiki/Indonesian_cuisine)**  | 832875              |
| 8    | 🇷🇺 **[Russian](https://en.wikipedia.org/wiki/Russian_cuisine)**        | 793379              |
| 9    | 🇮🇳 **[Indian](https://en.wikipedia.org/wiki/Indian_cuisine)**          | 778534              |
| 10   | 🇳🇱 **[Dutch](https://en.wikipedia.org/wiki/Dutch_cuisine)**            | 681041              |

In the first position, the **Italian cuisine**, with an overall length of **1.26 million characters**! :tada:

### The longest pages (independently from the language)

The top ten of longest cuisines (among all considered Wikipedias) is the following:

{: .hightable style="margin: auto;" }

|      | Cuisine and language                                                                    | Native title page         | Length  |
| ---- | :-------------------------------------------------------------------------------------- | :------------------------ | ------- |
| 1 🥇 | 🇷🇺 **[Russian (in Polish)](https://pl.wikipedia.org/wiki/Kuchnia_rosyjska)**            |  Kuchnia rosyjska         | 363864  |
| 2 🥈 | 🇩🇪 **[German (in Russian)](https://ru.wikipedia.org/wiki/Немецкая_кухня)**              |  Немецкая кухня           | 279328  |
| 3 🥉 | 🇦🇷 **[Argentine (in Italian)](https://it.wikipedia.org/wiki/Cucina_argentina)**         |  Cucina argentina         | 227606  |
| 4    | 🇺🇸 **[American (in French)](https://fr.wikipedia.org/wiki/Cuisine_des_États-Unis)**     |  Cuisine des États-Unis   | 218192  |
| 5    | 🇺🇸 **[American (in Japanese)](https://ja.wikipedia.org/wiki/アメリカ料理)**               |  アメリカ料理               | 190920  |
| 6    | 🇺🇸 **[American (in English)](https://en.wikipedia.org/wiki/American_cuisine)**          |  American cuisine         | 181443  |
| 7    | 🇮🇩 **[Indonesian (in Russian)](https://ru.wikipedia.org/wiki/Индонезийская_кухня)**     |  Индонезийская кухня      | 175120  |
| 8    | 🇲🇾 **[Malaysian (in English)](https://en.wikipedia.org/wiki/Malaysian_cuisine)**        |  Malaysian cuisine        | 162794  |
| 9    | 🇮🇹 **[Italian (in Kannada)](https://kn.wikipedia.org/wiki/ಇಟ್ಯಾಲಿಯನ್‌_ಪಾಕಪದ್ಧತಿ)**           |  ಇಟ್ಯಾಲಿಯನ್‌ ಪಾಕಪದ್ಧತಿ          | 152911  |
| 10   | 🇦🇷 **[Argentine (in Spanish)](https://es.wikipedia.org/wiki/Gastronomía_de_Argentina)** |  Gastronomía de Argentina | 140174  |

At the top, the longest cuisine is the page on the **[Russian cuisine (written in Polish)](https://pl.wikipedia.org/wiki/Kuchnia_rosyjska)**, with **363864 characters**! :tada:

**A curiosity on the 9th place (just because I'm Italian)**  
I wasn't aware of the existence of [Kannada](https://en.wikipedia.org/wiki/Kannada) (a language spoken in southern India), but it seems they are really interested in the [Italian cuisine (ಇಟ್ಯಾಲಿಯನ್‌ ಪಾಕಪದ್ಧತಿ)](https://kn.wikipedia.org/wiki/ಇಟ್ಯಾಲಿಯನ್‌_ಪಾಕಪದ್ಧತಿ). As an Italian I think is wonderful to read something written in a completely different alphabet but at the same time find images of caffettiere (coffee makers), [focacce](https://en.wikipedia.org/wiki/Focaccia) and [tiramisù](https://en.wikipedia.org/wiki/Tiramisu):

{: style="text-align: center; padding: 0 10%;"}
<img src="{{site.url | append: '/media/20200922/kannada_italian_cuisine.png'}}" title="Page on the Italian cuisine written in Kannada" class="responsive" onclick="window.open(this.src)">

Someone pointed out that the part on [Turin bicerin](https://en.wikipedia.org/wiki/Bicerin) seems untranslatable (_"I think that there is a word for 'latte' ('milk') in Kannada"_). But partial translation are common on Wikipedia, nothing too strange here! :)

### The languages with most cuisine pages

{: style="text-align: center;"}
<a href="{{site.url | append: '/media/20200922/cumulative_languages_length.html'}}" target="_blank" rel="noopener noreferrer">↬ Link to the interactive version ↫</a>
<img src="{{site.url | append: '/media/20200922/cumulative_languages_length.jpg'}}" title="Overall length for every language, obtained adding up all national cuisines pages written in the same language" class="responsive" onclick="window.open(this.src)">

No wonder, the Wikipedia version with more cuisine pages is **[the English Wikipedia](https://en.wikipedia.org/wiki/)** 🇬🇧

## How was this analysis made?

To avoid a long digression on the implementation, I will only briefly mention the used packages and give an overview on data collection and processing. For those interested in digging more into this part, the [repository of this project is on GitHub](https://github.com/albertosantagostino/wiki-cuisines-correlation-heatmap)

**Used packages**  
The entire project is developed in Python. The main packages used (handled using [Poetry](https://python-poetry.org/)) are the following:

{: style="margin: auto;"}

| Package          | PyPi page                                      | Description                                     |
| ---------------- | ---------------------------------------------- | :---------------------------------------------- |
| `beautifulsoup4` | [🔗](https://pypi.org/project/beautifulsoup4/) | Handle/parse low-level HTML[^14]                |
| `pandas`         | [🔗](https://pypi.org/project/pandas/)         | Must-have to store and analyze data             |
| `emoji`          | [🔗](https://pypi.org/project/emoji/)          | Needed for emojis, used for national flags      |
| `plotly`         | [🔗](https://pypi.org/project/plotly/)         | A must-have to create visualizations/plots[^15] |

**Download and data processing**  
There are 4 steps of data preparation. At each step, the same data structure is enriched with more and more information.  
The functions (that represent the steps) are the following:

* `step1_prepare_cuisines_data`  
  The list of all "cuisine candidates" is created starting from [this Wikipedia template](https://en.wikipedia.org/wiki/Template:Cuisines). Redirects are ignored and only national cuisines are taken into account. Wikipedia page IDs are also stored
* `step2_populate_other_languages`  
  For each cuisine in the list, translations in other languages (except English) are identified. Titles and URLs are saved
* `step3_fill_lengths`  
  Needed page lengths are obtained through [API calls](https://www.mediawiki.org/wiki/API:Main_page)
* `step4_preprocess_data_frame`  
  The data structure is converted from dictionary to `pandas.DataFrame`. During this step, a filter is applied to reduce data size. The obtained data frames are saved: `table_dataframe.dat` (filtered version) and `table_dataframe_full.dat` (complete version, used to compute overall statistics)

**Visualization and graphs**  
A final step (`step5_create_plots`, in `visualization.py`) loads the previously created data structures to create graphs, tables and stats that are saved in images, HTML and Markdown

## Conclusions

This whole analysis was made *just for fun*, out of curiosity and to do something new. That being said, I'm happy of the results! It's really interesting to look for strange correlations in the heatmap, discovering new cuisines and languages that I didn't know about!

If you find something curious or want to create similar statistics to a different Wikipedia category, let me know or try directly by yourselves (the code is as always open-source ([repository su GitHub](https://github.com/albertosantagostino/wiki-cuisines-correlation-heatmap)) and it's released under MIT license)

### Things (still) to do

Since when I started writing this article some improvements and new graphs to make have come to my mind. I'm happy with the current status, but in the future I would like to implement (by importance/relevance):
* Automation of data collection/analysis step[^16]. Wikipedia pages change really often, this analysis may be already obsolete in a couple of months[^17]
* Statistics to highlight longest cuisine pages for each language, <u>excluding diagonal entries</u>
* Normalization of lengths, to make pages "stand out" with respect to the mean length of the page for that Wikipedia edition
* Take into account local languages, trying to use a similar approach for Italian dialects[^18]

Thanks for reading, see you next time! :)

<br>

[^1]: [ITAQA](https://albertosantagostino.github.io/blog/2020/05/29/ITAQA_introduction_it) is going on and I have new things to talk about! I hope to write about it soon
[^2]: Narrow it down to Wikipedia simplifies a lot everything!
[^3]: I already had a [guess](https://en.wikipedia.org/wiki/Italian_cuisine), but I wasn't able to prove it (*yet*)
[^4]: A collection of interesting voices is "[featured articles](https://en.wikipedia.org/wiki/Wikipedia:Featured_articles)", but it only classify in "interesting" vs "not interesting"
[^5]: As explained later, I know that the length of a page is not a certain measure of its fame. Also it was pointed out that different languages have different [information density](https://linguistics.stackexchange.com/questions/30408/density-of-information-semantic-of-chinese-and-korean-language-versus-european-l)
[^6]: Yes, I know, a lot of countries and languages are missing, I will explain later
[^7]: Note that on some rows there are multiple dots, indicating all countries where that language is the main one. On this regard: some countries have more than one main language (Switzerland, Luxembourg, Belgium), in which case multiple dots on the same column should be marked. This higher level of detail is not implemented (yet)
[^8]: A dear friend of mine (who loves Greek cuisine) commented: "there is *really little* to say on their cuisine, it can be summarized in: [feta](https://en.wikipedia.org/wiki/Feta), [moussaka](https://en.wikipedia.org/wiki/Moussaka), [gyros](https://en.wikipedia.org/wiki/Gyro), i [cosi con la vite](https://en.wikipedia.org/wiki/Dolma), [olive](https://en.wikipedia.org/wiki/Oliva). Stop."
[^9]: Namely, all the national cuisines that are listed in the English Wikipedia
[^10]: Namely, all the languages that have at least a voice on one of the national cuisines taken into account
[^11]: I ignored all voices shorter than 4000 characters, all cuisines present in less than 13 languages, all languages with less than 14 cuisine pages and all Wikipedias in local dialects
[^12]: The interactive version has on the language axis some language prefixes not converted in the language name. It's still interesting to navigate!
[^13]: All statistics and graphs are based on the situation on October 4th, 2020
[^14]: Initially I planned to do the parsing/data download using the `wikipedia` ([🔗](https://pypi.org/project/wikipedia/)) package, but currently is incomplete and not optimized. For this reason I switched to the low-level approach with `beautifulsoup`
[^15]: I think that `matplotlib` is a little bit outdated and a blob, there are some alternatives (like `plotly`) that are lightweight and natively interactive/modern. I have still to try `seaborn` ([website](https://seaborn.pydata.org/)), I've read some nice thing
[^16]: Maybe using directly [GitHub Actions](https://github.com/features/actions) (I don't know how much it would be feasible, but I want to try it)
[^17]: Since when I started to write this post there was already a change to make: the German cuisine overtook the Japanese one, moving on to the second place, after a big expansion of the page "[German cuisine in Russian](https://ru.wikipedia.org/wiki/%D0%9D%D0%B5%D0%BC%D0%B5%D1%86%D0%BA%D0%B0%D1%8F_%D0%BA%D1%83%D1%85%D0%BD%D1%8F) at the end of September
[^18]: But I'm afraid that local-dialect Wikipedias are too small, I don't think they contain a lot of information on the cuisines of other regions