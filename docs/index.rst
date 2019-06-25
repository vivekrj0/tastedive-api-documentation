.. tastedive-api-documentation documentation master file, created by
   sphinx-quickstart on Tue June 11 12:43:07 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

=================================
TasteDive API Documentation
=================================

Overview
========

TasteDive (formerly named TasteKid) is an entertainment recommendation engine for films, TV shows, music, video games, and books. It also has elements of a social media site. 

When a user types in the title of a film or TV show, the site's algorithm provides a list of similar content. It provides recommendations for TV shows to watch based on films liked by the user, and vice versa. It also provides recommendations for music, video games, and books, and includes film and TV trailers and music videos. The API responds to standard URL query strings, and it returns data in an easily interpretable and scrapable JSON format. 

An account is free and is not required to receive recommendations, but recommendations are more accurate for those with an account. The more a user explores the site, the more the site learns about the user's preferences and the better the results become. The site also has a social media aspect where one can see activity and gain recommendations from other users, how many others in the community like or dislike any recommendation, and how popular their tastes are within the TasteDive community.

Requirements
============

Anyone with an internet browser can readily access the TasteDive API. If you decide to use it, you have to `request an access key <https://tastedive.com/account/api_access/>`_. Using this key, you can perform 300 requests per hour. It requires no special programs or installations. The API, however, presents results in JSON. Thus, a JSON reader of some kind can help organize the page into a user-friendly, human-readable format. (JSONview, for instance, has an exceptional extension for `Chrome <https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc?hl=en>`_ or `Firefox <https://addons.mozilla.org/en-Us/firefox/addon/jsonview/>`_ users.)


Learn more
==========

The following sections give a high-level overview of the TasteDive parameters (i.e., the categories of recommendations of the specific type) and walk through the process of querying the parameters values for specific results.

.. toctree::
   :maxdepth: 2
   
   endpoints
   querying_endpoints

