# Portaledge - full webdev stack

*TL;DR* Development stack for state-of-the-art web programming. Warning: alpha quality - v0.0.1.

This can create a virtual machine with all the technologies below with a single command. Technically it is an Ansible playbook that is supposed to provision a Vagrant VM. Google these.

Base OS is Ubuntu 12.04 LTS Precise Pangolin 64bit, aka `precise64` in Vagrant's terms.

## Packages

+ Zsh instead of bash with really cool git-aware prompt
+ Git 1.8.3
+ Ruby 2.0.0-p195
+ Node.js 0.10.20 via `nvm`
+ `npm` + global modules:
  - `grunt`, `bower`, `yeoman`, `coffee-script`, `jade`, `less`, `uglify-js`, `debug`, `mocha`, `karma.js`
+ Java7 - `openjdk-7-jre`
+ Clojure 1.5.1 + Leiningen 2.2.1
+ Postgres 9.2

## Dependencies

- Ansible
- Vagrant

## Usage

```
git clone <repo>
cd repo
vagrant up
```

- To get rid of your dev environment: run `vagrant destroy`, format your hard drive, throw your MacBook out of the window...
- To set it up all again: `vagrant up` :-)

Note: might take few minutes because of all the dependencies and stuff...

## TODO

+ Postgres apt package is installed, but not configured (service, users, permissions...), this needs special sub-playbook. Common postgres extensions (compatible with Heroku) would be nice too.
+ Ruby can be installed either from Brightbox apt repo (bad) or with rbenv from source (slow). How do I install latest ruby from official repository (?) without compiling? The ruby dir has to be cleaned up.
+ Node version manager (nvm) is probably useless in Vagrant setu(. Same as above: what is an idiomatic way to install latest node via apt?
+ Upgrade Postgres to 9.3. These Ubuntu apt repos suck, <3 homebrew.
+ Add Mongo
+ Add Redis
+ Add some easy feature toggles for all these technologies
+ Extract version infos from the playbooks to some special config
+ Decide what packages would have specified fixed versions and which would auto-upgrade themselves
+ Add a Continuous Integration server. Jenkins? TeamCity?
+ Some common toolbelts? Heroku? DigiralOcean?
+ I want DynamoDBLocal.
+ Add Google Closure Compiler - sooner or later I would need it for something
+ Ensure that headless browsers like PhantomJS, WebDriver, etc. are working
+ Stuff around SSH keys etc...
+ Setup Emacs with all the dotfiles, plugins etc

## Docker

In the future I would like to setup deployment/development with/via Docker (www.docker.io). So far I don't have time to explore it.

## Other

This originally started as a clone of https://github.com/owainlewis/vagrant-ansible