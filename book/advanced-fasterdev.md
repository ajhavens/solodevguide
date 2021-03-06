# Faster Development

There are some tricks to developing on Solo faster that we have not documented in the rest of this guide.

## Remove SSH Password Prompt

If you do not want to be prompted for a password each time you SSH into Solo, you can copy your SSH public key to Solo:
<div class="host-code"></div>

```sh
solo provision
```
By copying your public key to Solo, you will no longer be prompted for your password each time you run `ssh`.
(see ["solo" Command Line Tool](starting-utils.html) for more information). 
<aside class="note">

## Optimizing SSH Access

You can optimize the ssh process further by adding the following to your `~/.ssh/config`:

<div class="host-code"></div>

```
Host solo 10.1.1.10
    Hostname 10.1.1.10
    Port 22
    User root
    StrictHostKeyChecking no
    UserKnownHostsFile=/dev/null
    IdentityFile ~/.ssh/id_rsa

Host soloctrl 10.1.1.1
    Hostname 10.1.1.1
    Port 22
    User root
    StrictHostKeyChecking no
    UserKnownHostsFile=/dev/null
    IdentityFile ~/.ssh/id_rsa
```

From then on, any Solo device can be accessed by this shorthand:

<div class="host-code"></div>

```
ssh solo
ssh soloctrl
```

<aside class="note">
We use the synonymous but explicit addresses `root@10.1.1.10` and `root@10.1.1.1` throughout the rest of this guide.
</aside>
