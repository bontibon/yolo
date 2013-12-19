# yolo

time tracker script to help track time

## Usage

If you don't have a task set, run either `yolo set <task description>` or `yolo set`, which will prompt you for a task.

    $ yolo set Take over the world
    2013/08/22 18:56:58 | Take over the world

    $ yolo set
    task: Take over the world
    2013/08/22 18:56:58 | Take over the world

Running `yolo` (or `yolo current`) will tell you what you're suppose to be working on.

    $ yolo
    Take over the world (started 55 seconds ago)

    $ yolo current
    Take over the world (started 55 seconds ago)

When you're done something, just run `yolo done`.

    $ yolo done
    Take over the world (completed in 22 seconds)

When you want to give up on a task, run `yolo abandon`.  Abandoned tasks will not be logged.

    $ yolo abandon
    Debug my current project (abandoned)

To review what you accomplished today, run `yolo today`.

    $ yolo today
    Finish assignment (completed in 34 minutes)
    Catch up on show (completed in 58 minutes)
    Listen to that song I like (completed in 4 minutes)

To review what you accomplished on a certain date, run `yolo on <time specification>`.
The time specification can be anywhere from a formatted date to english words as it uses `date -d`.

	$ yolo on yesterday
	Completed tasks for 2013/12/18:
	Finish assignment (completed in 34 minutes)
	Catch up on show (completed in 58 minutes)

Passing `--bare` to any command (except set) will not show any annotations along with the task (e.g. the "ago" time).

    $ yolo current --bare
    Do 20 push-ups

## Log file

The log file yolo writes to is either:

-  the file in the `YOLO` environment variable, or
- `~/.yolo`

A log file looks like the following:

    2013/08/22 15:57:53 - 2013/08/22 17:00:21 | Work on assignment
    2013/08/22 18:05:47 - 2013/08/22 19:49:50 | Watch TV show
    2013/08/22 19:55:32 | Debug this script

## Requirements

- [zenity][1] (for `yolo-gui`)

## License

[MIT][2] (see LICENSE).

[1]: https://wiki.gnome.org/Zenity
[2]: http://opensource.org/licenses/MIT
