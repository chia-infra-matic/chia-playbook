# chia-playbook

Example to install:  

NOTE!: Ensure you pass mnemonic into fork_mnemomic variable. Recommended to be stored in ansible-vault.
ansible-playbook chia-playbook.yml --extra-vars "target=<hostname> fork_name=seno fork_role=farmer action=install"


Examplet to backup:
ansible-playbook chia-playbook.yml --extra-vars "target=<hostname> fork_name=seno fork_role=farmer action=backup"
