# world
## venus

This challenge is named `venus`, and is located within module `world`.

When users start this challenge, their environment will have:
- `/flag`
- `/challenge/takeoff`
- `/challenge/launch`

In this challenge, `takeoff` is a statically instanced file.
There is also files `.init`, `planets.txt`, and `launch.template` which students will never see.
At run time, `.init` reads in `planets.txt` to construct `launch` from the templated file `launch.template`.
This gives the challenge static instancing dependent upon the flag.
In general, it is best to define a pool of static instanced files prior, so that this setup does not need to be performed at runtime every challenge start.
However, for simple cases, this may be acceptable.
It is important to note, however, that the results of these static instances are still dependent upon the flag, which means running the challenge with a different flag (e.g. with a practice flag), will change the behavior of the instance.
