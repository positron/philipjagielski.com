---
layout: post
title: "Python: Amazon FPS Example using Boto"
private: true
categories:
- blog
---

Surprisingly, it is impossible to find example code for using Amazon's [Flexible Payments System][fps] (FPS) on the internet.

{% highlight python %}
from boto.fps.connection import FPSConnection

# The connection object can live the lifetime of the server deployment
fpsconn = FPSConnection(host='fps.sandbox.amazonaws.com')

inputs = {
   'paymentReason': 'Buying some stuff!',
   'returnURL': request.host_url + 'secure-return-from-amazon/',
   'pipelineName': 'SingleUse',
   'callerKey': app.config['AWS_ACCESS_KEY_ID'],
   'transactionAmount': purchase.price/100.0,
   'CallerReference': str(purchase.download_id)
}

{% endhighlight %}

# Gotchas
For testing, make sure you use 127.0.0.1, not localhost. FPS "validates" the hostname and for some reason it returns 'Invalid URL' for localhost but 127.0.0.1 is allowed.

# Conclusion
If you've never heard of [Stripe][stripe] go check them out. It took me 5 minutes to have a working payment system set up and integrated with my custom backend. Contrast that to tens of hours I spent poring over the bad AWS documentation just to get a hacky system working. The API 


[fps]: http://aws.amazon.com/fps/
[localhost]: https://forums.aws.amazon.com/thread.jspa?threadID=46061
[stripe]: https://stripe.com/
