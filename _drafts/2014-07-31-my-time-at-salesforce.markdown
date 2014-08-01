---
layout: post
title:  "What I learned at Salesforce"
date:   2014-07-31 16:43:45
categories: jekyll update
---

I have been an intern at Salesforce since February and it has been a great learning experience.  I remember when I first started my internship I was pretty scared of just being completely incompetent and failing everything that was expected of me.

Lesson #1: You aren’t expected to know everything right off the bat.

People understand it takes time to get spun up on the technologies you are using.  I’m pretty sure your manager wasn’t born knowing all the ins and outs of javascript (or whatever stack you are using), and he/she doesn’t expect you to either.  After all, the whole point of the internship for the intern is for it to be a learning experience.  Anyways I basically learned a ton about building stylish web apps that are optimized for mobile platforms.

The first app I worked on during my time at Salesforce was RollCall, an event management app that allows users to check-in and keep statistics on event attendees.  This app took my team the longest to build due to the fact that we were all students during the time and that it was our first time building a web app on the Salesforce platform.  This is when I first “learned” javascript.  Before my internship my experience in web development was limited to only Ruby on Rails apps, which was great for CRUD operations and I never had to write a single line of javascript.  At that point I had a very naive understanding of it as Java except the only data type is var.  It wasn’t until I was writing a bunch of javascript remoting call to get and pass data from the server that I gained experience in javascript.  At first we were only using vanilla javascript, so editing the DOM I manually created elements and such, so I actually hated it because it just seemed like I was writing really hacky code.  This is where I learned a valuable lesson: Don’t reinvent the wheel.  There are plenty of javascript libraries out there that can easily solve your problems.  I learned the ropes of jQuery in order to edit my DOM and used d3 in order to give a graphical representation of the data gathered from the app.   BUGS I ENCOUNTERED

Also as side not, interning while being a student was pretty hard.  I worked about 20/hrs a week on site, and it was about a 20-30 minute commute.  What also made it worse was I had pretty difficult problem sets on due on Mondays at noon, and since I had to go in on Mondays it meant I had to finish by 8 AM.  This usually meant I didn’t sleep much Sunday nights and I therefore I made up for my sleep deprevation on Tuesdays by sleeping through my classes.  Because I missed Mondays and Tuesdays,  I was already behind for lectures for the rest of the week.  I also got sick alot because of my lack of rest.  This was my own fault my choices.

The second app that I worked on was Inspector, an app that allows users to fill out inspections for various things.  This app is where I first started using Angular.js, and also fell in love with it.  The two way data binding is simply amazing, and all the directives just make dynamic single page web apps much easier to build.  BUG I ENCOUNTERED.  What I learned through this developing this app is that S1 displays visualforce pages through a safari web view.  Interesting thing is that Safari doesn’t support html5 form validation.  That means I though I didn’t have to worry about form validation because all I needed was the required tag on the html element, but it was just chrome stopping me.  That means I had to do my own form validations.  Thankfully someone else fell into this problem way before me and create the h5validation library.  We later realized that the h5validate library wasn’t really meant for a phone, so on larger forms it tends to get noticeably smaller.

The third app we worked on was Tasky, a Project Management app where users can create projects, tasks, and assign collaborators in a project to a task.  In this app we tried to integrate more of the build in S1 views in order to make use of all it has to offer, and just to make it more integrated.  The only problem that came up was after you edited a record through the S1 view the app doesn’t update because to get to the S1 view there aren’t any call backs.  Our workaround was to implement the platforms streaming API.  This allowed our app to listen to changes in the records and update accordingly.  Even though this isn’t mobile optimal it would work.




You'll find this post in your `_posts` directory - edit this post and re-build (or run with the `-w` switch) to see your changes!
To add new posts, simply add a file in the `_posts` directory that follows the convention: YYYY-MM-DD-name-of-post.ext.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll's GitHub repo][jekyll-gh].

[jekyll-gh]: https://github.com/jekyll/jekyll
[jekyll]:    http://jekyllrb.com
