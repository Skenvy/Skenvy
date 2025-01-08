# _G'day_ 🤠
<!-- Usually I header my projects with a link to the corresponding repo but this
is a special case; being the "Profile Repo" https://github.com/Skenvy/Skenvy, we
also don't need the typical "top header is repo name hyperlinked to itself"! -->

<!-- Host and src imgs without bloating this or using lfs, by committing images
to this's wiki. ```git clone git@github.com:Skenvy/Skenvy.wiki.git``` to get the
wiki, then add and commit, and the image file is now generally available at path
https://raw.githubusercontent.com/wiki/:owner/:repo/a/b/c.xyz e.g.
https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/assets/imgs/*.* -->

> [!CAUTION]
> Likey, nothing better symbolises the chaotic vibe of my approach to coding than this; the time when I was 15, stumbled upon a broken umbrella, and had no qualms asking, or answering: "Could you fit all the pieces of an umbrella in an apple?"

<img alt="An apple with pieces of an umbrella poking through it." src="https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/assets/imgs/umbrella_apple.jpg" width=830 height=432 style="display:block;margin-left:auto;margin-right:auto;"/>

## `whoami` 🤷‍♂️
> [!IMPORTANT]
> Howdy, I'm [Nathan](https://www.linkedin.com/in/nathan-levett/), a.k.a. [Skenvy](https://www.reddit.com/user/Skenvy/submitted/), "30's"-year-old Australian 'devops' human.
>
> I'm building inconsequential projects for fun and learning. The more inconsequential the better.
>
> Degree'd in Computer Engineering, Maths and Geology, I've spent several years working across a range of technical roles: FPGA development, product support, Azure apps, "consulting", "data", and for the last few years as something that is 'SRE-adjacent', "devops"-y cloud [thangs](https://www.youtube.com/watch?v=ijN3Oho2Qf0).

> [!TIP]
> My dotfiles are _their own how-to_, from [`main`](https://github.com/Skenvy/dotfiles/tree/main). [`home`](https://github.com/Skenvy/dotfiles/tree/home) is _my_ home. Or, [make yourself at home](https://github.com/Skenvy/dotfiles/tree/base), too. [Home Is Where the Dotfile Is](https://www.youtube.com/watch?v=dAZgor62vMI).

<!-- ## Ethos 🚎 -->

<!--
Links to relevant content to maybe include
https://www.youtube.com/watch?v=K7hU_z9X4Kk "define your wins" -- How To Make Coding Addictive -- bigboxSWE
https://www.youtube.com/watch?v=bJQj1uKtnus "cult of done" -- The Cult of Done: How to Finish the Thing -- NoBoilerplate
https://www.youtube.com/watch?v=8GQZuzIdeQQ -- How to make hard choices | Ruth Chang -- TED
https://www.youtube.com/watch?v=5nY_cy8zcO4 -- Don't Contribute to Open Source -- t3dotgg
https://medium.com/@bre/the-cult-of-done-manifesto-724ca1c2ff13 "cult of done" reprint by one of the original authors.
-->

## Tools 🛠️

<!-- Probably pointless decoration having the lists here, but it feels empty without them. Might make it relevant eventually, might not. -->

<details>
<summary>Generic</summary>

### IDE
* vsc
* vim
### Cloud
* AWS (via CFN/CDK/TF)
* GCP (via TF)
### CICD
* GitHub Actions
* BuildKite
### Containerisation
* Docker
* Docker-Compose
* K8s
* Helm
* K9s
### Db
* PostgreSQL
* BigQuery
* RedShift
* dabbled in Cassandra
### VC
* Git
* Mercurial
### Methodologies
* Agile
* Kanban
* Scrum

</details>

<details>
<summary>Languages</summary>

### Primary
* Python
* Bash
* Java
* Yaml (lol)
* Make (lol).
### Secondary
* C#
* Go
* Ruby
* PowerShell
* Julia
* R
* VHDL
### Currently learning
* Rust
* Kotlin+Android
* Erlang/Gleam
### _Always learning_
* JS
* TS
* Node

</details>

## Projects 📂

> [!NOTE]
> I maintain several niche packages that besides their respective typical hosts, also live in [GitHub Packages.](https://github.com/Skenvy?tab=packages)
> There's also my [gists](https://gist.github.com/Skenvy). One that I have on my favourites bar because I regularly need to access it to remember it is [SSH for multiple GH accounts](https://gist.github.com/Skenvy/8e16d4f044707e63c670f5b487da02c0).

1. [julia-release](https://github.com/Skenvy/julia-release): A github action to release a julia project in a way that feels more ideologically alligned with how I'm familiar with releasing, as opposed to julia's officially recommended release pattern.
1. [dependabot-linguist](https://github.com/Skenvy/dependabot-linguist) A ruby [package](https://rubygems.org/gems/dependabot-linguist) that can be used to have a guess as to what sort of dependabot configuration is appropriate for a given repository, with the primary use case of automating the configuration across multiple repositories without the need to manually investigate their contents.
1. [Collatz](https://github.com/Skenvy/Collatz): An attempt at a personal Rosetta Stone and collation of _language-fu-isms_, all attempting to achieve sort of the same thing, along with various general repository health examples, and learning github actions. There's probably more collatz repositories on GitHub than you could poke a stick at. This is just one of them. I picked the topic to match the goal of "personal Rosetta Stone" rather than the other way round. The choice of topic came from having a bunch of python scripts written years ago that went down a rabbit-hole, so I made this to make myself stick to KISS.
1. [Sudoku](https://github.com/Skenvy/Sudoku): A java JFrame implementation of a sudoku solver I wrote circa 2013 and have been sitting on with the desire to one day convert it into an android app. The distinction between this and other solvers is that this tries to catagorise the difficulty of the puzzle by which tactics it needed to solve it, that is to say, it tries to solve it using only specific techniques, in order, without resorting to heuristics / brute force that would be unobtainable for a person.

## Publications 🖨️
* Honours Thesis (2017): [ECDSA and ECDH in VHDL for FPGA](http://hdl.handle.net/1959.14/1262355)

## License 📄
> [!NOTE]
> <p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/Skenvy/Skenvy">Skenvy</a> by <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://github.com/Skenvy">Nathan Levett</a> is licensed under <a href="https://creativecommons.org/licenses/by-sa/4.0/" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC-BY-SA-4.0 <img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/sa.svg?ref=chooser-v1" alt=""></a></p>
