---
layout: post
title: Working with Camel Case in Visual Studio
---
Recently I was shown a cool feature of CodeRush which allows you to navigate within words in Visual Studio based on its Camel Case. The standard navigation in Visual Studio is using CTRL+Left Arrow and CTRL+Right Arrow will progress you one word to the left and right respectively. But if you have say a method named Test_CreateNewUser_Succeeds and you want to edit the middle part of this, you need to Right Arrow from the start to the point you want to edit. What would be nice if you can jump within the word based on the Capital Letters – such as jump to C for Create, then N for New.

I am using Visual Studio 2010 with ReSharper 5.0 which has a feature called <a href="http://blogs.jetbrains.com/dotnet/2008/02/resharper-in-detail-camelhumps/" target="_blank">Camel Humps</a> which you can turn on within the ReSharper options.

![camelcase1]({{ site.baseurl }}public/images/camelcase1.png){:class="img-responsive"}

The problem I found after turning this on, is that it replaces the default behaviour for CTRL+Left Arrow and CTRL+Right Arrow. What I would like to be able to do is to continue using the default behaviour of CTRL+Right Arrow jumping to the next word, but use an alternative to jump within the word. I found that CodeRush uses the key mapping of **ALT+Left Arrow** and **ALT+Right Arrow** to achieve this so to replicate this behaviour in ReSharper you need to do the following:

- Open the Visual Studio Options window from **Tools** –&gt; **Options**
- Expand Environment and scroll down to **Keyboard**
- Map the two commands *ReSharper_HumpNext* and *ReSharper_HumpPrev* to the key mappings you wish (E.g. **ALT+Right Arrow** and **ALT+Left Arrow**) by selecting the command from the list and entering the key mapping in the Press shortcut keys textbox, then click **Assign**

![camelcase2]({{ site.baseurl }}public/images/camelcase2.png){:class="img-responsive"}
