---
layout: post
title:  "Ember Hot Seat Episode 017: Jo Liss"
author: Ember Hot Seat
comments: true
duration: 25:46
file: ep017
length: 12368792
excerpt: "This week in the Hot Seat we have Jo Liss of Broccoli fame. Hear us chat about the Broccoli build tool, the importance of tooling, and getting involved open source!"
date: 2014-06-02
---

Hey Embereños!

This week in the Hot Seat we have Jo Liss of Broccoli fame. Hear us chat about the Broccoli build tool, the importance of tooling, and getting involved open source! Jo was gracious enough to get this episode transcribed for the listeners. I think that's something I'm going to start doing going forward. Hope you enjoy! And as always, if you'd like to come on the Hot Seat, please feel free to ping me at <dbrown@zendesk.com> or on [Twitter](https://twitter.com/emberhotseat).

<iframe width="100%" height="166" scrolling="no" frameborder="no" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/152465656&amp;color=ff5500&amp;auto_play=false&amp;hide_related=false&amp;show_artwork=true&amp;show_comments=true&amp;show_user=true&amp;show_reposts=false"> </iframe>


**DeVaris P. Brown:** All right, welcome everyone. It is a Saturday morning here for me. I'm working hard for you guys to make sure that you have the content that you want, and another highly requested person for the Hot Seat is here today. Everyone, welcome Jo Liss to the Hot Seat. Say hello to the world, Jo.

**Jo Liss:** Hi, everyone. Hi, DeVaris. Thanks for having me on your podcast.

**DeVaris:** No worries. Thank you for coming on. I know we've been playing, I guess, Twitter-tag back and forth, but it's good to have you on the show.

**Jo:** Finally, yeah. I'm excited.

**DeVaris:** Yeah. Now, I guess, give the people a little bit of an introduction to who you are, and what you do kind of thing.

**Jo:** Yeah, sure. So, I guess most people know me from my open-source work in the front-end JavaScript space. I spent a couple months working on a tool called Broccoli, which is for building client-side JavaScript apps mostly. So, if you have used the Rails asset pipeline before, Broccoli is sort of like that except it's back-end independent and the architecture is a bit more modern, I guess. And for my day job I run a solitaire site which is ad monetized, and that's starting to pay the rent.

**DeVaris:** Oh, wow.

**Jo:** Yeah, that's like officially my full-time business now.

**DeVaris:** You said solitaire, right? Like the card game that came with Windows that everyone plays?

**Jo:** Exactly, exactly. It's an HTML5 solitaire, so it's right there in the browser. And you wouldn't believe how much search traffic there is for solitaire, it's ludicrous.

**DeVaris:** Huh. So what's the URL so we can go ahead and get that out there so everybody -

**Jo:** Sure. It's [solitr.com](http://www.solitr.com/).

**DeVaris:** Okay. Well, everyone knows that you can re-purpose games.

**Jo:** Very much. There's no copyright on it.

**DeVaris:** Oh, wow. Wow, that is amazing. Okay. So, yeah, everyone knows you from Broccoli nowadays, but when I first saw you, you were pretty much the testing expert. And we probably won't get into this too much, but is there a preferred testing route that you choose, or is it just, or do you have an opinion on the state of testing so far in Ember?

**Jo:** So, I think the new ember-testing package seem really good to me. I have not actually had a chance to use it because right now I don't have a single Ember app that I'm working on.

**DeVaris:** Okay.

**Jo:** So, I'm really behind on all the testing stuff and so I haven't had a chance to play with it.

**DeVaris:** Okay. Now, you're also, and I had Robert Jackson on last week so I got to make sure I ask you about tooling and stuff like that. Like you said before, you're responsible for Broccoli, and a lot of the feedback that I see in the community is which route is going to be blessed? Which set of toolings, which packaging is going to be the one? So I guess, kind of give people the benefits of using Broccoli versus Ember tools, or Ember App Kit, or things like that.

