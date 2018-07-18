# UNDER CONSTRUCTION
## This API is still under construction, and will be frozen when https://github.com/tosdr/tosdr-firefox starts relying on it.

For now, there is only one file the V2 API: https://tosdr.org/api/2/all.json

It is a JSON-encoded object that contains the following keys:

## tosdr/api/version

Always `2`.

## tosdr/data/version

Milliseconds since the beginning of 1970 until the time this snapshot was created.

## tosdr/review/<domain.com> (for <domain.com> a FQDN):

### References

For instance:
```js
  'tosdr/review/google.co.uk': {
     see: 'google.com'
  },
```
If a service has multiple domain names (e.g. '500px.com', '500px.me', '500px.net', etc), then only the first one will contain the review data the others will be included as references.

### Reviews
They contain the following fields:

#### name
E.g. 'Google'

#### logo

URL of a 72px by 72px .png logo, e.g. "https://tosdr.org/logo/500px.png"

#### rated

The ToS;DR review rating of this service. One of 'A', 'B', 'C', 'D', 'E', or `false` if this service has not been comprehensively reviewed yet.

#### points

An array of review points (i.e. individual positive/neutral/negative remarks about the terms of this service), in which each element contains:

* short (a short text to display as a title, say 1 line of text)
* long (a longer text to display as a paragraph in addition to the title, say 5 lines of text)
* discussion (URL at which this point can be discussed with other reviewers)
* icon (one of 'good', 'neutral', 'bad', 'blocker')
* score (number [0..100], the higher the score, the more important this point)
* privacyRelated (true or false, used to decide whether this point should influence DuckDuckGo's Privacy Grade or not)

#### documents

An array of reviewed documents, in which each element contains:

* name (e.g. 'Privacy Policy')
* url (e.g. 'https://google.com/tos')