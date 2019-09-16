ansible-playbook -i inventories/test mongodb.yml
ansible-playbook -i inventories/test mongodb.yml --tags add_mongo_schema


ansible-vault encrypt inventories/test/group_vars/test_mongodb.yml
ansible-playbook --ask-vault-pass -i inventories/test mongodb.yml --tags add_mongo_schema





#######################################
# When creating/editing/encrypting/decrypting/rekeying a file:
ansible-vault --vault-password-file=vault_password edit inventories/test/group_vars/test_mongodb.yml

# When running ansible playbooks

echo "secret_password" > vault_password
ansible-playbook --vault-password-file=vault_password -i inventories/test mongodb.yml --tags add_mongo_schema

https://serversforhackers.com/c/how-ansible-vault-works
