s3cmdw
======

A project-level-config-aware wrapper for s3cmd (http://s3tools.org/usage).

Why?
----

s3cmd always looks for its S3 access/configuration at `$HOME/.s3cfg`. However, individual projects often have their own S3 credentials and may need project-specific settings. s3cmd requires a `--config=/path/to/.s3cfg` passed with each command to support this.

s3cmdw travels up your directory tree to detect your project-level config file and calls s3cmd with it, passing on your additional arguments directly. Right now, it looks for .s3cfg and .s3/s3cmd.conf (the format used by [Sculpin](https://sculpin.io/)).

Installation
------------

Place s3cmdw in a directory in your $PATH, such as $HOME/bin. From that directory, run `chmod +x s3cmdw`. Reload your bash profile, e.g., `source ~/.bash_profile`, and you should now be able to run commands like `s3cmdw ls` and use the appropriate config file.

Contributing
------------

If you would like another config format to be supported, or would like to fix a big or add another feature, please patch and submit or add an issue on Github.