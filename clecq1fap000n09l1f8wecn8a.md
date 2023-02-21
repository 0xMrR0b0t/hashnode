# How many ways can we access localhost in browser?

## What is localhost?

`Localhost` is a special word that refers to the computer you're using right now. When you use a website or program, it has to communicate with other parts of the computer, like the web browser or server. When a program is set to use `localhost`, it means it's only communicating with itself on your computer.

In web development, developers use `localhost` to test their websites and apps before they're published online. This allows them to make sure everything works correctly and looks good before other people can see it. It's like trying on a new outfit at home before going out to show it off to others.

So, in summary, `localhost` is the computer you're using right now, and it's used in web development to test websites and apps on your computer before they're shown to others online.

## How to set up our apache local server in Linux?

### Enabling Apache2 as a local server on Linux involves the following steps

**Install Apache2 web server software by running the following command in the terminal:**

```apache
sudo apt install apache2
```

**Once the installation is complete, start the Apache2 service by running the following command:**

```apache
sudo systemctl start apache2.service
sudo systemctl enable apache2.service
```

## How to check local server is enabled or not in Linux?

```apache
sudo systemctl status apache2.service
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676882067186/7eac5e19-dc50-428a-9854-bfb21d17bbe7.png align="center")

Apache2 service has been successfully started and is now fully operational. The provided image serves as evidence of its current status. Apache2 is a versatile and widely adopted open-source web server software that facilitates the seamless delivery of web content. It operates as a background process, constantly listening for and fulfilling incoming client requests.

## There is some way we can open a local host in the browser.

### 1\. Accessing Your Local Host Server Using `localhost` in Linux.

```bash
http://localhost:port
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676887207485/de3ebc0b-3700-403e-aa39-9bceaaf5d577.png align="center")

### 2\. You can open your local host server using your local IP address.

**How to check our local IP in Linux?**

To check your local IP address in Linux, you can use the `ifconfig` command in the terminal. This command displays the IP addresses assigned to your network interfaces, including your local IP address.

```apache
ifconfig
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676884726317/72a65fe2-a124-4809-afa2-a05268874d4f.png align="center")

Based on the image provided, it appears that the user is highlighting the IP address `192.168.1.9` which is associated with the `eth0` network interface. This indicates that the user's machine is configured to use the `eth0` interface for connecting to the internet and that the highlighted IP address is the machine's local IP address.

Local IP addresses are used to identify devices on a local network and can be used to access local resources such as a local server or the `local host` address. In this case, the user can access a local server running on their machine by entering the local IP address (192.168.1.9) into their web browser.

```bash
http://192.168.1.9:port
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676885924035/5063869f-587e-4dba-a171-aa8f9b19f29e.png align="center")

### 3\. You can also use 127.0.0.1/255 to access our local host server.

```bash
http://127.0.0.1:port
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676886117976/347d0678-8194-4334-abf0-85a8798a78be.png align="center")

### 4\. You can also use 127.1 to access our local host server.

```bash
http://127.1:port
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676886277214/3d14946c-0bde-48a4-8ab6-e05fc7fbb4cb.png align="center")

### 5\. You can also use 127.0 to access our local host server.

```bash
http://127.0:port
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676886387201/811516ec-86e8-4e6b-b421-8943db768b8a.png align="center")

### 6\. You can also use 127.0.1 to access our local host server.

```bash
http://127.0.1:port
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676886453736/3c596066-8b2f-49cb-a1fa-7dc81dca7ea3.png align="center")

### 7\. You can also use 127.0.1 to access our local host server.

```bash
http://127.0.0:port
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676886531152/e90a18b2-f522-4e0d-b0ed-f40b532620ae.png align="center")

### 8\. You can also use 0.0.0.0 to access our local host server.

```bash
http://0.0.0.0
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676886665106/06e27faf-bb2d-4fba-a605-7d1e591845b3.png align="center")

### 8\. You can also use 127.1.0.0 to access our local host server.

```bash
http://127.1.0.0
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676886730312/84b5bfd5-4a05-4b17-a0c2-1b09d15a74f0.png align="center")

### 9\. You can also use a decimal IP value to access our local host server.

```bash
http://2130706433:port
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676887049650/c13202cf-0d7e-4722-ad59-54b6c8eba9b4.png align="center")

**Note:** If you want to know more about IP you can also check this cheat sheet [link](https://pbxbook.com/other/ipcheat.html).

That's all! Thank you for getting this far. I hope you find this article useful. If you did find this article valuable.

Toss us a follow for more amazing articles on Linux, Networking etc

And be sure to share with other Linux folks who you think it might be useful to them.