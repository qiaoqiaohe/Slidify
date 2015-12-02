---
title       : Meeting Notes
subtitle    : Nov 26, 2015
author      : Fang
job         : 
framework   : io2012      # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax,quiz,bootstrap,interactive]            # {mathjax, quiz, bootstrap}
ext_widgets : {rCharts: [libraries/nvd3, libraries/leaflet, libraries/dygraphs]}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
--- 

## Data Base Preparation

### Write funcitons:

1. Get all the info of a specified site.
2. Merge FluxTwr and MODIS data.
3. Get value at given "Location" and "Time". 

   (Consider that if the given data doesn't exit in the current table? Interpolation?)
4. Other useful functions.

### Put all the functions in a package.


--- .class #id 

## Modeling

### For regression model

1. Use CCI 



### For landmarks

1. Dirichlet Distribution
2. Dirichlet Regression


### For smoothing

1. Integration under the curve 

--- .class #id 

--- .segue bg:grey

# Quizzes

--- &radio

## Radio

Eleanor scores 680 on the Mathematics part of the SAT. The distribution of SAT scores in a reference population is Normal, with mean 500 and standard deviation 100. Gerald takes the American College Testing (ACT) Mathematics test and scores 27. ACT scores are Normally distributed with mean 18 and standard deviation 6. Assuming that both tests measure the same kind of ability, who did better?

1. _Eleanor_
2. Gerald

*** .explanation

The best way to compare their performance is to calculate their standardized scores.

$$z_E = \frac{680 - 500}{100} = 1.8$$
$$z_G = \frac{27 - 18}{6} = 1.5$$

Since, Eleanor has a higher standardized score, we can conclude that Eleanor did better!

--- &radio2

## Radio (Two Column)

Which of these two scatterplots have a higher correlation?

1. A
2. B

*** =image

<img src=https://oli.cmu.edu/repository/webcontent/470835bf80020ca60018d5a6c359d34c/_u2_summarizing_data/_m2_examining_relationships/webcontent/linear1.gif>

*** .explanation

Both have the same correlation.

---  &checkbox

## Checkbox

Linda is 31 years old, single, outspoken, and very bright. She majored in philosophy. As a student, she was deeply concerned with issues of discrimination and social justice, and also participated in anti-nuclear demonstrations.

Which is more probable?

1. _Linda is a bank teller._
2. Linda is a bank teller and is active in the feminist movement.

*** .hint

Think about the probabilities of each event, and that of both of them together.

*** .explanation

If you chose (2), stop back and think. Suppose we denote the event of Linda being a teller by A and the event she is active in the feminist movement by B, then probabilities in question can be written as.

- P(A)
- $P(A \cap B)$

This is called the [conjugacy fallacy](http://en.wikipedia.org/wiki/Conjunction_fallacy) that occurs when it is assumed that specific conditions are more probable than a single general one.

---  &multitext

## Multi Text

The length of human pregnancies from conception to birth varies according to a distribution that is approximately Normal with mean 266 days and standard deviation 16 days.

1. What percent of pregnancies last fewer than 240 days?
2. What percent of pregnancies last between 240 and 270 days?
3. How long do the longest 25% pregnancies last?

*** .explanation

1. <span class='answer'>5.2081279</span>
2. <span class='answer'>54.6625046</span>
3. <span class='answer'>276.791836</span>

*** .hint

This is a hint

---  &submitcompare1

## Submit and Compare

What is the sample space for this experiment?

*** .explanation

The sample space for this experiment is

{HH, HT, TH, HH}

---  &submitcompare2 rows:5

## Submit and Compare (2 Column)

The solid curve represents the distribution of heights of all males in the US. The dotted curve represents the distribution of heights reported by males on OkCupid, an online dating website.

<img class=center
  src=http://cdn.okcimg.com/blog/lies/MaleHeightDistribution.png width=400px>


*** =question

What is happening here?

*** .explanation

It is easier to interpret things if we overlay a fitted normal distribution for the heights reported by males on OkCupid. Looking at the graph carefully, we can observe two things.

<img class=center
  src=http://cdn.okcimg.com/blog/lies/MaleHeightDistributionYoink.png width=400px>

1. Males on OkCupid probably tend to inflate their heights!
2. You can also see a more subtle vanity at work: starting at roughly 5' 8", the top of the dotted curve tilts even further rightward. This means that guys as they get closer to six feet round up a bit more than usual, stretching for that coveted psychological benchmark.

--- .segue bg:grey

# Interactivity

---

## Interactive Console

<div align="center">

<!-- MotionChart generated in R 3.2.1 by googleVis 0.5.10 package -->
<!-- Tue Dec  1 20:32:24 2015 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataMotionChartID25636cc9179 () {
var data = new google.visualization.DataTable();
var datajson =
[
 [
 "Apples",
2008,
"West",
98,
78,
20,
"2008-12-31" 
],
[
 "Apples",
2009,
"West",
111,
79,
32,
"2009-12-31" 
],
[
 "Apples",
2010,
"West",
89,
76,
13,
"2010-12-31" 
],
[
 "Oranges",
2008,
"East",
96,
81,
15,
"2008-12-31" 
],
[
 "Bananas",
2008,
"East",
85,
76,
9,
"2008-12-31" 
],
[
 "Oranges",
2009,
"East",
93,
80,
13,
"2009-12-31" 
],
[
 "Bananas",
2009,
"East",
94,
78,
16,
"2009-12-31" 
],
[
 "Oranges",
2010,
"East",
98,
91,
7,
"2010-12-31" 
],
[
 "Bananas",
2010,
"East",
81,
71,
10,
"2010-12-31" 
] 
];
data.addColumn('string','Fruit');
data.addColumn('number','Year');
data.addColumn('string','Location');
data.addColumn('number','Sales');
data.addColumn('number','Expenses');
data.addColumn('number','Profit');
data.addColumn('string','Date');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartMotionChartID25636cc9179() {
var data = gvisDataMotionChartID25636cc9179();
var options = {};
options["width"] =    600;
options["height"] =    500;
options["state"] = "";

    var chart = new google.visualization.MotionChart(
    document.getElementById('MotionChartID25636cc9179')
    );
    chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
var pkgs = window.__gvisPackages = window.__gvisPackages || [];
var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
var chartid = "motionchart";
  
// Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
var i, newPackage = true;
for (i = 0; newPackage && i < pkgs.length; i++) {
if (pkgs[i] === chartid)
newPackage = false;
}
if (newPackage)
  pkgs.push(chartid);
  
// Add the drawChart function to the global list of callbacks
callbacks.push(drawChartMotionChartID25636cc9179);
})();
function displayChartMotionChartID25636cc9179() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  window.clearTimeout(window.__gvisLoad);
  // The timeout is set to 100 because otherwise the container div we are
  // targeting might not be part of the document yet
  window.__gvisLoad = setTimeout(function() {
  var pkgCount = pkgs.length;
  google.load("visualization", "1", { packages:pkgs, callback: function() {
  if (pkgCount != pkgs.length) {
  // Race condition where another setTimeout call snuck in after us; if
  // that call added a package, we must not shift its callback
  return;
}
while (callbacks.length > 0)
callbacks.shift()();
} });
}, 100);
}
 
// jsFooter
</script>
 
<!-- jsChart -->  
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartMotionChartID25636cc9179"></script>
 
<!-- divChart -->
  
<div id="MotionChartID25636cc9179" 
  style="width: 600; height: 500;">
</div>
</div>




