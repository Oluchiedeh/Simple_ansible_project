### Ansible Project.

***Use ansible to deploy a website to multiply instances.***
1.  First launch an EC2 instance/machine called ansible machine, then install Ansible on it.
2.  Create key pairs on the ansible machine and use the key pair to establish ssh connection between the ansible machine and the servers I want to configure.
3.  To establish an ssh connection, I will create a security group that allows ssh access between the ansible machine and the servers.
4.  Next, I will launch three(3) EC2 Instances.(the instance where I will configure ansible and install the website on.
5.  An Ansible playbook will be created on the ansible machine.
6.  Then I will create an Inventory file and configuration file.


## Steps involve in the project creation.
**1. Create security group(SG) for the ansible machine.**
   - In the management console type VPC, and select VPC under services. scroll 
      and select security group
   - Click the security group and give it a name [ansible_machine SG]
   - Give the SG a description name.
   - Select the default VPC.
   - The inbound rule will be 'ssh rule' and source to 'My IP'
   - Then select create security group.
     
     ![](securitygroup1.png)

     ![](securitygroup2.png)
     
**2. Create security group to add to webservers.**
   - In the management console type VPC, and select VPC under services. scroll 
      and select security group
   - Click the security group and give it a name [server SG]
   - Give the SG a description name.
   - Select the default VPC.
   - The inbound rule will be two(2) rules 1. 'HTTP' and source to 'anywhere IPv4', 2. 'ssh' and source 'ansible_machine sg'
   - Then select create security group.

    ![](securitygroup3.png)

    ![](securitygroup4.png)

    ![](securitygroup5.png)
     
