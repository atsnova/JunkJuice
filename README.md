## Welcome to my Junk Juice Model


You can use the [editor on GitHub](https://github.com/atsnova/StockPick/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/atsnova/StockPick/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.



# Model to look at selecting stocks using ML and AI and eventually Deep Learning 



Time series forecaster:
    https://facebook.github.io/prophet/
    forecast time series data using additive models

Tuts:
https://enlight.nyc/projects/stock-market-prediction/ - basic stock forecast
https://www.youtube.com/user/sentdex
https://pythonprogramming.net
https://pythonprogramming.net/machine-learning-python-sklearn-intro/
IMPORTANT!! :https://pythonprogramming.net/getting-stock-prices-python-programming-for-finance/
https://github.com/PythonProgramming/PythonProgramming.net-Website
https://ntguardian.wordpress.com/2018/07/17/stock-data-analysis-python-v2/
https://www.datacamp.com/community/tutorials/finance-python-trading
https://www.learndatasci.com/tutorials/python-finance-part-yahoo-finance-api-pandas-matplotlib/
https://managingfundswithpythonandsql.wordpress.com/2017/10/03/setting-up-the-bloomberg-api-to-work-with-python-anaconda/
https://www.datacamp.com/courses/intro-to-python-for-finance
https://www.datacamp.com/courses/intro-to-financial-concepts-using-python
https://www.datacamp.com/courses/introduction-to-time-series-analysis-in-python
https://www.datacamp.com/courses/intro-to-portfolio-risk-management-in-python
https://www.datacamp.com/courses/importing-managing-financial-data-in-python
https://www.datacamp.com/courses/manipulating-dataframes-with-pandas
https://www.datacamp.com/courses/manipulating-time-series-data-in-python
https://www.datacamp.com/courses/machine-learning-for-finance-in-python
https://www.datacamp.com/courses/machine-learning-for-time-series-data-in-python
https://www.datacamp.com/courses/financial-forecasting-in-python
https://www.datacamp.com/courses/interactive-data-visualization-with-bokeh

Very important :::
https://github.com/robertmartin8/MachineLearningStocks - the main SH1T !!!!!

Arctiles:
https://www.researchgate.net/publication/301847788_Equity_forecast_Predicting_long_term_stock_price_movement_using_machine_learning

API:
bloomberg: https://github.com/msitt/blpapi-python	
context info: http://contextors.com/api/

Sources:
https://www.bloomberg.com/quote/SBK:SJ
https://finance.yahoo.com/quote/AAPL/financials?p=AAPL

Code:
https://pypi.org/project/Yahoo-ticker-downloader/ - Get all the ticker info from Yahoo
https://github.com/WillKoehrsen/Data-Analysis/tree/master/stocker - pre built library of stock computations and graphs

# Process:

## Getting financials data: This consist of Ratios as well as price

	1. extract all the tickers from yahoo finance
	2. extract data for range of tickers.
		2.1 get the price at each closing day over the range
		2.2 get the financial ratios as and when updated over the range
	3. split data into training and testing data
		3.1 use various time period to test with 90 days forward
			ie multiple observation and outcome windows
		3.2 use various stocks to test with
		3.3 think about industry in this process
		3.4 use cross folding in the process
	4. Define an outcome period at 90 days from "today"
		4.1 Classify stocks into various growth rates 5%, 7.5%, 10%, 12.5%, 15%, etc in 2.5% upto 50?
		4.2	Use a histogram to understand long term changes in growth rate 
	5. Train the model thinking about Geographics, industry, growth rate 
	6. Test the model
	7. THINGS to think about :
		7.1 create a portfolio of stocks
		7.2 test the portfolio against stocks to be added and removed every iteration (90 days?)
		7.2 factor in cost of switching at some stage

Decide on what model to use : Read about SVM
Decide on what model to use : Read about timeseries computation : histogram of returns and volatility + other statistical measures for stocks

https://www.tradingtechnologies.com/help/x-study/technical-indicator-definitions/list-of-technical-indicators/
https://za.markets.com/education/technical-analysis/mathematical-indicators/
http://financeformulas.net/Stock-and-Bond-Formulas.html
https://www.dundas.com/support/learning/documentation/analyze-data/formulas/list-of-formulas
https://towardsdatascience.com/technical-analysis-library-to-financial-datasets-with-pandas-python-4b2b390d3543
https://technical-analysis-library-in-python.readthedocs.io/en/latest/ta.html#momentum-indicators
https://www.quantopian.com/posts/technical-analysis-indicators-without-talib-code


Other models to consider:  specific Recurrent Neural Networks (RNN) /  specific Convolutional Neural Networks (CNN) http://stocksneural.net/
XGBOOst is very powerful, SVM, CART, ANNs, HS-ANN (Artifical Neural network) and Boosting HS-ANN (http://iopscience.iop.org/article/10.1088/1757-899X/322/5/052053/pdf)

## Getting News:

###	News articles that cover:
		industry
		Geographics
		company - Ticker
		directors
		board
		suppliers
		competitors

		Need to think about association between these factors ie some sort of graph element or latice structue impact on the price

		Use Scrapy : https://blog.michaelyin.info/scrapy-tutorial-1-scrapy-vs-beautiful-soup/
		Extract news

		then process data and extract important information:
			Ticker
			industry
			Geographics
			directors
			board
			suppliers
			competitors
			brand
			sentiment (-1,0,1 as scores for now = negative, neutral or positive) 
			tense of article (past - what happened, future - speculation/just discovered)




### Exchange rate info:
	Given values are in USD think about how we represent growth when moving back to local currency
