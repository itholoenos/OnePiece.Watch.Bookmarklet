# OnePiece.Watch.Bookmarklet

## Installation

1. Create a folder `One Piece` in your bookmarks
2. Create a subfolder `Backup` to manually save watched episodes. If you clear browser's memory/cache etc. you may loose what's watched!
3. Create a link named `Mark as watched and go to next` and paste the following code as URL

    ```javascript
    javascript: (function() {
        var urlTemplate = "http://www.goodanime.co/one-piece-[NUM]";

        var regex = /one-piece-(\d+)/;

        var url = window.location.href;
        if (!regex.test(url))
            return;

        var matches = url.match(regex);
        var episode = matches[1];

        var saveConfirmed = confirm('save episode ' + episode + ' as watched and go to next?');
        if (saveConfirmed) {
            window.localStorage.setItem('lastWatched', url);

            var nextEpisodeUrl = urlTemplate.replace("[NUM]", ++episode);
            window.top.location = nextEpisodeUrl;
        }
    }());
    ```
    
4. Create a linked named `Go to next unwatched` and paste the following code as url

    ```javascript
    javascript:(function () {
        var urlTemplate = "http://www.goodanime.co/one-piece-[NUM]";

        var regex = /one-piece-(\d+)/;

        var lastWatchedUrl = window.localStorage.getItem('lastWatched');

        var matches = lastWatchedUrl.match(regex);
        var episode = matches[1];

        var nextEpisodeUrl = urlTemplate.replace("[NUM]", ++episode);

        window.top.location = nextEpisodeUrl;
    } ());
    ```
