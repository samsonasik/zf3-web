---
layout: post
title: Zend Framework 2.0.0 STABLE Released!
date: 2012-09-06 04:00
update: 2012-09-06 04:00
author: Matthew Weier O'Phinney
url_author: http://mwop.net/
permalink: /blog/zend-framework-2-0-0-stable-released.html
categories:
- blog
- released

---

 The Zend Framework community is pleased to announce the immediate availability of Zend Framework 2.0.0 **STABLE**! Packages and installation instructions are available at:

- [http://framework.zend.com/downloads/latest](/downloads/latest)

 Zend Framework 2 has been years in the making. Version 1.0.0 was released in July 2007 -- over 5 years ago! Since then, we've incrementally added features, building on the solid base we'd created.

 A lot of code has been written on those foundations -- estimates of ZF downloads run anywhere from hundreds of thousands to millions, depending on the statistics you look at. It's been used to build everything from hobbyist websites to powering some of the most visited sites on the web. We've done a lot with Zend Framework 1 over the years.

 We also exposed a lot of cracks in the foundations. Patterns we'd taken for granted, such as Singletons, reared their ugly heads and showed us where we'd built in inflexibility and hard-coded dependencies. We realized that while we'd built a number of interfaces, our code was making assumptions that fell outside those definitions. Some code, while it felt elegant, was difficult to learn, or improperly intermingled different architectural concerns, creating problems where we hadn't had any before.

 Zend Framework 2 aims to build on our experiences with Zend Framework 1, to learn both from our mistakes as well as our successes.

 It's not perfect. No software project is. But I think it's qualitatively _better_. We finally achieved a dream that was conceived in the 0.X days of Zend Framework, to be able to create and consume standalone modules of MVC code. Thanks to the efforts of [Evan Coury](http://blog.evan.pro/), this was made possible via a new component, the [ModuleManager](/manual/2.0/en/modules/zend.module-manager.intro.html), making the process trivially easy. Another problem that plagued ZF1 was how to get dependencies into controllers -- the ZF1 solution of using a singleton (`Zend_Controller_Front`) to get at a registry (`Zend_Application_Bootstrap`) -- was, quite simply, a testing nightmare. Today, via [the ServiceManager](/manual/2.0/en/modules/zend.service-manager.intro.html), or, if you're gutsy, [Zend\\Di](/manual/2.0/en/modules/zend.di.introduction.html), we have standard, testable solutions; we have [Ralph Schindler](http://ralphschindler.com/) to thank for both. Altering the workflow of the application or a single component was often difficult -- the various hooks were either not plentiful enough or difficult to arrange in different configurations. Thanks to the [EventManager](/manual/2.0/en/modules/zend.event-manager.event-manager.html), these use cases are easily resolved.

 The end result is that writing applications is a lot more flexible, and in many cases easier.

 If you've worked significantly with ZF1, ZF2 will look alien to you. That's okay. We'll continue to support ZF1 with bugfixes and security updates for the next 18 to 24 months. But start learning ZF2 -- I think once you do, you'll be amazed and impressed by what you can accomplish. We plan to publish a migration guide in the coming weeks to make your transition simpler, and to encourage you to start utilizing the power of ZF2 sooner.

 I'd go into detail on all the new components, but I don't want to bore you. You can [read the changelog](/changelog/2.0.0), or attend one of the [many upcoming ZF2 webinars](http://www.zend.com/en/company/events/) at zend.com. I'll be [hosting a ZF2 Intro next Wednesday](http://www.zend.com/en/company/news/event/1112_webinar-getting-started-with-zf2) if you want some guidance.

 If you're feeling brave and want to try out ZF2 today, we offer the following resources:

- [Our downloads page](/downloads/latest) details how to get your hands on the source code.
- [Our skeleton application](/downloads/skeleton-app) is a fast way to have a working application that you can start tweaking.
- [Or try out ZF2 on phpcloud](/downloads/phpcloud), which will get you up and running without needing to even start a web server!

 ZF2 has been the project of many people over the last couple years. I'd especially like to call out my team, and the community review team (CR Team) for their efforts:

- Ralph Schindler (Zend)
- Enrico Zimuel (Zend)
- Rob Allen (CR Team)
- Pádraic Brady (CR Team)
- Evan Coury (CR Team)
- Maks3w (CR Team)
- Ryan Mauger (CR Team)
- Dolf Schimmel (CR Team)
- Ben Scholzen (CR Team)

 Take a moment to thank them when you get a chance -- without their efforts, there would not be a ZF2.

 Now, let's go build amazing things!