# Secret manager

As a team we:

1. do have secrets we want to share
2. do not want to make those secrets public

right now we use an ad-hoc solution; DM-ing .env files or individual variables to each other.

This isn't necessarily bad, but its not advanced or _nice_

Therefore, we should develop a secret manager to make sharing secrets between each other easy.

## details

- have a CLI we develop in a private repo
  - could even be in a language other than JS (!!!)
  - lets be real tho not likely
- install from github repo; thereby not publicly accessible
- accesses a hidden/private database where secrets are kept to make sharing them easy

### simplest implementation:

- CLI that does key-value gets
  - basically, a cloud dictionary accessed from the command line

### advanced implementation:

- secret manager has some notion of 'projects'
- secrets can now share names so long as they are in different projects;
- i.e. settle-up/DATABASE_URL and galactos/DATABASE_URL

- can sync an .env file instead of key/value gets
  - this command could even be put into a git hook;
  - so whenever you push ur new env vars are pushed
  - whenever you pull u download any new ones

## Architecture

A few options for architecture:

### 1-layer architecture

build only a CLI that connects directly to the database
pro/cons:

- simple and easy to deploy
- not MEGA secure...

### 2-layer architecture

build CLI and a web server that it communicates with
pros/cons

- more complex architecture -> harder to manage and deploy
- more secure;
  - private DB can be kept in env var in deployed site -> client never gets access; escalation of privilege avoided.
- login can be done with username/password; again, more secure but much harder to build
