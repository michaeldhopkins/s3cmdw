s3cmdw
======

A project-level-config-aware wrapper for s3cmd (http://s3tools.org/usage) for use with Sculpin projects.

Why?
----

Sculpin's S3 deployment script can be configured to look for a project-level configuration file at `project_directory/.s3/s3cmd.conf`. However, s3cmd always looks for its configuration at `$HOME/.s3cfg` unless `--config=/path/to/project_directory/.s3/s3cmd` is present. 

s3cmdw travels up your directory tree to detect your project-level file and calls s3cmd with it, passing on your additional arguments directly.

Installation
------------

Place s3cmdw in a directory in your $PATH, such as $HOME/bin. From that directory, run `chmod +x s3cmdw`. Reload your bash profile, e.g., `source ~/.bash_profile`, and you should now be able to run commands like `s3cmdw ls` and use the appropriate config file.