# Cypto-Consultant
# CRYPTO CONSULTANT
#### Video Demo: <https://youtu.be/__kDhOudUI8>
#### Description:
    With inflation on the rise, there is a growing urgency for people to have a safe place to invest their money so it does not
    continue to lose value, Cryptocurrency has been that appealing investment besuase it is decentralizd from banks and is independent
    of how the economy is perfomring. With the Crypo Consultant, one can eliminate the fear of picking the wrong crypto coin to
    buy, with all the multiple choices that are out there!

    This program is mainly split into four parts:
    1. Requesting Crypto market data from the CoinMarketCap API
    2. Storing that data and also outputting it to a spreadsheet
    3. Using various metrics from that data and performing mathmatical calculations to figure what are the top coins to invest in.
    4. Packing this information nicely in a streamlit application for the user

## 1. Requesting Crypto market data from the CoinMarketCap API
    To be able to communicate with the CoinMarketCap API, I had to create an acoount and get an API key. From there, there is specific
    documentation for being able to request whatever information about the market. For this program, I only needed the latest data on
    various metrics for all crypto coins. This is explained [here](https://coinmarketcap.com/api/documentation/v1/#operation/getV1CryptocurrencyListingsHistorical)

## 2. Storing and Outputting the data
    Levering CoinMarketCap API documentation, I was able set the limit of coins to 250 and sort by market cap. I am only interested in
    the coins that are trded with the highest volume. This eliminates a lot of the random memecoins that are likely to be scams or
    fail. After specifying what type of data I want, I then used the pandas library to output that information to an excel spreadsheet.

## 3. Creating Consultant Function
    This was tough because I had to do some research and use my own knowledge and experience on trading Crypto to create a mathematical
    calculation that would yield trustworthy results and selct the best coins from a multitude of options. The toughest part was figuring
    out how complex I wanted this to be and what specific metrics I wanted to use. I decided to use; volume, percent change over 1 hour,
    over 1 day, over 1 week, and over 1 month. Cryto is a very volatile investment so being constantly upto date on the lates trends is
    very important. More information can be gotten from the listing_data.xlsx

## 4. Streamlit App
    I battled between implemeting this or not as I believe this is not intergral for passing CS50P course. At the end of the day, my goal
    was to implement a program that I would be proud of having my friends and colleagues tryout so I had to keep the end user in mind throughout
    the entire process. Abulk of this part of the project was created in a separate file [litapp.py] because it is a lot of lines of code,
    mostly to foramt the app in specific ways and I did not want to crowd my project.py file. I also had to download the streamlit library
    and follow documentation for this.
    Finally, I wanted to give the user a way to access the the streamlit app without typing in an entire command for that so I used the subprocess
    library for that and ran litapp.py from within project.py as so:
    ```
    from subprocess import call
    .
    .
    .
    def open_app(t):
    if t == "yes" or t == "y":
        call(["python", "litapp.py"])
        return True

    elif t == "n" or t == "no":
        return False

    ```

    Overall, this was a very challenging project because I had to give up midway with an idea I had and ocmpletely start from scratch on something
    different. I think this was more rreqording, though, than anything else, and I made something I am very proud of.
