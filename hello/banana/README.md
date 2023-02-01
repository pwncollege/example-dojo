# hello
## banana

This challenge is named `banana`, and is located within module `hello`.

When users start this challenge, their environment will have:
- `/flag`
- `/challenge/banana`
- `/chalenge/.config`

Within a challenge's definition, directories which begin with `_` are statically instanced.
Users will randomly, but deterministically, be assigned one instance of the challenge.
Every time they start the challenge, they will be assigned the same static instance.
This allows different users to receive different versions of the same challenge.
