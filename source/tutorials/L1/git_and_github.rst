Git and GitHub
==============

.. What is version control?
.. What is Git?
.. What is GitHub?
.. Basic vocabulary

.. Key concepts
.. create github account
.. JupyterLab git plugin
.. Git from the command line

.. Using Classroom for Github



This tutorial covers the very basics of `version control <https://en.wikipedia.org/wiki/Version_control>`__ using `Git <https://en.wikipedia.org/wiki/Git_(software)>`__, `GitHub <https://github.com/>`__, and JupyterLab git plugin.


Sources
-------

These materials have been adapted from:

- `Version Control with Git <http://swcarpentry.github.io/git-novice/>`__
- `GitHub Education Campus Advisors resources <https://github.com/Campus-Advisors>`__
- `Git documentation <https://git-scm.com/about/>`__
- `GitHub Campus Advisor materials <https://education.github.com/teachers/advisors>`__
- `Geo-Python Course <https://geo-python-site.readthedocs.io/en/latest/lessons/L2/git-basics.html>`__
- `Data Science: A First Introduction <https://datasciencebook.ca/version-control.html>`__




What is version control and why should I use it?
------------------------------------------------
Imagine your code as an evolving storybook, where every line written is a new chapter. 
Version control is like a magic quill that records every change, every plot twist, and character development in this coding adventure.
Version control systems are like time-traveling wizards for your documents! 
They start with a magical base version and then keep a record of every change you make along the way. 
It's like rewinding your favorite movie, starting from the beginning and watching each cool edit you've made until you reach your latest masterpiece!


.. figure:: img/version_control_02.png
   :alt: Motivation for version control

   Source: "Piled Higher and Deeper" by Jorge Cham, http://www.phdcomics.com


**Why Should We Use Version Control?**

- **History Keeper:** Version control systems, like Git, maintain a detailed history of changes made to your code. It's a time machine allowing you to revisit any point in your project's history.
- **Undo & Redo Magic:** Made a mistake? Version control lets you rewind! It's like an "Undo" button for your code, helping you revert to a previous state effortlessly.
- **Collaboration Made Easy:** Imagine working on a group project without version control—it's like writing a book together without being able to share drafts! Version control makes collaborating a breeze, allowing multiple people to work on the same codebase without chaos.
- **Experimentation & Branching:** Want to experiment with new features without breaking everything? Version control introduces branching—creating alternative storylines for your code, exploring new ideas without affecting the main plot.
- **Backup & Safety Net:** Your code is valuable! Version control provides a safety net by keeping your code stored safely, like a backup that you can always rely on.



.. admonition:: What is Git?

    `Git <https://en.wikipedia.org/wiki/Git_(software)>`__ is a version control software that is used to track and store changes in your files (often source code for programs) without losing the history of past changes. 
    Files in Git are stored in a repository, which you can simply think of as a directory containing files (or other directories) related to a single 'project'. Git is widely used by professionals to keep track of what they’ve done and to collaborate with other people.



What is GitHub?
---------------

.. figure:: img/github_logo.png
   :alt: GitHub Logo
   :width: 400px


`GitHub <https://github.com/>`__ is a web based Git repository hosting service and social network. 
GitHub is the largest online storage space where coders gather, share ideas, and collaborate on projects. 
It's more than just version control; it's a hub for open-source contributions, a portfolio showcase, and a networking paradise for coding enthusiasts worldwide.
GitHub provides a nice web-interface to your files that is easy to use. 


GitHub's Superpowers:
~~~~~~~~~~~~~~~~~~~~~

1. **Public Repositories & Open Source:**

GitHub hosts open-source projects, allowing anyone to contribute and learn from the vast library of code available.

2. **Issue Tracking & Discussions:**

Discuss ideas, report bugs, and track progress through GitHub's issue tracking system—a virtual space for coding dialogues.

3. **Pull Requests & Collaboration:**

Submit pull requests to propose changes or improvements to projects, fostering a collaborative atmosphere among developers.


Key Concepts in Version Control with Git and GitHub
---------------------------------------------------

