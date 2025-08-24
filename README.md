<div align="center">
  <h1><code>setup-luau</code></h1>
  <p>
    <a href="https://github.com/ewd3v/setup-luau/actions?query=workflow%3Atest"><img src="https://github.com/ewd3v/setup-luau/workflows/test/badge.svg" alt="test" /></a>
  </p>
</div>

GitHub action to install [Luau](https://github.com/luau-lang/luau); a scripting language derived from Lua.

## Usage

Use the latest released version of `Luau` with default parameters:

```yaml
steps:
    - uses: ewd3v/setup-luau@v0.1.0
```

For a list of default parameter values, [check here](https://github.com/ewd3v/setup-luau/blob/main/action.yml#L5-L20).

### Advanced

For more advanced cases, use the parameters below.

```yaml
steps:
    - uses: ewd3v/setup-luau@v0.1.0
      with:
          version: "0.688" # name of git tag in Luau (uses latest tag by default)
          path: some_dir/my_project # path to project dir containing `Luau.toml` ("." (current dir) by default)
          cache: false # whether to enable binary caching between runs (false by default)
          token: ${{ github.token }} # GitHub token to bypass rate limit (${{ github.token }} set by default)
```

## Inputs

### `version`

The git tag of `Luau` to install from releases and use. By default this input will be assigned to the latest version of `Luau`.

### `token`

Set to a GitHub token to be used when downloading `Luau` to increase the GitHub rate-limit. Note, these two options, `${{ github.token }}` and `${{ secrets.GITHUB_TOKEN }}`, are equivalent and passed by default. **Thus, you do not need to specify this parameter unless you are using a token different from the owner of the repository.**

## Credits

[@ok-nick](https://github.com/ok-nick) - For creating `setup-aftman` (which this is a fork of)
