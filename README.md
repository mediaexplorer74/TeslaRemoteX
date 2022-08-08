# TeslaRemoteX

My XF fork of some TeslaRemote project.

This is the part of Project Gemini.

## Screenshots
![screenshot1](Images/shot1.png)

## Plan of RnD
- Research
- Design
- Tech
- Dev
- Intro

## Platforms
- Win10/11 (Windows Tablet, min os build 16299)
- Android 
- iOS

## Some useful resources that I found

1 Tesla API / Tesla Remote GitHub repos ::

- https://github.com/themonomers/tesla (Python)
- https://github.com/timdorr/tesla-api (Ruby)
- https://github.com/morrisonbrett/teslalib (C#)
- https://github.com/gglockner/teslajson (Python)
- https://github.com/jimmyhuang/tesla-remote-app (JS, etc.)
- https://github.com/CoolTechYT/Tesla-Dashboard (JS / HTML / Shell)
- https://github.com/Clancey/TeslaRemote (C#)
- https://github.com/tiratira/TeslaRemote (Kotlin)
- https://github.com/joeblau/teslaapi.io (Shell)
- https://github.com/cham/TeslaAPI (JS)
- https://github.com/jdemeyer1/TeslaAPIThruPostman (Postman Web)
- https://github.com/jonasman/TeslaSwift (Swift)
- https://github.com/tbee/teslaApi (Java)
- https://github.com/teslahunt/inventory (JS)
- https://github.com/cham/TeslaUMF (UMF scheme)
- https://github.com/zuyezheng/TeslaApi (Scala)
- https://github.com/shrutinehra/TeslaAPI (C#; Tesla Model S API)
- https://github.com/markjulmar/teslaapi-net (C# .NET)
- https://github.com/futugyou/TeslaAPI (C#)
- https://github.com/driis/dr.TeslaApiFacade (C#; Facade for Siri)
- https://github.com/afaq-khan/TeslaApiTokenGenerator (C#; Tesla's SSO service)

2 Some Tesla API videos / demoreels ::

- https://www.youtube.com/watch?v=fmkeXRfgXEs Let's Learn Elixir - Github REST API Client with Tesla (Audio Reup)
- https://www.youtube.com/watch?v=R3Ec4gpfpLM FINALLY I got the Solar Value card from the Tesla mobile app to work from the API !!!
- https://www.youtube.com/watch?v=FYqiB_D5DmE An Appeal To Elon Musk: Please Open Up The Tesla API!
- https://www.youtube.com/watch?v=WgSprr-KAt0 Tesla Model S REST API Demo 1
- https://www.youtube.com/watch?v=uaJN28O-IKc Tesla Model S REST API Demo 2
- https://www.youtube.com/watch?v=f8X1fLf9beo Tesla Dashboard on Raspberry Pi [API Scraper Tutorial]
- https://www.youtube.com/watch?v=zSkwkvBf1RY Anki Vector + Tesla API = 😎
- https://www.youtube.com/watch?v=UrAyL5oojE8 Apps For Tesla Owners - Tezlab vs. TeslaFi
- https://www.youtube.com/watch?v=3Q0oEqGelqs #7 Comment générer un token API Tesla facilement.
- https://www.youtube.com/watch?v=fG9ySnNQVxI How to hack Teslas and why the automotive ecosystem needs to be secure
- https://www.youtube.com/watch?v=L3bCVUH74AY How to generate a Tesla API Token safely and why you need to be careful
- https://www.youtube.com/watch?v=KGt7Wy_bkpc Hack a Tesla with the TOP SECRET Tesla API!
- https://www.youtube.com/watch?v=l1pqhlGSuVg How to use the Tesla API - Part 1
- https://www.youtube.com/watch?v=FlJFXlrhn04 How to use the Refresh Token to get a new Access Token for Tesla API Authentication?
- https://www.youtube.com/watch?v=q77eGQGOV2Y What can your Tesla's data tell you? | Overview of Teslametric & Tesla API
- https://www.youtube.com/watch?v=kmDN6tAW8X4 Tesla Authentication - Finally Found Something That Works!

3 Docs / Articles ::

- https://teslaapi.dev/ Tesla API Docs
- https://www.teslaapi.io/ Tesla API
- https://tesla-api.timdorr.com/ Tesla JSON API (Unofficial)
- https://www.teslarati.com/tesla-api-controlling-model-s-model-x/ API Tesla Mobile
- https://medium.com/@jhuang5132/a-beginners-guide-to-the-unofficial-tesla-api-a5b3edfe1467 A Beginner’s Guide to the Unofficial Tesla API

## Get your Tesla crendentials

You can use the following apps to generate an Access Token & Refresh Token from the Tesla server :: 
- iOS: https://apps.apple.com/us/app/auth-app-for-tesla/id1552058613#?platform=iphone
- Android: https://play.google.com/store/apps/details?id=net.leveugle.teslatokens
## Quick Tutorial (for your own DIY)) , by Jimmy Huang

