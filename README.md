# hubot-google-translate

Allows Hubot to know many languages using Google Translate

See [`src/google-translate.coffee`](src/google-translate.coffee) for full documentation.

## Installation

In hubot project repo, run:

`npm install hubot-google-translate --save`

Then add **hubot-google-translate** to your `external-scripts.json`:

```json
[
  "hubot-google-translate"
]
```

## Configuration

Google may block translation requests coming from shared environments,
especially Heroku. An API key is required to distinguish your requests from
the other people on the same machine.

Note, this requires an account with configured billing.

* Create a new project in the [Google Dev Console][]
* Enable the translation
  * navigate to: API: APIs & Auth > APIs > Translate API
  * click "Enable API"
  * Enable billing: Click "Quotas". Click "Enable billing.
* Create an API key:  
  APIs & Auth > Credentials > Add credentials > API key > Server Key

If using Huroku, add to the env config:
```
heroku config:set HUBOT_GOOGLE_TRANSLATE_API_KEY=YourGoogleAPIKey
```

[Google Dev Console]: https://console.developers.google.com

## Sample Interaction

```
user> hubot translate me bienvenu
hubot> " bienvenu" is Turkish for " Bienvenu "
user> hubot translate me from french into english bienvenu
hubot> The French " bienvenu" translates as " Welcome " in English
```
