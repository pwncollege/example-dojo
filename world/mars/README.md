# world
## mars

This challenge is named `mars`, and is located within module `world`.

When users start this challenge, their environment will have:
- `/flag`
- `/challenge/orbit`
- `/challenge/planets.txt`

In this challenge, `orbit` reads in the flag and seeds random off of it.
While this is a challenge-specific detail, it is a broadly useful idea.
It allows for the challenge's behavior to be dynamically dependent on the flag.
This offers a similar paradigm to instanced challenge files.
However, it is dynamically instanced, rather than statically instanced.
Statically instanced values may be accessed by a student, while dynamically instanced values may not be (since they are dependent on the flag).
Which style is appropriate depends on the specifics of the challenge.
