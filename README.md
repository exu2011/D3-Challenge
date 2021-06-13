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
data.CSV file shows that Data has the following columns:  id, state, abbr, poverty, income, healthcare, smokes, obesity etc.
Once read by d3.csv then it is like an array of 20 objects as key-value pair format so I will need to use foreach or arrow functions to get arrays
console.log(Data) see below after d3.csv

2.  Define Function xScale and yScale
I defined function used for updating x-scale var upon click on axis label
scaling function: https://www.d3indepth.com/scales/

create scales function used for updating xAxis var upon click on axis label function used for updating circles group with a transition to new circles
as compared to renderCircles, the attr iterator needs to match what is created initially
So above I use "cx" and below I use "x" -  this needs to match the attr on line 245
text is positioned by x,y attributes, circles are positioned by cx, cy attributes function used for updating circles group with new tooltip
Below circlesGroup is having the tooltip added but other elements could also have the tool tip added

I also added onmouseout event

3.  SVG Setup 
I set up SVG using d3.select to add into div id=scatter in html. xScale uses width so xScale() can only be called below this point
Create an SVG wrapper, append an SVG group that will hold our chart, and shift the latter by left and top margins.
then I append an SVG group

4.  BRING in Data and ADD Structure 

Initial Params - includes any axis selection that has multiple options
Retrieve data from the CSV file and execute everything below
parse data - set values to numerical data types

xLinearScale function above csv import; Note:  xLinearScale is functioncontains scaled data specific to the defined axis
Important note:  xScale uses width that is defined above; xScale can only be called below width in the code
scaling function: https://www.d3indepth.com/scales/
Create y scale function
Create initial axis functions; generates the scaled axis
append x axis; adds x axis chart data tick marks to chartgroup
for future axis value changes then the renderAxes() function needs called
append y axis
provide data first to grouped elements 
now I am adding the 'circles' with one circle for each data
note that the attributes are "cx" and "cy"; the data is being scaled by the scaling functions defined above; see it is a function
the centers of the circles are also coming from the specific x data group 'chosenXAxis'
append initial circles
I wanted to add text to the circles - probably several ways of doing this but here is one.
data is bound to ciclesGroupAll like above and now I add a text element at "x" and "y", not the difference from above.
added round function to make the numbers in the cirlces have no decimals; this is a random data selection; I just wanted something inside the circles. If you want to see why these values are like they are then you need to back-calculate what xScale and transpose is doing

Create group for two x-axis labels
create Y-axislabel group
updateToolTip function above csv import
  
  5.  ADD updates upon clicking axis text  
  x axis labels event listener
  if you comment out the entire labelsGroup section then you can see that the plot populates but does not update when selecting the axis
  note that above this section, only the updateToolTip and xScale functions are called of all the user created functions at the top of the script
  the other functions at the top of the page are used to re-define the data applied to the xLinearScale function, xAxis object, circlesGroup elements, textcirclesGroup elements, circlesGroup elements
  functions here found above csv import
  updates x scale for new data
  updates x axis with transition
  updates circles with new x values
  New - updates text labels within circles
  changes classes to change bold text
  create yLabelGroup listener
  get value of selection
  replaces chosenXAxis with value
      // updates x axis with transition