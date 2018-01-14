# EMerge LOg Parser

Emlop parses emerge logs (as generated by [portage](https://wiki.gentoo.org/wiki/Project:Portage),
the [Gentoo](https://www.gentoo.org/) package manager) to yield useful info like merge history and
merge time prediction. It aims to be a faster, more accurate and more practical replacement of
[genlop](https://wiki.gentoo.org/wiki/Project:Perl).

## Installation

Until a proper release is made and an ebuild is writen and added to the main portage tree, follow
these steps to get emlop:

* Install [Rust](https://www.rust-lang.org/) via portage or [rustup](https://www.rust-lang.org/en-US/install.html).
* `cd` into emlop's git repo, and run `cargo install`.
* `cp ~/.cargo/bin/emlop /usr/local/bin` or some other system-wide PATH folder if you wish.

## Basic usage

    # See online help
    emlop -h
    emlop list -h

    # Show merge history and merge times
    emlop list
    emlop l gcc$

    # Show merge statistics
    emlop summary
    emlop s gcc$

    # Predict merge time for current merge
    emerge -rOp | emlop p

## Contributing

Thanks for using emlop :) Please create issues and send pull request via
[Github](https://github.com/vincentdephily/emlop). Emlop is licensed as GPLv3.

Emlop is at an early stage of development. There are plenty of bugs, missing features, and needed
refinements. I'm still rather new to Rust and using this as a learning project.