**Jo:** So, Broccoli is a very low-level build tool, and so the way it fits into the ecosystem is, we've been kind of using [Grunt](http://gruntjs.com/) and Grunt is a task-runner. It's not really a build tool, so if you use Grunt for building apps, then as your app grows it's going to be slower and slower. So what I've seen with medium-sized teams, just like 5, 6 developers working on an app for a couple of months, and as the code base grows, the rebuild time gets to like 10, 15 seconds. And that is clearly unacceptable, right? Like you edit a file, and then you reload the browser, and there's a 10-second delay, and that really affects your productivity, having a delay like that in your core feedback loop as a developer. So Broccoli is a dedicated build tool sort of like the Rails asset pipeline, as I said, and it plugs into Grunt, or you can plug it into other tools, as well. And the stuff that is coming up with [Ember CLI](https://github.com/stefanpenner/ember-cli) (the successor of Ember App Kit) that is based on Broccoli now.

**DeVaris:** Oh, okay.

**Jo:** So, Ember App Kit was Grunt-based, but Ember CLI is based on Broccoli now, and Robert has actually been working on migrating the build process for Ember itself to Broccoli, which I think is very cool. And for me that's kind of the really, the acid test for Broccoli to see if it holds up compiling a complex library like Ember.

**DeVaris:** Okay. Now look at that community collaboration. So, but what ended up getting you involved with Ember? Like what drew you to the community? And you were pretty prolific in the Rails community as well, so what kind of drew you to start contributing to the community as much as you did?

**Jo:** So I originally started working on a Rails app, a voting software app for universities, and the business never took off, but I was working on this Rails app, and I thought it would be great to have a good UI for that because it's a really hard problem that needs a good UI. And I started doing kind of Ajax stuff with Rails and it pretty soon turned into a spaghetti mess. And then that was around the time Backbone came out, so I switched to Backbone and I used that for a while, and then I thought, well this is not going to scale either, like it is better, but it has a different set of problems now. And then I switched to Ember. And Ember, for like the first time, I was like, "Oh yes, this thing actually solves the problem correctly, like of binding data into the UI into the HTML and keeping it updated." So that's what got me into Ember, sort of the realization that it was really the correct tool for the job.

**DeVaris:** Okay. And then now, like I said, you contribute pretty heavily to tools and things. So what, I guess, what motivates you to participate in the community as much as you do and build these tools that pretty much everyone uses?

**Jo:** So, the way I look at it is-- actually let me back up a step. So, I kind of, I've been programming when I was young, and I had a job between high school and university, and I was doing like C++ and Python stuff and just kind of messing around with code. And then like in late 2000s I was building my first Rails app, and I was like, "Wow, I'm incredibly productive right now". And I had actually taken time off of writing code, but like I came back and picked up Rails, and all of a sudden I was ridiculously productive. And so without doing anything, my productivity had increased. And that was kind of this turning point for me when I realized that if you want to be a great developer, it's not so much about your own ability to write code, but it's about the tools that you use. And in the webspace, most of these tools are open-source, thankfully, right? It's not like .NET where you have all these proprietary libraries. And so, clearly if you want to be a good developer, you should try always finding the best tools for the job. But the best developers are clearly the ones that *wrote* the tools, like DHH, like, those are developers like you and me. They wrote the-- He started Rails, and clearly he is a great developer now because he wrote the tool. And so I sort of approached my career with that notion that I should not just try to use good tools, but I should also *produce* tools.

**DeVaris:** Hmm, okay.

**Jo:** Work on the tooling.

**DeVaris:** That's a very good perspective. And that's one of the things that as web development and JavaScript gets more popular, that people that are coming from these closed backgrounds like .NET are asking for the same type of tool-set, and see it getting there with certain IDEs and things like that, but definitely like the low-level tools that you create are useful, yeah.

**Jo:** Yeah, and I think, so I definitely think that just the libraries that we use for our production apps are clearly important, like active record on the back-end side, or Ember on the front-end side, what have you. But production code is not everything, right? And a lot of the code that we use is actually not going to run in production, but it's still very, very important. So to give you an example actually, I recorded myself making a tiny library for NPM a while back, and so I kind of looked at the time breakdown, like what did I actually spend time on doing. And so reviewing these screen recordings of myself making the library, it turns out I spent like 90 minutes on the whole thing and 15 minutes were writing the actual production library code, and then there was 20 minutes writing documentation, and another 25 minutes writing tests. And I spent 10 minutes packaging up the whole thing and then doing some bookkeeping. And also like another 20 minutes or something on Twitter and IRC, just sort of bouncing things off of people and trying to figure out what the right approach was and how to get some edge cases right. So, less than a fifth of the time was actually spent writing the production code. And I think that kind of illustrates how important it is that we focus really on the whole tool chain that we use as developers. The whole, like our complete workflows, and not just the parts that are obviously production code.

