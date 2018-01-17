# Introduction to SELinux on CentOS

From https://www.digitalocean.com/community/tutorials/an-introduction-to-selinux-on-centos-7-part-1-basic-concepts

## Basic Concepts

Security Enhanced Linux or SELinux is an advanced access control mechanism built into most modern Linux distributions. 
It was initially developed by the US National Security Agency to protect computer systems from malicious intrusion and tampering. 
Over time, SELinux was released in the public domain and various distributions have since incorporated it in their code.

## SELinux Packages

To check what SELinux packages are installed on your CentOS 7 system, 
you can run a few commands like the one below (with different search terms after grep) as the root user:

`rpm -qa | grep selinux`

## SELinux Modes

 At any one time, SELinux can be in any of three possible modes:
 
- Enforcing
- Permissive
- Disabled

We can run the `sestatus` command to check the current SELinux mode.  
`sestatus`

When SELinux is disabled the output will show:  
`SELinux status:        disabled`

## SELinux Configuration File

The main configuration file for SELinux is /etc/selinux/config. We can run the following command to view its contents:  
`cat /etc/selinux/config`  

The output will look something like this:  
```perl
# This file controls the state of SELinux on the system.
# SELINUX= can take one of these three values:
#     enforcing - SELinux security policy is enforced.
#     permissive - SELinux prints warnings instead of enforcing.
#     disabled - No SELinux policy is loaded.
SELINUX=disabled
# SELINUXTYPE= can take one of these two values:
#     targeted - Targeted processes are protected,
#     minimum - Modification of targeted policy. Only selected processes are protected. 
#     mls - Multi Level Security protection.
SELINUXTYPE=targeted
```

There are two directives in this file. 
The SELINUX directive dictates the SELinux mode and it can have three possible values as we discussed before.  

The SELINUXTYPE directive determines the policy that will be used. The default value is targeted. 
With a targeted policy, SELinux allows you to customize and fine tune access control permissions. 
The other possible value is "MLS" (multilevel security), an advanced mode of protection. 
Also with MLS, you need to install an additional package.  

## Disabling SELinux

As a first step, we need to edit the `/etc/selinux/config` file to change the SELINUX directive to permissive mode.

`vi /etc/sysconfig/selinux`

``` perl
...
SELINUX=permissive
...
```
Now issue a system reboot:  
`reboot`
