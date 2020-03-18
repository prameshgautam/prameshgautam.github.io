---
layout: post
title:  "How to fix OpenVPN not working in Ubuntu 16.04"
date:   2016-07-25
categories: Openvpn
permalink: /2016/07/25/how-to-fix-openvpn-not-working-in-ubuntu-16-04/
author: Pramesh
---

So guys,

I came across this error log while trying to run OpenVPN in Ubuntu 16.04.

`AUTH_FAILED,Google Authenticator Code must be a number`

I had installed OpenVPN from repo and had two factor authentication enabled. If you are getting the same issue, then follow these steps in order to fix the issue. Solution is to install OpenVPN from source. These are the steps. Enjoy!!!

1. First download OpenVPN from [here][openvpn-download]
2. Extract the file to required location with this command `tar -xvf <file_name>`
3. Enter the OpenVPN directory and run the command `./configure && make && make-install`
4. Navigate to the directory `<open_vpn_main>/src/openvpn` and run openvpn executable from this location and run command `sudo ./openvpn –config client.ovpn`
5. you can set symbolic link if you want to run it from any location. Just run this command `sudo ln -s <path_to_openvpn_executable> /usr/bin/openvpn`



[openvpn-download]: https://swupdate.openvpn.org/community/releases/openvpn-2.3.11.tar.gz




