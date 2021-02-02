# zsh-cmd-status
ZSH plugin to report the status of commands including return code and time taken (duration).

This plugin will report the return code of the previously run command if it returns nonzero.
It will report the time taken to run the command if its greater than the duration threshold
([ZSH_CMD_STATUS_DURATION_THRESHOLD](#config)).

## Examples

```
> false

returned 1
```

```
> sleep 10

took 10s
```

```
> sleep 11 && false

returned 1 & took 11s
```

```
> grep
usage: grep [-abcDEFGHhIiJLlmnOoqRSsUVvwxZ] [-A num] [-B num] [-C[num]]
	[-e pattern] [-f file] [--binary-files=value] [--color=when]
	[--context[=num]] [--directories=action] [--label] [--line-buffered]
	[--null] [pattern] [file ...]

returned 2
```



## Config
| Option env var                    | Default | Description                                                 |
| --------------------------------- | ------- | ----------------------------------------------------------- |
| ZSH_CMD_STATUS_DURATION_THRESHOLD | 10      | time in seconds under which duration should not be reported |
