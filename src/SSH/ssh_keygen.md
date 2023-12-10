# SSH Key generator

```
ssh-keygen -t rsa -b 4096 -C "$(git config user.email)" -f gh-pages -N "" 

Generating public/private rsa key pair.
Your identification has been saved in gh-pages
Your public key has been saved in gh-pages.pub
The key fingerprint is:
SHA256:**
The key's randomart image is:
+---[RSA 4096]----+
|o oo+***=+       |
|     . o         |
|      . .        |
+----[SHA256]-----+
```