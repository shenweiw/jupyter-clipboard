# Jupyter Clipboard

Use Jupyter's Comm mechanism to copy remote content to a local clipboard. Useful if you're running Jupyterhub!


## Installing (Live)

- `jupyter nbextension install --sys-prefix https://github.com/njwhite/jupyter-clipboard/archive/master.tar.gz`
- `jupyter nbextension enable --sys-prefix jupyter-clipboard-master/jupyter-clipboard/main`

## Installing (Dev)

Run (from the root of this repo)

- `jupyter nbextension install --symlink --sys-prefix jupyter-clipboard`
- `jupyter nbextension enable jupyter-clipboard/main --sys-prefix`

## From stackoverflow
I wrote a Jupyter nbextension to do this (installation instructions in the README).

It overwrites Panda's pandas.io.clipboard.copy & pandas.io.clipboard.clipboard_set (which is an embedded copy of pyperclip) to send messages to the Jupyter frontend via the Comm mechanism. I had to add a simple bootstrap-based UI that pops up when the client-side JS receives a message, as browsers won't let you push data onto the system clipboard without explicit user interaction (security!).
