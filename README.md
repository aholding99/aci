# README.md
- This is a dumping ground for some temporary ACI automation code
- They are NOT designed for production use
- I am NOT a programmer, so if you do use them, it's at your own risk!

# REQUIREMENTS
- sudo yum update
- python -V
- sudo yum install python-pip
- pip install xmljson (required for REST)
- ansible-galaxy collection install cisco.aci

# hosts file as follows;
- [apics:vars]
- ansible_connection=local
- username=aciuser
- password=aciuser!
- ansible_python_interpreter="/usr/bin/python"

- [apics]
- 2.6.10.132 ansible_host=2.6.10.132

# Test as follows;
- ansible -i ./hosts -m ping apics
- ansible-playbook -i ./hosts 01_aci_tenant.yaml --check -vvvv --tags snapshot
