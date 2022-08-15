> This is an abstract of a potential presentation to give during the "Solution 1" event to be held by the C# discord.

# Introduction

- Name: [Zachary Patten](https://github.com/ZacharyPatten)
- Origin: Kansas USA
- Programming History: since 2010 (C# since 2011)
- Work History: professional software developer since 2014
- C# Discord History: member since March 2019
- Topic: [dotnet-console-games](https://github.com/ZacharyPatten/dotnet-console-games) repository on GitHub
- Estimated Duration: <30 minutes

# Purpose Of The Repository

Console applications are where the majority of developers start learning how to code in .NET. There are countless tutorials on how to make .NET console applications, but most cover boring covering topics like making a body mass index formulas, converting units of measure, or making a calculator. However, console applications don't have to be boring. You can make games :video_game: too.

[dotnet-console-games](https://github.com/ZacharyPatten/dotnet-console-games) is a repository on GitHub that contains game examples coded in .NET console applications with the primary purpose of providing project ideas for developers learning to code for the .NET platform. There are currently 43 game examples and all the examples thus far have been coded in C#. More games will be added in the future.

Developers are encouraged to play the game examples and then try to code the games themselves from scratch (as if each game was a "kata"). The games are ordered in the `README.md` by "Weight" to guide beginners towards the easier games to code.

# How To Play The Games

> **Note** Demonstration
>
> Now I would like to demonstrate how to play several of the games.
> 
> 1. clone/download repo and run the games from source locally
>    - Visual Studio
>    - Visual Studio Code
>    - Command Line
> 2. play the web version of the 
> 3. download the binaries included in the repo

Except for Snake and Tetris, most console games you will find on GitHub tend to be turn-based, so I want to highlight a few games in the repo that are **not** turn-based:
- [Quick Draw](https://github.com/ZacharyPatten/dotnet-console-games/tree/main/Projects/Quick%20Draw) _reaction time_
- [Tug Of War](https://github.com/ZacharyPatten/dotnet-console-games/blob/main/Projects/Tug%20Of%20War) _button masher_
- [Whack A Mole](https://github.com/ZacharyPatten/dotnet-console-games/blob/main/Projects/Whack%20A%20Mole) _reaction time (random buttons)_
- [Rythm](https://github.com/ZacharyPatten/dotnet-console-games/blob/main/Projects/Rythm) _timed button presses_
- [Drive](https://github.com/ZacharyPatten/dotnet-console-games/blob/main/Projects/Drive) _top-to-bottom scrolling map_
- [Helicopter](https://github.com/ZacharyPatten/dotnet-console-games/blob/main/Projects/Helicopter) _right-to-left scrolling shooter_
- [Bound](https://github.com/ZacharyPatten/dotnet-console-games/blob/main/Projects/Bound) _dodge the obtacles_
- [Duck Hunt](https://github.com/ZacharyPatten/dotnet-console-games/blob/main/Projects/Duck%20Hunt) _first person target shooting_
- [PacMan](https://github.com/ZacharyPatten/dotnet-console-games/blob/main/Projects/PacMan) _...pacman_

So just because you are in the console doesn't mean you can't make an engaging skill-based game.

# Repository Structure

- The projects are all in the `Projects` folder to reduce the number of items in the root folder.
- If you want to make your repository Visual Studio Code friendly, you need to include the `.vscode` folder
  - `.vscode/extensions.json` lets you nudge users to install required extensions
  - `.vscode/tasks.json` is where you define pre-launch tasks
  - `.vscode/launch.json` is where you define the launch options in the debug view
- GitHub Actions go in the `.github/workflows` folder and use the YAML format
  - `<GAME> Build.yml` there is a build workflow for each game for continuous integration. This is not required by any means as you could just build the solution, but a seperate build status for each game is nice to see on the readme
  - `Website Deploy.yml` this workflow deploys the blazor webassembly website to the `github-pages` branch where GitHub Pages hosts it for free
  - `Binaries Deploy.yml` build the binaries of the games and deploys them to the `binaries` branch so that the binary stays out of the source code

# How the Web Ports Of the Games Work

I get asked quite often how do I run the console games on the website. Let me start by saying that this was pretty tricky to figure out. The `dotnet-blazor-games` repo was where I started porting the games to the web, but I wanted the console games themselves to be playable and not a completely different looking web interface. So, a bunch of hacking later I currently have a [`BlazorConsole`](https://github.com/ZacharyPatten/dotnet-console-games/blob/main/Projects/Website/BlazorConsole.cs) class where I reimplement most of the members of `System.Console` and I copy-paste the console code into the website and use a field, `public readonly BlazorConsole Console = new();`, to make all the calls use my `BlazorConsole` rather than `System.Console` since fields have priority over static classes.

I want to make a special mention that Blazor Webassembly is currently single-threaded. You cannot run code in parallel. Multithreading is supported by webassembly but it hasn't been built into .NET blazor webassembly just yet. Even though I have `async`+`await` throughout the ports of the code, I still have to delay the current task to pass back control to the UI Task.

Is there a better way than my approach? Probably. :D But it is working pretty decent at the moment.

# Conclusion

Just remember that all of the games were coded by developers in their free time. The purpose of the repository is to provide project ideas; **not tell people how to code**. If you code any of the games yourself and end up with very different code from the repository, that is great. :)

Please share this repo with other beginner developers you think could learn from it.

I hope this taught you something interesting about the console, GitHub repos, Blazor WebAssembly, etc. Thank you for your time.

Any questions?
