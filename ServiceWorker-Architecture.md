
# Install-Event:

# Activate-Event:

# Fetch-Event:

## OHIOH-Strategy

We use  an combination to make sure of less Network-Traffic and maximal easy User-Experiance.
1.
2.
3.

## Strategy: Cache with Network FallbackPage

If the ServiceWorker has to load something that is not yet avaible in the Cache [ because it wasn't loaded yet as an example] 
the serviceWorker will ask for Networkconnection. When this is not avaible it will redirect  to the fallbackPage.html to inform the User about.


## Strategy: Cache only

This strategy helps in situation, where a relink or data change would brake the information by it self. MAyby when loading something from the database.
Then it is important to only use cache when Nétwork is not avaible. On this way the dataquality is secured.

## Strategy: Network Only

This is the opposite to Cache only. This is how Homepage etc are working

## Strategy: Network with Cache Fallback

This strategy request a page from the ServiceWorker in a situation where the Network is not avaible.
Then the serviceWorker will request this data from Cache. This is a very helpful strategy.

## Strategy: Cache, then Network
This is a really useful strategy in alot of cases. The idea is to get the content as fast and traffic saving as possible.
If and update is avaible on the avaible network this will update the content.
1.The page will directly request the cache and getting the content
2.At the same time the page request the ServiceWorker that request the network for new content for the page and the cache.If new contant is avaible the serviceWorker pushit to the  page too. The user has the best experinace on this way
Important for Coders:This  process is in the requested *.js file and the serviceWorker

## Version: Cache then  Network  (all data to dynamic Caching again) Strategy:


## Version: Cache then  Network  (all data to dynamic Caching after compare) Strategy:

## Implimitionway for seperated files Step-byStep:
The important question to understand why we have do give this a look is "What is loaded first...the serviceworker or the wihed *.js file from the index.html?"

## Kill a ServiceWorker


## Dynamic Caching vs Caching Dynamic Content
This  both methods are not equal.
Dynamic Caching works by loading  he page, caling the ServiceWorker. This makes a request to Network and send it back to ServiceWorker. Now this new content is  stored in the Cache and is send  to the PAGE. This is a part of a Caching-Strategies.

# Caching Dynamic Content

Here the Page requests information from the ServiceWorker. Buit instead of useing the Cacha API, this uses the Indexed( or other DB) Key-Value-Object Database (in  Json). 
Works similar NetworkThenCache Strategy  concationated  with the DB.
Data changes frequently  is dynamic and thetypically way to handle this is the JSON-Format.


# Background Sync  

What happens if the user has no internet and will  make a new request. MAybe for sending Research Data or getting newst information?
We biult in a storage for the serviceworker like a "register Sync Task" as json file in DB (at the beginning in indexedDB) that waits for a Internet connection.
This is a "Sync"-Event in the ServiceWorker in the background of the application.





