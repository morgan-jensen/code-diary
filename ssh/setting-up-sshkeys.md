# How to set up some SSH keys

## Choosing an Algorithm and Key Size
(Information pulled from [ssh.com](https://www.ssh.com/academy/ssh/keygen#choosing-an-algorithm-and-key-size))

### Recommended 
* ed25519 - this is a new algorithm added in OpenSSH. It is suggested to be more secure and performant than RSA keys, however,
support for it in clients is not yet universal, thus its use in general purpose applications may not yet be advisable. 
(Is supported by GitHub and GitLab).
* ecdsa - a new Digital Signature Algorithm standardized by the US government, using elliptic curves. This is probably a good 
algorithm for current applications. Only three key sizes are supported: 256, 384, and 521 bits. Most SSH clients now support 
this algorithm.

### Old Reliable
* rsa - an old algorithm based on the difficulty of factoring large numbers. A key size of at least 2048 bits is recommended for RSA; 4096 is better.
RSA is getting old and significant advances are being made in factoring. Choosing a different algorithm may be advisable. It is quite possible the RSA
algorithn will become practically breakable in the foreseeable future. All SSH clients support this algorithm.

### Not Recommended
* dsa - an old US government Digital Signature Algorithm. It is based on the difficulty of computing descrete logarithms. A key size of 1024 would normally
be used with it. DSA in its original form is no longer recommended. 

## Using ssh-keygen to Generate Keys 
The algorithm is selected using the `-t` option and key size using the `-b` option. 

Ex:
* `ssh-keygen -t rsa -b 4096`
* `ssh-keygen -t dsa`
* `ssh-keygen -t ecdsa -b 521`
* `ssh-keygen -t ed25519`

## Using a Config File
2 Kinds of Config File: 
* Global: Found at `/etc/ssh/ssh_config`
* Per-User: Found at `~/.ssh/config`

The config file keeps manages the ssh keys found on the system and can specify what domain they are used for.

### Rules
* Empty lines starting with '#' are comments
* Each lines begins with a keyword, followed by an argument(s)
* Configuration options may be seperated by whitespace or optional whitespace and exactly one '='
* Arguments may be enclosed in double quotes (") in order to specify arguments that contain spaces

### Example 
```
Host gitlab.com
    IdentityFile gitlab_key

Host github.com
    IdentityFile github_key
```

For a full list of client configuration options, check [here](https://www.ssh.com/academy/ssh/config)
