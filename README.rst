`FZF <https://github.com/junegunn/fzf>`_ Widgets for `Xonsh <http://xon.sh>`_
======================

.. image:: https://img.shields.io/badge/License-GPL%20v3-blue.svg
   :alt: License
   :target: http://www.gnu.org/licenses/gpl-3.0

.. image:: https://img.shields.io/pypi/v/nine.svg
   :alt: Pypi version
   :target: http://pypi.python.org/pypi/xontrib-fzf-widgets


This extension will add some fzf widgets to your xonsh shell that you can bind and use as follows:

.. figure:: https://raw.githubusercontent.com/shahinism/xontrib-fzf-widgets/master/docs/cast.gif
   :alt: Screencast

Current widgets
----------------

- **ssh:** Search in `/etc/ssh/ssh_config` or `~/.ssh/config` items and issue `ssh` command on the chosen item.
- **history insert:** Search in all history entries and insert the chosen command to the prompt.
- **find file:** Find one or more files in the current directory and its sub-directories.
- **find directory:** Similar to the previous one, but intended to only search for directories.

How to use it
----------------

Install the package:

.. code-block:: sh

   pip install xontrib-fzf-widgets

Enable it by adding `fzf-widgets` to your `~/.xonshrc` file:

.. code-block:: python

    xontrib load fzf-widgets

And set your desired keybindings for each widget in `~/.xonshrc` file or set it to `None` to disable it:

.. code-block:: python

    $fzf_history_binding = "c-r"  # Ctrl+R
    $fzf_ssh_binding = "c-s"      # Ctrl+S
    $fzf_file_binding = "c-t"     # Ctrl+T
    $fzf_dir_binding = "c-g"      # Ctrl+G

Other configuration variables:

- ``$fzf_find_command``: A command used by `fzf` to search for files.
- ``$fzf_find_dirs_command``: A command used by `fzf` to search for directories.

.. code-block:: python

    $fzf_find_command = "fd"
    $fzf_find_dirs_command = "fd -t d"

You can find the names of various keys here_ in ``python-prompt-toolkit``.

.. _here: https://github.com/jonathanslenders/python-prompt-toolkit/blob/master/prompt_toolkit/keys.py