Git serves as our time-traveling historian for code! It records changes made to our files over time, preserving every twist and turn in our coding journey.
A "repository," often called a "Git project" or simply "repo", is like a container that holds all the files and folders associated with a project. 
It's where Git stores the complete history of changes for each file. 
You can maintain your files on your local computer, creating a dedicated local repository. Additionally, you can establish a remote repository hosted on GitHub servers.
In general, it is recommended that each project, library or discrete piece of software should have it's own repository.
For example, each assignment in this course has it's own repository on GitHub.

Cloning a Repository:
~~~~~~~~~~~~~~~~~~~~~
We begin by duplicating an existing repository from GitHub onto our computer with git clone. 
Think of it as getting your hands on a unique copy of our assignment project. 
This copy is yours to explore, work on, and personalize according to your coding style and ideas.

Publishing Changes:
~~~~~~~~~~~~~~~~~~~
In order record changes to our files, we first add changes to a so called staging area (using the command ``git add``). 
The idea is, that you can have a (sometimes messy) working directory, and by using ``git add`` you tell Git which files to include in the next committed snapshot. 
Then, the command ``git commit`` records a permanent snapshot of the staged changes.
Once you have made one or more commits that you want to share with your collaborators, you need to push (i.e., send) those commits back to GitHub. 
This updates the history in the remote repository (i.e., GitHub) to match what you have in your local repository. 
`Read more about basic snapshotting <https://git-scm.com/book/en/v2/Appendix-C:-Git-Commands-Basic-Snapshotting>`__.

.. figure:: img/version_control_concepts01.png
    
    Version control steps using Git (adapted from `Data Science: A First Introduction <https://datasciencebook.ca/version-control.html#overview-12>`__).


Syncing Changes:
~~~~~~~~~~~~~~~~
If you are working on a project with collaborators, they will also be making changes to files.
To obtain the new changes from the remote repository on GitHub, you will need to pull those changes to your own local repository. 
By pulling changes, you synchronize your local repository to what is present on GitHub.


.. figure:: img/version_control_concepts02.png
    
    Update your Git project local repository using pull commands. Always pull before you push (especially when working in a shared project)!

.. note::

    During this course, we often start by cloning an existing repository from GitHub
    to our own computer using ``git clone``. Using ``git pull`` we can fetch (and merge) new changes from GitHub,
    and ``git push`` publishes our local changes to GitHub. 

    `Read more about sharing and updating Git projects <https://git-scm.com/book/en/v2/Appendix-C:-Git-Commands-Sharing-and-Updating-Projects>`__.


Basic vocabulary
~~~~~~~~~~~~~~~~

Here are a few basic terms that are used often when using git and GitHub (not exhaustive).

-  **Repository** = a location where all the files for a particular
   project are stored, usually abbreviated as "repo." Each project will
   have its own repo, which is usually located on a server and can be
   accessed by a unique URL (a link to GitHub page for example).

-  **Commit** = To commit is to write or merge the changes made in the
   working copy back to the repository. When you commit, you are
   basically taking a "snapshot" of your repository at that point in
   time, giving you a checkpoint to which you can reevaluate or restore
   your project to any previous state. The terms 'commit' or 'checkin'
   can also be used as nouns to describe the new revision that is
   created as a result of committing.

-  **Revision / version** = A revision or a version is any change in
   made in any form to a document(s).

-  **Clone** = Cloning means creating a repository containing the
   revisions from another repository. This is equivalent to pushing or
   pulling into an empty (newly initialized) repository. As a noun, two
   repositories can be said to be clones if they are kept synchronized,
   and contain the same revisions.

-  **Pull / push** = Copy revisions from one repository to another.
   Pull is initiated by the receiving repository, while push is
   initiated by the source. Fetch is sometimes used as a synonym for
   pull, or to mean a pull followed by an update.

-  **Merge** = A merge or integration is an operation in which two sets
   of changes are applied to a file or set of files.



Preparations
------------


Let's go through the basics of using Git. We are going to see how we can create a github account and create a new repository in GitHub.
Then we are going to see how we can clone a repository from GitHub to our JupyterLab session, and how we can make changes to the repository and push them to GitHub.



Create a GitHub account
~~~~~~~~~~~~~~~~~~~~~~~

