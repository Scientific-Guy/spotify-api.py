# Spotify-Api.py

Simple wrapper for Spotify api written in python by the [@spotify-api](https://github.com/spotify-api) Organization!


# Quick Docs

## Client Class

Client class will be the main class to access other classes!

```py
from spotifyapi import Client

client = Client(
  token='your-token'
)
```

Now as the Spotify Token Regenerates for every 5 minutes you can get a new token by Client ID and Client Secret!

```py
# You can use set interval if u want

from spotifyapi import Client

client = Client(
  token='NO TOKEN' # Leave it like this
)

my_auth = client.oauth.get(
  client_id='your-id',
  client_secret='your-secret'
)

print(my_auth['access_token']) # Will print token. If you find errors, you can create an issue in Github repo
```

## Track Class 
Track class will let you to find, get and configure your search with tracks. You have to load `client`. Example given above 

First define tracks if needed
```py
track = client.track

# or

from spotifyapi.Track import Track
track = Track('some-token')
```

### Functions

| Name           | Params                           | Example                           |
|----------------|----------------------------------|-----------------------------------|
| search         | `query: str`, `limit: int`       | `track.search('some query', 5)`   |
| get            | `trackID: str`, `advanced: bool` | `track.get('some-id')`            |
| audio_features | `trackID: str`                   | `track.audio_features('some-id')` |
| audio_analysis | `trackID: str`                   | `track.audio_analysis('some-id')` |

## Artist Class 
Artist class will let you to find, get and configure your search with artists. You have to load `client`. Example given above 

First define artist if needed
```py
artist = client.artist

# or

from spotifyapi.Artist import Artist
artist = Artist('some-token')
```

### Functions

| Name           | Params                       | Example                             |
|----------------|------------------------------|-------------------------------------|
| search         | `query: str`, `limit: int`   | `artist.search('some query', 5)`    |
| get            | `artistID: str`              | `artist.get('some-id')`             |
| albums         | `artistID: str`, `limit: int`| `artist.albums('some-id',5)`        |
| top_tracks     | `artistID: str`              | `artist.top_tracks('some-id')`      |
| related_artists| `artistID: str`              | `artist.related_artists('some id')` |

## Album Class 
Album class will let you to find, get and configure your search with albums. You have to load `client`. Example given above 

First define album if needed
```py
artist = client.album

# or

from spotifyapi.Album import Album
artist = Album('some-token')
```

### Functions

| Name           | Params                       | Example                                 |
|----------------|------------------------------|-----------------------------------------|
| search         | `query: str`, `limit: int`   | `album.search('some query', 5)`         |
| get            | `albumID: str`               | `album.get('some-id', 5)`               |
| get_tracks     | `albumID: str`, `limit: int` | `album.get_tracks('some-id', 5)`        |

## User Class 
Album class will let you to find, get and configure your search with users. You have to load `client`. Example given above 

First define user if needed
```py
user = client.user

# or

from spotifyapi.User import User
user = User('some-token')
```

### Functions

| Name           | Params                       | Example                                 |
|----------------|------------------------------|-----------------------------------------|
| get            | `userID: str`                | `user.get('some-id')`                   |

# Support 

So, hey facing troubles? We have some ways you to support you!

- [Discord Support Server](https://discord.gg/FrduEZd)
- [GitHub Repo](https://github.com/spotify-api/spotify-api.py/)
