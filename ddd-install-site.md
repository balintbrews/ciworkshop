---
layout: page
title: Install the Drupal site
permalink: /install-site/
---

The Drush command to install our sample site:
    
{% highlight bash %} 
drush site-install cidrupal --site-name="CI Drupal" --account-pass=admin --db-url="mysql://{user}:{password}@{host}/{database}" -y
{% endhighlight %}
Change the values between the { and } marks.
