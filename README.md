# pt

Minimal client to use Pivotal Tracker from the console.

## Setup
If using Ruby 2.0.0 - ensure your Ruby version is >= `ruby-2.0.0-p451`. If not, run `rvm install ruby-2.0.0-p451`.

Run `bundle install` to install gem dependencies.

Run `./install.sh`. This will create symlink to `/usr/local/sbin/pt`, so that you have `pt` in your $PATH.

The first time you run it, `pt` will ask you some data about your Pivotal Tracker account API key.

Run it from inside your project directory and it will ask you to pick project from PT corresponding with your work. It will save project id inside your project directory in `.pt` file, so that `pt` will refer to this project every time you will run it from inside project's directory.

File with you username and API key will go to `~/.pt`.

## Install ZSH completion plugin

Copy / link `completions/_pt` to your completions dir.

If using Oh My ZSH:

	cp ./completions/_pt ~/.oh-my-zsh/completions/_pt

Run:

	compinit;unfunction _pt;autoload _pt

## Usage

Run `pt` from the root folder of your project.

- `pt` - show all available tasks
- `pt todo` - show all your not finished tasks
- `pt started [user]` - show (all|user's) started stories
- `pt show [id]` - shows detailed info about a task
- `pt list [user|all]` - list tasks for user or all task
- `pt updates [number]` - shows number recent activity from your current project
- `pt open [id]` - open a task in the browser
- `pt start [id]` - mark a task as started
- `pt finish [id]` - indicate you've finished a task
- `pt deliver [id]` - indicate the task is delivered



## Not tested commands

**They can be fixed and prepared if believed to be useful.**

pt create    [title] <owner> <type> -m     # create a new task (and include description ala git commit)


pt tasks     [id]                          # manage tasks of story

pt assign    [id] <owner>                  # assign owner

pt comment   [id] [comment]                # add a comment

pt label     [id] [label]                  # add a label

pt estimate  [id] [0-3]                    # estimate a task in points scale




pt accept    [id]                          # mark a task as accepted

pt reject    [id] [reason]                 # mark a task as rejected, explaining why

pt done      [id]  <0-3> <comment>         # lazy mans finish task, opens, assigns to you, estimates, finish & delivers

pt find      [query]                       # looks in your tasks by title and presents it

pt updates   [number]                      # shows number recent activity from your current project

pt recent                                  # shows stories you've recently shown or commented on with pt

All commands can be run entirely without arguments for a wizard based UI. Otherwise [required] <optional>.
Anything that takes an id will also take the num (index) from the pt command.

## Problems?

You can [open a new issue](https://github.com/raul/pt/issues/new). It can be helpful to include a trace of the requests and responses you're getting from Pivotal Tracker: you can get it by adding the `--debug` parameter while invoking `pt` (remember to remove all sensible data though).

# Contributors
- [orta therox](http://orta.github.com) (Current maintainer)
- [Raul Murciano](http://raul.murciano.net) (Original author)
- [Anthony Crumley](https://github.com/craftycode)
- [Johan Andersson](http://johan.andersson.net)

## Thanks to...
- the contributors mentioned above and all the issue reporters
- the [Pivotal Tracker](https://www.pivotaltracker.com) guys for making a planning tool that doesn't suck and has an API
- [Justin Smestad](https://github.com/jsmestad) for his nice `pivotal-tracker` gem
- [Bryan Liles](http://smartic.us/) for letting me take over the gem name

## License
See the LICENSE file included in the distribution.

## Copyright
Copyright (C) 2013 Orta Therox <orta.therox@gmail.com>.
Copyright (C) 2011 Raul Murciano <raul@murciano.net>.
