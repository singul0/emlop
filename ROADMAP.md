# Emlop roadmap
This is a quick overview of what I'd like to eventually implement in emlop.
See the github issue tracker for actual bugs.

## Milestones
### 0.1
The first release has a very limited feature set, but provides a solid base to build on
(architecture, tests, logging, error handling...). Target audience is early adopters.

### 0.2
The next release will add polish, easy features that were left out of 0.1 to focus on getting it out
the door, and maybe one or two cherry-picked bigger feature. Target audience is every portage user.

### 0.x
Following releases can focus around specific features, bugfixes, and polish. Release when the're
something interesting. Hopefully we should be able to iterate quickly and safely at this stage.

Not sure if/when 1.0 should arrive.


## Todo
In no particular order and with no promises. Send a PR if you want one of these *now* ;)

### Testing
#### Use catname.txt
To better validate parsed ebuild category/name. Might just use category.
#### Unittest PretendParser
#### Unittest commands
Just a framework at least. Test cases can be added as bugs are found.
#### Misc
* More testcases
* https://github.com/killercup/assert_cli

### Refactoring
#### StructOpt crate
#### Failure crate
#### Proper logging

### Features
#### Optional --headers
#### `--utc` and `--local`timezone selection date output
#### Options to format dates and durations differently
#### `--mindate` and `--maxdate`
Ideally in both 'YYYY-MM-DD' and 'N days ago' formats.
#### Add color where it makes sense (if `tty` and not `--no-color`)
Color-coded durations would be nice.
#### Automatically run `emerge -rOp` for `predict`
#### Parse and optionaly display sync dates, unmerges, failed merges, etc
For the `list` command.
#### Write ebuild
And get it upstreamed ;)
#### Better/selectable prediction algorythm
Currently is just averaged over the last `--limit` times, but should probably be a weighted average.

One of the weight is obviously how recent a particular build is. The current algorythm is equivalent
to giving a weight of 1 to all builds within `--limit` and 0 to all others, but using a `log()`
function to assign weigths might be better.

Another weigth should probably be how close slot or the version is (for example, qtsvg:4 takes
longer to compile than qtsvg:5, but the older version is still regularly compiled on my system).

Using the mean might be better than the average, to take care of outlyers.
#### Json output
Because why not. Should also help with unit-testing.
#### Pull timings from gentoo.linuxhowtos.org for first-time emerge
Never used this in genlop, but I guess others will want the feature.
#### Extra package info (use flags, build env, first/last merge, etc)
Should go into the `summary` command.
#### Config file to set defaults
#### Benchmarks
AKA more speed. Not a huge issue as all release runs take < 0.5s, but debug runs and `cargo test`
could do with being faster.
#### Bash completion
Clap has something builtin.
