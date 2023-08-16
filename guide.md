

# 1. Create SSH Keys with YubiKey


```sh
ssh-keygen -t ed25519-sk
```

- Emplacement: /Users/axel/.ssh/server_key
- Passphrase: Bitwarden
- Pub_key: github.com/axel-2.keys

# Generated password for user oukerie

ansible all -i localhost, -m debug -a "msg={{ 'mypassword' | password_hash('sha512', 'mysecretsalt') }}"

mypassword and salt => bitwarden


# 3. Install the requirements

```
ansible-galaxy install -r requirements.yml
```

# 2. Run ansible for the first time

```sh
ansible-playbook --ask-vault-pass run.yml -v --ask-pass
```

Maybe it will block on UFW Enable. You have to run the playbook a second time and normally it will work.

# 4. Vault


```sh
ansible-vault create group_vars/all/vault

ansible-playbook --ask-vault-pass second.yml -v -K
```

# 5. Second

```
 ansible-playbook --ask-vault-pass second.yml -v  
``` 


# 6. EVITER DE METTRE TT LE TEMPS LE MDP

```
export ANSIBLE_VAULT_PASSWORD_FILE=./.vault_pass.txt
```


# A AJOUTER DANS ANSIBLE
sudo tailscale up --accept-dns=false



sudo ufw delete allow 22
sudo ufw insert 1 allow 22

sudo ufw reload



# NET DATA
ngrok http 19999 --oauth=google --oauth-allow-email=verga.axel10@gmail.com



# UFW 

Status: active

To                         Action      From
--                         ------      ----
Anywhere on tailscale0     ALLOW       Anywhere                  
22                         ALLOW       Anywhere                  
Anywhere                   DENY        Anywhere                  
Anywhere (v6) on tailscale0 ALLOW       Anywhere (v6)             
22 (v6)                    ALLOW       Anywhere (v6)             
Anywhere (v6)              DENY        Anywhere (v6)             

Anywhere                   ALLOW OUT   Anywhere on tailscale0    
22                         ALLOW OUT   Anywhere                  
53                         ALLOW OUT   Anywhere                  
123                        ALLOW OUT   Anywhere                  
80                         ALLOW OUT   Anywhere                  
443                        ALLOW OUT   Anywhere                  
22 (v6)                    ALLOW OUT   Anywhere (v6)             
53 (v6)                    ALLOW OUT   Anywhere (v6)             
123 (v6)                   ALLOW OUT   Anywhere (v6)             
80 (v6)                    ALLOW OUT   Anywhere (v6)             
443 (v6)                   ALLOW OUT   Anywhere (v6)             
Anywhere (v6)              DENY OUT    Anywhere (v6)             
Anywhere (v6)              ALLOW OUT   Anywhere (v6) on tailscale0


# secure SSH
https://www.ssh-audit.com/hardening_guides.html#ubuntu_22_04_lts



https://gist.github.com/gjrdiesel/4e93d8743b71babb58dcba4ee049247c