---
layout: post
title: Zend Framework 2.5.1 Released!
date: 2015-06-04 17:30
update: 2015-06-04 17:30
author: Matthew Weier O'Phinney
url_author: http://mwop.net/
permalink: /blog/zend-framework-2-5-1-released.html
categories:
- blog
- released

---

Today we've released Zend Framework 2.5.1!

 To update, use [Composer](https://getcomposer.org):

 
    <pre class="highlight">
    $ composer update zendframework/zendframework


### Changes

 The only issue reported against 2.5.0 was a blocker for many: with the shift to ZF becoming a metapackage, one component, [zend-ldap](https://github.com/zendframework/zend-ldap), had a hard requirement on a specific PHP extension (ext/ldap), meaning that the extension then became a requirement for the entire framework.

 ZF 2.5.1 addresses this by making zend/ldap a [ suggested](https://getcomposer.org/doc/04-schema.md#suggest) component. _This means that the zend-ldap component is no longer installed by default._ If you rely on zend-ldap for your application, you will need to perform the following after upgrading to 2.5.1:

 
    <pre class="highlight">
    $ composer require zendframework/zend-ldap


 The above will add zend-ldap as a requirement to your project, ensuring it is present going forward.

 We also audited all other components for hard dependencies on extensions; no other components did so.