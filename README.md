smartdel
========

`smartdel` is a tool to delete and restore files.

Usage
-----
`smartdel [option] filename`

Options
-------
``-d`` 
  Delete the file (not directory) specified by [filename]

``-r``
  Restore the file specified by [filename] to the current directory.

Description
-----------
The default option is –d, which means if you use `smartdel` without any option, 
`smartdel` will delete the file specified by [filename]. Please note that the operational 
scope of `smartdel` is inside  the current user’s home directory. I.e. `smartdel` does not 
delete/ restore file at /root, /bin, or other  non-user directories.
