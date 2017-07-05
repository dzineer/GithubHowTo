--- Generating SSH Keys (using Git Bash) ---

----------------------------------------------------------------------
| See if you have any ssh keys
----------------------------------------------------------------------
ls ~/.ssh/
----------------------------------------------------------------------
| If empty then create new key or if you want  to use different keys:
| Add new sshkey
| ssh-keygen -t rsa -b 4096 -C '<github:email>'
----------------------------------------------------------------------
ssh-keygen -t rsa -b 4096 -C 'frank@dzineer.com'
----------------------------------------------------------------------
| Check if ssh-agent is running:
----------------------------------------------------------------------
eval "$(ssh-agent -s)"
-- output:
Agent pid 343439 <--- some number
----------------------------------------------------------------------
| Find generated ssh-keys (private, public)
----------------------------------------------------------------------
id_rsa <--- private key
id_rsa.pub <--- public key
----------------------------------------------------------------------
| Add our new ssh-key( private ) to our local identities
----------------------------------------------------------------------
ssh-add <ssh-key-private:path>/id_rsa

-- output:

Identity added: <ssh-key-private:path>/id_rsa (<ssh-key-private:path>/id_rsa)
----------------------------------------------------------------------
| On Page: https://github.com/settings/ssh
| Get the public key and add it to GitHub
----------------------------------------------------------------------
cat <ssh-key-private:path>/id_rsa.public
-- output (example):

$ cat /c/Users/huranku/.ssh/github_id_rsa.pub
----------------------------------------------------------------------
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDJWb42bK8uXBwFdxX1ZVzEL5weWzAjCKnRdaJfCv+MbanqvGu8b7XPe47z/fIgAJp6G5zFFKVZSOXDpVywteoPT5l7Lswkh7Re7PR+jX0gy4HRjAuWgP7K10LulwPiHCjl7ID7kkohEdZjZJW6um0wTVFvL4Hdu1jupA9wANN58/gzJ2xtDTjlt7bgA/m288MmNuW/tJFPMQk7gD4HvbHbEKtZ3KXUepVJYEbEW4436WqrzoWjP6xGV9AO2jtipgSfUXqjW+i2nta9zMmuBCru7zn/beHDCILEoLTWk3KETZwxHbe0qMov8aCYAV7b7Q1FgozUKLwhi7dTBQpyJtbiI4doqb+opZswNW45WzYjF130JkMgm9Zol7pYUzfmML+Pth0m8PSbm8IPZARiwcvdE1HoUFQvyhVKNOHyVK98+Ici9brqkVbo1+kQgsD3XC9J8SSsbmz+T41ADIjVkRD5duu5AZYiFaWZiFIcwQWH8EKIjaxx11BBE4umqbr8GT4S61gWpFSY8e1/Brj/bUAP/03C+z0RRdri2G8491KD9F4bgpW8JK9jQQDX62MJFGJuRJdosNOQMEEoof50wNMwxHG63fo1XtFNPLnJQTvYFUUtl/olg7QOhD9RXPLfDdPNqHm00z8g0XjficyTPVjPh8c0qZM0pBWS8PoDt28kjQ== frank@dzineer.com
----------------------------------------------------------------------
| Copy output as public key to save in github
----------------------------------------------------------------------
| Connect to github with new User
----------------------------------------------------------------------
ssh -T git@github.com
