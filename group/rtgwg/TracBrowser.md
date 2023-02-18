---
title: Trac Browser
description: 
published: true
date: 2022-12-22T20:42:43.604Z
tags: 
editor: markdown
dateCreated: 2022-12-22T20:29:16.839Z
---

# The Trac Repository Browser 

The Trac repository browser can be used to browse specific revisions of directories and files stored in the repositories associated with the Trac environment.

At the top-level of the repository browser is the **Repository Index**, listing all the configured repositories. Each repository has a name which is used as a path prefix in a "virtual" file hierarchy encompassing all the available repositories. One of the repositories can be configured with an empty name; this is the default repository. When such a default repository is present, its top-level files and directories are also listed, in a **Default Repository** section placed before the repository index. If the default repository is the only repository associated with the Trac environment, then the **Repository Index** will be omitted. This means that after upgrading a single-repository Trac of version 0.11 (or earlier) to a multi-repository Trac (0.12), the repository browser will look and feel the same, that single repository becoming automatically the "default" repository.

Directory entries are displayed in a list with sortable columns. The list entries can be sorted by *Name, Size, Age* or *Author* by clicking on the column headers. The sort order can be reversed by clicking on a given column header again.

The browser can be used to navigate through the directory structure by clicking on the directory names. Clicking on a file name will show the contents of the file. Clicking on the revision number of a file or directory will take you to the [TracRevisionLog](/group/rtgwg/TracRevisionLog) for that file. Note that there's also a Revision Log navigation link that will do the same for the path currently being examined. Clicking on the diff icon after revision number will display the changes made to the files modified in that revision. Clicking on the Age of the file - will take you to that changeset in the timeline.

It's also possible to browse directories or files as they were in history, at any given repository revision. The default behavior is to display the latest revision but another revision number can easily be selected using the View revision input field at the top of the page.

The color bar next to the Age column gives a visual indication of the age of the last change to a file or directory, following the convention that blue is oldest and red is newest, but this can be [configured](/group/rtgwg/TracIni).

At the top of the browser page, there's a Visit drop-down menu which you can use to select some interesting places in the repository, for example branches or tags. This is sometimes referred to as the browser quickjump facility. The precise meaning and content of this menu depends on your repository backend. For Subversion, this list contains by default the top-level trunk directory and sub-directories of the top-level branches and tags directories (`/trunk`, `/branches/*`, and `/tags/*`). This can be [configured](/group/rtgwg/TracIni) for more advanced cases.

If you're using a Javascript enabled browser, you'll be able to expand and collapse directories in-place by clicking on the arrow head at the right side of a directory. Alternatively, the [keyboard](https://trac.edgewall.org/wiki/TracAccessibility) can also be used for this:

- use `j` and `k` to select the next or previous entry, starting with the first
- `o` (open) to toggle between expanded and collapsed state of the selected directory or for visiting the selected file
- `v` (view, visit) and `<Enter>`, same as above
- `r` can be used to force the reload of an already expanded directory
- `a` can be used to directly visit a file in annotate (blame) mode
- `l` to view the log for the selected entry

If no row has been selected using `j` or `k` these keys will operate on the entry under the mouse.

For the Subversion backend, some advanced additional features are available:

- The `svn:needs-lock` property will be displayed.
- Support for the `svn:mergeinfo` property showing the merged and eligible information.
- Support for browsing the `svn:externals` property, which can be configured.
- The `svn:mime-type` property is used to select the syntax highlighter for rendering the file. For example, setting `svn:mime-type` to `text/htm`l will ensure the file is highlighted as HTML, regardless of the file extension. It also allows selecting the character encoding used in the file content. For example, if the file content is encoded in UTF-8, set `svn:mime-type` to `text/html;charset=utf-8`. The charset= specification overrides the default encoding defined in the `default_charset` option of the `[trac]` section of [trac.ini](/group/rtgwg/TracIni).

&nbsp;
&nbsp;
&nbsp;

---

*The content of this page was last updated on 2016-05-11. It was migrated from the old Trac wiki on 2022-12-22.*