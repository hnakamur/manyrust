manyrust
========

An script to install multiple rust versions.
Currently this script is supported only for OSX.

## Install manyrust

Download the `manyrust`

```
mkdir ~/bin
curl -s -o ~/bin/manyrust https://raw.githubusercontent.com/hnakamur/manyrust/master/manyrust
chmod +x ~/bin/manyrust
```

Set `PATH` environment variable to include `~/bin`.
For `bash` users:

```
echo 'export PATH="$HOME/bin:$PATH"' >> ~/.bash_profilie
exec $SHELL -l
```

## Usage

### Install rust

Install the rust from the stable channel.

```
manyrust install
```

Install the rust from the beta channel.

```
manyrust install beta
```

Install the rust from the nightly channel.

```
manyrust install nightly
```

### The installed directory structure

You can change the root directory by setting the `MANY_ROOT` environment variable.

```
$MANYRUST_ROOT (default: $HOME/rust)
├── beta
│   ├── 1.2.0-beta.2
│   │   ├── etc
│   │   └── rust
│   └── current -> 1.2.0-beta.2
├── bin
│   └── rustup.sh
├── nightly
│   ├── 2015-07-14
│   │   ├── etc
│   │   └── rust
│   └── current -> 2015-07-14
├── stable
│   ├── 1.1.0
│   │   ├── etc
│   │   └── rust
│   └── current -> 1.1.0
└── tmp
```


### Set up for using rust

I recommend you to use [direnv]( https://github.com/direnv/direnv ).

Use the current version from the stable channel.

```
manyrust showcfg >> .envrc
direnv allow .
```

Use the current version from the nightly channel.

```
manyrust showcfg nightly >> .envrc
direnv allow .
```

Use the specific version from the nightly channel.

```
manyrust showcfg nightly 2015-07-15 >> .envrc
direnv allow .
```


## License
[Apache License, Version 2.0](http://opensource.org/licenses/Apache-2.0)