A Beginner’s Guide to the Unofficial Tesla API
Check out my basic implementation using React Native on Github.

Source: https://www.tesla.com/support/tesla-app

Basic Concept of an API

Before we begin, we should briefly explore a few concepts.

First, what exactly is an API? API stands for Application Programming Interface. It allows applications to talk to each other and lets external users consume data without resorting to web scraping. The easiest way to describe an API is a server that will fulfill your requests for data and/or actions. As you might have guessed, the Tesla API will be the main resource for our application.

APIs will usually send back data in the form of JSON, or JavaScript Object Notation. With JSON, you can easily query the information you need and update the state of your own application with that information.

APIs are also generally designed with an architectural style called REST, or Representational State Transfer. It covers the 4 CRUD actions: Create, Read, Update, and Delete. The two most common type of requests are: GET (read), and POST (create) requests. These are the two that we will be using today.

What is REST? | Codecademy
REST, or REpresentational State Transfer, is an architectural style for providing standards between computer systems on…
www.codecademy.com

The last nominal topic to cover is what an unofficial/private API is. It refers to an API that isn’t officially acknowledged by the provider but still allows access (with authentication). It is hard to speculate on the reasons why this is the case for the Tesla API, but it could vary from not being ready for public use to the company not wanting to have engineers maintain the service.

Unofficial API Documentation
Luckily for us, people have been able to reverse engineer the API. There are two sites that have graciously provided documentation on how to access these API endpoints. An endpoint is the URI of the server that will receive our requests and allow us to communicate directly with the API. There will be multiple endpoints — each serving their own purpose.

The two sites are here:

Introduction - Tesla JSON API (Unofficial)
tesla-api.timdorr.com

Tesla API - Tesla API
www.teslaapi.io

DISCLAIMER:

Before we continue, note that that certain API requests can perform remote actions on your car.


Source: https://www.teslarati.com/tesla-model-3-app-phone-key-features-screenshots/
Step 1: Generating a Bearer Token
Let’s start by getting data about our car. We can kick off the process by submitting POST and GET requests to the Tesla API endpoint. But before we can do that, we must figure out which endpoint to hit and then complete the authorization process through OAuth 2.0. OAuth is a protocol to tell the API that we have the proper credentials and should be permitted access.

From the Unofficial API documentation, we have Tesla’s Client ID and their Client Secret. The client ID is a public identifier for the app, and the client secret is used for identifying with the authorization server.

The Client ID and Secret - OAuth 2.0 Servers
www.oauth.com

All we need to now is to go through the OAuth Password Grant which exchanges our first-party (rather than third-party) credentials for an access token. Since Tesla owners must make an account before purchasing a car, it is relatively simple. The username and password we use for the Tesla site can be exchanged directly for a token.

OAuth 2.0 Password Grant Type
The Password grant type is used by first-party clients to exchange a user's credentials for an access token.
oauth.net

We can send a POST request to:

https://owner-api.teslamotors.com/oauth/token 
through the Fetch API which is built into any modern browser.

An easy way to do this is by using Postman. It also allows us to debug the initial requests (e.g. Did we hit the right route? Is the header and body valid? What type of JSON data is being send back?) easily. However, we need to send header information to authenticate ourselves.

The POST request requires two things in this case:

a header that contains the below key-value pair
{ Content-Type: application/json }

2. a body that contains the information mentioned above — grant type, client id, client secret, our email, and our password.

{
  "grant_type": "password",
  "client_id": "CLIENT_ID_FROM_UNOFFICIAL_API",
  "client_secret": "CLIENT_SECRET_FROM_UNOFFICIAL_API",
  "email": "YOUR_EMAIL",
  "password": "YOUR_PASSWORD"
}
// Note that the "grant_type" value is literally the string "password."
A successful response should return JSON similar to below:

{
  "access_token": "YOUR_ACCESS_TOKEN",
  "token_type": "bearer",
  "expires_in": 3888000,
  "refresh_token": "YOUR_REFRESH_TOKEN",
  "created_at": 1540704299
}
A bad response (likely from an incorrect username/password combo) will return the below response:

{ "response": "authorization_required_for_txid_``" }
If all went well, congrats on submitting your first POST request and getting your bearer/access token. Treat this like your password — you do not want to share this with other people because it will allow them to perform remote actions on your car!

Step 2: Finding the vehicles attached to your account and your Vehicle ID(s)
With the token, we can finally start receiving real-time data from your car. Instead of passing around your Tesla username and password like before, we can authenticate ourselves with only a token. For all future GET requests, we should attach the following header (again as a key-value pair):

{ Authorization: Bearer "YOUR_BEARER_TOKEN"}
Note: You will need to add the word “Bearer” as it is above and your bearer token does not have to be in quotes.

The endpoint to hit here is:

