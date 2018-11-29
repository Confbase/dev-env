# dev-env
This is our automated installation for our development VM images.
We are going to be installing the newest version of Fedora Workstation into a virtualbox image, which is then exported to a vagrant box for development purposes.

How to run: 
- Step 1: Make sure you generated a private and public key pair using `scripts/make_local_ssh.sh`
- Step 2: Make sure you've installed both vagrant and packer.
    - `brew install packer`
    -  Download vagrant from [their website](https://www.vagrantup.com/downloads.html)