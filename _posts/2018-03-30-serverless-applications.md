---
layout: post
title: Serverless - What Does It Mean?
date:   2018-03-30 14:14:00 +0500
categories: serverless amazon-web-services google-cloud
description: "What does Serverless mean? How will this technology change the web? What are pros and cons?"
cover-img:
  src: "/assets/images/cloud-computing.jpg"
  width: "800"
  height: "350"
  alt: "Serverless cloud computing"
author:
  name: "Ars Potapov"
  photo: "/assets/images/arseniy-round.jpg"
  avatar_class: ars
  email: "arseniy@pypie.com"
  github: "muzhig"
  linkedin: "arseniypotapov"
  bio: "Full-stack Developer & team leader, Python expert, relentless machine learning enthusiast"
  profile: "https://pypie.com/arseniy"
---

> Just like wireless internet has wires somewhere, serverless architectures still have servers somewhere.

What serverless really means is that, you don’t have to think about those servers, they are abstracted away from your process of building an application letting you to focus on what actually provides value to your users. Managing your MySQL servers or upgrading your Linux distro does not provide value to your users. Rolling out your product does. So why not focusing on business logic instead of servers?

Besides many other aspects of serverless approach, like using managed services for everything from databases and search index to email delivery and SMS messaging, there is one that makes serverless stand out: FaaS - Function as a Service. Think of it as a managed service for running your code on cloud without thinking about environment, scale and resourses. Just pure business logic: functions are executed in response to various events your application has to process: from incoming web requests or API calls to scheduled periodic routines and updates on database records or files in storage - you name it, the list of options is almost endless.

### How Serverless App Works

Everytime when an incoming event is received, in matter of milliseconds a new container with your function is initialized, then function handles the event and container dies. You pay only for the time consumed by execution of your function and they don’t block each other: you can have any number of simultaneously executing instances of your function and process stream events in near-real time speed under any load.

[Amazon Lambda](https://aws.amazon.com/lambda/features/ "Amazon Lambda Features"){: rel="nofollow"}, part of [AWS](https://aws.amazon.com/ "Amazon Web Services Cloud"){: rel="nofollow"} - a one-stop shop for web developers, deservedly can be considered a de-facto standard for FaaS.
Other cloud vendors like Google, Microsoft, IBM and IronIO also offer their “Cloud Function” solutions, so implementation details might differ across them.

### Advantages Of Serverless Architecture
Utilization of serverless technologies gives you huge business benefits from the day one, let's list most noticeable of them:

1. **Cost Reduction**
you no more have to maintain fatty servers just to be prepared for your userbase growth or spikes of load. 99% of the time such extra resources are terribly underutilized. Comparing to that serverless architecture lets you have full resource utilization without paying a cent for idle time. Cost-savings over a “regular” cloud VM could be around 90%
1. **Auto-Scaling**
your cloud provider manages the scaling challenges. No load? You don’t pay. Traffic spike? No more a problem, a burst of incoming requests triggers exactly the same amount of functions to handle them. All of them execute simultaneously without competition for resources like CPU or memory. It’s scalabe and fault-tolerant by design.
1. **No Managing**
it’s already managed on micro level. Just deploy code without dealing with infrastructure: there is no concept of a cluster, an instance, or even an operating system, simply nothing to do for sysadmins.
1. **Shorter Time To Market**
The loop between idea and deploying to production is shorter because there is nothing to provision or manage, smaller teams can ship more features.

### Challenges of serverless architecture
It wouldn't be fair to expect a breakthrough technology not to bring it's own challenges, all of them are solvable but worth mentioning:
1. **Deploying Big Applications**
The most granular unit of a serverless app being deployed is not a module, package or service, but a function. Because of that it’s super easy to screw something up during deployment if an app has tens or even hundreds of functions. Deployment process must be polished and support atomic updates for groups of functions and rollbacks. [Serverless Framework](https://serverless.com/framework/ "Serverless Framework"){: rel="nofollow"} is a recommended solution for this problem, it’s a really extensive tool that takes care of deployment process as well.
1. **Vendor Lock-in**
Developing an application for a particular cloud core very quickly becomes tied to that cloud and migration to another one can be nearly impossible without a serious (if not complete) rewriting of backend code. Luckily, Serverless Framework solves this problem as well: it let’s developers define the functions, APIs and events in a cloud-agnostic way. Besides AWS Lambda following FaaS are supported: Google Cloud Platform, Microsoft Azure, and IBM OpenWhisk.
1. **Monitoring and Debugging**
The level of abstraction serverless approach offers plays negative role if you need to debug something, there is no possibility to put a breakpoint or attach a debugger. Your functions must care about monitoring, logging metrics and errors. Handling that definitely will add extra execution time. On the other hand... debugging on production, seriously? A common advice would be setting up an error-logging system from day one, something like [Sentry](https://sentry.io/ "Sentry Error Logging"){: rel="nofollow"} or [Rollbar](https://rollbar.com/ "Rollbar Error Tracking"){: rel="nofollow"} definitely will save a lot of time when s**t hits the fan.
1. **It's Different**
Serverless architecture is completely different from well-known time-proven patterns, so development team needs a shift of mind to adopt the idea and get used to "Serverless" approach. It didn't appear out of nowhere though, micro-services seem to be very close in terms of application architecture, so relevant experience would definitely help.

### Bottom Line
So, what does *Serverless* mean? Personally for me, as a developer, it means staying focused on developing valuable features, deploying often, getting feedback quickly and keeping momentum. This means being sure that environment will provide enough power for scaling without breaking client's bank. This means defining *infrastructure as a code*, spending way less time clicking buttons in cloud's UI.

But what does it mean for You?
Tell your story: [arseniy@pypie.com](mailto:arseniy@pypie.com)
