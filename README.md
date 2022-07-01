# Adobe-Launch-Publisher
Create direct links to specific development libs on DEV/Staging envs. Avoids the need to merge and juggle changes on staging and does not require Launch access or Browser Plugins.

Problem:
Adobe Launch only allows one "Staging" lib at a time per environment.  When vendor validation is required, they can only test via staging and at any given time multiple vendors may need to do validation.  So multiple projects get mixed up into the one staging library.  Since it is not possible to precisely schedule 3rd party validation, this pending staging lib is often rebuilt, juggling the various pending projects.  This increases the risk of changes not intended for production being published and adds a significant amount of overhead to Launch development projects. This problem is further exacerbated by Launch's challenges with versioning, aka difficulty with going back in history.

Solutions to date:
Browser plugins, such as Search Discovery's "Launch and DTM Switch" attempt to solve this problem and they work great, internally. However, they require the user to have access to Adobe Launch in order to work, which doesn't work for 3rd party vendors.

Our Solution:
We propose to make a library switcher which doesn't require launch access or a browser plugin. As a result it will work for all browsers and devices.  This will make it possible to keep all projects entirely separate from each other within Launch, until they are ready to publish to production.

Solution Overview:
Adobe Launch has an extensive API. It was part of its original design/architecture.  We will use that API to get the list of Launch development libraries that are pending (pre-staging) at any given time and choose which of those to load on the site based on user input.

This option will only be available on development environments and only to vendors who receive a link from us to activate the feature. We can provide links to vendors or QA that are specific to a certain change and not allow other changes or libraries to be revealed.
