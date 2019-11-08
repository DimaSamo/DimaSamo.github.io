---
layout: post
title:      "Javascript & Rails Project"
date:       2019-09-04 16:21:14 -0400
permalink:  javascript_and_rails_project
---


So for this project I've made an app that allows users to create and attend social events, and being able to view what other members are attending specific events. One of the struggles I had is with model relationships, because users could have their own events (created events) and also having the events that they are attending, so I made an RSVP model and I found a way to have that relationship going like this: 
```
class User < ApplicationRecord
    #Validations
    validates :user_name, presence: true
    validates :user_name, uniqueness: { case_sensitive: false }
    has_secure_password
    #Associations
    has_many :events
    has_many :rsvps
    **has_many :rsvped_events, through: :rsvps, source: :event**
```

After that the rails part was done, and I moved on to Javascript and I basically made API endpoints with my Rails controller letting the information render in a JSON format, and then I used Jquery to show information asynchronously.

All in all it was a pretty fun project to make and I'm happy to go to the next step.
