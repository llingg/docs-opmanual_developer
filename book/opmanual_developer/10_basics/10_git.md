# Developer Basics: Git {#sec:developer_basics_git level=sec status=draft}

<minitoc/>

Every time there is a large project, with many contributors and
the need for code versioning and history, developers rely on VCS
(Version Control Systems) tools.
Duckietown uses Git as VCS and [GitHub.com](https://github.com) 
as a service provider for it.
The Duckietown organization page on GitHub is 
[github.com/duckietown](http://github.com/duckietown).


## Monolithicity VS Modularity

Whether a software project should be monolithic or modular is
one of the most debated decisions that a group of developers
faces at the beginning of a software project. Books have been 
written about it. Duckietown started as a monolithic project, 
and some of us still remember the infamous 
[Software](http://github.com/duckietown/Software) repository,
and only later transitioned to a full modular approach.

There are two levels of modularity in Duckietown. We distinguish
between **Modules** and **Nodes**. Modules form our first and highest 
level of modularity, with each module being a collection of nodes.
Nodes constitute the smallest software entities, and each node is
usually responsible for a very specific task. Nodes are not allowed
to exist outside modules.
We will revisit these concepts later in the book, but in a nutshell,
modules represent high level concepts, like _autonomous driving
capability_ for a vehicle, while nodes within a module tackle more
granular tasks, like _traffic signs detection_.

In Duckietown, code is separated so that each module has its own
repository. All repositories are hosted under the same GitHub
organization [github.com/duckietown](http://github.com/duckietown).
Be brave, (as of April 2020) we have more than 220 repositories 
there.


## Ask the community

If you have any questions about how to use of Git in Duckietown,
join the Slack channel 
[#help-git](https://duckietown.slack.com/archives/C6YS9B3G8).


## Hands on

You can gain access to GitHub by creating an account on 
[github.com](https://github.com/join) (if you don't have one already).

We higly suggest that you setup an SSH key for secure passwordless
access to GitHub by following these steps.

See: [Basic SSH config](+software_reference#github-access).

See: [Key pair creation](+software_reference#howto-create-key-pair).

See: [Adding public key on Github](+software_reference#github-access).