---
title: "Take-home qualification tasks"
---

We know that working on existing codebases can be daunting, and you
might end up working on a new project anyway, so this year we have some
alternative qualification tasks (we'll add more soon, so come back).

You can still opt for the standard ones (such as fixing issues on
GitHub) --- these are just alternatives that are available.

---

### sway configuration override

sway is a replacement for the popular i3 windows manager in Windows. We care a lot about it because a very successful project from GSoC '22 integrated it in Regolith linux, a ubuntu based distribution that we love.

A configuration option that sway has (and i3 as well) is to include partial configuration files from directories, like this:

File: /etc/regolith/sway/config
```
 ###############################################################################
  # sway Config Partials
  ###############################################################################

  # Include any regolith sway partials
  include /usr/share/regolith/sway/config.d/*

  # Include any user sway partials
  include $HOME/.config/regolith2/sway/config.d/*
```

Note that it first imports the global configuration, then the user configuration, which often overlaps.
We want to add a new directive called include_one that would work like this:
```
include_one $HOME/.config/regolith2/sway/config.d/* /usr/share/regolith/sway/config.d/*
```

Note that both directories are passed to the same include_one. It would include all the files in the first directory and then from the second directory it would only import the files that weren't import before. So if the first directory contains a file called for example, "70_bar" then such file would be skipped when processing the second directory.

### Meetup auto-RVSP

Language: Any Must work in: **Linux**

This task is relatively simple (in theory), but it will help us assess
your code organization abilities.

Write a program for meetup.com that sends an auto-RVSP to specific
groups. For example, suppose you are a member of 7 different Meetup
groups, some of which have very popular events that fill up quickly. You
want to sign up for them as fast as possible to ensure that you get a
spot.

Your program needs take care of authentication, searching for events in
configured groups (not all), and automatically signing up on the user's
behalf in a timely manner. Usage of existing Meetup client libraries is
permitted.

It's OK for your program to be a simple command-line tool that needs to
be run from cron once an hour or something like that.

---
### Export data from MyFitnessPal to Grafana

Language: Any Must work in: Linux (anything server side)

MyFitnessPal is a mobile app used to track food & energy intake,
exercise, and more. It supports CSV data export (e.g. through email) to
facilitate archival, but this style is a bit antiquated for manual
viewing.

A simple website that accepts CSV exports and renders nice visual
representations using Grafana would be much better for users. This
should be feasible to complete in a few days since all of the major
components already exist.

---
### Compile Flutter on Mac

If you have a Mac, prepare distributables for any of our Flutter programs for Mac. 
If it doesn't work, fix it and send a PR.
acon").

---
### Camera with intelligent autozoom in Flutter

Language: Flutter Must work in: Android, iOS (OK if you can just
test in one, but we will test in both and if it doesn't work we'll
send you the debug info so you can fix it).

Write a Flutter app that lets you take pictures of anything and
autozooms to the right size to pick up an object that is in view. For
example: Take a collection of dogs, or cats (there are probably
pretrained models for this, it's up to you to look them up). If your
app is used to take a picture of a dog, then the zoom should be
automatically adjusted to take a picture of the dog in foreground, even
if the dog is a bit far.

It must be fast or the dog will move!
