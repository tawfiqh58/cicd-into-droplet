# CI/CD pipeline with Droplet

This is a simple CI/CD pipeline with digitalocean droplet.

Github private repo clone
Create ssh key to the droplet and past it to github ssh and gpg keys
$ ssh-keygen -t ed25519 -a 200 -C "your_email@example.com"

Copy past to own authorized_keys
$ nano .ssh/authorized_keys
$ chmod 700 .ssh/authorized_keys

required fields in the project `secrets`

`SSH_HOST` - is the IP address of the droplet
`SSH_KEY` - is the private key of your droplet
`SSH_USERNAME` - is the username of the droplet

How it works?
A: It creates ssh key on the droplet and add that public key to github
as well as it's own authorized_keys, which means now github will give
access to clone private repo and by pasting the private key in the project
gives access to ssh to the instance. because that public key only will
satisfy that private key.

Note:
`Known hosts` - For the first time if github actions can not
clone your repository then do it manually. You will be promted
to say 'yes'. Next time github actions can clone your repository
but you don't need to clone that project everytime for this case.
