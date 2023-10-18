# Singularity on your local machine

This is modified from the [Singularity 3.7 documentation](https://docs.sylabs.io/guides/3.7/admin-guide/installation.html).

I use version 3.7 as that is max version installed on the Artemis HPC. However, this uses a Centos 7 host, wheras Artemis uses Centos 6, results may not be compeltely comparable.

Singularity requires a Linux VM. Vagrant is the recommend solution, it can be installed with Homebrew on Mac:
```bash
brew install virtualbox
brew install vagrant
brew install vagrant-manager
```

On Windows I recommended using WSL and the native Linux installation of Singularity. 


Now, make a new directory to house your VM.

```bash
mkdir vm-singularity
cd vm-singularity
```

You can then initialise your new VM with an image.
```bash
vagrant init sylabs/singularity-3.7-centos-7-64
```
You can find additional base-images at: [https://app.vagrantup.com/boxes/search](https://app.vagrantup.com/boxes/search).
This will create a file `Vagrantfile`. Modify it as needed. You may like to include [port-forwarding](https://developer.hashicorp.com/vagrant/docs/networking/forwarded_ports) for example.

Finally launch your VM and connect to it with ssh
```
vagrant up
vagrant ssh
```

Now you must `scp` data in and out of the vagrant VM as needed.
You can then  pull/build/run singularity images as needed from your Linux VM.





