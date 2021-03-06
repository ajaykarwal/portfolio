---
  layout: post
  title:  Edit the Terminal Prompt name on macOS
  permalink: /edit-terminal-prompt-on-mac/
  artwork: 'terminal-prompt.jpg'
---

As a developer you're likely to spend a lot of time in the Terminal and may have already customised the appearance of it to suit you, but what about the prompt name?

The Terminal prompt name is the text that appears before the `$` sign. By default this is set to

```
HOST_NAME:USER_NAME CURRENT_DIRECTORY $
```

{% include image.html
  file="posts/terminal-1.png" 
  alt="Default Terminal prompt" 
  link="self"
  width="500"
%}

Depending on what you've named your computer, this can take up a lot of valuable real-estate on each line of the Terminal. In order to change this default prompt you will need to make a change to your `.bash_profile` file.

Open up a new Terminal window and type the command
```bash
$ cd ~/
```

This will ensure you're in your User Home directory. 

Type `ls -la` to show the contents of your Home directory and check if a `.bash_profile` exists.

If it does not exists, you can create one with the command
```bash
$ touch .bash_profile
```

## Changing your Terminal prompt

To edit the `.bash_profile` in your default text editor (TextEdit) use the command
```bash
$ open -e .bash_profile
```

If this is the first time you're editing this file, it should be empty. Add this line to the file and save.
```bash
$ export PS1="\u$ "
```

The `\u` flag sets the prompt to your User name (in my case, Ajay). Remember to keep a space after the `$` symbol to make things easier to read in practice.

Quit Terminal and relaunch to see your new prompt in action.

{% include image.html
  file="posts/terminal-2.png" 
  alt="Custom Terminal prompt" 
  link="self"
  width="500"
%}

## Options for customising the prompt

Here are a few common flags you can use to customize your Terminal prompt:

- `\d` – Current date
- `\t` – Current time
- `\h` – Host name
- `\#` – Command number
- `\u` – User name
- `\W` – Current working directory (ie: Desktop/)
- `\w` – Current working directory with full path (ie: /Users/Admin/Desktop/)

## Going further

There are several options for customising your Terminal prompt including custom strings, timestamps colours and even emoji 👉.

More information can be found on [OSX Daily](http://osxdaily.com/2006/12/11/how-to-customize-your-terminal-prompt/)
