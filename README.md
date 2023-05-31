# sentiment_ratio
The Sentiment Ratio indicator gauges current Market Sentiment between -100% and 100%, where lower than -40% is considered Bearish and higher than 40% is Bullish. The channel between the two is considered Neutral.

The indicator has been a very useful filter tool for signals within a trading system.

Example call function:

//Return sentiment if trigger level is activated

int sentiment_indicator(double trigger_level){

	double sentiment_ratio=iCustom(NULL,0,"Sentiment Ratio",0,0,0);

	if(sentiment_ratio>=trigger_level) return(OP_BUY);
  
	else if(sentiment_ratio<=-trigger_level) return(OP_SELL);
  
	return(-1);//Default: No indication

}

Basis of calculation:

The calculation in the indicator applies weighted averages from RSI, Stochastic Oscillator, and William’s Percent Range.
