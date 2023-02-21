# What Is sysctl Command In Linux And How To use It

## What is sysctl command?

In Unix-based operating systems, the `sysctl` command is a useful tool that enables users to see and alter kernel settings in real time. The `sysctl` command can access and modify this virtual file system of accessible kernel settings.

You may access details about your system's hardware, networking, and other low-level settings by using the `sysctl` command. You may also change these settings to enhance system performance or activate particular functionality.

Sysctl is a strong tool for skilled users who wish to optimize the performance of their system or diagnose problems at the kernel level. It should be used cautiously, though, since wrongly changing kernel settings might lead to system instability.

## **The syntax of the sysctl command:**

```apache
$ sysctl [options..] [variable..] [value..]
```

## Uses of sysctl command with example

### 1\. How we can see all kernel parameters using sysctl command?

```apache
$ sudo sysctl -a
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676967976550/1592008a-571d-45cd-892a-08ef607e282e.png align="center")

### 2\. How to read kernel parameters using sysctl command?

```apache
$ sudo sysctl net.ipv4.conf.all.forwarding
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676970672363/141e22c2-d883-45b1-b914-40f8ed72e637.png align="center")

### 3\. How to temporarily modify any kernel parameter's value?

If I want to stop my IP forwarding, I must change the value from 1 to 0 here. If I want to enable it, I must change the number from 0 to 1. You may view the sample below.

```apache
$ sudo sysctl -w net.ipv4.conf.all.forwarding=0
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676971604343/08961196-134c-4d77-bd23-c2d8035b2b3d.png align="center")

As you can see, I have deactivated IP forwarding, but this is not a permanent change; we must also modify the configuration file to make this change permanent.

### 4\. How to modify a kernel parameter's value permanently?

You must visit the /etc/sysctl.conf directory and make the necessary changes there if you wish to permanently alter the kernel parameter value.

```apache
$ sudo nvim /etc/sysctl.conf
```

You may use any text editor here, I am currently using nvim. After opening the config file you need to find/add your kernel parameter and value then save it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676973653676/514aaa7b-ac8f-48fb-9b7b-3d84ada102c3.png align="center")

if you want to make your config file you need to add this file in /etc/sysctl.d/your\_filename.conf after this you need to run a command.

```apache
$ sysctl -p /etc/sysctl.d/your_filename.conf
```

## **Conclusion**

On Unix-based operating systems, the `sysctl` command is a potent tool for viewing and changing kernel settings live. It offers a means of optimizing system performance and enabling/disabling particular functionalities. It may be used for everything from memory management to process scheduling, file system settings, and network setup. Its hierarchical tree-like structure facilitates navigation and allows for simple system parameter modification for improved performance. System administrators, programmers, and anybody else who wants to control and improve system performance depend on the `sysctl` command. you can also check the man page of the `sysctl` command.

That's all! Thank you for getting this far. I hope you find this article useful. If you did find this article valuable.

Toss us a follow for more amazing articles on Linux, Networking etc

And be sure to share with other Linux folks who you think it might be useful to them.