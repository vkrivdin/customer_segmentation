# Description

This is BI dashboard project aimed to present one of my real work projects for a client

# Business case

The company needs an instrument that could help start making decisions about customer retention and customer acquisition centrally based on data that everyone could agree on and everyone could use in conversations that happen at the top management level

The process of customer discussion already exists 

- CEO meets with each region General Manager (GM) and inquires them about current situation with the customer base
- Every GM presents a story in a form that suits them best
- CEO can understand what is happening in each region and directs an action that should be performed in the nearest months - i.e., putting more resource into retaining customers or acquiring new ones

There are problems though that slow down or sometimes prevent some of the decisions

- Each story is different and metrics used are different
- There is no common methodology around customer segmentation
- When CEO asks to present a list of “top customers” every GM will approach it differently

# Project goals

Main goal:

- Provide analytical tool that is always accessible for CEO and General Managers in the company and helps them see and understand current customer situation at level of details enough for managing an international company operating in multiple geographical regions so that they can spend less time on agreeing on data and make more effective decisions

Sub-goals:

- Help CEO and General Managers continue to hold regular monthly discussions about customer situation
- Provide ability to see where (in which region, in which business line) the amount of customers is growing or falling down
- Provide a view at situation with customers at a whole company level, region level and country level
- Suggest a universal customer segmentation methodology that audience will easily understand and may potentially agree to use
- Utilize the same methodology for ways to calculate amount of customers and segments into which they can be separated
- Suggest visualizations that can help achieve the business goals

# Approach to development process

As you can see the business case is a bit challenging as we need to deal with several aspects

- Top management audience
    - Need to be careful with suggesting the dashboard and not to overload it with information.
    - Everything must be crystal clear and should pass the “5 second” rule
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

## Business case specifics

### Metrics

1. Count of Customers in a selected period
2. Amount of Sales Revenue in a selected period
3. Count of Customers in each customer segment in a selected period

### Customer segmentation methodology

- Due to customer expected cycle of next consecutive purchase the 12 months window is chosen to find and assess their activity
- If the customer did not perform a purchase over last 12 months they are considered as “lost”. Otherwise, the customer is “active”
- Each customer Sales Revenue over last 12 months is used as a variable that defines a segment where they fall into
- The 12 months value is calculated for each selected period dynamically
    - If I am looking at January 2024 then the 12 months are December 2022
- 5 customer segments are set to label them accordingly:
    1. highest - $3k and more
    2. high - from $2k to $3k
    3. middle - from $1k to $2k
    4. low - from $0.5k to $1k
    5. lowest - below $0.5k

## Data security

- There must be possibility to restrict access of single user to a country or set of countries