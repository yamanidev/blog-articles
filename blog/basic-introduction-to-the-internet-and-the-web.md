---
title: 'Basic Introduction to the Internet and the Web'
description: 'I explain in this article what the internet is, how it works and what happens under the hood when you open a page using your web browser, as well as concepts like IP addresses, DNS, servers and HTTP.'
canonicalUrl: "https://mohamedyamani.com/blog/basic-introduction-to-the-internet-and-the-web/"
pubDate: 2021-07-24
image: "/images/thumbnails/basic-introduction-to-the-internet-and-the-web.jpg"
imageAlt: "earth from outer space"
---

## Table of content

- Introduction
- What is the internet?
- How are computers linked via the internet?
- The journey of data sent between two devices
- How do we surf the web?
- Conclusion

## Introduction

Similarly to electricity, we use the internet on a daily basis without knowing how any of them function behind the scenes.

As a web developer, having a basic understanding of the internet and its different parts gives you more perspective on the environment you're working on, which broadens your knowledge in this field.

## What is the internet?

The internet is a network of networks.

Great, very informative, the hell is a network?

A network is a number of connected devices (computers, phones, or even a smart refrigerator) through Wi-Fi, Bluetooth or cables.

## How are computers linked via the internet?

Since the internet is this vast network; a large number of connected devices…

What kind of connection ensures that every single device is connected to every other device in this network?

The answer is, cables!

Yep, long copper or optical fibers under the seas.

Take a look at this [map](https://www.submarinecablemap.com) that covers all the fibers in the world! Pretty cool.

These cables get taken care of by your country's telephone infrastructure, and get integrated with the phone-line that reaches every house.

Simply put, internet arrives to your doorstep via the phone-line.

Phone-lines transmit light signals, in order to use the internet, these light signals must be converted to electricity via a **modem**, which you connect to via Wi-Fi or Ethernet.

## The journey of data sent between two devices

In order to send data from a device to another, a connection must first be established.

What ensures successful transmission (which means data sent to the right receiver) are pieces of equipment called **routers**. Let's take an example:

**Person A** wants to send a message to **Person B** through the internet.

Upon **Person A** hitting _send_, the message is transmitted via the phone-line to reach a router.

The router receives the data and redirects it to the right receiver (or **Person B** in this case). That's why they're called routers, they define the correct route data goes through.

The router of this example is one of many special interconnected routers that are part of an **ISP** (Short for: _Internet Service Provider_).

An **ISP** is an organization that sells internet, web hosting etc. It takes care of distributing internet and its services.

## How do we surf the web?

We access the web using software called **browsers** which allow us to view websites and navigate through them.

More formally, a browser is a software that reads website documents (_HTML_ and _CSS_ files) and executes its linked scripts -_JavaScript_-

The way you navigate to websites is through the address bar, where you write a website's link (more formally, the **_URL_**):

**URL example**: http://www.facebook.com

- **http**: short for Hyper Text Transfer Protocol which is a set of rules for fetching resources (HTML, CSS, images etc.)
- **www**: the sub-domain
- **facebook**: the domain name
- **com**: the top-level-domain

**Note**:

Usually when we navigate to websites, we omit the **_http_** part of the **_URL_**, and it works just fine because the browser adds it by default when it is missing because it is an essential part of the **_URL_**.

Now that our **_URL_** is typed and we press _Enter_… is where the fun all begins!

Continuing on the **URL** example www.facebook.com

### 1. The browser checks the cache for the DNS record

The browser checks in the cache memory for a previous entry of the domain name (facebook.com) in a **DNS** record.

**DNS** (short for Domain Name System) is a number of **servers** that map each domain name to a corresponding numeric address called **IP address** (short for _Internet Protocol_).

Just bear with me a little!

**Servers** are powerful computers running applications that listen to **_HTTP_** requests from clients (usually browsers) and serve them with resources (or error codes when something goes wrong. For example a missing resource which returns the famous 404 error code).

**IP addresses** are unique numeric addresses given to each and every device connected to the internet.

Writing out (and remembering) *www.facebook.com* is much more easier than 69.63.181.15 (Facebook's IP address). That is why we use **DNS** which stores mappings of domain names to their corresponding IP addresses, exactly like a phone book.

Regressing back to our explanation.

If the browser finds the corresponding IP address of the domain name in cache memory, it sends an HTTP request to the mapped IP address of the domain name.

If the domain name is not in cache, the ISP's DNS server runs a DNS query; searching different DNS servers on the internet to find the given domain name's IP address, jumping from DNS server to another until it finds it!

### 2. The browser sends an HTTP request to the website's server to fetch resources

Upon finding the website's server IP address (thanks to DNS), the browser issues an HTTP request to the server to get the necessary documents of the website, from HTML and CSS files to the web page's images.

The server issues a response and sends back the requested resources, if everything goes well (no errors).

All these resources get rendered (read) by the browser and displayed!

## Conclusion

That was a brief introduction to functioning of the internet and the web. We barely scratched the surface, and made everything seem simple and cozy, it's not the case.

The infrastructure underneath the internet is much more complex than that and is very interesting, we only covered some basics in this article, maybe we will dive into more complex concepts in the future!

## Thank you for reading!

That was it. I hope you learned something new and enjoyed reading!

Follow my blog and my [Twitter](https://twitter.com/yamanidev) for more!

Have a nice one.

---
 
Thumbnail picture by [NASA](https://unsplash.com/@nasa?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) on [Unsplash](https://unsplash.com/photos/photo-of-outer-space-Q1p7bh3SHj8?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)
