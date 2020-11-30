# Frozen Tasks

Welcome to Frozen Tasks, a Visual Studio Code extension to help an individual manage tasks using plain text files and a small set of rules. It is based on the principles of [Bullet Journaling](https://bulletjournal.com/), and inspired by the excellent extension [TODO+](https://marketplace.visualstudio.com/items?itemName=fabiospampinato.vscode-todo-plus).

The basic premise is to provide a consistent interface for an individual to manage thier tasks. Bullet Journaling provides not only an uniform interface for day-to-day task lists, but also workflows for managing tasks over time. The magic is the simplicity within this system that it easily works with on paper using loose sheets in a binder or a journal. Frozen Tasks goal is to continue in this vein of simplicity, but provide an interface to do so via vscode. One challenge faced when using bullet journaling on physical media is that indexing and searching can be very challenging when using this system to manage tasks for work.

## Features

* Based upon wonderful Bullet Journaling methodology by Ryder Carroll
* All data kept in text files
* Uses a simple notation set (minor extension of the official bullet journaling ones)
* Support for daily, monthly, future, and custom logs
* Simple tagging to improve searching
* Migration workflows to help manage tasks between the various logs

### Notation

Frozen Tasks files are build on the premise that they will be readable plain text files. Thus, the frozentasks extension isn't required, but hopefully it helps usability. The basic notation used for frozen task files is:

     *  A task
     >  A migrated task to a different log, such as month, day (where)
     <  A migrated task to the future log (date)
     x  A completed task
     o  An event
     -  A note
    --- A cancelled task or event
    !*  An important task
     ?  A question task
    |*  A blocked task (@person)
     => Item asigned to another @person
    <=  Response from another @person

Tasks, events, and notes can be nested to indicate their relationship.

     *  A main task
         *  A sub task
         -  A sub note
         o  A sub event

Any text that isn't a header may contain tags. Tags are identified as text that begins with the '@' symbol. Tags help when searching through frozentask documents, thus they are used to identify such things as people, organizations, projects, etc.

There is also a set of priority tags: @low, @medium, @high, @urgent that can be included to help prioritize tasks.

     *  This is a task with a tag of a person named @Joe
     *  This is a task with @high priority

## Install

To come...

## How to Use

To come...

## Extension Settings

To come...

## Known Issues

To come...

## Releases

To come...
