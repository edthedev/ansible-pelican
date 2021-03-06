ansible-pelican
===============

Ansible with Vagrant setup for running Pelican for static website generation.

Prerequisites
--------------
Requires Vagrant_, VirtualBox_ and Ansible_.

Steps
------

Checkout your Blog from Git
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Check out this project with Git.::

    git clone https://github.com/edthedev/ansible-pelican.git

Modify the submodule "blog" in `.git/config` to point to your blog, instead of mine.::

    [submodule "blog"]
	url = git@bitbucket.org:yourusername/blog.git

Now make sure a copy of your blog has been fetched.::

    git submodule foreach git pull origin master

Setup your Editor
~~~~~~~~~~~~~~~~~~
If you don't prefer Vim as your blog editor, you will want to manually install your prefered editor.

You may also want to enable a graphical interface to the Virtual Machine.::
    
    vim Vagrantfile
      config.vm.provider "virtualbox" do |v|
        v.gui = true
      end

Bring up the VM
----------------

Now create the Virtual Machine, will all Pelican requirements satisfied.::

    cd ansible-pelican
    vagrant up
    # This step will take a few minutes. Enjoy some tea.

Do some blogging
-----------------
Now connect to the Virtual Machine and edit and publish your blog as usual.::

    cd ansible-pelican
    vagrant ssh
    cd /vagrant/blog
    vim /vagrant/blog/content/some_blog_file
    ...etc...
