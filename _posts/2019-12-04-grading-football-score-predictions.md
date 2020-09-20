---
layout: post
title:  "Grading Football Score Predictions!"
date:   2019-12-04 20:00:00 -0500
author:  Bill Kratzer
categories: football
css_file: post.css
---

For the last few years, I have been making predictions to scores of Penn State football games.  

More recently, I have become interested in the idea of grading my predictions as well as benchmarking my predictions against others. 
After all, don't we all want to measure how good we are?

Before coming up with my own system, I decided to see if there were any true-and-tried measurement systems. It turns out, I couldn't find any.   I might just be a bad Internet Googler, so if you find some that you like, please let me know.

I decided that it would be fun to come up with my own model.

These were the driving guideposts to my grading model:

+ Reward correctly guessing the winner of the game.
+ Reward closer score predictions.
+ Generate a final grade based on traditional school grades in the United States: A, B, C, D, F.   

# The Model

## Rationale 

The core component of the grading model revolves around how accurately I predicted the score of the game.  
This involves adding score difference for both PSU and the Opponent (my prediction vs. actual).

Specifically:

`score = | My_PSU_Score - Actual_PSU_Score | + | My_Opponent_Score - Actual_Opponent_Score |`

The next question is: "Well, then what makes an A, B, C, D, and F"?  What constitutes a great, "grade A" prediction? By my measure, a great score prediction is being off by a total of 7 to 14 points.  Using this measuring stick, I initially decided that "10" would be my breaking point; so 10 points or fewer grede me an A, 11-20 points grade me a B, etc.

However, I really want to have the *plus* and *minus* stratification as well:  A+, A, A-, B+, B, B-. etc.

Since there would be three groupings within each grade letter (plus, no sign, minus), I reduced the scoring range from each letter grade from 10 to 9, which is easily divisible by 3.

## Scoring Table

Here's the final scoring table:

| Grade | Score 
|-------|--------|
| A+    | 0-3    |
| A     | 4-6    |
| A-    | 7-9    |
| B+    | 10-12  |
| B     | 13-15  |
| B-    | 16-18  |
| C+    | 19-21  |
| C     | 22-24  |
| C-    | 25-27  |
| D     | 28-36  |
| F     | > 37   |

## Adjustments

While this is a good starting point, there are some refinements to this scoring system.

I value predicting the winner.  In my book, predicting the winner is like scoring a touchdown.  So, if I predict the winner, I subtract seven from my score differential above.

In college football, things get really wierd and unpredictable in high scoring games.  I decided to add a cap to all scores, both predicted and actual.   That cap is 50 points.   Anything above 50 points is meaningless on the field and in this simulation.

# 2019 Season Results

This season, I averaged an A-.  

Not too shabby.

Below are the game-by-game results:

| Game  | Final Score | Prediction | Grade | 
|-------|-------------|------------|-------|
| Idaho | 79-7 (W) | 38-3 (W) | A- | 
| Buffalo | 45-13 (W) | 38-7 (W) | A |
| Pitt | 17-10 (W) | 45-10 (W) | C+ |
| Maryland | 59-0 (W) | 35-24 (W) | D |
| Purdue | 35-7 (W) | 31-10 (W) | A+ |
| Iowa | 17-12 (W) | 14-13 (W) | A+ |
| Michigan | 28-21 (W) | 21-17 (W) | A |
| Michigan State | 28-7 (W) | 20-17 (W) | B+ |
| Minnesota | 26-31 (L) |  24-17 (W) | B- |
| Indiana | 34-27 (W) | 35-24 (W) | A+ |
| Ohio State | 17-28 (L) | 17-31 (L) | A+ |
| Rutgers | 27-6 (W) | 44-0 (W) | B- |
