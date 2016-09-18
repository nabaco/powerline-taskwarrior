Powerline Taskwarrior
===================

The set of the [Powerline][1] segments for showing information from the [Taskwarrior][2] task manager.

It will show current context and the most urgent active task.

![screenshot][4]

Requirements
------------

The Taskwarrior segments require [task][2] of version 2.4.2 or higher.

Installation
------------

Installing the Taskwarrior segments can be done with pip:

```txt
pip install powerline-taskwarrior
```

On Debian (testing or unstable), installation can be performed with apt:

```txt
apt install python-powerline-taskwarrior
```

Then you can activate the Taskwarrior segments by adding it to your segment configuration,
for example in `~/.config/powerline/themes/shell/default.json`:

segment displays current context name
```json
{
    "function": "powerline_taskwarrior.context",
    "priority": 70
}
```

segment displays the most urgent active task
```json
{
    "function": "powerline_taskwarrior.active_task",
    "priority": 70
}
```

segment displays the most urgent next task
```json
{
    "function": "powerline_taskwarrior.next_task",
    "priority": 70
}
```

obsolete segment displays both of listed above
```json
{
    "function": "powerline_taskwarrior.taskwarrior",
    "priority": 70
}
```

Configuration
-------------
If you have custom name for `task`, you should specify it in segment configuration.
`powerline_taskwarrior.active_task` and `powerline_taskwarrior.next_task` segments accept `description_length` parameter.
It's maximum length of description. If the description is longer, it is truncated by words.
`powerline_taskwarrior.next_task` segment accepts `ignore_active` parameter. If it set to `true` segment will be shown
always, regardless of existence active task.
```json
{
    "function": "powerline_taskwarrior.next_task",
    "priority": 70,
    "args": {
        "task": "taskwarrior",
        "description_length": 40
    }
}
```

License
-------

Licensed under [the MIT License][5].

By [German Lashevich][3].

[1]: https://powerline.readthedocs.org/en/master/
[2]: http://taskwarrior.org/
[3]: https://github.com/zebradil
[4]: https://github.com/zebradil/powerline-taskwarrior/blob/master/screenshot.png
[5]: https://github.com/zebradil/powerline-taskwarrior/blob/master/LICENSE
