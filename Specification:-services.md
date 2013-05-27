## id

The id is used by other files to refer to this specific file.

Keep it simple, lowercase. Use a "-" for any non-Az-01 character.

_For instance: AT&T's id is "at-t", App.net's id is "app-net"_

## name

This is the name of the service. It is the common way people refer to it. You can use capitals, etc. 

_For instance: "Google" or "Facebook" or "App.net"_

## type

Type can be either "service" or "software". 

_For instance, diasp.org or joindiaspora.com are a "service" but diaspora is "software"._

## urls

urls are an array, because a service can be accessed from different urls (e.g. google.com and google.de). The urls is particularly useful for the browser extension to display the ToS;DR rating (see [#tosdr](#tosdr)) while the user is on a website.

Be careful when you chose the urls, to allow subdomains or not. 

_For instance, blogs hosted at wordpress.com can be accessed through blogname.wordpress.com. We do not want to refer to this url when we deal with the ToS for wordpress.com. So instead, we use `"urls": ["en.wordpress.com", "(etc.)"]`_

## keywords

Array to refer to keywords commonly used to refer to that service. Useful for showing similar services and for search purposes

## related

Array for related services. Use other services's id to refer to them.

_For instance: wordpress.com will have `"related": ["tumblr"]`_

## parent

When a service belongs to another service or is based on software.

_For instance: wordpress.com is owned/run by "automattic" and diasp.org is based on the software "diaspora"._

## alexa

The alexa.com ranking for the service. We use it to order services from most visited to less. 

## fulltos

    `"fulltos": {
        "privacy": {
          "service": "automattic",
        }, 
        "tosback2": "akismet.com", 
        "terms": {
            "name": "Terms of Use", 
            "url": "https://akismet.com/tos/"
        }
    },` 

## tosdr
    `"tosdr": {
        "rated": false
    },
}`

## dataexport

## freesoftware

## license