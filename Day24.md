## Working with variables in ansible
![image](https://github.com/Abhinavcode13/DevOpsDrift-Daily/assets/126642111/7d223e59-8d7f-41d7-ab0f-447fc97a5be1)

## Ansible Vaults
- It is is used to secure our data
- When we configure username and password in variables files everybody can see them which is not a good practise.
- When dealing with sensitive data which should secure it.
- Using ansible vault we can secure and protect the data.

### Ansible vault commands
- $ ansible-vault create test.yml - To create ansible vault
- $ ansible-vault encrypt foo.yml - To Encrypting Unencrypted Files
- $ ansible-vault decrypt foo.yml - To Decrypting Encrypted Files
- 
