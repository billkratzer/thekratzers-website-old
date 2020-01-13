---
layout: post
title:  "Grading Football Score Predictions!"
date:   2019-12-04 20:00:00 -0500
author:  Bill Kratzer
categories: football
---
For the last few years, I have been making predictions to scores of Penn State football games.  

More recently, I have become interested in the idea of grading my predictions as well as benchmarking my predictions against others. 
After all, don't we all want to measure how good we are?

Before coming up with my own system, I decided to see if there were any true-and-tried measurement systems.  
It turns out, I couldn't find any.   I might just be a bad Internet Googler, so if you find some that you like, please let me know.

I decided that it would be fun to come up with my own model.

These were the driving guideposts to my grading model:

+ Reward correctly guessing the winner of the game.
+ Reward closer score predictions.
+ Generate a final grade based on traditional school grades in the United States: A, B, C, D, F.   

# The Model

The core component of the grading model revolves around how accurately I predicted the score of the game.  
This involves adding score difference for both PSU and the Opponent (my prediction vs. actual).

Specifically:

`score = | My_PSU_Score - Actual_PSU_Score | + | My_Opponent_Score - Actual_Opponent_Score |`

The next question is: "Well, then what makes an A, B, C, D, and F"?

I thought about *getting an A* first.  What constitutes a good prediction?   I've been thinking about this alot.  
I generally thought that a really good score prediction was being off by a total of 7 to 14 points.  

I initially decided that "10" would be my breaking point.   So, 10 points or less scored me an A, 11-20 points score me a B, etc.

However, I really wanted to have the *plus* and *minus* stratification as well:  A+, A, A-, B+, B, B-.

Since there would be three groupings within each grade letter, I reduced the scoring range from each letter grade from 10 to 9, since 9 is easily divisible by 3.

| Grade | Score |
|-------|--------|---------|
| ambrosia | gala | red delicious |
| pink lady | jazz | macintosh |
| honeycrisp | granny smith | fuji | 