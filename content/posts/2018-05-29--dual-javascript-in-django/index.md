---
title: Use javascript ajax requests in django
category: "testimonies"
cover: wade-austin-ellis-672668-unsplash.jpg
author: Lucas McDaniel
---

Sometimes, when executing an event in a django template on click event in the `<a href=` tag,
you want to do more than just execute an `HttpResonse()`.  Sometimes you need the response to go nowhere,
but also without a redirect to the current page because that causes a refresh.  But you might also want to send along
an api request to log some data about that element.  I couldn't find a way to do it in Django, nor could I figure out a
way to not cause a redirect when executing some `reverse()` in the href.  You can execute the api request, but it
will also cause a redirect, or that seems to be the intended pattern in this method.  So, an ajax request to the api
in the `<script></script>` tags.  In addition, any additional JS could be run at this time, such as showing a message to
user.  We can run an alert (or modal) to show new material and make the ajax post to the django url to trigger the method
from the javascript.  You can also pass python values to the JS also in the `<script></script>` tags.  Your two javascript
methods battling it out in a django arena.

![unsplash.com](./wade-austin-ellis-672668-unsplash.jpg)

### Let's get down to the code.

Let's solve this problem. Begin by getting a click event on the target element in the `<script>` tag of the django template.

```javascript
<script>
$('.target-element').on('click', function() {
    console.log('Successfull click event targeted!');
});
</script>
```


### We begin with the script tag, and then insert it into the template.

![test](./33893097-e5a70c34-df5a-11e7-8f5e-40e057626770.png)

