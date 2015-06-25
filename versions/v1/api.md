## Has.Menu API Version 1

### Configuration

#### Setup

    POST /setup

    g: geo-location

The setup API helps to find the nearest city where Has.Menu is present.

This API should be directed to https://has.menu.


#### Settings

    GET /settings

The settings API returns a hash of settings applicable for a city, including the locations.


#### Locations

    GET /locations

The locations API returns a list of valid locations for a city.


### Authentication

    POST /auth

Has.Menu relies on OAuth2.0 for authentication.
Currently Google+ is the only supported provider.

Has.Menu implements Google+ One-Time Code flow for authentication.
The client side apps should request for code during the authorization
and post it to Has.Menu.

Upon successful authentication, a JSON Web Token is used to secure
further interactions with the API.

To sign out perform a DELETE operation.

    DELETE /auth

A special GET request is provided to verify the token. Pass the auth key
in this GET request to get it verified. If the auth key is returned as is,
it is still valid.

    GET /auth


### Search

    POST /search

Search requests should be posted to Has.Menu API. Valid search fields include:

Basic

    q: search query
    e: entity (items/restaurants)

Qualifiers

    g: geo location
    h: how
    w: where

Facets

    d: distances
    c: cuisines
    p: prices
    r: ratings

Tags

    t: tags

Sort

    s: sort

Pagination

    n: page number
    z: page type (items/restaurants)


Two special search paths allow to search only the respective entities.

#### Search Restaurants

    POST /search/restaurants


#### Search Items

    POST /search/items


### Restaurant

Retrieve the details fo restaurant using the restaurants fragment.

    GET /restaurants/<restaurant-uid>


### Menu

Get the default menu

    GET /restaurants/<restaurant-uid>/menu

Get a specific menu

    GET /restaurants/<restaurant-uid>/menus/<menu-uid>


### Item

Get a specific item

    GET /restaurants/<restaurant-uid>/items/<item-uid>

Please note that the item is independent of menus in a restaurants.
For example, vegetable-soup present in dine-in-menu, and takeaway-menu
are considered to be the same item. For this reason, the item is mapped
directly to the restaurant, not through the menus.

Menus act like a document or a collection,
and sections like a qualifier for an item.


### Social

#### Likes

Restaurants can be liked and un-liked using POST and DELETE operations.

    POST   /restaurants/<restaurant-uid>/like
    DELETE /restaurants/<restaurant-uid>/like

Similarly an item can be liked and un-liked.

    POST   /restaurants/<restaurant-uid>/items/<item-uid>/like
    DELETE /restaurants/<restaurant-uid>/items/<item-uid>/like


#### Bookmarks

Restaurants can be bookmarked and un-bookmarked using POST and DELETE operations.

    POST   /restaurants/<restaurant-uid>/bookmark
    DELETE /restaurants/<restaurant-uid>/bookmark

Similarly an item can be liked and un-liked.

    POST   /restaurants/<restaurant-uid>/items/<item-uid>/bookmark
    DELETE /restaurants/<restaurant-uid>/items/<item-uid>/bookmark


#### Comments

Comments can be added and deleted using comment fragment for restaurants

    POST   /restaurants/<restaurant-uid>/comment
    DELETE /restaurants/<restaurant-uid>/comment/<id>

and items

    POST   /restaurants/<restaurant-uid>/items/<item-uid>/comment
    DELETE /restaurants/<restaurant-uid>/items/<item-uid>/comment/<id>


#### Errors

Errors can be added and deleted using erratum fragment for restaurants

    POST   /restaurants/<restaurant-uid>/erratum
    DELETE /restaurants/<restaurant-uid>/erratum/<id>

and items

    POST   /restaurants/<restaurant-uid>/items/<item-uid>/erratum
    DELETE /restaurants/<restaurant-uid>/items/<item-uid>/erratum/<id>


#### Feedback

Feedback can be added and deleted using feedback api, only for restaurants

    POST   /restaurants/<restaurant-uid>/feedback
    DELETE /restaurants/<restaurant-uid>/feedback/<id>


### Personal

#### Account

Manage account through the my/account api

    GET   /my/account
    PATCH /my/account


#### Preferences

Manage preferences through the my/preferences api

    GET   /my/preferences
    PATCH /my/preferences


#### Bookmarks

View bookmarks (personal menu) using my/bookmarks api

    GET   /my/bookmarks
    GET   /my/bookmarks/restaurants
    GET   /my/bookmarks/items
