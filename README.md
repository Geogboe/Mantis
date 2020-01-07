# Mantis - [WORK IN PROGRESS - Planning phase]

A tools to automate your breaks.

## Overview

Mantis is a tool which helps you take breaks from working. The basic pseudoscience behind the idea is that, when you're really involved in a project it may be too difficult to remember to step away and take a break. Tools such as timers and alarms are neat but can be too easily dismissed. More drastic actions needs to be taken to remove your work's grip on your soul. Meet Mantis, a tool designed to help you escape the pull of work by allowing you to schedule automatic shut down or sleep of your computer at a given time in the future. This immediate and and often painful transition is generally enough to snap one out of their flow. Then, the following (often painful) re-engagement process with the activity is usually daunting enough to force folks to go take a break before getting back to work and not immediately powering the box back on.

Note: For some folks it might be best to force close all running applications and shutdown rather then simply putting the computer to sleep. This forces the startup process to be a little slower and may be daunting enough to preventy you from going back to work immediately.


## Why?

Why not just use shutdown.exe? -- Because it's boring.

Backstory: Well, one day I was working on my laptop (which has a terrible battery) and it shut down about an hour to an hour and a half into my work. This was annoying but had the unintended consequence of forcing me to take a break from my work while I hunted for a charger and power outlet. This process repeated over time and I began to realize that this 1 to 1 1/2 hour break was actually helping me refresh and reset. Every time I resumed work after these break I had a clearly head, was more focused, and could properly re-evaulate what I was doing.


## Installation

Mantis is a single cmdline exectuable. You can either download it directly from GitHub or you can install the package using the Chocolatey package manager for Windows.

To install using Chocolatey:
```
choco install mantis
```

To uninstall:
```
choco uninstall mantis
```

## Usage

Calling the built in help will display how to use this tool.
```
mantis --help

mantis gotosleep        Intiate a sleep or shutdown event at a given time in the future
mantis list             List all currently scheduled shutdown or sleep events
mantis remove           Remove a given scheduled shutdown or sleep event by ID
```

#### Examples

Force computer to go to sleep at a given time:
```
mantis gotosleep --time "14:30:00"
```

Force computer to go to sleep in a specified amount of time:
```
mantis gotosleep --in "00:30:00"
```

Force computer to shutdown at a given time:
```
mantis gotosleep --shutdown --time "14:30:00"
```

List all scheduled shutdown or sleep events:
```
mantis list
```

Example output:
```
id          |           event               |           time
-------------------------------------------------------------
1           |           shutdown            |           "14:30:00"
2           |           sleep               |           "12:12:00"
...
```

Remove a given shutdown event
```
mantis remove --id 1
```

## Development

Work in progress