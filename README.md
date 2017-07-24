# Predict the World Cup with Machine Learning

A tutorial about predicting the winner of the FIFA World Cup by using Machine Learning.

We'll train models to predict winners of international football (soccer) matches by using publicly available data from the [FIFA website](http://www.fifa.com/).

We will then operationalize these models inside a "tournament simulator" program which will run simulations on the World Cup final tournament scheduled to take place in Russia in June 2018.

We will visualise the results and make predictions about the chances of each team to win the tournament.

## Input Data

In the [input](/input) folder of this repo you'll find two datasets:

* `competitions.json` contains data about past FIFA-sanctioned international competitions.

```json
[
	{
		"IdCupSeason": "2000010101",
		"NumOrder": "6506",
		"CupName": "Friendly"
	},
	{
		"IdCupSeason": "6",
		"NumOrder": "2520",
		"CupName": "FIFA World Cup™ Qualifier"
	},
	{
		"IdCupSeason": "7",
		"NumOrder": "1017",
		"CupName": "FIFA World Cup™ Final"
	},
```

* `matches.json` contains international matches played since 1950.

```json
[
    {
        "date": "19560930",
        "team1": "AUT",
        "team1Text": "Austria",
        "team2": "LUX",
        "team2Text": "Luxembourg",
        "resText": "7-0",
        "statText": "",
        "venue": "Ernst Happel Stadium - Vienna , Austria",
        "IdCupSeason": "10",
        "CupName": "FIFA World Cup™ Qualifier",
        "team1Score": "7",
        "team2Score": "0"
    },
    {
        "date": "19561003",
        "team1": "IRL",
        "team1Text": "Republic of Ireland",
        "team2": "DEN",
        "team2Text": "Denmark",
        "resText": "2-1",
        "statText": "",
        "venue": "DUBLIN - Dublin , Republic of Ireland",
        "IdCupSeason": "10",
        "CupName": "FIFA World Cup™ Qualifier",
        "team1Score": "2",
        "team2Score": "1"
    },
```

## TODO 

1. Clean up venue information (home/away)
    - known issues:
        - lots of missing data for venue
        - venues for which text matching doesn't work:Moscow/URS, Leipzig/Germany DR etc
        - how many instances, can we find additional data?

2. Olympics
    - do we use them?

3. Win percentage
    - how do we account for strength of schedule (ex. KOR having a better win% than ITA or NED)
    - do we use successor countries or not? ex. FRG -> GER, URS -> RUS, etc.


4. Feature engineering
    - add strength of schedule as a rolling feature somehow
    - get more data?
        - economic data
        - weather at date of game & venue
        - coaching (e.g. how many coaching changes in the past X? how recent was the coach changed?)
        - rolling data by type of game? (e.g. rolling 20 wins for games of the same type - qualifiers)

5. What value are we predicting?
    - classifier vs regression
    - calculate an outcome from the actual result + (something else?)

6. What algorithms are we using?

7. How do we split the data into training / testing?
        