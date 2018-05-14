---
layout: post
title:  "concourse for embedded"
date:   2018-05-14 10:05:09 +0200
categories: ci concourse
---
I recently started investigating concourse as an option for our CI. We are currently using Jenkins but I'm not really happy about it:

* the pipeline view is completely unhelpful
* the groovy syntax for dynamic pipelines create an unmaintainable mess of files
* Jenkins feels too bloated for us

Ok it looks like a lot of *feelings* but hear me out: we are a small team and using Jenkins for our smoke testing and package building feels like using a gigantic hammer to pin a postcard to the wall.

So looking at options I stumbled upon [concourse-ci][https://concourse-ci.org] and quickly fell in love with it: it's simple, very straightforward, written in Go, and focused around Docker. What's not to love?

Well the only issue is the default support for embedded. You see we are working on small microcontrollers and our smoke tests need to run on target. While that may seem alien to most developpers nowadays we cannot run everything in the cloud, and as I mentioned earlier: concourse is *heavily* docker focused.

What does that mean for me? Well I have to find a way to run the concourse worker (the part that actully runs the concourse tasks) on servers with direct access to hardware. Luckily I mentionned concourse is written in Go so it's just a matter of running a compiled version of the worker on a server right? Right?

Not quite but not far. Follow me down the rabbithole!

Jekyll also offers powerful support for code snippets:p

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
