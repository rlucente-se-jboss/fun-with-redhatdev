# Fun with Red Hat Developer

This is a short set of instructions to get you up and running with
Red Hat Enterprise Linux from the [Red Hat Developer](https://developers.redhat.com)
web site.  This is intended for personal exploration and learning.
You can also use your Red Hat Developer credentials to log in to
the [Red Hat Customer Portal](https://access.redhat.com) and use
the [kickstart configuration tool](https://access.redhat.com/labs/kickstartconfig/)
to automate the installation.

* Sign up for a free account at [Red Hat Developer](https://developers.redhat.com)
* Download the ISO for the Red Hat Enterprise Linux (RHEL) distribution you'd like to try
* Install RHEL using the downloaded ISO image

Next, run a short set of commands to register and update the system.
Log into your system as `root` then in a terminal, type:

    subscription-manager register --username USER --password PASS
    subscription-manager attach --auto
    subscription-manager repos --disable='*'

where `USER` and `PASS` match your [Red Hat Developer](https://developers.redhat.com)
credentials.

For RHEL 7, type the following:

    subscription-manager repos \
        --enable=rhel-7-server-rpms \
        --enable=rhel-7-server-optional-rpms

For RHEL 8, instead type:

    subscription-manager repos \
        --enable=rhel-8-for-x86_64-baseos-rpms \
        --enable=rhel-8-for-x86_64-appstream-rpms

Then for either operating system, pull the updates using:

    yum -y update
    yum -y clean all

Refer to the extensive [RHEL documentation](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/)
for more information.

