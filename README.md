# HT-TradingView
***Hobby Trader*** Examples using HTML Files with Javascript integration of TradingView's LightWeight Charts for non Technical Hobbyists learning to code through trading examples.  For simplicity of learning, all the code has been placed in single HTML Files and includes sections for:  
- Library initialisation (CDN)
- CSS Data in the header
- HTML Code  
- Javascript  

# Installation
```
git clone https://github.com/HobbyTrader/HT-TradingView.git
```  
This will install a copy of the HTML files used has scaffolding for the lightweight charts javascript library.  
The HTML Code will use a ***CDN Version*** of the library for update simplicity.  

# CDN Version  
TradingView offers a dynamically downloadable CDN (Content Delivery Network) version of the lightweightCharts Javascript library. To use this version simply replace the following lines of code:
```
<!-- Adding the Online CDN version of Lightweight charts -->
<script
    type="text/javascript"
    src="https://unpkg.com/lightweight-charts/dist/lightweight-charts.standalone.production.js"
></script>
```

# Example code
| # | File | Description |
|---|---|---|
| 1 | chart01.html | The most basic example full width using hard coded price data and all the default values such as white background, green and red candles, time frame at the bottom and price scale on the right |
| 2 | chart02.html | Simple line chart that represents an Simple Moving Average. SMA Data is hard coded for simplicity, but should be calculated in real charts |
| 3 | chart03.html | Chart with multiple data (candlestick and SMA). Also custom color for line chart |
| 4 | chart04.html | Loading data from web source and display simple candlestick chart. |
| 5 | chart05.html | Loading data from web source and display simple candlestick chart sized to the chart container width and size. Also added flexibility for csv file headers (checking strings and column names). Used a unix timestamp instead of a string date |


## Basic config structure
1) HTML ***Container*** for chart to be displayed in the DOM
2) Instantiate a ***chart*** object
3) Add a ***series*** to the chart
4) Load some ***Data*** with appropriate structure for the series added
5) use the seriesVar.setData( loadedData ) method to add data to the Chart
6) Add a window resize event handler to refresh the chart when necessary


 ## Series Data format
{ time, open, high, low, close, customValue, color }  
    

| Serie Type | SeriesDataType | List of { key:value ) pairs |
|---|---|---|
| CandlestickSeries | CandlestickData | { time, open, high, low, close, customValue?, color?, borderColor?, wickColor? } |
| BarSeries | BarData | { time, open, high, low, close, color?, customValue? } |
| LineSeries | LineData | { time, value, color?, customValue? } |
| AreaSeries | AreaData | { time, value, lineColor?, topColor?, bottomColor?, customValue? } |
| HistogramSeries | HistogramData | { time, value, color?, customValue? } |
| . | . | . |


> *keys with a "?" are optional data fields.*


## Hard Coded Data For testing
```
candles = [
  { time: "2018-10-19", open: 180.34, high: 180.99, low: 178.57, close:  179.85 },
  { time: "2018-10-22", open: 180.82, high: 181.41, low: 177.56, close:  178.75 },
  { time: "2018-10-23", open: 175.77, high: 179.49, low: 175.44, close:  178.53 },
  { time: "2018-10-24", open: 178.58, high: 182.37, low: 176.31, close:  176.97 },
  { time: "2018-10-25", open: 177.52, high: 180.51, low: 176.83, close:  179.07 },
]
```
## References  
[Lightweigth Charts](https://www.tradingview.com/lightweight-charts/) documentation by Trading View  
[Trading View on NPM](https://www.npmjs.com/org/tradingview) for their CDN Management using UNPKG  
[UNPKG](https://unpkg.com/#about) open source CDN side project for NPM users and organisations  
[Lightweight Charts CDN URL](https://unpkg.com/lightweight-charts@5.0.9/dist/lightweight-charts.standalone.production.js)  

