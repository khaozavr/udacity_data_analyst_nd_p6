# Summary
With this visualization I tried to show in an engaging way the distribution of flight delays over the year 2008. I created a very simple "calendar of delays" by using a javascript calendar plugin. Each day in the calendar is colored according to the percentage of all US inbound flights that departed at least 15 min late that day. The actual percentage can be seen by hovering over a particular day.

***
# Design
Having settled on the flights dataset, I started looking for a story to tell. There are many interesting variables in this dataset, but the ones of particular practical importance to a broad audience in my opinion have to do with delays and cancellations. So I quickly formed an idea to try and visualize all the delayed flights. To keep things somewhat simple, I chose to focus on the latest available year, 2008.

The first thing that came to mind was to create a simple line plot, with days of the year on the x-axis, and number of delayed flights on the y-axis.
I did a crude sketch of it, and noticed that I wouldn't be able to easily see which days of the week had more delayed flights. After giving it some more thought, I figured a line plot would be best for showing a trend over time, and that actually was not what I was expecting from my data.

Thinking more about the design, I came to the idea of heatmaps. It occurred to me that I could use color saturation to represent days with more flight delays. Trying to come up with a good layout it became clear that I was in effect trying to represent a colored calendar for the year 2008. So why not do an actual calendar? With that revelation, I searched for a simple javascript calendar implementation, and found a perfect one in Jim Camut's "Calendarize". Now I had to format it to my needs and connect my delay data with days in the calendar.

I decided to use a color gradient to represent the relative amount of delayed flights on a given day. I prepared a separate dataset with calculated delay percentages per day, for all flights that had at least a 15 minute departure delay. This dataset was used in the visualization. For the color, I chose a red gradient, as delays are something negative and the typical "positive" colors such as green or blue seemed a bit out of place. In the data, the lowest percentage was around 6%, and the highest slightly above 50%. So I initially made a 6-step gradient with categories in 10%-steps. The initial rendering of my delay calendar can be seen in "index1.html".

After the first constructive feedback, I set out to make the message I was trying to convey with the visualization clearer. First, I decided to refine my gradient with 5%-steps, totaling 11 categories. I adjusted the red hue to be more pastel. But the most pressing problem was how to show the percentage of delayed flights. I initially thought it might not be necessary to show the numbers at all, and the viewer would just get the idea from the color gradient. But the feedback made it clear that this approach misses out on day-to-day comparisons, which would be useful and easy were I to show the actual numbers. The first idea how to do that was to show the numbers in the square for the given day when hovering over it. So I implemented that and showed the graphic to the next person.

The next feedback I got focused more on the layout of the calendar. One obvious thing that hadn't occurred to me was that the dummy days at the beginning and the end of each month were completely redundant and just cluttering the space. So I quickly got rid of those. Next, I tried to reduce the margins between the month blocks to save some more space and give the calendar a tighter look. Another good idea was to find a more professionally-sounding and informative title. Finally, I started looking for a possibility to include numbers for days of the month as well, which would facilitate direct comparisons. At this point, my "heatmap over a calendar layout" morphed into "calendar 2008 with extra colorful info".

I decided to make percentages appear on hover as a tooltip. This way, I would have a full calendar with color gradient background representing flight delay categories, and percentage numbers that would pop up on hover. The third round of feedback that I updated upon concerned mostly the aesthetics of the tooltip. I gave it a bluish fill and a larger text, and worked on in and out transitions to make the animation smoother. One last insightful comment made me zoom out to fit the whole calendar on one page, and I had to admit it looked much better that way, providing a quick overview of the whole data. To make it appear this way from the start, I implemented the CSS "zoom" function, which unfortunately does not work in Firefox for some reason. So this project is best viewed in any other browser.

***
# Feedback
### Person 1
* the red hue is quite ugly
* maybe add more intermediate steps to the gradient
* although it is clear what the graphic tries to communicate, the message "doesn't pop out"
* it would be better to provide actual delay percentages as well

### Person 2
* the title could be more informative
* year number after each month name is unnecessary, better to include once in the title
* dummy days at the beginning and end of each month are redundant
* the months could be brought together more compactly
* it would be better to show day of the month as well, not just the delay percentage, better for comparisons

### Person 3
* ideally the whole calendar would fit on one page without scrolling
* maybe add color to the percentage pop-up and make the text in it larger
* make the pop-up animation smoother

***
# Resources
* Jim Camut's [Calendarize](https://github.com/jimcamut/calendarize)
* RGB Color Gradient Maker: http://www.perbang.dk/rgbgradient/
* The best programming community: [StackOverflow](http://stackoverflow.com/)
"# udacity_data_analyst_nd_p6" 
