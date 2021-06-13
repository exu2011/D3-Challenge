# D3-Challenge

Welcome to the newsroom! You've just accepted a data visualization position for a major metro paper. You're tasked with analyzing the current trends shaping people's lives, as well as creating charts, graphs, and interactive elements to help readers understand your findings.
The editor wants to run a series of feature stories about the health risks facing particular demographics. She's counting on you to sniff out the first story idea by sifting through information from the U.S. Census Bureau and the Behavioral Risk Factor Surveillance System.
The data set included with the assignment is based on 2014 ACS 1-year estimates from the US Census Bureau, but you are free to investigate a different data set. The current data set includes data on rates of income, obesity, poverty, etc. by state. MOE stands for "margin of error."
You need to create a scatter plot between two of the data variables such as Healthcare vs. Poverty or Smokers vs. Age.
Using the D3 techniques we taught you in class, create a scatter plot that represents each state with circle elements. You'll code this graphic in the app.js file of your homework directory—make sure you pull in the data from data.csv by using the d3.csv function. Your scatter plot should ultimately appear like the image at the top of this section.


Include state abbreviations in the circles.


Create and situate your axes and labels to the left and bottom of the chart.


Note: You'll need to use python -m http.server to run the visualization. This will host the page at localhost:8000 in your web browser.

1.  Data Exploration 
 data.CSV file shows that Data has following columns:  rockband, hair_length, num_hits, num_albums
Once read by d3.csv then it is like an array of 20 objects as key-value pair format so I will need to use foreach or arrow functions to get arrays
console.log(Data) see below after d3.csv

2.  Define Function 
// function used for updating x-scale var upon click on axis label
// scaling function: https://www.d3indepth.com/scales/

 // create scales
  // function used for updating xAxis var upon click on axis label

  // function used for updating circles group with a transition to
  // new circles

 as compared to renderCircles, the attr iterator needs to match what is created initially
  // So above I use "cx" and below I use "x" -  this needs to match the attr on line 245
  // text is positioned by x,y attributes, circles are positioned by cx, cy attributes

  // function used for updating circles group with new tooltip
  //Note:  Below circlesGroup is having the tooltip added but other elements could also have the tool tip added

        // onmouseout event
3.  SVG Setup 