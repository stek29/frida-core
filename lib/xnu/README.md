# FridaKernelAgent.kext

Experimental kernel driver for boosting Frida's capabilities on macOS:

- [Spawn-gating](https://gist.github.com/oleavr/ae7bcbbb9179852a4731)
- Attach to any process
- Improved stealth by avoiding `task_for_pid()`, which modifies the extmod stats

## Installation

1. Open `FridaKernelAgent.xcodeproj` and build it with Xcode
2. Review `reload.sh`, adjusting it to match your system
3. Run `reload.sh` to install and load the driver

To verify the installation, run this in a terminal:

```sh
$ cat /dev/frida
```

And you should see a real-time feed of all processes being spawned on
your system.

## Usage

The driver is used transparently by Frida >= 10.6.9 if `/dev/frida` is
available.
