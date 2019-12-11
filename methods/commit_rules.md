# Commit rules

Writing a good commit is far from being an easy task. This little guide
will help you to improve your commit messages by avoiding common pitfalls.

## Rules

Those rules are more tips than anything else, feel free to adapt them to your
needs or only pick some of them !

- [Commit length](#commit-length)
- [Commit tenses](#commit-tenses)
- [Commit meaning](#commit-meaning)
- [Commit theme](#commit-theme)

### Commit length

A commit should **not exceed 50 characters**. Instead of writing a long commit
message, consider improving its content below.

Instead of:

```text
Update the config file because the last one was causing issues on Ubuntu 19.10 and contained the wrong IP for the test server
```

Consider doing:

```text
Update config file

- Fix issues on Ubuntu 19.10
- Update server IP address
```

📑 _Please note that since 50 is pretty short, and to avoir making the message_
_harder to understand by burdening it, you generally should avoid adding a final_
_dot to your commit._

### Commit tenses

Your commit should be seen as a whole sentence, constructed as:
`If I apply this commit, it will (...)`

By using this method, your history will be much more readable. That's also why
you should **avoid past tenses and prefer the present**. (Try this method on the
following examples !)

Instead of:

```text
> Refactored the source code  <- If I apply this commit, it will refactored the source code
> Translated homepage         <- If I apply this commit, it will translated homepage
> Created MailService class   <- If I apply this commit, it will created MailService class
```

Consider doing:

```text
> Refactor the source code    <- If I apply this commit, it will refactor the source code
> Add homepage translation    <- If I apply this commit, it will add homepage translation
> Create MailService class    <- If I apply this commit, it will create MailService class
```

### Commit meaning

Don't forget that during your project, you will write plenty of commits and this
will build your whole history. That's why, whenever you have do dig up some old
feature push a month ago, it may be a living hell.

To avoid this, try to **write meaningful and concise commit messages**,
even if this seems obvious on the spot.

Instead of:

```text
> Fix bug
> Fix again
> Fix this time it will work
> anjfes,hlsef
```

Consider doing:

```text
> Fix wrong parameter type in MailService call
> Fix missing argument in MailService method
> Fix incorrect exit condition in MailService method
> Fix missing exit condition in MailService method
```

### Commit theme

This one is more like a personal tip. Reviewing tons of commits is not the most
pleasant task. Even when using the tips written previously, having dozens of
short lines of text is not a very inspiring thing.

To solve this, I suggest to **put a little tag in front of each commit message**
. My favorite way to use it is with emojis: it is pretty understandable by
anyone and only use one character on the 50 recommended. Moreover, each team
can build and use its own custom emoji list.

This is also a good way to go back to a specific moment (were you looking for
documentation ? Bug fixing ? etc.)

If you want a ready-to-use list, I suggest you to [check my emoji list](https://github.com/pBouillon/git_tutorials/blob/master/methods/emoji_commit_list.md)
which is limited to 10 emojis to avoid confusion among the team.

```text
> Add .gitignore file
> Create empty solution
> Add main method
> Add unit tests for the main class
> Fix incorrect assertion
```

Consider doing:

```text
> 🔧 Add .gitignore file
> 🌱 Create empty solution
> ✨ Add main method
> ✅ Add unit tests for the main class
> 🐛 Fix incorrect assertion
```
