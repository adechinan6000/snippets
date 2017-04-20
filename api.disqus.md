
// comments system api (disqus)
----------------------------------
<div id="disqus_thread"></div>
<script>

/**
*  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
*  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables*/

this.page.url = 'http://example.com/helloworld.html';
this.page.identifier = '2583573';
this.page.title = 'a unique title for each page where Disqus is present';
this.page.category_id = '123456';

var disqus_config = function () {
this.page.url = 'http://laravel-blog.dev/';  // Replace PAGE_URL with your page's canonical URL variable
this.page.identifier = '1'; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
};

(function() { // DON'T EDIT BELOW THIS LINE
var d = document, s = d.createElement('script');
s.src = 'https://laravel-blog-5.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>