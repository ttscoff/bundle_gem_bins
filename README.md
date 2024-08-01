
### Description

Creates a "bundle" file of all installed gems with executables. The resulting file is an executable script that can be run standalone, or in combination with this script to add options like `sudo` or `--user-install` to the `gem install` commands. These options can be specified when creating the file as well. A file created with `sudo` or `--user-install` commands can still be overridden when running via this script and `--install`.

Created file is called `Binfile` in the current directory unless another path is specified with `--file`.

### Installation

Save the script to a directory in your $PATH and make it executable with `chmod a+x bundle_gem_bins`.

### Usage

Run `bundle_gem_bins` to create a Binfile in the current directory. That file can optionally be made executable (you'll be prompted). In the future when doing a clean install or using a new system, you can just run that file to reinstall all of your gem binaries.

Using this script with the `--install` flag will read the Binfile and execute it line by line, adding options like version numbers, sudo, or the `--user-install` flag.

You can also run with subcommands `bundle` or `install`, e.g. `bundle_gem_bins install`.

```
Usage: bundle_gem_bins [options]
        --[no-]versions              Include version info in output (default true)
        --dry-run                    Output to STDOUT instead of file
    -s, --sudo                       Install gems with sudo
    -u, --user-install               Use --user-install to install gems
    -f, --file FILE                  Output to alternative filename (default Binfile)
    -v, --version                    Display version
        --install                    Run bundle script
    -h, --help                       Display this screen
```

