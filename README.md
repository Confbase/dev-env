# dev-env
This is our automated installation for our development VM images.
We are going to be installing the newest version of Fedora Workstation into a virtualbox image, which is then exported to a vagrant box for development purposes.

How to run: 
- Step 1: Make sure you generated a private and public key pair using `scripts/make_local_ssh.sh`
- Step 2: Make sure you've installed both vagrant and packer.
    - `brew install packer`
    -  Download vagrant from [their website](https://www.vagrantup.com/downloads.html)
    -  Download VirtualBox from [their website](https://www.virtualbox.org/wiki/Downloads)
- Step 3: Run `packer build -var-file=public/vars.json -var-file=private/vars.json -force fedora_29.json` to build the virtualbox image.
    - Right now, this keeps the virtualbox image mounted in virtualbox-- change `keep_input_artifact` from `true` to `false`, and `keep_registered` from `true` to `false`.
- Step 4: cd into the vagrant directory, and call the following:
    - `vagrant box add conf-dev.box`
    - `vagrant up`
    - `vagrant ssh`

That's it! Nice and simple!