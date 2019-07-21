# rtop

<div align="center">

*Another* TUI based resource monitor, this time in Rust! Currently a WIP.

</div>

## Usage

### Keybinds

- Quit: `q` or `<C-c>`
- Process navigation:
	- `k` and `<Up>`: up
	- `j` and `<Down>`: down
	- `<C-u>`: half page up
	- `<C-d>`: half page down
	- `<C-b>`: full page up
	- `<C-f>`: full page down
	- `gg` and `<Home>`: jump to top
	- `G` and `<End>`: jump to bottom
- Process actions:
	- `<Tab>`: toggle process grouping
	- `dd`: kill selected process or group of processes
- Process sorting:
	- `c`: CPU
	- `m`: Mem
	- `p`: PID
- Process filtering:
	- `/`: start editing filter
	- (while editing):
		- `<Enter>`: accept filter
		- `<C-c>` and `<Escape>`: clear filter
- CPU and Mem graph scaling:
	- `h`: scale in
	- `l`: scale out
- `?`: toggles keybind help menu

### Mouse

- click to select process
- mouse wheel to scroll through processes

### Colorschemes

rtop ships with a few colorschemes which can be set with the `-c` flag followed by the name of one. You can find all the colorschemes in the [colorschemes folder](./colorschemes).

To make a custom colorscheme, copy one of the default ones to `~/.config/rtop/<new-name>.json` and load it with `rtop -c <new-name>`. Colorschemes PRs are welcome!

### CLI Options

```
USAGE:
    rtop [FLAGS] [OPTIONS]

FLAGS:
    -a, --average-cpu    Show average CPU in the CPU widget.
    -b, --battery        Show Battery widget (overridden by 'minimal' flag).
    -f, --fahrenheit     Show temperatures in fahrenheit.
    -h, --help           Prints help information
    -m, --minimal        Only show the CPU, Mem, and Process widgets.
    -p, --per-cpu        Show each CPU in the CPU widget.
    -s, --statusbar      Show a statusbar with the time.
    -V, --version        Prints version information

OPTIONS:
    -c, --colorscheme <colorscheme>    Set a colorscheme. [default: default]
    -i, --interfaces <interfaces>      Comma separated list of network interfaces to show. Prepend an interface with '!'
                                       to hide it. 'all' shows all interfaces. [default: !tun0]
    -r, --rate <rate>                  Number of times per second to update the CPU and Mem widgets. [default: 1]
```
