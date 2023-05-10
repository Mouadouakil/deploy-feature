## Tenant provisionning 
Ask your admin here https://discord.com/channels/948214033746624584/965961854977474591 to provision your tenant
The informations needed are : 
* Team name 
* Emails of members (Gmail based emails) 

## Changing flux configuration

FluxCD will automatically sync the cluster with the git repository. 

In order to declare you project to Flux, change to following : 

```
my-namespace -> your project namespace
my-team -> your team name
path -> the path to your project in the git repository
name -> the name of your project
```


## Generating SSH key for Flux

The secret here is named gitops-myapp-auth, but it should be changed to your project name.

```
ssh-keygen -t ecdsa -b 521

flux create secret git gitops-myapp-auth --url=ssh://git@github.com/octocampus/sample-gitops-project.git --private-key-file=flux -n mfa
```
