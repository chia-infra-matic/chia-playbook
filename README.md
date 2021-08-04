# chia-playbook
## Intro

Hello there! If you reached this page you are probably looking for something to allow you to manage your Chia and Chia's Forks farmers in a more efficient and automated way. Because you probable noticed that there are a lot of new forks and it's getting complicated to manage them at the same time.
Lets assume you have a single host with your plots mounted. You can use this playbook to keep your forks up to date.
Suppose you have a more complex infrastructure. You have one host with farmers and other one with your plots. You can automatically configure your farmer (as a primary host) and you can also automatically configure your harvester to join your main farmer).
So i think you are going to enjoy this Ansible Playbook. And I know it because you are going to perform most common operations with a little of initial setup. 
After you set it up. You can/may/should/must (Pick one at your preference) schedule this tasks (I.E.: In a crontab).

### What can this ansible-playbook do for you:
- Install
- Configure (Including additional harvester to a farmer)
- Upgrade (Yes, you read it well, upgrade)
- Remove
- Backup (Yup!)
- Restore (Yeahh!)

### To what components?:
- Farmer (Full node + Farmer + Harvester + Wallet)
- Harvester (Only)

### To what forks is this playbook compatible?:
The list is getting larger and larger and larger. I will just mention some of them but, if not mentioned. Please check the Wiki sections of compatible forks.
- Chia (Of course, afterall we are here because of it)
- Silicoin
- Flax
- Flora
- Etc etc

### To what Operative Systems?:
- Fully tested and working in Ubuntu Server AMD64 and ARM64 (Yup! raspberry too)
- Requires some test but probably will work in any Linux flavor

### Pre-reqs:
- Developed and tested in Ansible version 2.9
- Crossed ssh keys / user configured to access any host that this playbook will execute commands
- You have fully configured a privileged user in any of the machines you are going to execute commands (For further information check the Wiki section)

Note: Again, please check the full list in our Wiki.

# WARNING - Rules
While this playbooks aims to make your life easier bear in mind that:
- Use at your own risk
- This playbook takes some disruptive actions (I.E.: Stop services. Delete data.)
- This playbook has no warranty and will not take responsability of any kind of data loss. If you choose to use we you accept this rules and you will be responsible.
- This playbook is community based. If you encounter an issue/error please submit it through the Issues sections. However, there will not be any resolution time and support will be best effort. Nevertheless, we will try to do the best.

# Sponsor / Support us:
If you find this playbook useful and you like to support us. Here you have some alternatives to send your donations:
- Chia - XCH: xch1pdqcl5aeudjx525st8ykpz3gtaewnq0ca84zclf4yej2umlquheqj4vwpl
- Silicoin - tSIT: tsit1wz80jzxcj8d07dfy4leql5w7s20vewlknj9nrws2e97zfpekd90s02wdts



# Example to perform an install action:  

NOTE!: Ensure you pass mnemonic into fork_mnemomic variable. Recommended to be stored in ansible-vault.
ansible-playbook chia-playbook.yml --extra-vars "target=<hostname> fork_name=silicoin fork_role=farmer action=install"


Examplet to backup:
ansible-playbook chia-playbook.yml --extra-vars "target=<hostname> fork_name=silicoin fork_role=farmer action=backup"