You will need an account for `GitHub <https://github.com/>`__ to follow the rest of the steps.

- Go to `https://github.com <https://github.com/>`__ and follow the “Sign up” link at the top-right of the window.
- Follow the instructions to create an account.
- Verify your email address with GitHub.
- Configure multifactor authentication.



Creating a remote repository on GitHub
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Once you have logged into your account, you can create a new repository to host your project by clicking on the “+” icon in the upper right-hand corner, and then on :kbd:`New Repository`.

.. figure:: img/github_01.png
    
    New repositories on GitHub 


.. figure:: img/github_02.png
    
    Repository configuration for a new project on GitHub 


Repositories can be set up with a variety of configurations, including a name, optional description, and the inclusion (or not) of several template files. 
One of the most important configuration items to choose is the visibility to the outside world, either public or private. 
Public repositories can be viewed by anyone. Private repositories can be viewed by only you. 
Both public and private repositories are only editable by you, but you can change that by giving access to other collaborators.



Generating a GitHub personal access token
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Before we start cloning our repository from GitHub, we need to create a Personal Access Token for us to be able to interact with GitHub. 
We will go through the basic setup here, but you can find more detailed instructions in the `GitHub documentation <https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token>`_.

#. If you have not already verified your email address, make sure to do so in your GitHub settings (`GitHub email verification <https://docs.github.com/en/get-started/signing-up-for-github/verifying-your-email-address>`_). On GitHub, go into your settings.

   .. image:: https://docs.github.com/assets/images/help/settings/userbar-account-settings.png
      :width: 200

#. Click on **Developer settings** in the left sidebar.
#. Click on **Personal access tokens**.
#. Click on **Tokens (classic)**.
#. We will create the token by clicking on **Generate new token** and then **Generate new token (classic)**.

   - If you are using two-factor authentication, you may be prompted to enter an authentication code at this point.
 
#. We can start by giving our token a name in under **Note**.

   .. image:: img/token_name.png
      :width: 500

#. We can then give the token an expiration date. You can choose the duration you prefer, but it would be best to set it to at least the end of the year.

   .. image:: img/token_expiration.png
      :width: 300

#. Now we need to set the permissions, or scopes, that our token is granted. We are going to need it to be able to access and change our exercise repositories. For that, we can select the check boxes for **repo**, **admin:repo_hook**, and **delete_repo**.

   .. image:: img/token_scopes.png
      :width: 500

#. At this point we can click the **Generate token** button to create and see our token.

#. We are then presented with our Personal access token, click the copy button to copy it to your clipboard and then paste it into a text file in the JupyterLab session.

   - Open a text document and copy and paste your Personal access token in a text file, because for now we are going to use it like this, and we will later see how we can cache it so that we don't need to copy and paste it every time we need it. If your access token is ever lost, you can just follow the steps above again to create a new one.

Now that we have created a personal access token, the next thing we need is the URL of your exercise repository from GitHub. **Go to** https://github.com/geo-python-2023/ **and navigate to your personal Exercise-1 repository.**

On GitHub, find the button **Code** and copy the url under *HTTPS*.

The URL looks something like this:
https://github.com/Geo-Python-2023/exercise-1-davewhipp.git but with your own username or team name.

.. figure:: img/git-copy-url.png


JupyterLab git plugin
---------------------

Clone a repository from GitHub
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

During this course, we will most often start working with the exercises using an existing repository from GitHub.
In order to get a copy of the exercise repository on our own computer (or the cloud computer), we need to ``clone`` it.

Navigate to the **my-work** folder in JupyterLab, create a new folder inside it called **exercises**, and double-click to enter that folder. Next, activate the git-plugin. The plugin will tell you that **exercises** is not a Git repository and gives you some options.

In our case, we want to **Clone a Repository**:

.. figure:: img/git-plugin-start-cloning.png

Go ahead and paste your exercise repository URL into the pop-up window:

.. figure:: img/git-plugin-clone.png

On the command line this action is equivalent to the ``git clone`` command.

.. note::

    **Pay attention to which folder you are in!** Git will create a new folder under the folder you
    are located in when cloning a repo.


Credentials
~~~~~~~~~~~

Git needs to know who you are in order to give you access to remote repositories.

