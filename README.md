# chef-cd-workshop Cookbook

This cookbook installs and configures Jenkins to facilitate a Continuous
Delivery workshop for Chef cookbooks.

# Recipes
### default
In addition to installing Jenkins, this cookbook also installs Git, ChefDK, and
Docker to facilitate a Continuous Delivery workshop.  When complete, Jenkins
will have security enabled and a single user configured:

** Default Jenkins   User **  
admin / CDWorkshop

Once security is enabled, you will need a key pair to interact with
Jenkins.  This cookbook has a pre-generated key pair to facilitate classroom
use.  **You should not use the included key pair except for evaluation
purposes.**


# Attributes

`node['jenkins']['plugins']` - A array of Jenkins plugin IDs to install.
Default is `%w(ghprb chef-identity envinject ansicolor)`  
`node['jenkins']['admin']['username']` - Username of the automatically created
user.  Default is `'admin'`  
`node['jenkins']['admin']['password']` - Password of the automatically created
user.  Default is `'CDWorkshop'`  
`node['jenkins']['admin']['private_key']` - The private key used to interact with
a secured Jenkins node.  The related public key must be associated with a
Jenkins admin user.  
`node['jenkins']['admin']['public_key']` - The public key associated with the
admin user

# Platforms
- CentOS 6.6+
