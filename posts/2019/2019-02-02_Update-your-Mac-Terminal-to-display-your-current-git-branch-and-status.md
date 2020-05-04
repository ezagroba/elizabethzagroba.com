.. title: Update your Mac Terminal to display your current git branch and status
.. date: 02 February 2019
.. tags: git, terminal, Mac, testing


**TLDR; You can copy [all the code from my github](https://github.com/ezagroba/bash-profile-branch-and-color/blob/master/export-PS1.gist).**

<p name="0fd7" id="0fd7" class="graf graf--p graf-after--h3">I spent the better part of a crafting day at the office updating my <code class="markup--code markup--p-code">.bash_profile</code> on my Mac. If I’m in a git repository, with every command prompt, I see the branch name and an asterisk if there are un-committed changes. The original prompt for the machine, the repository name, and the branch name each appear in different colors. Here’s what it looks like:</p>

![](/images/posts/2019/command-prompt.png)

<p name="47d3" id="47d3" class="graf graf--p graf-after--figure">It may look like this one line in my <code class="markup--code markup--p-code">.bash_profile</code> file is where the magic happens, because this is where the colors are set:</p>

```bash
export PS1="\[\033[36m\]\u\[\033[32m\]\w\[\033[33m\]\$(git_branch)\$(parse_git_dirty)\[\033[00m\]$"
```
![](/images/posts/2019/colors.png)

<p name="c9ba" id="c9ba" class="graf graf--p graf-after--figure">Unfortunately the colors, branch, and status still need to be variously activated and calculated. 

<p>This function calculates if the branch has new changes:</p>

```javascript
function parse_git_dirty {
  [[ -n "$(git status -s2> /dev/null)" ]] && echo "*"
}
```

<p name="b7b9" id="b7b9" class="graf graf--p graf-after--figure">The last thing is fetching the branch name:</p>

```bash
git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -d 's/* \(.*\)/ (\1)/'
}
```

<p name="5ccd" id="5ccd" class="graf graf--p graf-after--figure">It took a lot of internet searching and help from colleagues to set it up. I had the git status and the branch name going separately, but combining them failed. Typing past the width of the window in the command prompt would send text to overwrite the current line instead of wrapping onto a second. <a href="https://askubuntu.com/questions/24358/how-do-i-get-long-command-lines-to-wrap-to-the-next-line" data-href="https://askubuntu.com/questions/24358/how-do-i-get-long-command-lines-to-wrap-to-the-next-line" class="markup--anchor markup--p-anchor" rel="noopener" target="_blank">This solved that for me</a>. <a href="http://jafrog.com/2013/11/23/colors-in-terminal.html" data-href="http://jafrog.com/2013/11/23/colors-in-terminal.html" class="markup--anchor markup--p-anchor" rel="noopener" target="_blank">There are also other color options</a>. The slashes <code class="markup--code markup--p-code">\</code> help end commands, but it was a lot of trial and error to get them all in the right spots. I was editing my <code class="markup--code markup--p-code">.bash_profile</code> intially in Sublime; any plain-text editor would have worked. I moved to nano in the Terminal when I wanted to see the changes more quickly. I did still have to close all open Terminal sessions before seeing the latest changes.</p><p name="fb1a" id="fb1a" class="graf graf--p graf-after--p">This lovely command prompt doesn’t prevent every mistake, but it does help call my attention to the status so I don’t:</p><ul class="postList"><li name="412e" id="412e" class="graf graf--li graf-after--p">open the wrong repository (easy to do when you’re migrating from one to another)</li><li name="9c89" id="9c89" class="graf graf--li graf-after--li">try to commit before the changes are saved</li><li name="8694" id="8694" class="graf graf--li graf-after--li">commit to master instead of a branch</li></ul><p name="7824" id="7824" class="graf graf--p graf-after--li graf--trailing">If nothing else, I enjoy a bit of color in an interface that doesn’t have any to start.</p></div></div></section><section name="c8d0" class="section section--body section--last"><div class="section-divider"><hr class="section-divider"></div><div class="section-content"><div class="section-inner sectionLayout--insetColumn"><p name="6696" id="6696" class="graf graf--p graf--leading graf--trailing"><em class="markup--em markup--p-em">Thanks to Maik Nog for suggesting I share this in a more shareable format. It’s available on </em><a href="https://github.com/ezagroba/bash-profile-branch-and-color/blob/master/export-PS1.gist" data-href="https://github.com/ezagroba/bash-profile-branch-and-color/blob/master/export-PS1.gist" class="markup--anchor markup--p-anchor" rel="noopener" target="_blank"><em class="markup--em markup--p-em">github</em></a><em class="markup--em markup--p-em">.</em></p></div></div></section>
</section>

*Originally published on [Medium](https://medium.com/@ezagroba/update-your-mac-terminal-to-display-your-current-git-branch-and-status-471c017436a2).*
