---
layout: post
title:  "How I Deploy My Applications"
date:   2016-02-14 00:00:00 -0700
---

An incredibly important part of the development process is deployment of your applications. When I deploy my applications, I deploy on [Digital Ocean](http://digitalocean.com). I use two pieces of technology to ensure a smooth deploy, [nginx](http://nginx.com) and [forever](https://www.npmjs.com/package/forever).

## Why do I use these tools?

Nginx allows me to quickly and easily deploy multiple applications on a single VPS. Forever allows me to continuously run my [Node.js](https://nodejs.org) script, even if there is an error.

## Getting started

Before you begin anything on my virtual server, you have to point your domain to the correct IP. You can do this in the `DNS` settings on your domain. If you're pointing the homepage, you can normally make an `A` record that points to the IP of your VPS or server. From here, we can jump into configuring it on the actual VPS.

## Configuring the server

Once you connect to your VPS, you can clone the repository like normal. This is a simple Node server that I coded up that serves a webpage.

``` shell
git clone https://gitlab.com/hcjk/SimpleNodeServer.git
```

After you cloned that repository, you can `cd` into it with the following command.

``` shell
cd SimpleNodeServer/
```

From there, we can install forever.

``` shell
npm install -g forever
```

Then we can start the server with the following command.

``` shell
forever start app.js
```

## Configuring nginx

We can create a new file for `httpd`. The "example.com" can be replaced by whatever your domain is.

``` shell
nano /etc/nginx/conf.d/example.com.conf
```

We can then add the following code to configure nginx. For this demo, "your-domain.com" should be replaced with the domain that you want to use. You can also replace "{YOUR_PORT}" with `3001`. At other times, you can set it to the port that you are running your server on.

``` shell
server {
    listen 80;

    server_name your-domain.com;

    location / {
        proxy_pass http://localhost:{YOUR_PORT};
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}
```

After this, you can exit the file and restart nginx with the following command.

```shell
service nginx restart
```

At this time, you should be able to go to the domain that you are using and view "Hey everyone!" You can see the example of this at [hey.henrykaufman.me](http://hey.henrykaufman.me).

_Thanks for reading!_

Reach out to me [@kaufmanhenry](https://twitter.com/kaufmanhenry) on Twitter or by [email](mailto:hello@henrykaufman.me).

