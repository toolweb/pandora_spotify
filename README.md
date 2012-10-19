Pandora2Spotify
===============

Open a spotify search for the currently playing song in Pandora.

How To
------

Create a new bookmark and paste the following code in the `location` field:

    javascript:function getTrackTitle(){return $(".songTitle").html()}function getAlbumTitle(){return $(".albumTitle").html()}function trimBraces(a){return a.split("(")[0]}if(window.location.hostname=="www.pandora.com"){var strTrackTitle=trimBraces(getTrackTitle());var strAlbumTitle=trimBraces(getAlbumTitle());var searchString="spotify:search: track:'"+strTrackTitle+"' AND album:'"+strAlbumTitle+"'";location.href=searchString}

Non-minified:

    javascript:
    if(window.location.hostname == "www.pandora.com"){
        var strTrackTitle = trimBraces(getTrackTitle());
    	var strAlbumTitle = trimBraces(getAlbumTitle());
    	var searchString="spotify:search: track:'" + strTrackTitle + "' AND album:'" + strAlbumTitle + "'";
    	location.href= searchString;
    }
    
    function getTrackTitle(){
    	return $('.songTitle').html();
    }
    
    function getAlbumTitle(){
    	return $('.albumTitle').html();
    }
    
    function trimBraces(strValue){
    	return strValue.split('(')[0];
    }
    
    
This will generate Spotify URIs (`spotify:` type links) and will only work when Spotify is set to open/handle these type of links in the browser.