**Insert your GitHub username and personal access token**:

.. figure:: img/git-plugin-credentials.png

Now you should see a new folder in JupyterLab that is identical to the repository on GitHub.

On the command line, credentials can be managed using ``git config``.

Git status
~~~~~~~~~~

Navigate to the new folder in JupyterLab and activate the Git plugin. You should now see some basic info about your repository:

.. figure:: img/git-plugin-status1.png

On the command line ``git status`` shows the status of the repository.


Add changes
~~~~~~~~~~~

Let's start making changes in the repository! Open the ``README.md`` file and make some edits. For example, add some text at the end of the file:

.. figure:: img/edit-readme.png
    :width: 750

    Edit a file in JupyterLab

After saving your changes, check the status of the repository. You should see ``README.md`` listed under **Changed** files:

.. figure:: img/git-plugin-changed.png
    :width: 350

    Changes visible in the Git plugin

These changes are not yet "staged for commit", which means that we need to add them first to the staging area if we want to make a permanent snapshot of these changes.

.. figure:: img/git-plugin-stage-changes.png
    :width: 350

After adding the changes, you should see the changed file under **Staged** in the Git plugin.

Note that you can also **unstage** and **discard changes** using the plugin.
For now, we are happy with the changes made, and are ready to commit them.

On the command line, ``git add`` is the command for adding changes to the staging area.

Commit changes
~~~~~~~~~~~~~~

Once the changed files are in the staging area, we can create a permanent snapshot by committing the changes.
Always remember to write an informative commit message to accompany your changes:

.. figure:: img/git-plugin-commit.png
    :width: 300

Once you hit the commit button, the plugin will most likely ask your name and email.

.. figure:: img/git-commit-credentials.png

You can insert the same details you used when signing up to GitHub.

.. figure:: img/git-plugin-commit-ok.png

Once the commit succeeds, you should see the latest set of changes under the History tab in the Git plugin:

.. figure:: img/git-plugin-history1.png

*Note: You might also see some previous changes by the course instructors. These changes have been generated automatically and you can ignore them.*

On the command line the syntax for committing is ``git commit -m "commit message"``. After committing, it is good practice to check the repository status using ``git status``.

.. note::

    We can **tell Git to remember our GitHub username and access token** to avoid typing them in all the time. Open up a Terminal window and type in this command:

    ``git config --global credential.helper 'store --file /home/jovyan/my-work/.git-credentials'``

    Then change the folder you are in by typing (with your username):

    ``cd exercises/exercise-1-davewhipp/``

    We then pull from our GitHub repository:

    ``git pull``

    Type your username, press enter, and go to the text file with your access token, copy it, and paste into your terminal with **Ctrl** + **v** and press **Enter**. Then your username and access token should be stored and you can pull and push to and from GitHub without having to type your access token every time.

Push changes to GitHub
~~~~~~~~~~~~~~~~~~~~~~

Next, we want to synchronize our local changes with the remote repository on GitHub.

.. figure:: img/git-plugin-pull-push-buttons.png

    Buttons for Pulling and Pushing changes between the local and remote repositories

First, it's good to use :code:`git pull` (button with arrow down) to double check for remote changes before contributing your own changes.

.. figure:: img/git-plugin-pull-ok.png

In this case, the repository is probably up-to-date and no new changes are downloaded. However, it is good practice to always use git pull before publishing your local changes in case someone made changes in the remote repository in the meanwhile!

Now we are ready to push the local changes to GitHub using :code:`git push` (button with arrow up):

.. figure:: img/git-plugin-push-ok.png

Now you should see the updates in GitHub! Go and have a look at your personal repository in https://github.com/Geo-Python-2023/ .

On the command line, ``git pull`` fetches and merges changes from the remote repository, and ``git pull`` publishes local changes.

That's all you need to know about Git for now :)

Git from the command line
-------------------------

There are many different ways of using Git, and you might want to try out using Git from the command line at some point.

Terminal
~~~~~~~~

