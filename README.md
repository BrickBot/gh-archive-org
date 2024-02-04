# gh-archive-org

A [GitHub CLI](https://cli.github.com/) extension script to archive all repositories—with their releases—in an organization, optionally filtering by topic or a [search string](https://docs.github.com/en/github/searching-for-information-on-github/searching-on-github/searching-for-repositories). If the repository has already been cloned it will attempt to switch to the default branch and pull.

## Installation

```bash
gh extension install BrickBot/gh-archive-org
```

## Usage

```txt
gh archive-org [-f RELEASE_FILES] [-p PATH] [-r REPO] [-t TOPIC] [-s QUERY] [-y] [-n] ORG
  ORG
    Github organization. Required if the GITHUB_ORG environment variable is not set.
  -f, --release_files [all | latest | none]
    Download all releases (default), latest release, or no releases.
  -p, --path PATH
    Archive path, under which org/repo folders will be created. Default: current directory.
  -r, --repo REPO
    Archive only the specified repo(s) within the given org.
    Multiple repos may be specified by separating repo names with spaces
    and then enclosing that entire group in double quotes (e.g. \"repo1 repo2\").
    If this argument is provided, '-t' and '-s' will be ignored.
  -t, --topic TOPIC
    Archive repositories with this topic
  -s --search QUERY
    Archive repositories found by this search string. If this is provided '-t' will be ignored.
    Example: -s \"is:public language:go\"
    See: https://docs.github.com/en/github/searching-for-information-on-github/searching-on-github/searching-for-repositories
  -y, --yes
    Archive without prompting for confirmation.
  -n, --dry-run
    Do not actually archive, just show what would be archived
  -h, --help
    Display this message.
```
