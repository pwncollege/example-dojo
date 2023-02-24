# Example Dojo

This repositories features an example dojo.

The dojo is defined by [dojo.yml](./dojo.yml).

It contains two modules, `hello` and `world`.

The module `hello` features challenges `apple` and `banana`.

The module `world` features challenges `earth`, `mars`, and `venus`.

Each challenge demonstrates different challenge definition capabilities, in an increasing order of feature complexity.

See each challenge's README for further information:
- [apple](./hello/apple)
- [banana](./hello/banana)
- [earth](./world/earth)
- [mars](./world/mars)
- [venus](./world/venus)

## Importing Modules and Challenges

For an example of how you can import another dojo's challenges, see: [pwncollege/example-import-dojo](https://github.com/pwncollege/example-import-dojo).

## Automatically Updating Dojo

For instructions on how you can setup automatic dojo updates, using GitHub actions, see: [pwncollege/dojo-update](https://github.com/pwncollege/dojo-update).

## Challenge Writing Laws

### The Flag

The flag is located at `/flag`, and is only readable by `root`. 
The challenge will execute as `root`.
Nothing else is true.

Do not assume any structure to the flag. 
It may or may not have a prefix/suffix. 
It may or may not be 50 bytes long.
These things WILL change, and if you rely on them, your challenge WILL break.

### The Challenge

The challenge is [`setuid`](https://en.wikipedia.org/wiki/Setuid).
This is how your challenge will execute as `root`.

What this *really* means:
- The process will run with an **effective** user of `root`.
- The process will run with a **real** user of `hacker`.

While an **effective** user of `root` is sufficient for opening the flag, there are some caveats.
When `/bin/sh` (which is linked to `/bin/dash`) is run under this, it will immediately set the **effective** user to the **real** user (unless the `-p` flag is provided).
This means that both the **effective** and **real** user will be `hacker`, and the flag will not be accessible.
This affects `system`, which ultimately just runs `/bin/sh`.

The challenge can rememedy this by explicitly setting the **real** user to the **effective** user:
```c
setreuid(geteuid(), -1)
```




