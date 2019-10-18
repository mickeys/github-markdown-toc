# NAME

**children** — generates a Markdown tree list of child pages

# SYNOPSIS

**children** \[**-a**|**--all-filetypes**] [**-u**|**--untracked**] directory

# DESCRIPTION

Generate a graphical relative representation of the child files and subfolders, providing hyperlinks to certain documents. By default only Markdown documents which are being tracked by `git` are shown, with the Markdown document title as the hyperlink text. Options, below, modify the set of documents shown.

Filtered out of results are the `.git` directory (the working store of the revision management system) and all `.DS_Store` files (used by macOS for housekeeping).

# Options

-a, --all-filetypes

	Provide hyperlinks to every child file.

-u, --untracked

	Provide hyperlinks to files not tracked by git.

These options cannot be combined; `-au` is invalid.

# EXAMPLES

For a directory with the following contents:

```
./children.sh
./untracked.txt
./README.md
./tracked.txt
./dir/subdir/subsubdir/untracked-file.txt
./dir/subdir/subsubdir/tracked.txt
./dir/subdir/README.md
./dir/README.md
```

The command `children .` generates a tree diagram of only the Markdown files (with their document titles as the link text). This behavior is designed to make it easy to provide an index into a repository containing many Markdown files.

<!-- github-markdown-child-pages-start -->
&#9122; [github-markdown-child-pages](./README.md)<br>
&#9123; dir<br>
&nbsp;&nbsp;&nbsp;&nbsp;&#9122; [The Top Level](./dir/README.md)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&#9123; subdir<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9123; [Something Nested Within](./dir/subdir/README.md)<br>
<table><tr><td><small><i>Generated by <a href="https://github.com/mickeys/github-markdown-child-pages?ts=4">github-markdown-child-pages</a></i>.</small></td></tr></table>
<!-- github-markdown-child-pages-end -->

The command `children --all-filetypes .` generates a tree diagram of all the files tracked by git:

<!-- github-markdown-child-pages-start -->
&#9122; [github-markdown-child-pages](./README.md)<br>
&#9122; [./children.sh](./children.sh)<br>
&#9122; [./dir/](./dir/)<br>
&#9122;&nbsp;&nbsp;&nbsp;&#9122; [The Top Level](./dir/README.md)<br>
&#9122;&nbsp;&nbsp;&nbsp;&#9123; [./dir/subdir/](./dir/subdir/)<br>
&#9122;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9122; [Something Nested Within](./dir/subdir/README.md)<br>
&#9122;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9123; [./dir/subdir/subsubdir/](./dir/subdir/subsubdir/)<br>
&#9122;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9122; [./dir/subdir/subsubdir/tracked.txt](./dir/subdir/subsubdir/tracked.txt)<br>
&#9122; [./tracked.txt](./tracked.txt)<br>
<table><tr><td><small><i>Generated by <a href="https://github.com/mickeys/github-markdown-child-pages?ts=4">github-markdown-child-pages</a></i>.</small></td></tr></table>
<!-- github-markdown-child-pages-end -->
The command `children --all-filetypes --untracked .` generates a tree diagram of all files, whether tracked by git or not:

<!-- github-markdown-child-pages-start -->
&#9122; [github-markdown-child-pages](./README.md)<br>
&#9122; [NAME](./children.1.md)<br>
&#9122; [./children.sh](./children.sh)<br>
&#9122; [./dir/](./dir/)<br>
&#9122;&nbsp;&nbsp;&nbsp;&#9122; [The Top Level](./dir/README.md)<br>
&#9122;&nbsp;&nbsp;&nbsp;&#9123; [./dir/subdir/](./dir/subdir/)<br>
&#9122;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9122; [Something Nested Within](./dir/subdir/README.md)<br>
&#9122;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9123; [./dir/subdir/subsubdir/](./dir/subdir/subsubdir/)<br>
&#9122;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9122; [./dir/subdir/subsubdir/tracked.txt](./dir/subdir/subsubdir/tracked.txt)<br>
&#9122;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9123; [./dir/subdir/subsubdir/untracked-file.txt](./dir/subdir/subsubdir/untracked-file.txt)<br>
&#9122; [./tracked.txt](./tracked.txt)<br>
&#9123; [./untracked.txt](./untracked.txt)<br>
<table><tr><td><small><i>Generated by <a href="https://github.com/mickeys/github-markdown-child-pages?ts=4">github-markdown-child-pages</a></i>.</small></td></tr></table>
<!-- github-markdown-child-pages-end -->

<!--
# FILES
-->

<!--
# ENVIRONMENT
-->

<!--
# BUGS

See GitHub Issues: <https://github.com/[owner]/[repo]/issues>
-->

# INSTALLATION

Move the script to a location on your `$PATH` and ensure it's executable.

```
mv children.sh /usr/local/bin/children
chmod +x /usr/local/bin/children
```

Move the man page to a location on your `$MANPATH`.

```
mv children.1 /usr/local/share/man/man1/
```

# AUTHOR

[Michael Sattler](https://github.com/mickeys/)

<!--
# SEE ALSO
-->