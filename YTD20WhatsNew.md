YouTube Direct 2.0 (i.e. any release after `20100422`) represents a substantial rewrite of the 1.0 codebase to allow for easier extensibility and testing. In addition to those backend changes, there are a number of new features that have been added and bugs that have been fixed.

**If you have an existing YouTube Direct 1.0 installation, please read our [migration guide](http://code.google.com/p/youtube-direct/wiki/YTD20Migration) for specific information about the upgrade process.**

## New Functionality: ##

  * Support for secure AuthSub, if properly [configured](GettingStarted#Registering_your_website_for.md).
  * Support for viewing and editing YouTube captions for any video submitted. All caption languages are supported.
  * Support for multiple YouTube Direct uploader embeds (for different assignments) on a single page.
  * Pre- and post-submission text is now configurable on a per-assignment basis with a special ASSIGNMENT\_MESSAGE macro.
  * Users can now select from a pre-populated list of the most recent 50 videos in their account when uploading an existing video.

## Public Issues Resolved: ##

  * [Language other than english in admin->configuration->initial message throws error](http://code.google.com/p/youtube-direct/issues/detail?id=8)
  * [Videos approved before youtube processing completed do not appear in playlist](http://code.google.com/p/youtube-direct/issues/detail?id=15)
  * [Order by date added to feed](http://code.google.com/p/youtube-direct/issues/detail?id=20)