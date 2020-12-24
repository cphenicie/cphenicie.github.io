---
title: "Generating priors from historical data"
tags:
  - forecasting
  - hardware
---

I have recently started forecasting on CSET's [Foretell](https://www.cset-foretell.com/) platform. I've been interested in forecasting for a while, but I've always gotten stuck on where to start. The advice that most people seem to give (including Foretell's own [tutorial](https://www.cset-foretell.com/courses/2/slides/1)) is to start with a base rate (aka an "outside view") and then update it using the specific of the specific situation you are forecasting (aka an "inside view"). The problem I've had with this is that I generally have neither and inside view nor an outside view for more forecasts. I generally just come in with a uniform prior, thinking that all the options of the forecast are equally likely. In this post I'll explain my first step to go beyond this "uniform prior" forecast. 

One nice thing about Foretell's questions is sometimes they provide data from which one can construct a base rate. One example of this is the question [What will be the value, in dollars, of all Chinese imports of semiconductor manufacturing equipment in 2021?](https://www.cset-foretell.com/questions/95-what-will-be-the-value-in-dollars-of-all-chinese-imports-of-semiconductor-manufacturing-equipment-in-2021) The "answer" to this question takes the form of your confidence that this dollar value will fall within the ranges (in units of billion USD) {[0, 20], (20, 30], (30, 40], (40, 50], (50, $$\infty$$)}

If you click "Show background information" below the question, they provide nine years' worth of data measuring exactly this quantity. 
![original data](/assets/images/2020-12-24-forecast/original_data.png)

Now, with this data in hand, I actually feel like I have a reason to start assigning numbers. If I want to start using some "outside view" thinking, 