Download Link: https://assignmentchef.com/product/solved-cpts-575-assignment-3
<br>



<em>This assignment has two questions. You are encouraged to use R Markdown to generate your report (in PDF). </em>

<strong>Question 1.</strong>  For this question you will be using either the dplyr package from R or the Pandas library in python to manipulate and clean up a dataset called msleep (mammals sleep) that is available on the course webpage at

<u>https://scads.eecs.wsu.edu/wp-content/uploads/2017/10/msleep_ggplot2.csv</u>

The dataset contains the sleep times and weights for a set of mammals. It has 83 rows and 11 variables. Here is a description of the variables:

<table width="347">

 <tbody>

  <tr>

   <td width="96"><strong>Name   </strong></td>

   <td width="251"><strong>Description </strong></td>

  </tr>

  <tr>

   <td width="96">name</td>

   <td width="251">common name</td>

  </tr>

  <tr>

   <td width="96">genus</td>

   <td width="251">taxonomic rank</td>

  </tr>

  <tr>

   <td width="96">vore</td>

   <td width="251">carnivore, omnivore or herbivore?</td>

  </tr>

  <tr>

   <td width="96">order</td>

   <td width="251">taxonomic rank</td>

  </tr>

  <tr>

   <td width="96">conservation</td>

   <td width="251">the conservation status of the mammal</td>

  </tr>

  <tr>

   <td width="96">sleep_total</td>

   <td width="251">total amount of sleep, in hours</td>

  </tr>

  <tr>

   <td width="96">sleep_rem</td>

   <td width="251">rem sleep, in hours</td>

  </tr>

  <tr>

   <td width="96">sleep_cycle</td>

   <td width="251">length of sleep cycle, in hours</td>

  </tr>

  <tr>

   <td width="96">awake</td>

   <td width="251">amount of time spent awake, in hours</td>

  </tr>

  <tr>

   <td width="96">brainwt</td>

   <td width="251">brain weight in kilograms</td>

  </tr>

  <tr>

   <td width="96">bodywt</td>

   <td width="251">body weight in kilograms</td>

  </tr>

 </tbody>

</table>

Load the data into R or Python, and check the first few rows for abnormalities. You will likely notice several. All of the tasks in this assignment can be hand coded, but the goal is to use the functions built into dplyr or Pandas to complete the tasks. Suggested functions for Python will be shown in blue while suggested R functions are shown in red. Note: if you are using Python, be sure to load the data as a Pandas DataFrame.

Below are the tasks to perform. Before you begin, print the first few values of the columns with a header including “sleep”. (head(), head())

<ol>

 <li>Count the number of animals which weigh under 50 kilograms and sleep more than 16 hours a day. (filter(), query())</li>

 <li>Print the name, order, sleep time and bodyweight of the animals with the 5 <em>longest</em> sleep times, in order of sleep time. (select(), arrange(), loc(), sort_values())</li>

 <li>Add two new columns to the dataframe; wt_ratio with the ratio of brain size to body weight, rem_ratio with the ratio of rem sleep to sleep time. If you think they might be useful, feel free to extract more features than these, and describe what they are. (mutate(), assign())</li>

</ol>

1

<ol>

 <li>Display the average, min and max sleep times for each order. (group_by(), summarise(), groupby(), agg())</li>

 <li>Impute the missing brain weights as the average wt_ratio for that animal’s order times the animal’s weight. Make a second copy of your dataframe, but this time impute missing brain weights with the average brain weight for that animal’s order. What assumptions do these data filling methods make? Which is the best way to impute the data, or do you see a better way, and why? You may impute or remove other variables as you find appropriate. Briefly explain your decisions. (group_by(), mutate(), groupby(),assign())</li>

</ol>

<strong>Question 2.</strong> For this question, you will first need to read section 12.6 in the R for Data Science book, here  (<u>http://r4ds.had.co.nz/tidy-data.html#case-study</u>). Grab the dataset from the tidyr package (tidyr::who), and tidy it as shown in the case study before answering the following questions. Note: if you are using pandas you can perform these same operations, just replace the gather() function with melt() and the spread() function with pivot(). However, you may prefer to use R for this question, as the dataset is from an R package.

<ol>

 <li>Explain why this line</li>

</ol>

&gt; <strong>mutate</strong>(key          =      stringr::<strong>str_replace</strong>(key,        “newrel”,                            “new_rel”))

is necessary to properly tidy the data. What happens if you skip this line?

<ol>

 <li>How many entries are removed from the dataset when you set na.rm to true in the gather command (in this dataset)?</li>

 <li>Explain the difference between an explicit and implicit missing value, in general. Can you find any implicit missing values in this dataset, if so where?</li>

 <li>Looking at the features (country, year, var, sex, age, cases) in the tidied data, are they all appropriately typed? Are there any features you think would be better suited as a different type? Why or why not?</li>

 <li>Explain in your own words what a gather operation is, and give an example of a situation when it might be useful. Do the same for spread.</li>

 <li>Generate an informative visualization, which shows something about the data. Give a brief description of what it shows, and why you thought it would be interesting to investigate.</li>

 <li>Suppose you have the following dataset called siteDemo:</li>

</ol>

<table width="590">

 <tbody>

  <tr>

   <td width="126"><strong>Site </strong></td>

   <td width="131"><strong>U30.F </strong></td>

   <td width="93"><strong>U30.M </strong></td>

   <td width="131"><strong>O30.F </strong></td>

   <td width="110"><strong>O30.M </strong></td>

  </tr>

  <tr>

   <td width="126">facebook</td>

   <td width="131">32</td>

   <td width="93">31</td>

   <td width="131">60</td>

   <td width="110">58</td>

  </tr>

  <tr>

   <td width="126">myspace</td>

   <td width="131">1</td>

   <td width="93">5</td>

   <td width="131">3</td>

   <td width="110">6</td>

  </tr>

  <tr>

   <td width="126">snapchat</td>

   <td width="131">6</td>

   <td width="93">4</td>

   <td width="131">3</td>

   <td width="110">2</td>

  </tr>

  <tr>

   <td width="126">twitter</td>

   <td width="131">17</td>

   <td width="93">23</td>

   <td width="131">12</td>

   <td width="110">17</td>

  </tr>

 </tbody>

</table>




You know that the U30.F column is the number of female users under 30 on the site, O30.M denotes the number of male users 30 or older on the site, etc. Construct this table, and show the code you would use to tidy this dataset (using gather(), separate() and mutate() or melt(), pivot(), and assign()) such that the columns are organized as: Site, AgeGroup, Gender and Count.




2