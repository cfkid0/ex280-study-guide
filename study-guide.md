# OpenShift 4.x EX280 Study Guide
Outline taken from [Red Hat's study points](https://www.redhat.com/en/services/training/ex280-red-hat-certified-specialist-in-openshift-administration-exam?section=Objectives)

## Manage OpenShift Container Platform
### - Use the command-line interface to manage and configure an OpenShift cluster
### - Use the web console to manage and configure an OpenShift cluster
### - Create and delete projects
```
oc new-project $project-name
oc delete project $project-name
```
### - Import, export, and configure Kubernetes resources
### - Examine resources and cluster status
### - View logs
`oc logs $pod-name (-n namespace)`

### - Monitor cluster events and alerts
### - Troubleshoot common cluster events and alerts
### - Use product documentation

## Manage users and policies
### - Configure the HTPasswd identity provider for authentication
Create an htpasswd file
`htpasswd -c -B -b $filename $user $password`

### - Create and delete users
### - Modify user passwords
### - Modify user and group permissions
### - Create and manage groups

## Control access to resources
### - Define role-based access controls
### - Apply permissions to users
### - Create and apply secrets to manage sensitive information
### - Create service accounts and apply permissions using security context constraints

## Configure networking components
### - Troubleshoot software defined networking
### - Create and edit external routes
### - Control cluster network ingress
### - Create a self signed certificate
### - Secure routes using TLS certificates

## Configure pod scheduling
### - Limit resource usage
### - Scale applications to meet increased demand
### - Control pod placement across cluster nodes

## Configure cluster scaling
### - Manually control the number of cluster workers
### - Automatically scale the number of cluster workers
