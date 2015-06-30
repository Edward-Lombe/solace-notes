# API Notes

## What is REST?

Rest is basically a way of generally specifying and interaction with a program over HTTP. This is done by using a **verb** and a **URL**.

This is a list of the most commonly used verbs:
- GET
- PUT
- POST
- DELETE

This allows the same URL to be re-used for different actions. For example `GET /property/<property name>` might get all of the details for the specified property, where as `POST /property/<property name>` might create a new property. However in both of these cases the url is the same. It avoids anti-patterns such as `GET /get/property/<property name>` and `GET /post/property/<property name>`. This is what allows us to only specify data in the URL, and behavior in the verb.

## URL Format

The API will utilize a RESTful interface, using the HTTP verbs specified above.
In general all urls that contain no presentation data, and only carry information, will be prefixed with `api`. This may change in the future to be a specific domain, but for now that should allow seperation of data and views. Where possible the naming convention for viewable URL's will try to match, as closely as possible, the format of the API request it represents.

The pattern used for querying will generally follow as such:
1. Get a list of the various things you want to query for
2. Present and format this data as html client side
3. When the user has made a selection, the client will then fetch the record specified by the id, and then display the record as a singular entry.

It is important to note here that the only time id's will not be used to identify records is for searching purposes. The client will never query a single record with anything other than its id.
