# cisco-aci
Using Ansible in virtual enviroment to configure Cisco ACI. Create and manage Tenants, VRFs, BDs. EPGs. on Cisco ACI fabrics.
Cisco APIC using: Cisco APIC sandbox: sandboxapicdc.cisco.com
# 1. Requirement
    python3

From your working directory

    git clone https://github.com/anhdoan-ntt/cisco-aci
    cd cisco-aci
    python3 -m venv --clear venv
    python3 -m venv venv
    source venv/bin/activate
    cd begin
    pip install -r requirements.txt
    
The pip command above will install the latest version of Ansible into your virtual environment and will not conflict with any other Ansible installation.

Change path for file inventory
Update the variable ansible_python_interpreter to the python interpreter in your environment by issuing 

    which python

In an activated python virtual environment the python path will look very similar to this

    /<folder-where-you-cloned-code-samples>/cisco-aci/venv/bin/python
  
 # 2. Run the playbook
 # 2.1. Create a tenant
 Run the command below to create a tenant
 
    ansible-playbook -i inventory 01_aci_tenant_pb.yml
 
 Check if tenant was created by login to:
 https://sandboxapicdc.cisco.com with
 admin/ciscopsdt
 # 2.2. Create multiple BDs and VRF
 Run the following
 
    ansible-playbook 02_aci_tenant_network_pb.yml -i inventory --extra-vars "vrf=prod_vrf"
 
 # 2.3 List all BD in a Tenant
 
    ansible-playbook 08_Query_BD.yml -i inventory
    
 # 2.4 Disable routing on all BDs, enable arp looding
 
     ansible-playbook 03_aci_tenant_bd_pb.yml -i inventory
 

