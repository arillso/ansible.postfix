# Ansible Role: Postfix
[![Build Status](https://travis-ci.org/arillso/ansible.postfix.svg?branch=master)](https://travis-ci.org/arillso/ansible.postfix)

## Description

Ansible role for installing and configure Postfix, a mail server.

## Installation

```
$ ansible-galaxy install arillso.postfix
```

## Requirements

None

## Role Variables

| Variable                  			| Default     						| Comments (type)                                   |
| :---              		        	| :---        						| :---                                              |
| ```postfix_inet_interfaces```			| ```all``` 						|													| 
| ```postfix_inet_protocols	```			| ```all``` 						|													| 
| ```postfix_hostname```          		| ```"{{ ansible_fqdn }}"``` 		|													|       
| ```postfix_mailname```          		| ```$myhostname``` 				|													| 
| ```postfix_mynetworks``` 				| ```- 127.0.0.0/8 ```				|													|
|	  	       				   			| ```- '[::ffff:127.0.0.0]/104'``` 	|													|
|								    	| ```- '[::1]/128'``` 				|													|
| ```postfix_mydestination ```			| ```- "{{ postfix_hostname }}"```  |													|
|								    	| ```- $myhostname``` 				|													|
|							   		    | ```- localhost.$mydomain``` 		|													|
|							   		    | ```- localhost``` 				|													|
| ```postfix_relayhost```				|									|													|
| ```postfix_relayhost_port``` 			|									|													|
| ```postfix_relaytls```				| ```true```						|													|
| ```postfix_sasl_auth_enable```		| ```true```						|													|
| ```postfix_sasl_user``` 				|									|													|
| ```postfix_sasl_password``` 			|									|													|
| ```postfix_sasl_security_options``` 	| ```noanonymous```					|													|
| ```postfix_root_mailbox``` 			| 									|													|


## Dependencies

None

## Example Playbook

```yml
- hosts: all
  roles:
     - arillso.postfix
```

## Changelog

### 1.3

* new roles tests

### 1.2

* rename role name

### 1.1

* add tags
* add become

### 1.0

* Initial release

## Author

* [Simon Bärlocher](https://sbaerlocher.ch)
 
## License

This project is under the MIT License. See the [LICENSE](https://sbaerlo.ch/licence) file for the full license text.

## Copyright

(c) 2016, Simon Bärlocher