---
layout: page
title: Get the code
permalink: /get-code/
---

## Build codebase
The Drush Make command to build our codebase:
    
    drush make --working-copy --no-gitinfofile platform.make web
    
This will run *platform.make*, which downloads our profile and recursively runs the makefile that is found in the profile's repository.

## Copy the code to a pre-configured webroot

We need to save the *sites* folder before we override it with the newly built code. It contains the *settings.php*, the *files* folder etc. Here is some help to quickly save the valuable part:
    
{% highlight bash %} 
if [ -d web ]; then
  mv web web-old
fi
{% endhighlight %}
    
Then, when we have the newly built *web* folder in place:

{% highlight bash %} 
if [ -d web-old ]; then
  rm -rf web-old/sites/all
  mv web/sites/all web-old/sites/.
  rm -rf web/sites
  mv web-old/sites web/sites
  rm -rf web-old
fi
{% endhighlight %}

