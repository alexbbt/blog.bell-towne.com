# Using Google Sheets as a Database

Yes, I really used Google Sheets as a Database, but not for a mission 
critical system, that would be crazy. I will get into how I set this up, but 
first, I should probably explain how we got here.

## I am getting married

> Insert engagement photo here.

I am getting married on August 13th, 2022. As someone who loves web 
development, I of course had to build my own wedding website. Now, I am not 
insane, so I did not build an entire wedding ecommerce based wedding registry, 
but I did want to create my own system for accepting RSVPs from our guests.

Our wedding site needed a couple of features.
 - Easily editable page content.
 - Mobile friendly design
 - Low bandwidth image downloads as well as thumbnails.
 - An RSVP from, including a way to manage the invites.

I want to focus here on the last requirement, the RSVP form, but I may go 
into the other features in future posts.

My fiancé and I decided we needed an easy way for both of us to manage the 
invite list, including which events everyone was invited to. This posed an 
interesting challenge, and being that I started this project in July 2020, I 
had lots of time to think about it.

> Insert covid empty time square photo here.

### The Options

#### Option 1 - Zola

The first and most simple option for this RSVP system is to use an off the 
shelf option from a company like Zola. This would be easy, but I had a lot 
of time on my hands during summer 2020, and I wanted to make something of my 
own, **so this is out**.

#### Option 2 - IMS

I could of course, build an entire IMS (or Invite Management System), but 
that would be a ton of over head for something that we are only using for 
about 4 months from April-June of 2022. I wanted to make something simple, 
easy to update (including from our phones), and requiring very little up keep.
This leads us to my third option.

#### Option 3 - Google Sheets

Google Sheets. This is where we had been organizing our wedding planning 
thus far. It is fairly easy to work with on mobile. My fiancé is very 
comfortable working with it. And best of all, it is running on someone else's 
servers, so there is no database to monitor, maintain, and backup. 

Clearly this is the option I chose, otherwise I would not be writing this. 
Lets get more into why Google Sheets is a great Database, then into how I 
set it up.

---

## Google Sheets is the Ideal Database...

Okay, that's not really true, but if your circumstances are right, it is 
pretty great. In our case, our top priority was not loosing data.

We had no need for low latency. 

The data set was very small, so we did not need any query language since the 
server could fetch the whole table at once. 

We can enforce all business logic in the application, so no need for storage 
layer constraints. 

Lastly, and most importantly, Google Sheets has version control. If any 
person manages to submit a malformed RSVP, and our server actually 
accepts and processes it, and that data ends up overwriting good data in 
the sheet, we can restore a backup or retrieve the missing data with about 3 
clicks. This data security, along with robust server logs, should ensure 
that in the worst case scenario, we can still retrieve every RSVP that was 
submitted.



-----
-----
-----
-----
-----

things to add
- Reverting
- caching
- array columns
- uuid generation
- emails


