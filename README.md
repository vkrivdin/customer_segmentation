# Customer segmentation

# Description

This is BI dashboard project aimed to present one of my real work projects for a client

# Business case

The company needs an instrument that could help start making decisions about customer retention and customer acquisition centrally based on data that everyone could agree on and everyone could use in conversations that happen at the top management level

The process of customer discussion already exists and looks as follows:

- CEO meets with each region General Manager (GM) and inquires them about current situation with the customer base
- Every GM presents a story in a form that suits them best
- CEO can understand what is happening in each region and directs an action that should be performed in the nearest months - i.e., putting more resource into retaining customers or acquiring new ones

There are problems though that slow down or sometimes prevent some of the decisions

- Each story is different and metrics used are different
- There is no common methodology around customer segmentation
- When CEO asks to present a list of “top customers” every GM will approach it differently

# Project goals

## Main goal

- Provide an analytical tool that is always accessible to the CEO and General Managers in the company and helps them see and understand the current situation with the customer base at a level of detail enough for managing a national company operating in multiple geographical regions so that they can spend less time agreeing on data and make more effective decisions

## Sub-goals

- Help CEO and General Managers continue to hold regular monthly discussions about customer situation
- Suggest a universal customer segmentation methodology (who are top customers, etc.) that the audience will easily understand and may potentially agree to use
- Utilize the same methodology for ways to calculate the amount of customers and segments into which they can be separated at each company level
- Provide a view of the situation with customers at a whole company level, region level, and country level
- Suggest other visualizations that can help achieve the business goals

# Approach to the development process

As you can see, the business case is a bit challenging as we need to deal with several aspects

- Top management audience
    - We need to be careful with suggesting the dashboard and not overloading it with information.
    - Everything must be crystal clear and should pass the “5-second” rule
- User preference to tell “their own” data story
    - We might face active resistance or indifference to our offer
- The process works somehow already today
    - If the intended audience already achieves some of their goals without the tool, what will make them try and use what we offer?
- There is no guidance on business methodology
    - Need to perform research and apply our knowledge and expertise with data to suggest that may work
    - Priority in choosing methodology is simplicity

# Requirements

## User interaction

- User can see “at a glance” view that is used primarily used in the call between CEO and GMs
- User can see obvious visualizations with details by by time, by geography, by business line
- User ideally does not want to spend any time on setting up the filters to see the right data

## Business logic specifics

### Metrics

1. Count of Customers in a selected period
2. Customer churn in a selected period
3. Amount of Sales Revenue in a selected period

### Dimensions

1. Time period - year, quarter, month
2. Geography - country, region, state, city
3. Product - group, sub-group, product name
4. Sales revenue segment - segment name

### Customer segmentation methodology

- Due to customer expected cycle of next consecutive purchase, the 12 months window is chosen to find and assess their activity
- If the customer did not perform a purchase over last 12 months they are considered as “lost”. Otherwise, the customer is “active”
- Each customer Sales Revenue over last 12 months is used as a variable that defines a segment where they fall into
- The 12 months value is calculated for each selected period dynamically
    - If I am looking at January 2024, then the last 12 months are from February 2023 to January 2024
- 5 customer segments are set to label them accordingly:
    1. highest - $3k and more
    2. high - from $2k to $3k
    3. middle - from $1k to $2k
    4. low - from $0.5k to $1k
    5. lowest - below $0.5k

## Technical solution



### Color choice

Color palette

- https://www.color-hex.com/color-palette/107693

Two main colors

- Good - [#728c80](https://www.color-hex.com/color/728c80)[](https://www.color-hex.com/color/61786e)
- Bad - [#875457](https://www.color-hex.com/color/875457)

## Data security

- There must be possibility to restrict access of single user to a country or set of countries

# Data source

As real customer data could not be used, the Superstore sample data was used
- https://www.kaggle.com/datasets/vivek468/superstore-dataset-final

# Credits

- DAX Pattern for dynamic customer segmentation - https://www.daxpatterns.com/dynamic-segmentation/
- Bravo for Power BI - used for DAX Autocalendar and Time intelligence measures - https://www.sqlbi.com/tools/bravo-for-power-bi/