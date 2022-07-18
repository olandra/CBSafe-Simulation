![[Efficient Learning Machines.acsm]]# Information about the tools

[< Back](../README.md)

---

## Table of Content
- [Plastic](#plastic)
- [VS Code](#vs-code)
- [Obsidian](#plastic)

---

## Plastic

It's to be noted that using Plastic SCM from within the Unity Editor, it's possible to recieve connection reset by the server error. This is frustrating as it might turn your Plastic pending and incoming changes lists into a mess. 

More so, if after Plastic SCM connection is reset while updating an asset from the Asset Store. This leads to Unity Package Manager to download the asset from the Asset Store and you'll see it as pending changes in Plastic. If you do go ahead and publish these changes and there were some development done to the asset already in the project, you might end up reseting the asset.

Luckily Plastic does have the option to revert back to an older changeset, but nevertheless, it's very annoying - Oh, I almost forgot that you cannot switch to another changeset if you have pending changes.

=> The teaching here is to use Plastic from outside Unity to avoid this kind of trouble. Personally, I prefer Plastic Gluon, which I open only when I need it. This is due to an older problem of Gluon hanging up if kept running for prolonged time.

## VS Code

While I don't have much against Visual Studio, I am running this development also on an older 4th gen Intel laptop. Having already heavy Unity Editor running and adding Visual Studio over it means a good loading time before I can start working (plenty of time to get some coffee while waiting). Another limitation of Visual Studio is that you cannot run it on Linux.

With these two matters in mind, I wish to add in the ease of customizing your VS Code. It has plenty of extensions and themes, but also something very dear for myself: The Vim emulator (vscodevim).

Now then, how to set up VS Code for the task?

I followed the instructions at https://code.visualstudio.com/docs/other/unity

As for the warnings, I found out that there are a couple of annoyances with VS Code. The first one is that OmniSharp warns about MonoBehaviour methods being unused (IDE0051). The other warning was about Unity's older way of handling 'new' operator and OmniSharp warning about 'new expression can be simplified' (IDE0090) by the newer implementation of C#.

I ended up simply turning off these two warning via .editorconfig file. It seems that the IDE0051 could be fixed by 'Regenerate project files' from Unity -> Edit -> Preferences -> External Tools, however, I prefer not to leave empty MonoBehaviour methods in my scripts, so I don't mind those warnings getting ignored.

After those two supressed warnings, there is but one thing I'm missing from Visual Studio. Ctrl + R Ctrl + E for Encapsulate Field shortcut. I haven't yet looked for or created a snippet for properties for VS Code, but that's a small matter when compared to the benefits like Vim emulation.

For those who wish to learn how to use Vim and it's control "melody", I would suggest installing VS Code extension called "Learn Vim" by vintharas. It's a great book which has been implemented in VS Code with an interactive do-it-yourself documents. This allows you to read and try in practise simultaneously.

While this extension provides just the tip of the iceberg about Vim, it's a good place to start. For an advanced user, it still provides a nice Cheatsheet and some new things and ways of thinking when using Vim.

Just remember, learning Vim takes time and patience and in some cases, it might even feel unnatural. However, if you keep pushing forward, you'll soon find the old way even more unnatural.

## Obsidian
https://obsidian.md/

I was a Joplin user for years before finding this piece of software. It shares the greatest part of Joplin without the greatest annoyance of having it's own database over files. I'm actually writing this documentation with Obsidian right now. 

Obsidian takes the SQLite databas Joplin uses and moves it as markdown files in folders. The main folder is called Vault and you can have vaults in any place you want. This makes sharing the files with others or uploading them into git so much easier than with Joplin. Not to mention that Joplin has a paywall for collaboration.

Now, I have to admit that you could forget about Obsidian as VS Code has a great support for markdown, including built in viewer. For me, it's actually easier to have these two separated. I'm running two or three screens all the time, so I have the space for keeping these two open all the time. Yes, I could run two instances of VS Code, but as I try to avoid using my mouse as much as possible, Alt + Tab'ing is easier with two programs which do look different.

There's just one small tweak I encourage for you to do if you choose VS Code and Obsidian. They share a very similiar command palette with file switching option, but the default shortcuts are not the same. I'd adjust Obsidian's shortcuts to match VS Code for these two commands.

Obsidian can also be enhanced with extensions and I'm yet to test at least the Kanban extension. I've been using Trello until now and if Obsidian can match it, I'm open for change.