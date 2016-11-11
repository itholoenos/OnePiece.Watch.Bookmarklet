# OnePiece.Watch.Bookmarklet

Add the following link in your bookmarks

```javascript
javascript:(function () {
    var regex = /http:\/\/www\.goodanime\.co\/one-piece-(\d+)-one-piece-(\d+)/;
    var url = window.location.href;

    if (!regex.test(url)) {
        alert('its not onepiece!');
        return;
    }

    var saveConfirmed = confirm('save episode # as watched and go to next?');
    if (saveConfirmed) {
        //save here
        alert('go to next');
    }
    else {
        alert('canceled')
    }
} ());
```
