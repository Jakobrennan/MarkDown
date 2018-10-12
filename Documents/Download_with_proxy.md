# Working around a Proxy when downloading repositories in ubuntu

instead of spending hours wondering why the repository you are downloading won't work, consider that the network you are trying to download from is running through a proxy, and that in turn is preventing you from downloading what you need to.

if you run code like this:

```bash
sudo apt-ket adv --keyserver keyserver.ubuntu.com --recv-keys BA300B7755AFCFAE
```

and you're getting this error:

```bash
Executing: /tmp/tmp.zwYQ4xlkfn/gpg.1.sh --keyserver
hkp://keyserver.ubuntu.com:80
--recv-keys
BA300B7755AFCFAE
gpg: requesting key 55AFCFAE from hkp server keyserver.ubuntu.com
?: [fd 4]: read error: Connection reset by peer
gpgkeys: HTTP fetch error 7: couldn't connect: eof
gpg: no valid OpenPGP data found.
gpg: Total number processed: 0
gpg: keyserver communications error: keyserver unreachable
gpg: keyserver communications error: public key not found
gpg: keyserver receive failed: public key not found
```

then you will  might very well be failing to download something through a proxy.

you can fix such an issue simply with the following code:

```bash
sudo add-apt-repository ppa:linaro-maintainers/toolchain
```

~~there is an article that talks about this in depth, but i'll be damned if i can remember it, so type the above code into google and it should be easy to find~~

