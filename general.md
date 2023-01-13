---
layout: default
---

# Assignments - General Guidance

## Setup a Python 3 Environment

The five programming assignments must be written in Python 3 and run
correctly on the CSE student machines.  (student00-07.cse.nd.edu)
If you prefer to do your development work on your laptop or another
machine, that's ok, but then you are responsible for setting up the appropriate
environment, and then ensuring that your work functions on the student machines.

The student machines have Python 3.6.8 installed by default,
which is a little on the old side.
For this class, you will need to set up
your own environment with the correct version.
(Other classes may require different versions.)

First, log into one of the student machines:

```
ssh <netID>@student00.cse.nd.edu
```

Where `<netID>` is your Notre Dame netID. Use your account password as student machine login password.

Then, download and install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) for Linux, if you haven't done so for another class:

```
curl https://repo.anaconda.com/miniconda/Miniconda3-py39_4.10.3-Linux-x86_64.sh > miniconda.sh
chmod 755 miniconda.sh
./miniconda.sh
```

Note: please enter `yes` for the last step of installation (initialize), which adds `conda` to `PATH`.

Once Conda is installed, you should log out and log back in.
Notice that your prompt should now have the prefix `(base)`,
which indicates you are in the `base` Conda environment.

Now, create an environment `distsys` just for this class:

```
conda create --name distsys python=3.9
```

Then, whenever you are working on this class, activate the `distsys`
environment, and you will have the right version of Python:

```
(base) dthain@student02$ conda activate distsys
(distsys) dthain@student02:~$ python -V
Python 3.9.6
```

To switch back to the default environment for another class,
 use `conda deactivate` one or more times, until your prompt is clean:

```
(distsys) dthain@student02$ conda deactivate
(base) dthain@student02$ conda deactivate
dthain@student02:~$ python -V
Python 2.7.5
```

When your prompt is clean, you are out of any Conda environment, using the original version of Python on the student machine.
Now you may use `conda activate` or `conda activate base` to go back to `base` Conda environment.
Similarly, as long as you have created `distsys`, you may use `conda activate distsys` to go to `distsys` Conda environment directly, which skips `base`.

## Focus on Standard Libraries

The general approach for solving the programming assignments in this class is to
learn how to use the basic Python language and standard libraries to build up
complex systems.  This will help you to understand these capabilities in detail
and develop the skills for building new libraries of your own.

To that end, you should become intimately familiar with the [standard library documentation](https://docs.python.org/3.9/library/index.html).  These modules in particular will be helpful:

- [File and Directory Access](https://docs.python.org/3.9/library/filesys.html)
- [subprocess](https://docs.python.org/3.9/library/subprocess.html)
- [time](https://docs.python.org/3.9/library/time.html)
- [json](https://docs.python.org/3.9/library/json.html)
- [http.client](https://docs.python.org/3.9/library/http.client.html)
- [socket](https://docs.python.org/3.9/library/socket.html)
 
Now, there do exist various additional packages and libraries that provide
implementations of some of the techniques that we discuss: remote procedure call,
consensus, persistence, and so forth.  However, we won't be using those, because
simply "installing package X" doesn't lead to any new understanding or experience.
If you find yourself trying to solve a technical problem by installing a new 
Conda package, then you are probably taking the wrong approach to the assignment.  Talk to the instructors to see if there is a better way.

On a related note, exercise care when searching for solutions online.
Q&amp;A sites like Stack Overflow can be helpful when trying to understand
obscure error messages, or find the right standard library to use.
However, don't just uncritically copy a bit of code that you find:
it may be solving a different problem, it may be an "advertisement" for someone's
favorite package, or it may not work at all.  Use that solution as a "clue"
to read the documentation for that particularly function or library, so that
you can understand how to use it yourself.

## Turning in Assignments

To turn in each assignment, simply copy the requested materials into your dropbox directory on the student machines.
Typically, this includes your source code and a written report.  Please do not turn in temporary files or large objects
unless specifically requested.

For example, the dropbox for assignment one is here:

```
/escnfs/courses/sp23-cse-40771.01/dropbox/NETID/a1
```

Graduate students enrolled in 60771 use this directory instead:

```
/escnfs/courses/sp23-cse-40771.01/dropbox/NETID/a1
```

Substitute your netid and the appropriate assignment number as needed.

Note that the dropboxes are just plain old directories.  So, you can submit preliminary work at an early time and update it later if needed.  It's recommended that you `ls -l` the dropbox after submission, so you can verify that you submitted what you meant to.
