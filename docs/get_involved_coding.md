Title: Getting Involved - Coding For the WLANPi
Authors: Nigel Bowden

# Getting Involved - Coding For the WLANPi

If you have a project you'd like to develop for the WLAN Pi, or you'd like to improve some of our existing features, you may like to contribute some of your own code to the WLAN Pi initiative.

The software running on the WLAN Pi tends to be from three different sources:

* Existing Linux open-source packages that we make available on the WLAN Pi
* Existing packages or Linux features that we configure and combine to provide a useful feature. These are usually glued together with bits of shell script or python to provide the required feature
* Software written from scratch by our team of volunteer developers. This tends to be software written in Python as so many people are currently keen to learn and hone their skills in this language, but we are not limited to just Python   

The range of skills among our developers varies widely. Many are learning, or are very keen to learn, to provide useful features for wireless network engineers through their coding efforts. We have beginners through to people who have bene looking at coding for several years. None of them (to my knowledge) are software developers as their main day job. The environment is very supportive of contributors of all skill levels.

## Development Workflow

Our development workflow has evolved over the last year or so based on our experience of trying to develop for the WLAN Pi, together with input from a few members who have had some exposure to development processes. As we develop in a collaborative manner, we use [GitHub][github] for sharing code repositories and version control. It is worth spending some time getting up to speed with the basics of git and GitHub before jumping in to development efforts (there are plenty of tutorials on YouTube to help with this.) Having said this, many of us are still very new to git and the whole development process, so don't worry about being the only person who is struggling with understanding how this all fits together! :)

In addition to GitHub, a large part of the development effort take place on a developer Slack community. This is where ideas, issues and suggestions are kicked around between contributors

The development process has evolved as follows:

1. An individual has a idea for a feature or software package they would like to build
2. They may like to build some initial code and/or run the idea by other developers on the Slack community
3. If the idea looks viable and is useful, a repository (repo) for the project is created by the originator of the idea. This is generally on the main WLAN Pi GitHub site, or may be on the originators own repo - either is fine as long as it is publicly available
4. Development work is usually carried out on a 'dev' branch of the project repo. If others wish to contribute to the code, they may fork the repo and then submit a pull request to the dev branch of the project repo. The project repo owner can then review the code in the pull request before merging it in to the main project repo 
5. Once the code has reached a point where it is ready to be released as version to be used by others, it is merged in the master branch of the project repo by the repo owner. At this point, a release number is also assigned to the code within GitHub by assigning a release tag - this allows the code at a particular point in time to be retrieved if/when required.

The fork and pull request steps that allows contribution by others may seem a little onerous and long-winded. But, this has been done to limit the number of people who have access to the main project repo for purposes of quality control and co-ordination of additions of software to each project.

## Conventions

There are a few conventions that are well worth observing when developing or contributing code:

* Before starting work on any new features, code updates or new software modules, make sure that you touch base with the other developers on Slack. Our time as volunteers is very sparse, so we need to ensure we operate as efficiently as possible. There may already work under way to implement a similar feature or another module that has dependencies that need to be accounted for in the new code. Turning up with a new idea of fully functioning code may not be the best route to get an idea included in the next WLAN Pi image release - it may require work in other software modules to accommodate it or may even break existing code.
* Documentation: coding is the fun part of contributing for all of us. However, if you are the only person who knows how or why something works, then it may delay getting your code included. Each project should have a well written document to explain what the software does, how to install it, any dependencies and how to use it.  Source code should be liberally sprinkled with embedded comments to explain how the software operates. If submitting a pull request, ensure that any existing documentation is also updated to include any new of changes to functionality that your code introduces (don't expect project owners to do your documentation)
* Version & release notes files: each project should have a file called 'version.txt' and a release_notes.txt file included in the root directory of the project. 
    * The 'version.txt' file should contain a version number that corresponds to the version release tag assigned in GitHub. Prior to release, alpha and beta designations may be used to indicate the code being reviewed is not yet a release version
    * The 'release_notes.txt' file should contain a brief description of the new features, fixes or changes introduced in this release  

## Special Notes For Development on Windows

1. When developing using a dev environment on a Windows laptop, we have had a number of issues with end-of-line characters being incorrectly set due to the differences between line endings used in Linux & Windows systems. Windows uses a "CRLF" at the end of each line, but Linux uses a "LF", When uploading files to GitHub that use the Windows "CRLF" end-of-line, there can be unusual issues when the files are finally run on the WLAN Pi platform. The best way to avoid this issue is to add the following line to a ".gitattributes" file in the root of each of your local repos (even cloned/forked repos) to ensure all line endings are "LF":
```
* text eol=lf
```

2. Some files need their execution bits set so that they are executable once downloaded to the WLAN Pi. Windows does not natively support the execution bit, so that it is not included when uploading files to GitHub. Please consult this article to ensure execute bits are set when developing on Windows: https://medium.com/@akash1233/change-file-permissions-when-working-with-git-repos-on-windows-ea22e34d5cee

## Final Thoughts

We're all finding our way in this process of both developing and figuring out the best workflow for our requirements. The process is evolving over time, so please provide your input if there is a better way of doing things.  Don't be too worried about diving out and figuring it al out - the main thing is to communicate with other folks so we can all move forwards together is a co-ordinated fashion. It's not easy at times as many of us are newbies, but we're a friendly bunch who are keen to push things forwards.

(Newbie note: One thing I found very useful was to work with a more fully featured development environment, as opposed to the text editors I started out with. I do not have extensive experience of different dev environments, but the [Visual Studio Code][vsc] environment has been very useful for me...you might like to try it out too - it's free!)

## Links

* [WLAN Pi GitHub site][github]
* [Git][git]
* [Visual Studio Code][vsc]

<!-- link list -->
[github]: https://github.com/WLAN-Pi
[vsc]: https://code.visualstudio.com/download
[git]: https://git-scm.com/


