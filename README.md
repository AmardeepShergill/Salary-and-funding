# Salary-and-funding
A python test looking at a dataset set on Salaries and funding for indian companies

This project will be working with a datasets containing information of over 20k Software Professionals with different variables like:

    the Rating of the company given by the employee,
    the Company Name,
    the Job Title of the employee,
    the employee Salary (in Indian Rupee ₹),
    the number of Salaries Reported,
    the Location of the company,
    the Employment Status and
    the category of the Job Roles
    
The dataset name is Software Professionals Salary.csv and you will find it in the data folder of this repository. The data is taken from a Kaggle question to the be analysed here. The below is the steps taken in order to look into the data


First Import the necessary libraries and load the .csv file to a DataFrame named sps. Check that all columns have the correct data type.

Then look at the basic questions that can be asked about the data set
    What is the shape (rows, cols) of the sps DataFrame?
    How many unique Job Roles are there in the dataset?
    How many unique Job Title are there for the "Python" Job Role?

The below then the questions that I have decided to ask the data set as a demonstration of what Python can do.

Of the Company Names that are listed in the DataFrame, how many have a "Python" Job Role with a Job Title containing the substring "Analyst"?


Which Company Name has the highest number of Salaries Reported (across all Job Titles)?


Given the Company Name you found at the previous question, how many Locations is this company present in?


The Salary is reported in Indian Rupees (ISO code: INR). Using the Open Access Endpoint (no API Key required) of the ExchangeRate-API service, create a new column named Salary USD containing the salary-equivalent in USD and round the result to zero decimals. What is the conversion rate between USD-INR at the time of your execution? Note: of course, this result will change in time


What is the average Salary USD for the "Python" Job Role?


Which Company Name has the highest average Salary USD across all Job Titles?


Create a Plot that shows the relationship between the average Salary USD and the average Rating for each Company Name. Do you see any anomaly in the plot? Which is the Company Name that is causing this oddity?



The next sections will use three different sheets for analysis looking at startup funding.

    startup_funding2019.csv
    startup_funding2020.csv
    startup_funding2021.csv

At this link you can find the source of the original data (Kaggle) as well as more information on its composition (note: the files in the data folder are slightly different from the originals).

Using a for loop, load all three .csv files in a temporary DataFrame called df_tmp and, at each cycle, add a new column named Year that includes the year of that csv file to the temporary table and append it to a final DataFrame named fnd. Your final fnd DataFrame should include the contents from all three csv files stacked one on top of the other.

What is the shape of the fnd DataFrame?


If you check the columns' data types, you'll notice that the columns Founded, Amount($) and Year are being interpreted as strings instead of numbers. Format those three columns to numeric data types.

What is the total Amount($) of funding given in the three years available?


The following code shows us that "Inflection Point Ventures" was the Investor that funded the highest number of Company/Brands overall (36 companies funded from 2019 to 2021).

How did "Inflection Point Ventures" rank (in terms of most Company/Brands funded) in 2020? (Note: in the answer write the rank number, where 1 = most funded company)

fnd.groupby('Investor', as_index=False).size().sort_values('size', ascending=False).head(1)


Load the Software Professionals Salary.csv file in a DataFrame named sps (just like you did in Part 1), then perform the following tasks and answer the question at the end:
        starting from the sps DataFrame, create a new DF called sps_loc where you group by Location and show, for each city in the dataset, the average Rating and Salary;
        starting from the fnd DataFrame, create a new DF called fnd_loc where you group by HeadQuarter and show, for each city in the dataset for the year 2021, the total number of Company/Brands funded and the total Amount($) invested;
        merge the two DataFrames you just created so to keep just the cities that are in both datasets and save the results in a third DataFrame called sps_fnd_loc (note: make sure to use the correct type of join);
        using the sps_fnd_loc DataFrame:
            delete the HeadQuarter column
            create a new column Amount($MM) that is equal to Amount($) divided by 1,000,000
            delete the Amount($) column
            rename all the columns to the following names: ['City', 'Avg. Rating', 'Avg. Salary', 'Nr. Companies Funded', 'Sum Funding ($MM)']

    Question: Look at the City that received the highest Avg. Rating score by employees: what is the Nr. Companies Funded in that city?


Create a scatterplot that shows the relationship between the Avg. Salary and the Sum Funding ($MM). Which City stands out in terms of total funding received by companies and salary paid to their employees?
