## HOW TO DOWNLOAD AND READ A NEWSPAPER IN THE TERMINAL


### Getting Started
The assumption is you probably have **Python 3** installed in your computer. If not, head on [here](https://www.tecmint.com/install-python-in-ubuntu/) to get started. If you are running _ubuntu 18.04_, Python3 comes in the box.


1. Install pip3 command needed to instal the _newspaper3k_ package

* `$ sudo apt update`
* `$ sudo apt install python3-pip`

    Confirm installation

* `$ pip3 --version`


2. Install the distribution via pip3

* `pip3 install newspaper3k`

    (It will take a few seconds to complete the installation)

3. Activate Python3

* `$ python3`


Now, let's learn how to download an Article from a major online newspaer:


#### First step

```python
# First import the Article object from the newspaper library
#save the article url from Business Daily  in a variable
```

`>>> from newspaper import Article ` 

`>>> url= 'https://www.businessdailyafrica.com/markets/capital/Top-10-best-and-worst-performing-stocks-2018/4259442-4909296-2n2m98z/index.html'`

`>>> article = Article(url)`

#### Second Step

```python
# Download the newspaer article
```

`>>> article.download()`


#### Third Step

```python
# Parse through the content
```

`>>> article.parse()`

(Now, you can access individual information as you wish. Here, I will show you how to find the author(s), top_image, date of publish, entire text)

`>>> article.authors`       or  `print(article.authors)`

`>>> article.top_image`     or   `print(article.top_image)`

`>>> article.publish_date`  or   `print(article.publish_date)`

`>>> article.text`          or    `print(article.text)`

`>>> article.movies`        or    `print(article.authors)`


#### Forth Step
Extracting Natural Language Properties from your text.

**NOTE: You must have called download() and parsed() before running NLP**

`>>> article.nlp()`

You may encounter an error as you try to run NLP. In this case, you will need to:

* `import nltk`
* `nltk.download()`

##### What is NLP?
NLP is an abbreviation for Natural Language Properties. It is useful in developing applications that are able to understand human languages such as in speech recognition and translation etc.  

##### Benefits of NLP
The internet is full of gigabytes of data generated by blogs, websites and social websites. There are companies gathering all these data to better understand and serve their customers. 

##### Implementations of NLP

* **Search Engines** like Google understand that you are a tech guy, so it shows you results related to that.
* **Social Websites** like Twitter's algorithms understand your interests using NLP and shows you related ads.
* **Speech engines** like Google Assistant and Apple Siri.

#### NLP Libaries
There are many open source NLP libraries, but the most popular one of them is **NLTK (Natural Language Toolkit)**.

`>>> article.keywords`

`>>> article.summary`

#### Easter Eggs
```python
import newspaper

newspaper.hot() # lists all trending terms on Google

newspaper.popular_urls() # displays all popular urls on the internet

newspaper.languages() # shows all the available languages
```

#### Extras

````python
import newspaper

bbc = newspaper.build('https://www.bbc.com/news')

for article in bbc.articles():
    print(article)


for category in bbc.category_urls():
    print(category)
````

In conclusion of part one, that is how you can read a newspaper article in the terminal. In the following sections, I will show you some advanced features of the _newspaper_ library.



### Advanced




#### References

1. [Newspaper3k Reference](https://newspaper.readthedocs.io/en/latest/) 

2. [NLP Tutorial](https://dzone.com/articles/nlp-tutorial-using-python-nltk-simple-examples) 