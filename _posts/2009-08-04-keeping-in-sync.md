---
layout: post
title: Keeping in Sync
---

For the past 12 months I have been collocated at a clients site developing an application. The application went live a few months ago and since then I have been working on-site providing support and enhancements a couple of days a week, and the other couple of days a week I have been working back in our company office. Consequently, on any given day I could be working on any one of three computers: my home PC, the clients office, or the company office.

Now this doesn’t cause any issues with source code as this is managed through Team Foundation Server which allows remote access. Also all of my emails and calendar appointments are managed through our corporate exchange server which also allows for remote access. So the big problem is having access to my working documents in all three locations. The solution I have implemented revolves around using <a href="https://www.mesh.com/welcome/default.aspx" target="_blank">Live Mesh</a> to synchronise files between the three computers.

The first thing I needed to do was to clean up and organise the way I stored all of my documents. Previously I would have documents saved to the desktop, under “My Documents”, under project folders on the c drive. I would also have shortcuts all over the desktop, quick launch bars etc trying to help me find where everything was. This was not only confusing, but how was I supposed to be effective at switching from one pc to another and remain productive? In order to make this work, I needed to come up with a clean and simple way to organise documents that would fit not only the work projects, but also home projects that I was working on.

From now all, all of my documents will be stored in a folder called “Davids Documents”. The reason for this is that my home pc is shared with my wife, so I don’t want to put everything directly under “My Documents” so this folder is nested under the “My Documents” folder. Within that folder there are two folders: “Reference Material” and “Working Documents”. “Working Documents” is where I store all working files for currently in-progress tasks, work projects, home projects, currently being investigated research. When documents are no longer working documents, or for longer term projects that I don’t need access to on a daily basis or are no longer active, I put these documents into the “Reference Material” folder. Because my internet plan limits me to 12GB per month and includes uploads, I need to make sure the volume of data I synchronise remains low. For this reason I will only sync the “Working Documents” folder using [Live Mesh]("https://www.mesh.com/welcome/default.aspx"){:target="_blank"}. These files will be the ones I am wanting access to on a daily basis.

Here is what the folder structure looks like:

![My Documents]({{ site.baseurl }}public/images/mydocuments.png){:class="img-responsive"}

As you can see, the “Working Documents” folder has been added as a Live Mesh Folder. The three computers I am syncing all need to have <a href="https://www.mesh.com/welcome/default.aspx" target="_blank">Live Mesh</a> installed and the settings for this folder allow all changes to be captured by all devices.</p>  <p>The other key information that I sync is my favourites. These are all stored in a folder under C:\Documents and Settings\{Username}\Favorites which I simply add as a Live Mesh Folder. Because my username may be different on each computer when I select to sync this folder with each device (computer) I simply specify the location where this folder lives.
