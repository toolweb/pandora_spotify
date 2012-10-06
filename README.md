Pandora2Spotify
===============

Open a spotify search for the currently playing song in Pandora.

How To
------

Create a new bookmark and paste the following code in the `location` field:

    javascript: if(window.location.hostname == "www.pandora.com"){
      var searchString="spotify:search: track:'" + $('.songTitle').html() + "' AND album:'" + $('.albumTitle').html() + "'";
      location.href= searchString;
    }
    
    
This will generate Spotify URIs (`spotify:` type links) and will only work when Spotify is set to open/handle these type of links in the browser.