# backhub
[![Build Status](https://travis-ci.org/danielbeardsley/backhub.png?branch=master)](https://travis-ci.org/danielbeardsley/backhub)

backhub creates and keeps up-to-date a backup of all your Github repos.

It's a Node.js app that listens to github post-receive hooks, cloning repos
that it hasn't backed up yet, and calls `git fetch` on ones that it has. This
way, a fresh backup of any github repo you control can be kept around.

This is most useful for effectively adding a reflog to github.
This allows recorvery from
[accidental force-pushes](http://www.reddit.com/r/programming/comments/1qefox/jenkins_developers_accidentally_do_git_push_force/)
or other mistakes without having to locate the person with the most up-to-date
clone of the repo.

## Usage (command line)

   $> backhub [options]          # Starts the backhub server
   
    --dir /path  Directory in which to store the backups (git clones).
    --port n     TCP port to listen on for HTTP github post-receive hooks.
    --jobs n     Number of parallel git commands allowed. If you don't want to
                 overload github or saturate your connection, set this lower.

## Installation

    $ git clone https://github.com/danielbeardsley/backhub.git
    $ cd backhub
    $ npm install --production

## Hacking

   Please fork and submit a pull!

    $ npm install
    $ npm test

## Requirements

 * [Node.js](http://nodejs.org/) (0.6 and above)

