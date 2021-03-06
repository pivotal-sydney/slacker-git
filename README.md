# SlackerGit

A command for [slacker](https://github.com/mikfreedman/slacker) that will return the value of the system configuration key `git_ref`

## Installation

Ensure you configure the project like so, or add the `Ref` module to the commands key of your main project:

```elixir
config :slacker,
  command_prefix: "slacker",
  slack_api_token: System.get_env("SLACK_API_TOKEN"),
  parsers: [Slacker.Parsers.Prefix],
  allow_direct_messages: false,
  commands: [SlackerGit.Commands.Ref],
  git_ref: System.get_env("GIT_REF")
```

set `git_ref` in any way that is appropriate for your deployment

If [available in Hex](https://hex.pm/docs/publish), the package can be installed as:

  1. Add slacker_git to your list of dependencies in `mix.exs`:

        def deps do
          [{:slacker_git, git: "https://github.com/mikfreedman/slacker-git"}]
        end
