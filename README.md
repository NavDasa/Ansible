# Ansible
Ansible-playbooks

# Using YAML for Ansible Playbooks

              User:
                -	Bob
                -	John
                -	Cindy


              User:
                Name: bob
                Job: engineer
                Salary: 10000

              Include newlines: |
                  Type some text
                  Even more text
                  The last of the text

              fold newlines: >
                  type some text
                  more text
                  last of the text

              [] {} : > |

              “{{ var_name }}”

              become: yes

              version: “1.0” 

              
# Install Ansible on ubuntu

On master:
    
    sudo apt-get update
    sudo apt install software-properties-common
    sudo apt-add-repository ppa:ansible/ansible
    sudo apt update
    sudo apt install ansible
    ansible --version

On slave:
    
    sudo apt-get update
    sudo apt-get install python
    
