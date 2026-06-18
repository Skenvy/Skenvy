[wiki]: https://github.com/Skenvy/Skenvy/wiki
[light-dark-img]: https://github.com/stefanjudis/github-light-dark-image-example
[figcap]: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figcaption
[cloud run python packages]: https://docs.cloud.google.com/run/docs/runtimes/python-dependencies#pre-installed_packages
# [Memes](https://github.com/Skenvy/Skenvy/blob/main/extra/docs/memes.md)
Welcome to my curated list of memes / reactions that I've made and used either
for general recurring use, or in response to a specific situation, over the last
several years.

## Where are the images stored?
<details>

<summary>Read how the images are stored and accessed</summary>

Read the original source of this
[here](https://github.com/Skenvy/Collatz/blob/main/.meta/banners/README.md).
It describes a methodology I've used in numerous places, and now here too!

To prevent committing too many large image files _here_, the generated images
will be committed in this repository's [wiki][wiki], and the links to the raw
files hosted in the wiki will be used in `img` tags. You can clone the wiki as
you would any other repo, with the `:owner/:repo` being `:owner/:<repo>.wiki`;
either as `git clone git@github.com:Skenvy/Skenvy.wiki.git` /
`git clone https://github.com/Skenvy/Skenvy.wiki.git`.

When accessing the raw contents, to `<img src=...>` the images hosted in the
wiki, the url does not use the `:<repo>.wiki` name, nor does it take a branch.
For files in the wiki at location `./a/b/c.xyz`, they would be accessed as
`https://raw.githubusercontent.com/wiki/:owner/:repo/a/b/c.xyz` e.g. if we host
the images as `./path/inside/wiki.png`, then we access them as
`https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/path/inside/wiki.png`.

</details>

## Html for including the images in READMEs

<details>

<summary>See the result snippet for embedding wiki images here</summary>

Read the original source of this
[here](https://github.com/Skenvy/Collatz/blob/main/.meta/banners/README.md).
It describes a methodology I've used in numerous places, and now here too!

We can embed images stored in the wiki and accessed via
`https://raw.githubusercontent.com/wiki/:owner/:repo/:filepath`, into the main
repo's READMEs, with [this html embedding of a `<picture>`][light-dark-img];
```html
<!-- Things that don't work: Align a p containing a figure -->
<p align="center"><figure>...</figure></p>
<!-- Things that don't work: Align the img -->
<img align="center"/>
<!-- Things that DO work: Align a p containing an img -->
<p align="center"><img/></p>
<!-- Things that DO work: Align a p containing a picture with source -->
<p align="center"><picture><source/><img/></picture></p>

<!-- For single image mode -->
<p align="center">
  <img alt="Alt text to describe an image for screenreaders"
    src="https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/a/b/c.png"
    width=830 height=666/>
</p>
<sub><p align="center"><i>
  A subtitle box that can include <a> elements
</i></p></sub>

<!-- For dark / light mode -->
<p align="center"><picture>
  <source media="(prefers-color-scheme: dark)"
  srcset="https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/a/b/c_dark.png"/>
  <img alt="Alt text to describe an image for screenreaders"
  src="https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/a/b/c_light.png"
  width=830 height=666/>
</picture></p>
<sub><p align="center"><i>
  A subtitle box that can include <a> elements
</i></p></sub>
```

</details>

## Memes list
Ordered alphabetically by "name of format" / "name of meme".

Sometimes an explanation of the origin is included, sometimes not..

### [Always-Has-Been](https://imgflip.com/memegenerator/Always-Has-Been)
#### [tf-go-types](https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/tf-go-types.png)
<p align="center">
  <img alt="Always-has-been Go gopher behind astronaut looking at Terraform"
    src="https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/tf-go-types.png"
    />
</p>
<sub><p align="center"><i>
  "Always has been" Go gopher behind astronaut looking at Terraform
</i></p></sub>

<details>

<summary>Explanation</summary>

Some gcp terraform modules were mangling unique IDs for resources / projects,
where a unique 21 character number ID was being cast internally during the go
code run underneath the hood of the public gcp modules via both `fmt.Sprintf`
and `strconv.FormatFloat`, so I put together this meme to go along with this
demonstration of how both casts were mangling the IDs (example project IDs).
```go
package main

import (
	"fmt"
	"strconv"
)

func main() {
	// the unique IDs are 21 length integers
	var f = make(map[string]float64)
	f["prod_"] = 112233445566778899001
	f["stage"] = 135792468013579246801
	f["dev__"] = 123456789012345678901
	var ff = make(map[string]string)
	ff["prod_"] = "112233445566778899001"
	ff["stage"] = "135792468013579246801"
	ff["dev__"] = "123456789012345678901"
	// Print the name, the string of the digits, and then the float rounded to nearest int, and then FormatFloat with "exact" precision (-1)
	for k := range f {
		fmt.Println(k, ff[k], "->", fmt.Sprintf("%.0f", f[k]), "->", strconv.FormatFloat(f[k], 'f', -1, 64))
	}
	// You'll see the digits of the float get mangled by both of these calls, which can be what happens in GCP modules to 21 character length IDs.
}
```

</details>

### [Am-I-a-joke-to-you](https://imgflip.com/memegenerator/155988880/Am-I-a-joke-to-you)
#### [cacheless](https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/cacheless.jpg)
<p align="center">
  <img alt="Am-I-a-joke-to-you meme -- git cache"
    src="https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/cacheless.jpg"
    />
</p>
<sub><p align="center"><i>
  
</i></p></sub>

### [Bernie-I-Am-Once-Again-Asking-For-Your-Support](https://imgflip.com/memegenerator/Bernie-I-Am-Once-Again-Asking-For-Your-Support)
#### [pr-review-pls](https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/pr-review-pls.jpg)
<p align="center">
  <img alt="Bernie-I-Am-Once-Again-Asking-For-Your-Support meme -- asking for a PR review"
    src="https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/pr-review-pls.jpg"
    />
</p>
<sub><p align="center"><i>
  
</i></p></sub>

### [Explain-your-smolness](https://imgflip.com/memegenerator/386339015/Explain-your-smolness)
#### [mvn-props](https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/mvn-props.jpg)
<p align="center">
  <img alt="Explain-your-smolness meme -- maven properties"
    src="https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/mvn-props.jpg"
    />
</p>
<sub><p align="center"><i>
  Big shiba inu wants to know why lil shiba inu is smol
</i></p></sub>

<details>

<summary>Explanation</summary>

I was replacing about 60 different lines in a build scripts that were each about
500 characters long and each supplying a different call to a `mvn` directive
with mostly the same massive arguments. I replaced them with 6 calls to `make`
targets each doing 10 or so of the `mvn` calls, that were now each about 50
characters long instead of 500, because I'd moved the 20ish arguments in to
the `pom.xml`'s [`<properties>`](https://maven.apache.org/pom.html#Properties).

</details>

### [go-apple-go-orange-go-banana](https://imgflip.com/memegenerator/79651560/go-apple-go-orange-go-banana-simpsons)
#### [log-diff-ori](https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/log-diff-ori.jpg)
<p align="center">
  <img alt="go-apple-go-orange-go-banana meme -- log vs diff vs *.ori"
    src="https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/log-diff-ori.jpg"
    />
</p>
<sub><p align="center"><i>
  Ralph's preferred method of maintaining history is via *.ori files..
</i></p></sub>

<details>

<summary>Explanation</summary>

Simply made in response to a PR that moved changed files to add `.ori` on the
end of their names instead of just update them and only keep the one actual
copy in use; to show my disdain for `*.ori` files as a practice when `git log`
and `git diff` are right there...

</details>

### [i-prefer-the-real](https://imgflip.com/memegenerator/130875502/i-prefer-the-real)
#### [uwuntu](https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/uwuntu.jpg)
<p align="center">
  <img alt="i-prefer-the-real meme -- uwuntu"
    src="https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/uwuntu.jpg"
    />
</p>
<sub><p align="center"><i>
  
</i></p></sub>

<details>

<summary>Explanation</summary>

Made as part of an escalation of referencing more obscure and niche distros..

</details>

### [Im-too-weak-UNLIMITED-POWER](https://imgflip.com/memegenerator/222337718/Im-too-weak-UNLIMITED-POWER)
#### [before-and-after-git](https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/before-and-after-git.png)
<p align="center">
  <img alt="Im-too-weak-UNLIMITED-POWER meme -- git"
    src="https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/before-and-after-git.png"
    />
</p>
<sub><p align="center"><i>
  Emperor Palpatine uses git, I guess? Sith lord Jar Jar Binks probably uses mercurial lol.
</i></p></sub>

<details>

<summary>Explanation</summary>

Not a lot of depth.. just used as a quippish way of replying to someone outside
of a tech team asking what all the fuss about `git` was..

</details>

### [It's Always Sunny in Philadelphia :: Title Card](https://iasip.app/)
#### [name-repo](https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/name-repo.png)
<p align="center">
  <img alt="It's Always Sunny in Philadelphia :: Title Card -- The gang names a repository"
    src="https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/name-repo.png"
    />
</p>
<sub><p align="center"><i>
  The Gang Names a Repository.
</i></p></sub>

<details>

<summary>Explanation</summary>

If you haven't watched IASIP, you probably should.

But if you haven't, the title card is usually a cut-to gag, often indicating
that the rest of the episode will be the gang doing something that they just
declared they _wouldn't_ do, or, that they will just end up in an unnecessary
conflict over something trivial, and there won't be any satisfying resolution.

Getting everyone to agree on naming a new repository can sometimes be this way..

This was made in direct response to an hours long on and off again chat thread
about "what should we call this new service / repo for the new service".

</details>

### [Oliver-Twist-Please-Sir](https://imgflip.com/memegenerator/13872228/Oliver-Twist-Please-Sir)
#### [more-pip-freeze](https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/more-pip-freeze.jpg)
<p align="center">
  <img alt="Oliver-Twist-Please-Sir meme -- asking for more pip freeze"
    src="https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/more-pip-freeze.jpg"
    />
</p>
<sub><p align="center"><i>
  Charles Dickens dystopias include no one ever locking their requirements.
</i></p></sub>

<details>

<summary>Explanation</summary>

Things were breaking in prod because some python serverless containers (lambdas
and cloud functions) were being deployed with a `requirements.txt` file that did
not lock any requirements, but just loosely specified either some totally
unversioned packages, or some with only loose pins.

When I saw this was the case while investigating what was causing a production
issue the first time looking at some project, I made this meme to inform the
team I was going to make the problem at least easier to debug by setting up a
process for creating a `requirements.txt` that would be the output of
`pip freeze`'ing the non-lock set of `requirements.txt`.

</details>

### [So-that-was-a-fucking-lie](https://imgflip.com/memegenerator/176178994/So-that-was-a-fucking-lie)
#### [gcp-cloud-func-setuptools](https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/gcp-cloud-func-setuptools.png)
<p align="center">
  <img alt="So-that-was-a-fucking-lie meme -- gcp cloud functions setuptools latest version"
    src="https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/gcp-cloud-func-setuptools.png"
    />
</p>
<sub><p align="center"><i>
  
</i></p></sub>

<details>

<summary>Explanation</summary>

The docs on GCP's `cloud run` / `cloud function`, specifically, the docs what
versions of packages that are preinstalled are... is not useful for knowing what
version of `pip`, `setuptools`, or `wheel` will be installed, as the version of
these three packages will get overwritten regardless of what you specify in your
`requirements.txt` file.

The [docs][cloud run python packages] _say_ """`setuptools` (latest version)""".

But this is not always true.. and can have consequential effects on other
packages. This was my way of summarising a day spent debugging why something was
breaking for no apparent reason, when the answer came down to the version of
`setuptools` being unexpected.

</details>

### [You-guys-always-act-like-youre-better-than-me](https://imgflip.com/memegenerator/170185878/You-guys-always-act-like-youre-better-than-me)
#### [ds-langs](https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/ds-langs.png)
<p align="center">
  <img alt="You-guys-always-act-like-youre-better-than-me meme -- Data Science Languages"
    src="https://raw.githubusercontent.com/wiki/Skenvy/Skenvy/memes/gen/ds-langs.png"
    />
</p>
<sub><p align="center"><i>
  
</i></p></sub>

<details>

<summary>Explanation</summary>

Sometimes it's fun to drop low effort programming language conflict rage bait.

</details>
