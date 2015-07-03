# Introduction #
The YouTube Direct platform is designed to run on Google App Engine. App Engine allows you to run applications on top of Google's infrastructure. Follow this guide to deploy your own instance of YTD.

If you are upgrading from a previous release, please familiarize yourself with the latest [release notes](http://code.google.com/p/yaw-project/wiki/ReleaseNotes).

# Details #

## YouTube Direct Getting Started Guide ##

  1. Register an application instance on Google App Engine (GAE)
    * [Sign up for an App Engine account](http://appengine.google.com/)
    * Permission additional Google Account addresses to be administrators of your App Engine instance. You should permission all users who will need to create assignments and moderate submissions, as well as any email addresses that you would like to use as the `From:` address for mails that App Engine sends.
    * [Read the App Engine Java Overview](http://code.google.com/appengine/docs/java/overview.html)
    * (STRONGLY RECOMMENDED) Install Eclipse plugin for GAE [http://code.google.com/eclipse/](http://code.google.com/eclipse/)
  1. Check out most recent tagged release of YTD project source code.
    * List of tagged releases at http://code.google.com/p/yaw-project/source/browse/#svn/tags
    * SVN readonly checkout URL: http://yaw-project.googlecode.com/svn/tags/YYYYMMDD
    * Subclipse (http://subclipse.tigris.org/) makes checking out SVN code into Eclipse straight forward, but any SVN client can be used.
  1. Edit your local copy of the war/WEB-INF/appengine-web.xml file:
    * Replace 

&lt;application&gt;

 with your registered App Engine instance name.
    * Replace 

&lt;version&gt;

 with 1, and increment it as you see fit.
    * Replace com.google.yaw.YTDeveloperKey property with your registered YT Developer Key (get one at [http://code.google.com/apis/youtube/dashboard/](http://code.google.com/apis/youtube/dashboard/))
    * Replace com.google.yaw.YTClientID the unique identifier string of your choice.
    * Deploy YTD using the local development webserver environment that comes with the App Engine SDK. If using Eclipse with the GAE plugin, the default "Run" Eclipse action will do this. The webserver runs at **http://localhost:8080/**.
  1. Build and deploy YTD to your application instance on GAE. Be sure that you have completed step 3 and have the correct App Engine instance name in appengine-web.xml!
  1. Go to the admin panel for YTD by visiting http://APP_ID.appspot.com/admin, where **APP\_ID** is your registered App Engine instance name. You'll need to log in with a Google Account that is set up as an administrator for your App Engine instance.
  1. Go to the "Configuration" tab and make the desired configuration changes. Mouse over the ? icons for descriptions of each option.
    * Make sure that the YouTube account you authenticate as is linked to the Google Account that owns your YouTube Developer Key.
  1. Go to the "Assignments" tab and create a new assignment.
  1. Select the new assignment by highlighting it in the list and click the "Embed Code" button to show the `JavaScript` code to embed the YTD uploader on your page.
    * Make sure that you modify the yaw-embed.js URL to point to the actual path to the file.
    * If your page has an existing `window.onload handler`, add the `yaw.embed()` `JavaScript` code to that instead of creating a new `window.onload`.
  1. Visit the "Submissions" tab to view submitted videos and approve/reject them as desired.
    * In the "Configuration" tab, you can specify an address that will receive mail whenever a new video is submitted.
    * Approved videos will be automatically added to a playlist associated with each assignment (owned by your YouTube account), and depending on your configuration settings, will have their descriptions and tags updated to reflect your approval.