**DeVaris:** Yeah, I definitely think that's a good perspective. It's interesting that you recorded yourself while you were programming, I mean, for the project. I suspect that if I were to do that, you probably wouldn't see me on Twitter and IRC. I'd probably be like on Facebook, and then like Hacker News, and all types of other things in the middle.

**Jo:** It's funny. When you record yourself you actually become a bit more disciplined because you don't want to be embarrassed, right?

**DeVaris:** Yeah, that is true. That is very true. I mean, maybe some employer now is going to listen to this and going to try that, so I think we've let the cat out of the box.

**Jo:** Yeah, I think I actually spend way too much time on Twitter and Hacker News, and much of it is not productive, yeah.

**DeVaris:** Yeah, so what are the projects that you're working on in the future, or that are going to released soon, or what are the open-source projects that you see in the community that have a lot of promise?

**Jo:** I don't know right now.

**DeVaris:** Okay.

**Jo:** So, I don't have anything in the pipeline coming up. So basically, I took several months off to work on Broccoli where I really just dedicated full-time work to it, and now I have to get back to some other stuff that will result in money.

**DeVaris:** Oh, okay. All right.

**Jo:** Right. Because I have to pay the rent. But I guess, like what I'm doing now is working part-time on Broccoli and pushing the plugin ecosystem forward, and there's obviously some really exciting stuff in the Ember ecosystem coming up. I haven't been following very closely, but I'm really excited about HTMLBars, and I think it's going to really change the way we write applications and that we can write, at some point we'll hopefully be able to write components, and not just entire apps. So I think my general plan is to work on my own stuff and figure out what other things bottleneck me now, now that I have a build tool. And then a year from now I'll identify another thing where there is low-hanging fruit, where if we can solve a problem well, we can gain productivity again.

**DeVaris:** Right. That seems to be very good approach. And if anybody out there wants to help Jo pay the rent, you probably can contact her, obviously on Twitter, right? She's there in IRC.

**Jo:** Yes. Twitter and IRC.

**DeVaris:** That's pretty cool. All right, so, can you give us a little bit of a history about like how Broccoli came to be? I know you said that at the time there were some tools that were getting developed and most of them were Grunt based, but what was the thought process and how did Broccoli become something that, what was your approach behind it? Yeah, so, talk a little bit about that.

**Jo:** Yeah, so originally I started thinking about this kind of problem space, I guess at last year's Ember conference, and the thing that was bothering me most was the lack of package management, sort of like Ruby Gems on the back-end side, or NPM for back-end JavaScript. And it turned out pretty quickly, as I started talking to people, that the package manager was not really the missing piece, but it was something sitting on top of a package manager that can tie all the files together, that tells you what to do with the files. So I think we have Bower as a pretty good package manager and that'll be fine, but we need a tool like Broccoli sitting on top of it. And so at first I was really just like, I started talking to people about the problem and kind of exploring the problem space and trying to understand better what we needed to solve this. And a lot people very graciously kind of humored me and talked to me about this and spent time with me, even though I had no code at all to show for it. It was just all in my head, I guess. And then I, in the summer of 2013, I went to 5 different conferences and I kind of kept pitching this idea of a build tool at people and trying to figure like, is my approach the right one? Like, what kind of problems do we need to solve? And so that way I kind of iterated on the solution. And this whole process really, really drove home to me how important community is for making open-source software. Like, if you look at git-blame, it's all me on Broccoli, basically. It's mostly, I wrote the code, but it really synthesizes a lot of community knowledge about building. There were some very crucial insights that I got that I would've never gotten on my own, that came out of these conversations that happened in 2013. And even in 2014, I was on a conference call with several build-tool maintainers and we kind of chatted about, like, the challenges of how to design APIs for build tools and that kind of stuff. And some really important insights came out of that conversation as well, and really shaped what the Broccoli API looks like now. So I guess in a way, I kind of had this abstract notion that, yeah, programming is not just a solitary activity, but it's about other people as well. But actually doing, writing Broccoli, actually going through this whole process really drove home to me like how important it is that we hang out together, that we talk a lot. And I think the time that we spend on Twitter talking about technical problems, sometimes it's just procrastination, right, but it is also like a really important part of the development process.

