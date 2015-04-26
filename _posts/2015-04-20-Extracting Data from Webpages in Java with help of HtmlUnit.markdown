---
layout: post
title:  "Extracting Data from Webpages in Java with help of HtmlUnit"
date:   2015-04-20 16:53:31
categories: Java Crawler
---
The World Wide Web (WWW) is an information system which inter-connects hypertext documents which is usually called as webpages and can be accessed through the internet. The webpage may contain any kind of data from text to multimedia. As per `worldwidewebsize.com` the web contains about `4.56 million` indexed web pages.

Internet plays major role in communication. It is the primary data source for almost 90% of applications and it has about `672 Exabytes (672,000,000,000 Gigabytes)` of accessible data. Following picture shows the data generated per second in internet.

--> PIC

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

# How To Guide:

#### Step 1:
Create a new java project in eclipse
--> PIC

#### Step 2:
Download the HtmlUnit API from [HtmlUnit's Source](https://sourceforge.net/projects/htmlunit/files/htmlunit) and add the HtmlUnit jar files into project’s build path
-- PIC

#### Step 3:
Create a java class, Here for example I have created `googleRes` class
{% highlight java %}
public class googleRes{
	public static void main(String []args){
	
	}
}
{% endhighlight %}

* __Create and initialize an object for WebClient:__ WebClient is root for HtmlUnit which is used to imitate a client browser. It has a parameterised and non-parameterised constructor. Here I have used single parameter constructor to create a new object by passing `BrowserVersion.CHROME` constant as an argument. By which a new WebClient object has been created to imitate a chrome browser.

{% highlight java %}
public class googleRes{
	public static void main(String[] args) throws FailingHttpStatusCodeException, MalformedURLException, IOException {
		WebClient webClient = new WebClient(BrowserVersion.CHROME);
		
	}
}
{% endhighlight %}

* __Create object for page:__ The WebClient class contains a method called getPage() which is used to fetch a webpage, Return type of getPage() method is HtmlPage. So create an object for HtmlPage and assign it by calling `webClient.getPage()`.The getPage() method requires one argument which is the URL of the webpage you want to fetch.

{% highlight java %}
public class googleRes{
	public static void main(String[] args) throws FailingHttpStatusCodeException, MalformedURLException, IOException {
		WebClient webClient = new WebClient(BrowserVersion.CHROME);
		HtmlPage page = (HtmlPage) webClient.getPage("http://en.wikipedia.org");
	}
}
{% endhighlight %}

HtmlPage object has been created which contains all the data stored in the webpage which you send as URL argument for getPage() method. Now you can play with the HtmlPage object and you can get whatever content your want from the webpage.

__Handling the JavaScript__

Nowadays all website contains javascript in it. Which is used to process or call background function when some event occurs or to show some dynamic advertisement in the page. So if you don’t have to do anything with the javascript then it’s better to turn it off.

Because in the background the javascript will be executed and if it has some internal function call again that will be executed and this process will keep on going which will reduce the performance of your program and will take lot of time to fetch the websites. The WebClient class offers methods to solve this issue by which you can enable/disable the javascript in the webpage.

{% highlight java %}
	webClient.getOptions().setJavaScriptEnabled(false);
{% endhighlight %}

* Getting page contents: HtmlPage class offers two unique methods called asText() & asXml() by which you can get the page’s text content without tag or with tag respectively.

{% highlight java %}
public class googleRes{
	public static void main(String[] args) throws FailingHttpStatusCodeException, MalformedURLException, IOException {
		WebClient webClient = new WebClient(BrowserVersion.CHROME);
		webClient.getOptions().setJavaScriptEnabled(false);
		HtmlPage page = (HtmlPage) webClient.getPage("http://en.wikipedia.org");
		String pageContent=page.asText();
		System.out.println(pageContent);
	}
}
{% endhighlight %}

Here I have used asText() method which will get all the text content from the webpage without any html tag and stored it in string object. When you are printing the string you will get the following result.

# Result:

-->PIC

__Sample Program to find no.of results for list of programming languages:__

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}


__Result__

-->PIC

Note—Based on the program result chart has been created using excel.

__This blog is written by Saddam Hussain, Business Analyst at__ [BRIDGEi2i](https://www.bridgei2i.com)

__About BRIDGEi2i:__ [BRIDGEi2i](https://www.bridgei2i.com) provides Business Analytics Solutions to enterprises globally, enabling them to achieve accelerated business impact harnessing the power of data. Our analytics services and technology solutions enable business managers to consume more meaningful information from big data, generate actionable insights from complex business problems and make data driven decisions across pan-enterprise processes to create sustainable business impact. To know more visit [www.bridgei2i.com](https://www.bridgei2i.com)
