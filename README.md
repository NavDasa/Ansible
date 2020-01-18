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

              
