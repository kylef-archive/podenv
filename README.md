# Pod Version Manager

podenv allows you to easily install, and switch between multiple versions of
CocoaPods, without managing Ruby.

<img alt="podenv screenshot" src="share/podenv.png" width=689 height=376 />

podenv allows you to:

- Change the **global CocoaPods version**, per user.
- Set a **per-project CocoaPods version**.
- Allows you to **override the CocoaPods version** with an environmental variable.

## Installation

**NOTE**: If you're on OS X, consider [installing with Homebrew](#via-homebrew).

### Via a Git clone

1. Check out podenv, we recommend `~/.podenv` (but it can be installed elsewhere as long as you set `PODENV_ROOT`).

    ```shell
    $ git clone https://github.com/kylef/podenv.git ~/.podenv
    ```

2. Configure environment.

    For Bash:

    ```shell
    $ echo 'export PATH="$HOME/.podenv/bin:$PATH"' >> ~/.bash_profile
    ```

    For ZSH:

    ```shell
    $ echo 'export PATH="$HOME/.podenv/bin:$PATH"' >> ~/.zshenv
    ```

    For Fish:

    ```shell
    $ echo 'setenv PATH "$HOME/.podenv/bin" $PATH' >> ~/.config/fish/config.fish
    ```

3. Restart your shell so the changes take effect.

### Via Homebrew

You can install podenv using the [Homebrew](http://brew.sh/) package manager
on OS X.

```shell
$ brew install kylef/formulae/podenv
```

## Usage

### Commands

##### `version`

Displays the current active CocoaPods version and why it was chosen.

```shell
$ podenv version
0.39.0 (set by Podfile.lock)
```

##### `versions`

Lists all installed CocoaPods versions, showing an asterisk next to the currently
active version.

```shell
$ podenv versions
* 0.39.0 (set by Podfile.lock)
  1.0.0.beta.2
```

##### `global`

Sets the global version of CocoaPods to be used by writing to the
`~/.podenv/version` file. This version can be overridden by
application-specific Podfilefile, or by setting the `COCOAPODS_VERSION`
environment variable.

```shell
$ podenv global 1.0.0.beta.2
$ podenv global
1.0.0.beta.2
```

##### `install`

Installs a version of CocoaPods.

```shell
$ podenv install 1.0.0.beta.2
```

##### `uninstall`

Uninstalls a specific CocoaPods version.

```shell
$ podenv uninstall 1.0.0.beta.2
```

##### `exec`

Runs an executable with the selected CocoaPods version. For example, this
can be used to install CocoaPods plugins.

```shell
$ podenv exec gem install cocoapods-bugsnag
```
