## cloudpair

A tool for getting your desired pairing configuraton ready. Ideal for users of a vim/tmux pairing configuration.

## Instructions

* With pip installed locally, run: `pip install -r requirements.txt`
* Install ansible requirements: `ansible-galaxy install -r requirements.yml`
* Launch a new ec2 instance (ubuntu is currently supported), download your new keypair `something.pem` file.
* Add the `something.pem` to your SSH identities: `ssh-add something.pem`
* Connect to ec2 instance and run `sudo apt-get update` to ensure package
  manager is up-to-date
* Update the configuration to meet your needs `ansible/hosts.yaml`:
  * public dns name of your host.
  * users and public keys using the server
  * dotfile repository (raymondberg/dotfiles is default)
* Run `bin/install`
* Clear your SSH identities, and re-add the default: `ssh-add -D && ssh-add`

## Feature Requests

* Ability to provision an ec2 instance in this script
* Ability to query for a list of cloudpairs and spin them up or down
