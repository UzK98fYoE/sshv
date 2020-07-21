# sshv

![configure-cas](https://gist.github.com/seanw2020/5035ca7036ac899dd3142cb004aefb34/raw/f68bf11491d563b6bfaaeb60d13e4501eb1d0f6d/configure-CAs.png)
![sign-and-use-certs](https://gist.github.com/seanw2020/5035ca7036ac899dd3142cb004aefb34/raw/f68bf11491d563b6bfaaeb60d13e4501eb1d0f6d/sign-and-use-certs.png)

```
Welcome to sshv

  Purpose: A vault-aware ssh client

    Usage: sshv [OPTIONS] destination [COMMAND]

  Example: sshv user1@sshserver
  Example: sshv user1@sshserver echo "hello world"
  Example: sshv user1@sshserver -- -p 1022 echo "hello world"
  Example: sshv user1@sshserver -- sudo tee -a /root/.ssh/authorized_keys <<< "ssh-rsa..."

Description
  sshv is a wrapper for ssh. It logs into vault, creates a local ssh keypair, sends
  the resulting public key to vault's CA (ssh secrets engine) for signing, receives
  the resulting certificate, and calls ssh with arguments to use the certificate
  against the user@server you specify.

Options:
  -d, --debug         Debug mode for sshv (i.e., enable bash's set -x)
  -f, --portforward   Deprecated June 2020: used to enable http://localhost:8080 and :8200.
  -h, --help          Display help
  -r, --remove        Remove sshv
  -s, --search        Search inventory. Example: sshv -s js1
  -u, --update        Update sshv, the latest hosts_ca cert, and latest inventory
  -c, --csv           Open a csv of the inventory
  -j, --json          Open a json version of the inventory
  -l, --links         Show links (URIs) to resources
  --                  Send everything after 2 dashes as arguments to ssh, not sshv
```
