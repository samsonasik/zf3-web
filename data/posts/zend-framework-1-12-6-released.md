---
layout: post
title: Zend Framework 1.12.6 Released!
date: 2014-04-15 22:00
update: 2014-04-15 22:00
author: Matthew Weier O'Phinney
url_author: http://mwop.net/
permalink: /blog/zend-framework-1-12-6-released.html
categories:
- blog
- released

---

 The Zend Framework community is pleased to announce the immediate availability of Zend Framework 1.12.6!

- [http://framework.zend.com/downloads/latest#ZF1](/downloads/latest#ZF1)

 This is a maintenance release, and corrects a backwards compatibility break introduced in 1.12.4.

Locale Updates
--------------

 Zend Framework 1.12.4 included an update to the [CLDR](//cldr.unicode.org/) version shipped, bumping to version 24. Our previous CLDR version, however, was version 2.0 or newer -- a version over 3 years old at this point.

 The problem that arose is that [more than two dozen locales have been renamed](https://github.com/akrabat/zf1/blob/0282f49112688f124373bcf915abb6227d050454/library/Zend/Locale.php#L38-L67) in the official CLDR sources since then, and Zend Framework 1.12.4 shipped exactly what CLDR ships. As a result, users of those old locales suddenly found their applications no longer working, due to newly invalid locales.

 We have created some functionality in Zend Framework 1.12.6 to alias old locales to the equivalent new locale string, thus restoring backwards compatibility with versions prior to 1.12.4.

Tag Updates
-----------

 Prior to 1.12.4, we used Subversion for maintaining Zend Framework 1, and thus for tagging releases. Tags in Subversion, however, are branches, not snapshots, and our build process at the time took advantage of that fact, for better or for worse: we would build the documentation, and then replace the documentation sources with the built artifacts; we would inject the ZF1 Extras repository; and we would inject the Dojo repository. As a result, the tag was not a 1:1 snapshot of the trunk at the time, but rather the result of a build process.

 This meant that if a user was using svn:externals and pinned to a tag, they would have the equivalent of our distribution packages -- in other words, access to the ZF1 Extras, Dojo, and documentation.

 With the [migration to Git a year ago](http://framework.zend.com/blog/2013-03-27-zf1-git-migration.html), our build processes needed to change. Git does true tags: a tag is a snapshot of the branch at the revision when it was tagged. The result is that tags no longer contain the ZF1 Extras or documentation. Several users contacted us indicating this broke apps in which they were using svn:externals.

 We have decided we will _not_ be returning to the previous tagging methodology, as we much prefer keeping a separation between tags and the build artifacts. For those users who want to retain the same semantic structure of having the ZF1 Extras imported via svn:externals within the ZF1 library, you can still do that, by adding an additional line to your svn:externals property:

 
    vendor/ZendFramework https://github.com/zendframework/zf1/tags/{VERSION}
    vendor/ZendFramework/extras https://github.com/zendframework/zf1-extras/tags/{VERSION}


 (Modify the above to reflect your own project structure, and to inject the appropriate version string.)

Thank You!
----------

 As always, I'd like to thank the many contributors who made this release possible! In particular, Rob Allen identified the various locales that needed updating, and submitted the locale aliasing solution.