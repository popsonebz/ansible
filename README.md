ansible-playbook -i inventories/test mongodb.yml
ansible-playbook -i inventories/test mongodb.yml --tags add_mongo_schema


ansible-vault encrypt inventories/test/group_vars/test_mongodb.yml
ansible-playbook --ask-vault-pass -i inventories/test mongodb.yml --tags add_mongo_schema