https://owner-api.teslamotors.com/api/1/vehicles
It will list your vehicle (or vehicles if you are lucky enough to own more than one).

If you receive the following error:

{
    "response": null,
    "error": "vehicle unavailable: {:error=>\"vehicle unavailable:\"}",
    "error_description": ""
}
You should wake up the car from your official Tesla app or turn on your car by pressing the handle. Sometimes your car will go into a deep sleep and will need to be triggered awake manually.

The response should look something like this:

{
    "response": [
        {
            "id": "YOUR_ID_HERE"
            "vehicle_id": "YOUR_VEHICLE_ID_HERE"
            "vin": "YOUR_VIN_HERE",                     
            "display_name": "Curiosity",
            "option_codes": "AD15,MDL3,PBSB,RENA,BT37,ID3W"
            "color": null,
            "tokens": [
                "YOUR_TOKENS_HERE"
            ],
            "state": "asleep",
            "in_service": false,
            "id_s": "YOUR_ID_S_HERE",                      
            "calendar_enabled": true,
            "api_version": null,
            "backseat_token": null,
            "backseat_token_updated_at": null
        }
    ],
    "count": 1
}
At this point, you should be getting comfortable with sending requests. Before we steamroll ahead, take note of the key “ id_s” . The value of “id_s” if your Vehicle ID, NOT the actual “vehicle_id” key. This is a mistake that most beginners make when trying to access the Tesla API.

Step 3: Finding the vehicle’s state
To find out the state of the vehicle, we can send another GET request.

https://owner-api.teslamotors.com/api/1/vehicles/YOUR_VEHICLE_ID_HERE/data_request/vehicle_state
You’ll notice that in our URI, we need to send the Vehicle ID we received from Step 2. Again, use the “id_s” value and not the “vehicle_id” value.

We must also send the same header as we did in Step 2. Both the Vehicle ID and Bearer Token will be necessary to continue.

{ Authorization: Bearer "YOUR_BEARER_TOKEN"}
Finally, we receive back our first piece of exciting data. It should respond with:

{
    "response": {
        "api_version": 3,
        "autopark_state_v3": "standby",
        "autopark_style": "dead_man",
        "calendar_supported": true,
        "car_version": "2018.41 4c56698",
        "center_display_state": 0,
        "df": 0,
        "dr": 0,
        "ft": 0,
        "homelink_nearby": false,
        "is_user_present": false,
        "last_autopark_error": "no_error",
        "locked": true,
        "media_state": {
            "remote_control_enabled": true
        },
        "notifications_supported": true,
        "odometer": 1650.501152,
        "parsed_calendar_supported": true,
        "pf": 0,
        "pr": 0,
        "remote_start": false,
        "remote_start_supported": true,
        "rt": 0,
        "software_update": {
            "expected_duration_sec": 2700,
            "status": ""
        },
        "speed_limit_mode": {
            "active": false,
            "current_limit_mph": 85,
            "max_limit_mph": 90,
            "min_limit_mph": 50,
            "pin_code_set": true
        },
        "sun_roof_percent_open": null,
        "sun_roof_state": "unknown",
        "timestamp": 8546705108352,
        "valet_mode": false,
        "valet_pin_needed": true,
        "vehicle_name": "Curiosity"
    }
}
We can view certain things in our vehicle state like our odometer, firmware version, valet mode, speed limit, etc.

Step 4: Triggering remote actions
There are many actions that we can trigger from the API. I would recommend referring back to the Unofficial API documentation as endpoints can be deprecated or act in odd manners (e.g. setting charge limits).

We can do a simple one by starting/stopping climate control in our car. Again, the pattern similarly follows Step 3. This is an example of how RESTful architecture works to standardize the way we interact with APIs.

Header:

{ Authorization: Bearer "YOUR_BEARER_TOKEN"}
Auto Conditioning Start Endpoint:

https://owner-api.teslamotors.com/api/1/vehicles/YOUR_VEHICLE_ID_HERE/command/auto_conditioning_start
Response (if successful):

{
    "response": {
        "reason": "",
        "result": true
    }
}
Auto Conditioning End Endpoint:

https://owner-api.teslamotors.com/api/1/vehicles/YOUR_VEHICLE_ID_HERE/command/auto_conditioning_stop
Conclusion
Congrats! You’ve made it through to the end. You now know how to generate a bearer token, check your vehicle’s state, as well as perform a remote action. These functions can be integrated into an app or even executed whimsically from your desktop. More likely than not, the official mobile Tesla App is using the same API when you connect with your car.

Keep playing around with different endpoints in the Unofficial API documentation — you never know if and when new features will be added. I hope you enjoyed following along this tutorial.

## Referencies
- https://medium.com/@jhuang5132/a-beginners-guide-to-the-unofficial-tesla-api-a5b3edfe1467 "A Beginner’s Guide to the Unofficial Tesla API" by Jimmy Huang 
## .

AS IS. No support. RnD only.

-- [m][e] 2022
 
