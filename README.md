# cisco-aci
Using Cisco ACI sandbox to configuring Cisco APIC
sandboxapicdc.cisco.com
# 1. Requirement
    python3
    Ansible

# From your working directory
    git clone https://github.com/anhdoan-ntt/cisco-aci
    cd cisco-aci
    python3 -m venv --clear venv
    python3 -m venv venv
    source venv/bin/activate
    cd begin
    pip install -r requirements.txt
# The pip command above will install the latest version of Ansible into your virtual environment and will not conflict with any other Ansible installation.
# Change path for file inventory
Update the variable ansible_python_interpreter to the python interpreter in your environment by issuing 

    which python

In an activated python virtual environment the python path will look very similar to this

    /<folder-where-you-cloned-code-samples>/cisco-aci/venv/bin/python
  
 # 2. Run the playbook
 # 2.1. Create a tenant
    ansible-playbook -i inventory 01_aci_tenant_pb.yml
