## Instructions

### Overview

Cryptocurrencies are on the rise, and we want to get in on the action. Let's build a bot that watches the prices of certain coins and their prices, and places trades for us when they hit certain levels. 

### Steps done

- Write an python application that will hit an API to get the top 3 cryptocurrency coins based on current market cap. (Please note the API call to get this data is in `crypto_api.py`). 
- Store these results in a database table. (Please design this table as well as inserting records into it. The primary fields to include are the symbol, name and current price, but feel free to include any other data you believe is relevant). Please utilize MySQL or a similar relational database. (A MySQL docker container has been provided but you are welcome to use a similar one if so desired)
- Compare each coin and it's current price (in USD) against the average of the last 10 prices on a daily interval (Please note the API call to get this data is in `crypto_api.py`)
    - If the current price is lower than the average price, place an order for "1 coin" and assume it was filled at the current price. (Please use the fake function `submit_order` to mock this trade, there is no real network request to place a trade)
    - If the current price is equal to or higher than the average price, do nothing and move onto the next coin
- Log the results of the trades (if any were made)
- Log the results of our current portfolio (coins owned and percentage loss/gain on each one. Round the percentage to 2 decimal places.)
- When logging the results, make sure the information appears both in the console and an app.log file located at storage/logs/app.log
- Scheduled to run every hour.

### Important Notes

- Your goal with this application should be to have a working solution. If you find edge cases you believe should be handled, feel free to add some notes/comments about them instead of coding the full solution. 
- Make sure you follow the local development setup steps below before writing any code.
- Jumping off point - python code located in `app.py`.
- The docker container comes with poetry as a python dependency manager. Do pip: `poetry add`. Ex. `poetry add flask`


## Local Development

You will need the following installed on your local machine:

- Docker

Steps to get up and running

1. Copy the `.env.example` file to `.env`
2. Run `make init` to spin up the docker container. Note you will automatically be "ssh'ed" into the main docker container from which you can run your python code.

### Database Access

If you would like to access the database via a GUI such as Sequel Pro or Tableplus, you can use the following credentials:

Host: `127.0.0.1`
User: `docker`
Password: `secret`
Database: `crypto`
Port: `33060`