**DeVaris:** No, I definitely agree. And I think that the collaboration and having people that you can, well intelligent people, and sometimes not intelligent, but people that aren't aware of the problem space, will bounce some problems off of them so that you can get perspective to help on a direction when you're kind of not sure you're sure, but you're not really clear about, is extremely helpful.

**Jo:** Exactly.

**DeVaris:** Yeah, so, quick question. How did you come up with name Broccoli?

**Jo:** It's stands for browser compilation library.

**DeVaris:** Wow.

**Jo:** I am very proud of that.

**DeVaris:** Yeah, I would be too. Wow, that is very applicable.

**Jo:** Right, isn't it.

**DeVaris:** Yeah, so how can people get involved with, or how do people, you said you were hoping to build out the Broccoli plugin components to Broccoli. Like, how do you suggest people start building plugins for that? Or what are the things that, I guess, are things that people have tried to ask for as part of, that should be included in the standard Broccoli package that you see more of as a plugin?

**Jo:** So there are several things that I think we need to work on. Obviously we want more plugins. And the biggest problem for writing plugins is always getting the performance right. So when you have, when you map input files one-to-one into output files like CoffeeScript where you have a .coffee file and you have .js file coming out. Getting the performance right for that is very easy because you know exactly when you have to rebuild a file. But for more complicated cases like Sass where one input file can import another input file, and that in turn can include another input file, it's much trickier to figure out when you need to rebuild a given file. And I don't think we've really figured that out really well, and it's kind of inherent to this problem of building apps fast. So I think we will need more brainpower on that problem. In particular from, not just from people who work on build tools, but also from people working on the compilers themselves. Like Sass and LESS and these kinds of tools. Another thing that we're working on is coming with a kind of default stack of tools. So that's what Ember CLI is trying to do, and I have kind of come to realize that Broccoli is-- I'm pretty confident about the architecture, but it's a little bit too low-level of t a kind of people to just get started with it very easily, right? Like, it's a bit confusing to use. And I think the fundamental problem is that it provides a very low-level abstraction of what you're actually trying to do. And the Rails asset pipeline kind of falls on the other extreme of the spectrum. It doesn't give you any way to customize what you're doing, but you can very easily add plugins to it and new file formats just by putting them in your Jam file. So what I think what we are going to have to do eventually is come up with a sensible abstraction layer on top of Broccoli that give you a little less flexibility than Broccoli, but that makes it easier for people to get started to plug in new plugins into their build pipeline.

**DeVaris:** Yeah, I think that definitely would be helpful. So if anybody out there is having some pains with Broccoli and the configuration and things like that, you're more than welcome to submit a pull request to the, what is the GitHub repo address, Jo?

**Jo:** It's, so for Broccoli itself it's [joliss/broccoli](https://github.com/broccolijs/broccoli), but I think also a really good place to discuss these things is the #ember-cli channel on Freenode.

**DeVaris:** Okay.

**Jo:** And a lot of people that care about the kind of tooling that we're building on top of Broccoli hang out in that channel.

**DeVaris:** Cool. Well, Jo, I won't keep you, but I really do appreciate you coming on the Hot Seat. It's been a pleasure. I feel smarter already. Thank you so very much.

**Jo:** Thanks for having me.

**DeVaris:** No problem. So where can the people find you on the internets?

**Jo:** It's [@jo_liss](https://twitter.com/jo_liss) on Twitter, and I guess joliss on IRC.

**DeVaris:** Okay.

**Jo:** And [joliss42@gmail.com](mailto:joliss42@gmail.com) if you want to email me or IM me. I'm very happy for people to add me on IM as well.

**DeVaris:** Okay. And one more time for the solitaire website. I got to check this out by the way, this is crazy.

**Jo:** It's [solitr.com](http://www.solitr.com/) and it's a super-simple business. It's like less than 1000 lines of code.

**DeVaris:** Okay.

**Jo:** So I'm really proud of how unambitious it is.

**DeVaris:** Well I'm happy that that is working out for you. And again, thank you so very much. It's been a pleasure and I'm really, really glad that I finally got you on the show.

**Jo:** Thank you, DeVaris.

**DeVaris:** Have a wonderful rest of the day

**Jo:** Thanks, you too.

**DeVaris:** All right.