.. note::
    You will need to know a couple of basic command line commands in order to use Git from the command line. Code Academy's `list of command line commands <https://www.codecademy.com/articles/command-line-commands>`__ provides
    a good overview of commonly used commands for navigating trough files on the command line. For using Git on the command line, you should at least be familiar with these commands:

    - ``ls`` - list contents of the current directory
    - ``ls -a`` - list contents of the current directory including hidden files
    - ``cd`` - change directory. For example, ``cd exercises``
    - ``cd ..`` - move one directory up


**Start a new Terminal session in JupyterLab** using the icon on the Launcher, or from *File* > *New* > *Terminal*.

.. figure:: img/terminal-icon.png

**Check if you have git installed** by typing :code:`git --version` in the terminal window:

.. code-block:: bash

    git --version

Anything above version 2 is just fine.

.. note::

    You can paste text on the terminal using :code:`Ctrl + V` or :code:`Shift + Right Click --> paste`

Configuring Git credentials
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Configure Git to remember your identity using the ``git config`` tools. You (hopefully) only need to do this once
if working on your own computer, or on a cloud computer with persistent storage on CSC notebooks.

.. code-block:: bash

    git config --global user.name "[firstname lastname]"
    git config --global user.email "[email@example.com]"


Basic commands
~~~~~~~~~~~~~~

The basic workflow of cloning a repository, adding changes to the staging area, committing and pushing the changes can be completed using these command line commands:

- ``git clone [url]`` - retrieve a repository from a remote location (often from GitHub)
- ``git status``- review the status of your repository (use this command often!)
- ``git add [file]`` - add files to the next commit (add files to the staging area)
- ``git commit -m "[descriptive message]"`` - commit staged files as a new snapshot
- ``git pull`` - bring the local branch up to date (fetch and merge changes from the remote)
- ``git push`` - transmit local branch commits to the remote repository

.. note::

    Remember to use ``git status`` often to check the status of our repository.

.. admonition:: Other useful Git commands

    Check out other commonly used git commands from `the GIT CHEAT SHEET <https://education.github.com/git-cheat-sheet-education.pdf>`__

.. admonition:: Remote repository

    Remote repositories are versions of your project that are hosted on a network location (such as GitHub).
    When we cloned the repository using ``git clone``, Git automatically started tracking the remote repository from where we cloned the project.
    You can use the ``git remote -v`` command to double check which remote your repository is tracking.

    **A common mistake during this course is that you have accidentally cloned the template repository in stead of your own/your teams repository.**

    `Read more about managing remotes <https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes>`__.

.. admonition:: Main branch

    **Branches and branching** are powerful features in Git that allow maintaining parallel versions of the same project.
    During this course you don't need to worry too much about branches. However, it is good to understand that **we are working on the main branch of our repository**. For example, when using the ``git push`` command,
    the full syntax is ``git push origin main`` which means that we are pushing the changes to the main branch of the remote repository called origin. `Read more about git branches <https://git-scm.com/docs/git-branch>`__.


Resolving conflicts
-------------------

It is possible that you will encounter a **merge conflict** at some point of this course. A merge conflict might happen if two users have edited the same content, or if you
yourself have edited the same content both on GitHub and locally without properly synchronizing the changes. In short, Git will tell you if it is not able to sort out the version history of your project by announcing a merge conflict.

We won't cover how to solve merge conflicts in detail during the lessons. You can read more about `how to resolve merge conflicts from the Git documentation <https://git-scm.com/docs/git-merge#_how_to_resolve_conflicts>`__.
**The best thing to do to avoid merge conflicts is to always Pull before you Push new changes.**
In case you encounter a merge conflict, don't panic! Read carefully the message related to the merge conflict, and try searching for a solution online and ask for help on Slack.

Remember that you can always download your files on your own computer, and upload them manually to GitHub like we did in Exercise 1!

.. figure:: https://imgs.xkcd.com/comics/git.png
    :alt: https://xkcd.com/1597/

    Source: https://xkcd.com/1597/



Summary
-------
After this lesson you should be able to do these steps in JupyterLab using git and the JupyterLab git-plugin:

1. `Clone a repository from GitHub`_
2. `Add changes`_
3. `Commit changes`_
4. `Push changes to GitHub`_

These steps can be completed either using the `JupyterLab git plugin`_ (we recommend this option for beginners) or using
`Git from the command line`_.