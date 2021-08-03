# rhcos-ami-upload
Use this ansible role to publish a coreos image to your AWS GovCloud Region. Red Hat
by default does not publish coreos images to aws govcloud. 

Additionally, coreos and openshift rarely share the same release cadence. It is not unusual
for only one or two coreos releases per openshift release. The role will create a temporary 
s3 bucket and then after everything is done will remove it.

## Variables
|Name | Description |
|------|------|
| `ocp_version` | The current ocp version, example: `4.8` |
| `rhcos_version` | The current version of the coreos image, example: `4.8.2`|
| `rhcos_arch` | Architecture of the vmdk, example: `x86_64`|

## Running the playbook
To use this playbook:
1. update `vars/main.yml`
2. run `ansible-playbook rhcos.yml`

Otherwise, you could run everything from a single command without editing anything
`ansible-playbook -e ocp_version=4.8 -e rhcos_version=4.8.2 -e rhcos_arch=x86_64`
