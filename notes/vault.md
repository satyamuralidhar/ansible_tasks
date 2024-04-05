### create a file with password

    $ echo "password: mypasswd" > creds.yaml

### Encrypt and set password for Vault

    $ ansible-vault encrypt creds.yaml # set password for vault

### View file is Encripted Or Not

    $ cat creds.yaml 

    $ANSIBLE_VAULT;1.2;AES256;dev
          30613233633461343837653833666333643061636561303338373661313838333565653635353162
          3263363434623733343538653462613064333634333464660a663633623939393439316636633863
          61636237636537333938306331383339353265363239643939666639386530626330633337633833
          6664656334373166630a363736393262666465663432613932613036303963343263623137386239
          6330

### Apply Playbook using vault password

    $ ansible-playbook git.yml --ask-vault-pass 

OR
    
    $ ansible-playbook git.yml --vault-id @prompt 

### View Encripted vault password into decrypted Way

    $ ansible-vault view creds.yaml 

### Decrypt vault password

    $ ansible-vault decrypt creds.yaml 


### To store vault paasword in a file 
    
    $echo "vaultpassword" > ~/.vaultpass

### Apply Playbook using vault password file

    $ ansible-playbook git.yml --vault-password-file ~/.vaultpass