---
layout: essay
type: essay
title: "Final Project Idea"
date: 2019-03-26
labels:
  - Software Engineering
  - Meteor
---

## Overview
The problem: UH Manoa Student Recreation Services offers many activities and classes, including such things as hiking, surfing, yoga and many more.  Unfortunately, students usually are unaware these programs exist, and the signup process requires you to fill out a lengthy form in person for every activity you wish to participate in.

The solution: An application that allows UHM students and faculty to register for classes and signup for email notifications when new classes, possibly matching certain criteria, are added.

## Approach
The application will support browsing a list of activities and classes, allowing for filtering based on interests and dates/days/times offered.

The application has three user roles:
<ul>
  <li>Regular users: search for activities, register for activities, review activities</li>
  <li>Basic admin users: same as regular users, able to add activities, and monitor reviews</li>
  <li>Admin users: same as basic admin users, able to modify activities, and able to add or modify registrants</li>
</ul>

Some possible mockup pages include:
<ul>
  <li>Landing page</li>
  <li>User home page</li>
  <li>Admin home page</li>
  <li>User profile page</li>
  <li>Activities listings page</li>
  <li>Activity details page</li>
  <li>Activity registration page</li>
  <li>Review activity page</li>
</ul>

## Use case ideas
Whether or not the following bullet points list all pages or not, the completed use case should show an end-to-end scenario of using the system:
<ul>
  <li>New user goes to landing page, logs in, sets up profile</li>
  <li>Admin goes to landing page, logs in, edits site</li>
  <li>User goes to landing page, logs in, looks for activities of interest, sets up notifications</li>
  <li>User goes to landing page, logs in, looks for activity of interest, registers for activity</li>
  <li>Admin goes to landing page, logs in, adds or modifies activities</li>
  <li>Admin goes to landing page, logs in, adds or modifies registrants</li>
</ul>

## Beyond the basics
After implementing the basic functionality, here are ideas for more advanced features:
<ul>
  <li>Use UH CAS Login instead of Meteor Login to guarantee that users are UH students or faculty</li>
  <li>A rating/review system for activities</li>
  <li>Map-based interface to indicate where activities take place</li>
  <li>Payment processing (outside the scope of an entry level programing course)</li>
</ul>
