# ACE — The Answer Constraint Engine

ACE is an efficient processor for [DELPH-IN](https://delph-in.github.io/) HPSG grammars, supporting parsing, generation, and transfer. It was written by Woodley Packard beginning in 2004 and publicly released in 2011 under the MIT License.

This repository is a Git mirror of the ACE source code, originally distributed via SVN at `sweaglesw.org`. It exists because the original source is hosted on a single personal server with no redundancy and no version control visibility. The initial commit corresponds to the SVN trunk as of the 0.9.34 release (January 2021), the last known release.

## Features

- **Parsing** with REPP, built-in POS tagging, token mapping, lexical filtering, and idiom checking
- **Generation** with trigger rules, index accessibility filtering, and post-generation subsumption testing
- **Transfer** via LOGON-style transfer grammars
- **[incr tsdb()]** support for distributed processing and benchmarking
- **Selective unpacking** with max-ent ranking
- **MRS** input/output with VPM support

ACE's parsing and generation performance is approximately 15x faster than the LKB and comparable to PET.

## Building

ACE is written in pure C. It requires [REPP](http://sweaglesw.org/linguistics/repp-0.2.2.tar.gz) as a build dependency.

```bash
# Linux
make

# macOS (see MacOSX.config)
make -f MacOSX.config
```

## Usage

```bash
# Compile a grammar
./ace -g path/to/config.tdl -G grammar.dat

# Parse
echo "The dog barks." | ./ace -g grammar.dat -n 5

# Generate
echo '<MRS string>' | ./ace -g grammar.dat -e
```

See `doc/options.wiki` and `doc/config.wiki` for full documentation.

## Precompiled Grammar Images

Precompiled images for the [English Resource Grammar](https://github.com/delph-in/erg) are available at [sweaglesw.org](http://sweaglesw.org/linguistics/ace/download/) (while the site remains accessible) and via [ERG GitHub releases](https://github.com/delph-in/erg/releases).

## License

MIT License. See [LICENSE](LICENSE) for details.

## Origin

ACE was created by Woodley Packard. This repository is a community preservation fork — not affiliated with the original author. The original ACE website is at [sweaglesw.org/linguistics/ace](http://sweaglesw.org/linguistics/ace/).
