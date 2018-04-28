---
layout: post
title: Jsonp in 5 minute
category: Web前端
keywords: JsonP
date: 2018-04-28 16:09:02
---

## Before Reading

1.  What you can learn after reading this article?

* Determine whether you should use jsonp
* Understand what is JSONP
* Understand how to make cross domain request using JSONP
* Extra of jsonp related issues

2.  How much time you will use for reading this article?
    40 minutes for reading and 1 hour for practice.

## Jeff is creating a online phone book

Jeff is a software engineer who loves his community,he notice that so many new immigrates don't know how to contact proper social worker or organization to get help.
Therefore,he intend to create a online phone book which contains such phone number via api.He is evaluating his requirement and technology to do this.

## Whether I should use jsonp?

<div class="minipic-container">
<img class="minipic" src="/blog_accessary/writing_common_accessary/decision.jpg" />
<div class="minitext-container">
<div class="minipic-title">Communication technique decision</div><br />
<div class="minipic-content">Cross domain request in client side need jsonp</div>
</div>
</div>
The AJAX(XMLHttpRequest) don't allow cross domain request(same origin policy).Therefore,we use jsonp to undergo cross domain request(allow cross domain request)
For example,the contact numbers which comes from different domain from different organization so jsonp need to be used.
And Jeff knows that he is going to use jsonp but he need to know what is jsonp in order to implement it correctly.

## What is jsonp?

### JSONP mechanism

For the

```
<script src="url"></script>
```

The browser will download the javascript file based on url **no matter the url is same domain or cross domain**.Then the browser will evaluate(run) the javascript file.

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
    <head>
        <title></title>
        <script type="text/javascript" src="/blog_accessary/jsonp/basic/remote.js"></script>
    </head>
    <body>
    </body>
</html>
```

<a href="/blog_accessary/jsonp/basic/local.html" download>Example file</a>
It is the fundamental property of browser which utilized by jsonp.

Moreover,the javascript can create the load the script to be loaded dynamically like

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
        "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
    <head>
        <title></title>
        <script>
            var url = "/blog_accessary/jsonp/advanced/remote.js";
            var script = document.createElement('script');
            script.setAttribute('src', url);
            document.getElementsByTagName('head')[0].appendChild(script);
        </script>
    </head>
    <body>
    </body>
</html>
```

<a href="/blog_accessary/jsonp/advanced/local.html" download>Example file</a>

### Jsonp component

The jsonp file will contain the message(usually in json format but not necessary) with a wrapper function **(which defined in local file)**.For example:

```
wrapper({"Name": "Police", "Id": 1, "PhoneNumber": 67221234});
```

After the loading this jsonp file using the script,when the browser evaluate the jsonp file,the jsonp file **call the wrapper function**,therefore the remote data of jsonp is **passed** to local file(due to the function is defined in local file).

Now Jeff knows what is jsonp now,he is going the build his online phone book now.

## How to make cross domain request using jsonp?

Here are three jsonp file
Hospital:

```
jsonPFileLoadedHandler({"Name": "Hospital", "Id": 1, "PhoneNumber": 63221234});
```

Police:

```
jsonPFileLoadedHandler({"Name": "Police", "Id": 2, "PhoneNumber": 67221434});
```

Library:

```
jsonPFileLoadedHandler({"Name": "Library", "Id": 3, "PhoneNumber": 67221224});
```

Local:

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
        "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
    <head>
        <title></title>
        <script src="//blog_accessary/jquery.js"></script>
        <script>
            var jsonPFileLoadedHandler = function (data) {
                console.log(data);
                $("#phones").append("<li>" +data.Id+" . " +data.Name + "("+data.PhoneNumber+ ")</li>");
            };
        </script>
    </head>
    <body>
        <ul id="phones"><li>first</li></ul>
    </body>
    <script type="text/javascript" src="/blog_accessary/jsonp/community/hospital.js"></script>
    <script type="text/javascript" src="/blog_accessary/jsonp/community/police.js"></script>
    <script type="text/javascript" src="/blog_accessary/jsonp/community/library.js"></script>
</html>
```

Result:
![ ](/blog_accessary/blog_images/jsonp/1.png)

<a href="/blog_accessary/jsonp/community/community.zip" download>Example</a>

As we can see that the wrapper function is not important(the important thing is the transmission of data and the evaluation(calling process)),therefore,
In **official jsonp format**,the wrapper function name is defined in the url,for example

```html
/blog_accessary/jsonp/community/hospital.js?callback=jsonPFileLoadedHandler
```

Then the server side will change to proper wrapper according to the callback name.

## Metaphore

In jsonp just like government department sending a US-Citizens(**jsonp provider**) with department name(**wrapper function**) and the people will write their opinion(**message in wrapper function**).The government will wait and receive until the citizen finish writing their opinion.

## Pros and Cons of jsonp

1.  Risk:
    https://en.wikipedia.org/wiki/JSONP

2.  JQuery implementation:
    http://stackoverflow.com/questions/5943630/basic-example-of-using-ajax-with-jsonp
    \*\*Although jquery put the jsonp in ajax function,it is

## Jeff has finished the phone book

The phone book is completed,the immigrates can use the online phone book to get the phone number of police,hospital and library.
