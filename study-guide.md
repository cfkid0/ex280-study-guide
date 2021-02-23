# OpenShift 4.x EX280 Study Guide
Outline taken from [Red Hat's study points](https://www.redhat.com/en/services/training/ex280-red-hat-certified-specialist-in-openshift-administration-exam?section=Objectives)

## Manage OpenShift Container Platform
### - Use the command-line interface to manage and configure an OpenShift cluster
### - Use the web console to manage and configure an OpenShift cluster
### - Create and delete projects
```
oc new-project $project-name
oc delete project $project-name
oc new-app $app-name
oc delete deployment/$app-name
```

### - Import, export, and configure Kubernetes resources
### - Examine resources and cluster status
```
oc get nodes
oc adm top nodes
oc describe node $node-name
oc get clusterversion
oc desribe clusterversion
oc get clusteroperators
```

### - View logs
`oc logs $pod-name (-n namespace)`

### - Monitor cluster events and alerts
### - Troubleshoot common cluster events and alerts
```

oc adm node-logs -u $user $node-name
oc debug node/$node-name
oc rsh $pod-name
oc cp $filename $pod-name:/$path
```

### - Use product documentation

## Manage users and policies
### - Configure the HTPasswd identity provider for authentication
Create an htpasswd file/user<br>
`htpasswd -c -B -b $filename $user $password`
**Note:** -c creates a new file.  Only needed for first user

Delete a user from htpasswd file
`htpasswd -D $filename $username`

Extract secret information
`oc extract secret/$secret-name -n $namespace --to $path --confirm`

### - Create and delete users
Create the secret
`oc create secret generic $secret-name --from-file htpasswd=$filename --dry-run -o yaml -n openshift-config | oc replace -f -`
** Note:** this command creates the secret and replaces the oauth in OpenShift all in one command.

### - Modify user passwords
Update htpasswd secret
`oc set data secret/$secret-name --from-file htpasswd=$filename -n openshift-config`

Delete the user from OpenShift
`oc delete identity $secret:$username`

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
