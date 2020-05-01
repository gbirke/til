# Show diff while writing the commit messsage

Most of the time when writing a commit message in Vim, the default view of
changed files is exactly the information I need. Sometimes I want some text from my commit in my autocomplete or look again at what I did. Then I wish I had called `git commit` with the `--verbose` flag. Until now, the usual procedure to correct this would have been a tedious multi-step procedure:

1. delete the commit message with `:0,$d`. This will put the message in the paste register and the register will be there on the next Vim start, but it's always a bit scary.
2. Quit Vim. This will cause the commit to abort because the message is empty)
3. call `git commit --verbose`
4. Paste message with `P`. If I accidentally used `p` instead, I have to
   delete the first, empty line.

Next time I run into this situation, I will use the `:DiffGitCached`
command. This will show the diff in a separate Vim window (splitting the
commit message). I can look up what I need and even use `Ctrl-P` in my
commit message window for autocompletion!

Tip: Use `Ctrl-WJ` and `Ctrl-WK` to switch between the windows.

Thanks to https://stackoverflow.com/a/26457364/130121
