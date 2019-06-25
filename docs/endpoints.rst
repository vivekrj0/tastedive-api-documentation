Endpoints
==========

The TasteDive API have a simple basic endpoint. You can get all type of similar recommendation of a movie, music etc.

      :: 

          GET
          
          https://tastedive.com/api/similar

    * Example Response

      :: 

          {"Similar": {"Info": [{"Name": "!!!", "Type": "music"}], "Results": [{"Name": "Meeting Of Important People", "Type": "music"}, {"Name": "La Tour Montparnasse Infernale", "Type": "movie"}, {"Name": "Young & Sick", "Type": "music"}, {"Name": "The Vanity Project", "Type": "music"}, {"Name": "Tyler Bryant & The Shakedown", "Type": "music"}, {"Name": "Sombear", "Type": "music"}, {"Name": "Thirsty Fish", "Type": "music"}, {"Name": "Better Luck Next Time", "Type": "music"}, {"Name": "The High Court", "Type": "music"}, {"Name": "Stars Of Track And Field", "Type": "music"}, {"Name": "Beachwood Sparks", "Type": "music"}, {"Name": "Tinted Windows", "Type": "music"}, {"Name": "Promise Of Redemption", "Type": "music"}, {"Name": "Zach Gill", "Type": "music"}, {"Name": "The Music", "Type": "music"}, {"Name": "Chappo", "Type": "music"}, {"Name": "Kisses", "Type": "music"}, {"Name": "The Young Romans", "Type": "music"}, {"Name": "Jarle Bernhoft", "Type": "music"}, {"Name": "The Postelles", "Type": "music"}]}}

Parameters
~~~~~~~~~~~~~~~~~~~~~~~
  * Query String Parameters

      +------------+-------------------+---------------------+
      |Query Param | Required/Optional |   Type              |
      +============+===================+=====================+
      |   q        |       Required    |   String            |
      +------------+-------------------+---------------------+
      | type       |        Optional   |   String            |
      +------------+-------------------+---------------------+
      | info       |        Optional   |Integer(Default = 0) |
      +------------+-------------------+---------------------+
      | limit      |        Optional   |Integer(Default = 20)|
      +------------+-------------------+---------------------+
      | k          |        Required   |  String             |
      +------------+-------------------+---------------------+

Parameters Details
~~~~~~~~~~~~~~~~~~~~~

query (?q=)
############

It is the search query; consists of a series (at least one) of bands, movies, TV shows, podcasts, books, authors and/or games, separated by commas. Sometimes it is useful to specify the type of a certain resource in the query (e.g. if a movie and a book share the same title). You can do this by using the "``band:``", "``movie:``", "``show:``", "``podcast:``", "``book:``", "``author:``" or "``game:``" operators, for example: " ``band:underworld``, ``movie:harry potter``, ``book:trainspotting`` ". It is the required parameter.

type
##########

It is the query type, specifies the desired type of results.It is of type string. It can be one of the following: music, movies, shows, podcasts, books, authors, games. It is optional, if not specified, the results can have mixed types. 

info
#########

It is the additional information is provided for the recommended items, like a description and a related Youtube clip (when available) and its wikipedia link. It is of type Integer having the values 0 or 1. When set to 1 it specifies, default is 0.

limit
######

It specifies the maximum number of recommendations to retrieve. It is optional and of type integer. It default value is 20.

API-Key (k)
#############

Your API access key. It is the required feild. You can access the recommendation without this key also but for the limited requests. Using this key, you can perform 300 requests per hour. Please provide a description of your product, together with some usage estimates. This allows us to increase the quota of certain applications that need it and get a better understanding of how the service is being used. 

