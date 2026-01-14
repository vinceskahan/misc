
```

#### my keys
gpg -K

#### known keys
gpg -k

#### encrypt a message
#### note: I did an edit-key and set trust to ultimate on his key
####
cat testdude.in | gpg --armor -se -r Testdude -o testdude.out
or
gpg -ea -r testmessage < testmessage.in > testmessage.out


#### gpg --check-sigs 
/Users/vince/.gnupg/pubring.kbx
-------------------------------
pub   ed25519 2023-01-31 [SC]
      257476E76CA767B4B50E5E7E1B334F4F46C58B06
uid           [ultimate] Vince Skahan <vinceskahan@gmail.com>
sig!3        1B334F4F46C58B06 2023-01-31  [self-signature]
sub   cv25519 2023-01-31 [E]
sig!         1B334F4F46C58B06 2023-01-31  [self-signature]

pub   rsa3072 2019-08-21 [SC]
      12345FDC4CAD6E6F815BAF6D0761F3DB1A95C4C5
uid           [ultimate] Test Dude <testdude.bunce@gmail.com>
sig!3        123453DB1A95C4C5 2019-08-21  [self-signature]
sub   rsa3072 2019-08-21 [E]
sig!         123453DB1A95C4C5 2019-08-21  [self-signature]

pub   rsa3072 2023-12-12 [SC]
      5E5311A995692D58DEF628248CB64BC5326EE825
uid           [ultimate] Vince Skahan (for signing rpms only) <vinceskahan@gmail.com>
sig!3        8CB64BC5326EE825 2023-12-12  [self-signature]
sub   rsa3072 2023-12-12 [E]
sig!         8CB64BC5326EE825 2023-12-12  [self-signature]


####  gpg --show-session-key < testdude.out
gpg: WARNING: no command supplied.  Trying to guess what you mean ...
gpg: encrypted with rsa3072 key, ID 12345839D4F6F04B, created 2019-08-21
      "Test Dude <testdude@gmail.com>"
gpg: public key decryption failed: No secret key
gpg: decryption failed: No secret key

```
