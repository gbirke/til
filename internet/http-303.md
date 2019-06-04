# HTTP 303 is the new 302

According to [Wikipedia](https://en.wikipedia.org/wiki/HTTP_302) the original description of the 302 status code was "Moved Temporarily". Browsers then implemented the standard wrong, changing POST to GET. Newer standards now split the behavior into status 303 (redicrect changing request method to GET) and 307 (keeping the request method). Most programming frameworks still use 302 for backwards compatibility reasons though.

I stumbled upon the 303 status code when reading [article about caching a PHP CMS web page and shop](https://smyck.net/2019/05/25/how-to-cache-your-website/).
