---
layout: post
title: Keeping in Sync – Part 2
---
Following on from my previous post on [Keeping in Sync]({{ site.baseurl }}{% link _posts/2009-08-04-keeping-in-sync.md %}), I wanted to discuss how I keep the rest of my files synced between my three working computers. As I mentioned in the last post, Live Mesh is used to sync my working documents which includes my OneNote notebooks and currently active project documents, however due to the size restriction of Live Mesh as well as the restriction in my Internet Service Provider limit there are many documents that I cannot sync using Live Mesh. To solve this, I am using Microsoft <a href="http://www.microsoft.com/downloads/details.aspx?familyid=c26efa36-98e0-4ee9-a7c5-98d0592d8c52&amp;displaylang=en" target="_blank">SyncToy</a> as my way of keeping them synchronised.

The files I like to keep synced between the computers include documents from non current projects or source code from old projects. I also have a collection of essential software such as system utilities, debugging tools, freeware desktop applications, development tools and SDKs. Finally I have a load of learning material including labs, video tutorials and eBooks.

The solution to keeping these files synchronised between three different PCS is, firstly each computer (Home, Work and Client) has an external USB drive. I have this mapped in all locations as X:. Next, I have a USB passport drive that comes with me everywhere. This is mapped as the Y: drive on all machines. There is no particular reason for my letter selection except that I wanted to use drive letters that were not already taken as part of group policy in my work, or client domains. I also wanted to use the same letters in all three locations so I could script the sync function and use the same scripts in all locations. Next I need to setup <a href="http://www.microsoft.com/downloads/details.aspx?familyid=c26efa36-98e0-4ee9-a7c5-98d0592d8c52&amp;displaylang=en" target="_blank">SyncToy</a>. There are essentially three directories that I will be syncing: 
1) Reference Material; 
2) Essentials; and 
3) Learning. 

The process of setting up is as follows:

- Launch <a href="http://www.microsoft.com/downloads/details.aspx?familyid=c26efa36-98e0-4ee9-a7c5-98d0592d8c52&amp;displaylang=en" target="_blank">SyncToy</a>
- Create a folder pair. The first folder pair I have created is between “My Documents\Davids Documents\Reference Material “ to “Y:\Davids Documents\Reference Material”

![Clip1]({{ site.baseurl }}public/images/clip_image001_thumb.png){:class="img-responsive"}

- Select the syncing option. For all of these folder pairs, I will be using Synchronize


![Clip2]({{ site.baseurl }}public/images/clip_image0016.png){:class="img-responsive"}

- Name the folder pair. This pair I will name “Sync_ReferenceMaterial”

![Clip2]({{ site.baseurl }}public/images/clip_image0018.png){:class="img-responsive"}

- Finish. 

I repeat this process for the other folder pairs: 
- Essentials:
  - Folder Pair: “Y:\Essentials“ to “X:\Essentials”
  - Name: “Sync_Essentials”
- Learning:
  - Folder Pair: “Y:\Learning” to “X:\Learning”
  - Name: “Sync_Learing”

When all the folder pairs have been created, select to “Preview All”. This will compare all files between the folder pairs and make a list of changes required. Prior to setting this up, I had different version of each of the folder pairs but I went through a clean up operation and made the passport drive (Y:) the master copy of all data. I then manually copied this to the paired locations so running the preview the first time showed no differences.

## Automating the Process

Rather than manually having to run the synchronisation process, <a href="http://www.microsoft.com/downloads/details.aspx?familyid=c26efa36-98e0-4ee9-a7c5-98d0592d8c52&amp;displaylang=en" target="_blank">SyncToy</a> includes a command line utility which allows us to automate the process. The command line utility is called SyncToyCmd and its options are as follows:

<blockquote>   <p>Usage:&#160;&#160;&#160;&#160; SyncToyCmd [-args]      <br />All arguments are optional.       <br />&#160;&#160; -R&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160; Run all folder pairs that are marked as Active for Run All.       <br />&#160;&#160; -R <span class="kwrd">&lt;</span><span class="html">name</span><span class="kwrd">&gt;</span>&#160;&#160;&#160; Run the named folder pair (only one folder pair can be specified).       <br />&#160;&#160; -?&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160; Display this help.       <br />      <br />Examples:       <br />&#160;&#160; SyncToyCmd -R MyFolderPair       <br />&#160;&#160; SyncToyCmd -R</p> 
</blockquote>  <p>&#160;</p>

We could therefore create a batch command from the scheduler to sync the required folders, however rather than trying to schedule a time to sync the folders, I want to sync them as soon as I plug in my portable drive. In the root of the passport drive, I have added a batch file called autorun.cmd as follows:

  <blockquote>   <p>C:     <br />cd &quot;Program Files\SyncToy 2.0\&quot;      <br />SyncToyCmd.exe -R</p> </blockquote>  <p>I have then added an autorun.inf file to the root of the passport drive with the following entries:</p>  <blockquote>   <p>[autorun]     <br />action=Start Microsoft Synctoy      <br />OPEN=autorun.cmd</p> </blockquote>

Now when the drive is plugged in, AutoPlay will start up and allow me to trigger the sync. If I want to run the sync before going home in the afternoon, all I need to do is manually launch the batch file autorun.cmd