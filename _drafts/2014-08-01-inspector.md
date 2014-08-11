---
layout: post
title:  "What I learned at Salesforce Part 3: Inspector"
date:   2014-08-01 16:52:17
categories: Salesforce Internship Angular.js
---

### AngularJS

The second app that I worked on was [Inspector][inspector-gh], an app that allows users to create and fill out inspections, for example creating and filling an inspection for a hotel.  This app is where I first started using Angular.js.  Honestly, I think it is one of the GREATEST javascript libraries out there.  The two way data binding is simply amazing, and all the directives just make creating dynamic web pages soooooooo much easier.  It's a library that I can see myself using so much I might become dependent on it to do any web development!

### Safari Form Validation Issue

What I learned through developing this app is that S1 displays visualforce pages through a Safari web view.  Interesting thing is that Safari doesn’t support html5 form validation.  How did I first notice this?  Well I was making form inputs and such and adding required tags to them in my Chrome browser, and when I tried to submit a form with the required fields blank it didn't submit (like it should).

{:.wrap-image}
![roll_call_clear](/pictures/inspector_form.png)

I went on my way and did the rest of the app when finally I tested form submission on the phone.  WHAM THE FORM SUBMITTED EVEN THOUGH THE REQUIRED FIELDS WHERE BLANK WHAT!?!?!?!?  After google searching why this would happen I found that some browers simply don't support html5 validation, and the Safari webview that S1 uses is one of them.  Great thing I found this library called [h5Validate][h5validate] that will do form validations for me.

Lesson Learned: Test on the actual device that the app will run on early on.

h5validate was more for desktops and less for mobile.  It wasn't until I started to test on larger form that I reazlied there is a noticable slowdown on mobile phones.  Even though it isn't ideal, we realized that making our own faster form validation wasn't worth our time because we wanted to get started with Tasky.


[inspector-gh]: https://github.com/chenhoward/salesforce_checklist
[h5validate]:https://github.com/ericelliott/h5Validate