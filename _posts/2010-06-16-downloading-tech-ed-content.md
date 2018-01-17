---
layout: post
title: Downloading Tech Ed Content
---
Last Week Tech Ed North America was held in New Orleans and if like me you were not able to attend, you can view most of the sessions and get access to most of the slide decks through <a href="http://www.msteched.com/" target="_blank">Microsoft Tech Ed Online</a>.&#160; Rather than right click and save each of the sessions and slides you can download all of the content using the following method: (Note: Thanks to <a href="http://geekswithblogs.net/sdorman/archive/2009/11/26/downloading-pdc-2009-content.aspx" target="_blank">Scott Dorman</a> and his PDC09 download script and instructions).
- Get the latest build of <a href="http://curl.haxx.se/download.html" target="_blank">curl</a> and extract into a folder. 
- Download the script <a href="http://cid-090d535e56bed79c.office.live.com/self.aspx/.Public/TechEdDownloader-Dev.zip" target="_blank">TechEdDownloader-Dev</a> and extract the .bat file into the same folder as above.
- Run the downloader batch file from a command prompt. This takes a single parameter which indicates the file you want to download. This can be:
    - WMVHIGH
    - WMV
    - MP4
    - PPTX
- Download <a href="http://cid-090d535e56bed79c.office.live.com/self.aspx/.Public/TechEdRenamer-Dev.zip" target="_blank">TechEdRenamer-Dev</a> and extract the .bat file to the same folder as the downloaded content.
- Run the renamer batch file from a command prompt to rename the files to the session title. This batch file also accepts a single parameter as above.

Note the downloader and renamer are currently just for the Developer Tools, Languages &amp; Frameworks stream. Check back for downloader and renamer batch files for the other streams.
