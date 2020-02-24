# Guldkorn

*Poesi för döda fiskar.*

The `guldkorn` tools locates forks with divergent commits or commits ahead of the original repository.

## Installation

```
go get github.com/mewmew/guldkorn
```

## Usage

```
guldkorn [OPTION]...

Flags:

  -owner string
        owner name (GitHub user or organization)
  -q    suppress non-error messages
  -repo string
        repository name
  -token string
        GitHub OAuth personal access token
```

## Examples

This example helped narrow down `250` forks across `2554` branches to `65` forks across `149` branches with divergent commits or commits ahead of origin, a subset of which are presented below.

```bash
$ guldkorn -owner diasurgical -repo devilutionX -token ACCESS_TOKEN

status: "diverged" (head=AJenbo:roguelike vs base=diasurgical:master)
AJenbo:roguelike ahead 3 (and behind 139) of diasurgical:master
https://github.com/diasurgical/devilutionX/compare/master...AJenbo:roguelike

status: "diverged" (head=NEMadman:master vs base=diasurgical:master)
NEMadman:master ahead 1 (and behind 970) of diasurgical:master
https://github.com/diasurgical/devilutionX/compare/master...NEMadman:master

status: "diverged" (head=cain05:difficulty_rebalance vs base=diasurgical:master)
cain05:difficulty_rebalance ahead 13 (and behind 833) of diasurgical:master
https://github.com/diasurgical/devilutionX/compare/master...cain05:difficulty_rebalance

status: "diverged" (head=qndel:pixellight vs base=diasurgical:master)
qndel:pixellight ahead 81 (and behind 22) of diasurgical:master
https://github.com/diasurgical/devilutionX/compare/master...qndel:pixellight
...
```

**Note:** Remember to set `ACCESS_TOKEN` to not hit the rate limit on GitHub. To create a personal access token on GitHub visit https://github.com/settings/tokens

If the environment variable `GULDKORN_GITHUB_TOKEN` is set, the access token will be read from there.
