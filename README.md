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
    

See below video for reference:https://www.youtube.com/watch?v=Km3BCQnV6sw


# Install docker using Ansible

Please fallow below link for reference:

https://www.digitalocean.com/community/tutorials/how-to-use-ansible-to-install-and-set-up-docker-on-ubuntu-18-04


To work ssh-keygen in the ansadmin--> useradd -m ansadmin


# Playbook to deploy Docker.

- hosts: web-servers
  become: true
  tasks:
    - name: Install aptitude using apt
      apt: name=aptitude state=latest update_cache=yes force_apt_get=yes

    - name: Install required system packages
      apt: name={{ item }} state=latest update_cache=yes
      loop: [ 'apt-transport-https', 'ca-certificates', 'curl', 'software-properties-common', 'python3-pip', 'virtualenv', 'python3-setuptools']

    - name: Add Docker GPG apt Key
      apt_key:
        url: https://download.docker.com/linux/ubuntu/gpg
        state: present

    - name: Add Docker Repository
      apt_repository:
        repo: deb https://download.docker.com/linux/ubuntu bionic stable
        state: present
        - name: Update apt and install docker-ce
      apt: update_cache=yes name=docker-ce state=latest

#    - name: Install Docker Module for Python
#      pip:
#      name: docker

#    - name: Adding ansadmin to Dockeradmin
#      command: usermod -aG docker ansadmin

#    - name: Make opt directory
#      command: rmdir /opt/docker && mkdir /opt/docker && cd /opt/docker

#    - name: Build docker image with tomcat webapp
#      docker_image:
#        name: Costumized_tomcat
#        build:
#          path: /opt/playbooks/Dockerfile
#          args:
#            listen_port: 8080
#        source: build
#    - name: Run tomcat container
#      docker:
#        name: Mytomcat
#        image: ansadmin/Costumized_tomcat
#        ports:
#        - "8080:8080"
#        state: started

#- hosts: web-servers
#  become: true
#  tasks:
    - name: copy jar/war onto tomcat servers
      copy:
        src: /opt/playbooks/webapp/target/webapp.war
        dest: /opt/apache-tomcat-8.5.50/webapps


