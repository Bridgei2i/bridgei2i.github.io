---
layout: post
title:  "Extracting Data from Webpages in Java with help of HtmlUnit"
date:   2015-04-20 16:53:31
categories: Java Crawler
---
The World Wide Web (WWW) is an information system which inter-connects hypertext documents which is usually called as webpages and can be accessed through the internet. The webpage may contain any kind of data from text to multimedia. As per `worldwidewebsize.com` the web contains about `4.56 million` indexed web pages.

Internet plays major role in communication. It is the primary data source for almost 90% of applications and it has about `672 Exabytes (672,000,000,000 Gigabytes)` of accessible data. Following picture shows the data generated per second in internet.

-->> PICTURE

While it is amply clear that enormous data is created on the internet, there is no standard structure being followed in webpages, each one has its own structure so getting data into our application is always a herculean task.

Secondly, while working on market intelligence projects, supplementing predictive analytics models and/or segmentation models with secondary research data on competitor’s market share offers a significant client impact.

But as we all know, secondary research involves sifting and collating data across competitors and across multiple webpages and presenting information in an analysis-ready form. Given that data is stored in thousands of webpages a manual copy-paste effort wouldn’t be a prudent investment of time. So to get the data, we have to dynamically iterate and extract data from those webpages.

Fortunately there is an `API` which allows us to `dynamically process` the webpages in java. In this blog I have explained about how to get (grab) data from websites in java with HtmlUnit API.

# HtmlUnit:
HtmlUnit is an API for java which can simulate a browser. Using this API with java program one can invoke pages, fill out forms, click links, this will work just like a normal browser. HtmlUnit offers the following features

* Support for the HTTP and HTTPS protocols
* Support for cookies
* Ability to specify whether failing responses from the server should throw exceptions or should be returned as pages of the appropriate type (based on content type)
* Support for submit methods POST and GET (as well as HEAD, DELETE)
* Ability to customize the request headers being sent to the server
* Support for HTML responses
* Wrapper for HTML pages that provides easy access to all information contained inside them
* Support for submitting forms
* Support for clicking links
* Support for walking the DOM model of the HTML document
* Proxy server support
* Support for basic and NTLM authentication
* Excellent JavaScript support



Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll’s dedicated Help repository][jekyll-help].

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help