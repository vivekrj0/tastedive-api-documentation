Querying Endpoints
==================

The TasteDive Endpoint, filterable and searchable, can return precise recommendations for TV shows to watch based on films liked by the user, music to listen liked by maximum user, etc. The API responds to standard URL queries: users can search the API using basic query strings.

Query basics
~~~~~~~~~~~~

A question mark (?) always demarcates the beginning of a URL query string: 

      ::

          # Basic pattern
          https://tastedive.com/api/similar?{query string}

          # Example query - recommendations of movie Guardians Of The Galaxy Vol. 2.
          https://tastedive.com/api/similar?q=Guardians Of The Galaxy Vol. 2
        

Queries can contain multiple parameters. An ampersand (&) separates each parameter:

      ::

          # Basic pattern
          https://tastedive.com/api/similar?{param1}&{param2}&{param3}

          # Example query - information about the movie and the similiar one.
          https://tastedive.com/api/similar?limit=1&q=Guardians Of The Galaxy Vol. 2

A few useful calls
~~~~~~~~~~~~~~~~~~

Basics with API-Key
########################

Each entry displays a collection of fields and corresponding data, e.g., an event has a classification, description, start_time, etc. Any of these data points may form the basis of a URL query:

    ::

        # Basic pattern
        https://tastedive.com/api/similar?{query}={value}&k=YOUR API-KEY

        # Example query
        https://tastedive.com/api/similar?q=Guardians Of The Galaxy Vol. 2&k=YOUR API-KEY



* Example Response

   ::

        {"Similar": {"Info": [{"Name": "Guardians Of The Galaxy Vol. 2", "Type": "movie"}], "Results": [{"Name": "Thor: Ragnarok", "Type": "movie"}, {"Name": "Star Wars: The Last Jedi", "Type": "movie"}, {"Name": "Spider-Man: Homecoming", "Type": "movie"}, {"Name": "Avengers: Infinity War", "Type": "movie"}, {"Name": "Power Rangers", "Type": "movie"}, {"Name": "Deadpool 2", "Type": "movie"}, {"Name": "Black Panther", "Type": "movie"}, {"Name": "Jumanji: Welcome To The Jungle", "Type": "movie"}, {"Name": "Bright", "Type": "movie"}, {"Name": "Pirates Of The Caribbean: Dead Men Tell No Tales", "Type": "movie"}, {"Name": "The Hitman's Bodyguard", "Type": "movie"}, {"Name": "Ready Player One", "Type": "movie"}, {"Name": "Kingsman: The Golden Circle", "Type": "movie"}, {"Name": "Baywatch", "Type": "movie"}, {"Name": "The Fate Of The Furious", "Type": "movie"}, {"Name": "The Divergent Series: Insurgent", "Type": "movie"}, {"Name": "Independence Day: Resurgence", "Type": "movie"}, {"Name": "Captain Marvel", "Type": "movie"}, {"Name": "Assassin's Creed", "Type": "movie"}, {"Name": "Ant-Man And The Wasp", "Type": "movie"}]}}
        
And again, the API also accepts multiple parameters, separated by an ampersand (&):

    :: 

        # For more than one parameter values
        https://tastedive.com/api/similar?limit=1&q=Thor: Ragnarok&k=YOUR API-KEY


*Note: type the spaces if a value has multiple words, e.g, Guardians Of The Galaxy Vol. 2. The API will automatically replace spaces with the correct encoding (“%20").*

Info
####

When verbose set to 1 in the request, each item can also contains the following additional keys: 

        +--------+-----------------------+
        |Items   | Information           |
        +========+=======================+
        | wTeaser| item description      |
        +--------+-----------------------+
        | wUrl   | item Wikipedia URL    |
        +--------+-----------------------+
        | yUrl   | item Youtube clip URL |
        +--------+-----------------------+
        | yID    | item Youtube clip ID  |
        +--------+-----------------------+

::

    # Basic pattern
    https://tastedive.com/api/similar?{query}={value}&k=YOUR API-KEY&info=1

    # Example query
    https://tastedive.com/api/similar?info=1&q=Thor: Ragnarok&k=YOUR API-KEY      

* Example Response

.. code:: json

    {
    "Similar": {
        "Info": [
            {
                "Name": "Thor: Ragnarok",
                "Type": "movie",
                "wTeaser": "\n\n\nThor: Ragnarok is a 2017 American superhero film based on the Marvel Comics character Thor, produced by Marvel Studios and distributed by Walt Disney Studios Motion Pictures. It is the sequel to 2011's Thor and 2013's Thor: The Dark World, and the seventeenth film in the Marvel Cinematic Universe (MCU). The film is directed by Taika Waititi from a screenplay by Eric Pearson and the writing team of Craig Kyle and Christopher Yost, and stars Chris Hemsworth as Thor alongside Tom Hiddleston, Cate Blanchett, Idris Elba, Jeff Goldblum, Tessa Thompson, Karl Urban, Mark Ruffalo, and Anthony Hopkins. In Thor: Ragnarok, Thor must escape the alien planet Sakaar in time to save Asgard from Hela and the impending Ragnarök.\n",
                "wUrl": "https://en.wikipedia.org/wiki/Thor:_Ragnarok",
                "yUrl": "https://www.youtube-nocookie.com/embed/ue80QwXMRHg",
                "yID": "ue80QwXMRHg"
            }
        ],
        "Results": [
            {
                "Name": "Avengers: Infinity War",
                "Type": "movie",
                "wTeaser": "\n\n\n\nAvengers: Infinity War is a 2018 American superhero film based on the Marvel Comics superhero team the Avengers, produced by Marvel Studios and distributed by Walt Disney Studios Motion Pictures. It is the sequel to 2012's The Avengers and 2015's Avengers: Age of Ultron, and the nineteenth film in the Marvel Cinematic Universe (MCU). It was directed by Anthony and Joe Russo, written by Christopher Markus and Stephen McFeely, and features an ensemble cast including Robert Downey Jr., Chris Hemsworth, Mark Ruffalo, Chris Evans, Scarlett Johansson, Benedict Cumberbatch, Don Cheadle, Tom Holland, Chadwick Boseman, Paul Bettany, Elizabeth Olsen, Anthony Mackie, Sebastian Stan, Danai Gurira, Letitia Wright, Dave Bautista, Zoe Saldana, Josh Brolin, and Chris Pratt. In the film, the Avengers and the Guardians of the Galaxy attempt to stop Thanos from collecting the all-powerful Infinity Stones.\n",
                "wUrl": "https://en.wikipedia.org/wiki/Avengers:_Infinity_War",
                "yUrl": "https://www.youtube-nocookie.com/embed/QwievZ1Tx-8",
                "yID": "QwievZ1Tx-8"
            }
        ]
    }
    }



HTTP Status Codes And Errors 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


APIs should define the functional, business view and abstract from implementation aspects. Success and error responses are a vital part to define how an API is used correctly.

* GET 

        GET requests are used to read either a single or a collection resource.

        GET requests for individual resources will usually generate a ``404`` if the resource does not exist

        GET requests for collection resources may return either ``200`` (if the collection is empty) or ``404`` (if the collection is missing)




