# Ansible_Ubuntu_Apache_SSL_Jenkins_Example

### Precondition:

#### Install aws cli [docs](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)

#### Create and setup AWS IAM account for aws cli [docs](https://docs.aws.amazon.com/cli/latest/userguide/cli-authentication-user.html)

#### Install terraform use [docs](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)

#### Install Python 3.7.9 [docs](https://www.python.org/downloads/release/python-379/) develop and tested on 3.7.9 version

#### Install ansible [docs](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

### How to use:

#### Modify ec2.tf file for your needs

#### Execute:

```
terraform init
terraform plan
```

#### Werify that output for terraform paln is correct

#### Execute:

```
terraform apply -auto-approve
```

#### Take ec2 public ip from output and set in to the hosts.ini:

```
<your instance public ip> ansible_ssh_user=<server username> ansible_ssh_private_key_file=<paht to pem file>
```

#### Execute:

```
ansible-playbook -i hosts.ini 000_setup.yml
```

#### When ansible finish copy password from output and open in browser:

```
https://<instance public ip>
```

#### Finaly setup your Jenkins master to your needs

##### TODO:

- Add slaves (linux, Windows, MacOs)
- Integrate terraform with ansible in single pipeline with terraform provisioners
