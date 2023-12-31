<h1 align="center">Kali Ansible Playbook</h1> 

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

---

<p align="center">  This Ansible playbook provides a streamlined solution for customizing newly installed Kali Linux images. With regular updates and tailored configurations, it enables you to quickly and efficiently set up a customized Kali Linux environment to meet your organization's specific needs. The playbook installs essential Linux packages and incorporates various tools from GitHub repositories. Furthermore, it offers flexibility for expansion, allowing you to add new tasks and roles as your requirements evolve.
 <br><br>
</p>

## Table of Contents
+ [Description](#description)
+ [Prerequisites](#prerequisites)
+ [Installation](#installation)
+ [Usage](#usage)
+ [Authors](#authors)


## Description <a name = "description"></a>

This playbook is designed for custom configuration of newly installed Kali Linux images. It serves as a reliable and up-to-date solution to ensure a consistent setup across your Kali Linux deployments. With regular updates, it stays current with the latest software packages and tools required for effective penetration testing and security assessments.

Key Features:
- Custom Configuration: Easily tailor your Kali Linux environment to match your organization's requirements.
- Regular Updates: The playbook is frequently updated to incorporate the latest packages and tools.
- Linux Package Installation: Install essential Linux packages for a comprehensive toolkit.
- GitHub Repository Integration: Incorporate various tools and resources from GitHub repositories.
- Expandable Architecture: The playbook is designed for easy expansion with additional tasks and roles.

By utilizing this playbook, you can save time and effort in configuring newly installed Kali Linux images, ensuring consistency and efficiency in your security testing and assessment workflows.

Please note that the playbook should be customized according to your specific needs and requirements, and additional roles and tasks can be added as your environment evolves.

## Prerequisites <a name = "prerequiisites"></a>

List the prerequisites and requirements for running your playbook. Include the following information:

- Supported operating systems: Kali Linux
- Ansible version requirements
  
  ```bash
  sudo apt update -y && sudo apt upgrade -y
  sudo apt install software-properties-common -y
  sudo apt-add-repository --yes --update ppa:ansible/ansible
  sudo apt install ansible -y
  ```
**_NOTE:_**  
 If you recieve an eror on step three, there may be a [bug](https://www.linuxquestions.org/questions/debian-26/debian-bullseye-sid-add-apt-repository-not-working-python-problem-4175720821/#post6403993). Please run **`sudo apt install python3-launchpadlib -y`** and re-run step 3 as noted found on this [page](https://www.mail-archive.com/debian-bugs-dist@lists.debian.org/msg1891547.html).
 
- Any additional dependencies or software packages
  
  ```bash
  sudo apt install sshpass
  ```
- Supported operating systems
    - Debian based
- Ansible version requirements
- Any additional dependencies or software packages

## Installation <a name = "installation"></a>

Provide step-by-step instructions on how to install and use your playbook. Include the following information:

1. Clone the repository:
   
   ```bash
   git clone https://github.com/cyberchinna/kali-ansible-playbook.git
   ```

## Usage <a name = "usage"></a>

Once the repo has been downloaded, change into the ansible-playbook directory. Execute the playbook using the steps below.

1. Change into the ansible repository.
    ```bash
    cd kali-ansible-playbook
    ```
    
2. Set the user  
   In order to create a new user, modify the `main.yml` file in the `group_vars/localhost` directory. Modify the
   local_user variable. Change `cyberchinna` to your desired new user.
   ```bash
   vi group_vars/localhost/main.yml
   ```
   
   ```bash
   local_user: cyberchinna
   ```
4. Execute the playbook:
   
    ```bash
    ansible-playbook -i ansible/local.ini playbook.yml -K 
    ```


## Authors <a name = "authors"></a>

- [@cyberchinna](https://github.com/cyberchinna) 
 
