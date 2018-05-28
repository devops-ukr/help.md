# terraform
The available commands for execution are listed below.
The most common, useful commands are shown first, followed by
less common or more advanced commands. If you're just getting
started with Terraform, stick with the common commands. For the
other commands, please read the help and docs before usage.

```bash
terraform [--version] [--help] <command> [args]
```

### Common Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 [`terraform apply`](#terraform-apply) | Builds or changes infrastructure according to Terraform configuration   files in DIR.   By default, apply scans the current directory for the configuration   and applies the changes appropriately. However, a path to another   configuration or an execution plan can be provided. Execution plans can be   used to only execute a pre-determined set of actions. 
 [`terraform console`](#terraform-console) | Starts an interactive console for experimenting with Terraform   interpolations.   This will open an interactive console that you can use to type   interpolations into and inspect their values. This command loads the   current state. This lets you explore and test interpolations before   using them in future configurations.   This command will never modify your state.   DIR can be set to a directory with a Terraform state to load. By   default, this will default to the current working directory. 
 [`terraform destroy`](#terraform-destroy) | Destroy Terraform-managed infrastructure. 
 [`terraform env`](#terraform-env) | Create, change and delete Terraform workspaces. 
 [`terraform fmt`](#terraform-fmt) | Rewrites all Terraform configuration files to a canonical format. 	If DIR is not specified then the current working directory will be used. 	If DIR is "-" then content will be read from STDIN. 
 [`terraform get`](#terraform-get) | Downloads and installs modules needed for the configuration given by   PATH.   This recursively downloads all modules needed, such as modules   imported by modules imported by the root and so on. If a module is   already downloaded, it will not be redownloaded or checked for updates   unless the -update flag is specified. 
 [`terraform graph`](#terraform-graph) | Outputs the visual execution graph of Terraform resources according to   configuration files in DIR (or the current directory if omitted).   The graph is outputted in DOT format. The typical program that can   read this format is GraphViz, but many web services are also available   to read this format.   The -type flag can be used to control the type of graph shown. Terraform   creates different graphs for different operations. See the options below   for the list of types supported. The default type is "plan" if a   configuration is given, and "apply" if a plan file is passed as an   argument. 
 [`terraform import`](#terraform-import) | Import existing infrastructure into your Terraform state.   This will find and import the specified resource into your Terraform   state, allowing existing infrastructure to come under Terraform   management without having to be initially created by Terraform.   The ADDR specified is the address to import the resource to. Please   see the documentation online for resource addresses. The ID is a   resource-specific ID to identify that resource being imported. Please   reference the documentation for the resource type you're importing to   determine the ID syntax to use. It typically matches directly to the ID   that the provider uses.   The current implementation of Terraform import can only import resources   into the state. It does not generate configuration. A future version of   Terraform will also generate configuration.   Because of this, prior to running terraform import it is necessary to write   a resource configuration block for the resource manually, to which the   imported object will be attached.   This command will not modify your infrastructure, but it will make   network requests to inspect parts of your infrastructure relevant to   the resource being imported. 
 [`terraform init`](#terraform-init) | Initialize a new or existing Terraform working directory by creating   initial files, loading any remote state, downloading modules, etc.   This is the first command that should be run for any new or existing   Terraform configuration per machine. This sets up all the local data   necessary to run Terraform that is typically not committed to version   control.   This command is always safe to run multiple times. Though subsequent runs   may give errors, this command will never delete your configuration or   state. Even so, if you have important information, please back it up prior   to running this command, just in case.   If no arguments are given, the configuration in this working directory   is initialized. 
 [`terraform output`](#terraform-output) | Reads an output variable from a Terraform state file and prints   the value. With no additional arguments, output will display all   the outputs for the root module.  If NAME is not specified, all   outputs are printed. 
 [`terraform plan`](#terraform-plan) | Generates an execution plan for Terraform.   This execution plan can be reviewed prior to running apply to get a   sense for what Terraform will do. Optionally, the plan can be saved to   a Terraform plan file, and apply can take this plan file to execute   this plan exactly.   If a saved plan is passed as an argument, this command will output   the saved plan contents. It will not modify the given plan. 
 [`terraform providers`](#terraform-providers) | Prints out a tree of modules in the referenced configuration annotated with   their provider requirements.   This provides an overview of all of the provider requirements across all   referenced modules, as an aid to understanding why particular provider   plugins are needed and why particular versions are selected. 
 [`terraform push`](#terraform-push) | Upload this Terraform module to an Atlas server for remote   infrastructure management. 
 [`terraform refresh`](#terraform-refresh) | Update the state file of your infrastructure with metadata that matches   the physical resources they are tracking.   This will not modify your infrastructure, but it can modify your   state file to update metadata. This metadata might cause new changes   to occur when you generate a plan or call apply next. 
 [`terraform show`](#terraform-show) | Reads and outputs a Terraform state or plan file in a human-readable   form. If no path is specified, the current state will be shown. 
 [`terraform taint`](#terraform-taint) | Manually mark a resource as tainted, forcing a destroy and recreate   on the next plan/apply.   This will not modify your infrastructure. This command changes your   state to mark a resource as tainted so that during the next plan or   apply, that resource will be destroyed and recreated. This command on   its own will not modify infrastructure. This command can be undone by   reverting the state backup file that is created. 
 [`terraform untaint`](#terraform-untaint) | Manually unmark a resource as tainted, restoring it as the primary   instance in the state.  This reverses either a manual 'terraform taint'   or the result of provisioners failing on a resource.   This will not modify your infrastructure. This command changes your   state to unmark a resource as tainted.  This command can be undone by   reverting the state backup file that is created, or by running   'terraform taint' on the resource. 
 [`terraform validate`](#terraform-validate) | Validate the terraform files in a directory. Validation includes a   basic check of syntax as well as checking that all variables declared   in the configuration are specified in one of the possible ways:       -var foo=...       -var-file=foo.vars       TF_VAR_foo environment variable       terraform.tfvars       default value   If dir is not specified, then the current directory will be used. 
 [`terraform version`](#terraform-version) |  
 [`terraform workspace`](#terraform-workspace) | Create, change and delete Terraform workspaces. 


### All Other Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 [`terraform debug`](#terraform-debug) | This command has subcommands for debug output management 
 [`terraform force-unlock`](#terraform-force-unlock) | Manually unlock the state for the defined configuration.   This will not modify your infrastructure. This command removes the lock on the   state for the current configuration. The behavior of this lock is dependent   on the backend being used. Local state files cannot be unlocked by another   process. 
 [`terraform state`](#terraform-state) | This command has subcommands for advanced state management.   These subcommands can be used to slice and dice the Terraform state.   This is sometimes necessary in advanced cases. For your safety, all   state management commands that modify the state create a timestamped   backup of the state prior to making modifications.   The structure and output of the commands is specifically tailored to work   well with the common Unix utilities such as grep, awk, etc. We recommend   using those tools to perform more advanced state tasks. 


## terraform apply
Builds or changes infrastructure according to Terraform configuration files in DIR. By default, apply scans the current directory for the configuration and applies the changes appropriately. However, a path to another configuration or an execution plan can be provided. Execution plans can be used to only execute a pre-determined set of actions.

```bash
terraform apply [options] [DIR-OR-PLAN]
```

#### Options: 

Options | Description 
------------------------ | ---------------------------------------------- 
`-backup=path`           | Path to backup the existing state file before modifying. Defaults to the "-state-out" path with ".backup" extension. Set to "-" to disable backup. 
`-auto-approve`          | Skip interactive approval of plan before applying. 
`-lock=true`             | Lock the state file when locking is supported. 
`-lock-timeout=0s`       | Duration to retry a state lock. 
`-input=true`            | Ask for input for variables if not directly set. 
`-no-color`              | If specified, output won't contain any color. 
`-parallelism=n`         | Limit the number of parallel resource operations. Defaults to 10. 
`-refresh=true`          | Update state prior to checking for differences. This has no effect if a plan file is given to apply. 
`-state=path`            | Path to read and save state (unless state-out is specified). Defaults to "terraform.tfstate". 
`-state-out=path`        | Path to write state to that is different than "-state". This can be used to preserve the old state. 
`-target=resource`       | Resource to target. Operation will be limited to this resource and its dependencies. This flag can be used multiple times. 
`-var 'foo=bar'`         | Set a variable in the Terraform configuration. This flag can be set multiple times. 
`-var-file=foo`          | Set variables in the Terraform configuration from a file. If "terraform.tfvars" or any ".auto.tfvars" files are present, they will be automatically loaded. 



-----
## terraform console
Starts an interactive console for experimenting with Terraform interpolations. This will open an interactive console that you can use to type interpolations into and inspect their values. This command loads the current state. This lets you explore and test interpolations before using them in future configurations. This command will never modify your state. DIR can be set to a directory with a Terraform state to load. By default, this will default to the current working directory.

```bash
terraform console [options] [DIR]
```

#### Options: 

Options | Description 
------------------------ | ---------------------------------------------- 
`-state=path`            | Path to read state. Defaults to "terraform.tfstate" 
`-var 'foo=bar'`         | Set a variable in the Terraform configuration. This flag can be set multiple times. 
`-var-file=foo`          | Set variables in the Terraform configuration from a file. If "terraform.tfvars" or any ".auto.tfvars" files are present, they will be automatically loaded. 



-----
## terraform destroy
Destroy Terraform-managed infrastructure.

```bash
terraform destroy [options] [DIR]
```

#### Options: 

Options | Description 
------------------------ | ---------------------------------------------- 
`-backup=path`           | Path to backup the existing state file before modifying. Defaults to the "-state-out" path with ".backup" extension. Set to "-" to disable backup. 
`-auto-approve`          | Skip interactive approval before destroying. 
`-force`                 | Deprecated: same as auto-approve. 
`-lock=true`             | Lock the state file when locking is supported. 
`-lock-timeout=0s`       | Duration to retry a state lock. 
`-no-color`              | If specified, output won't contain any color. 
`-parallelism=n`         | Limit the number of concurrent operations. Defaults to 10. 
`-refresh=true`          | Update state prior to checking for differences. This has no effect if a plan file is given to apply. 
`-state=path`            | Path to read and save state (unless state-out is specified). Defaults to "terraform.tfstate". 
`-state-out=path`        | Path to write state to that is different than "-state". This can be used to preserve the old state. 
`-target=resource`       | Resource to target. Operation will be limited to this resource and its dependencies. This flag can be used multiple times. 
`-var 'foo=bar'`         | Set a variable in the Terraform configuration. This flag can be set multiple times. 
`-var-file=foo`          | Set variables in the Terraform configuration from a file. If "terraform.tfvars" or any ".auto.tfvars" files are present, they will be automatically loaded. 



-----
## terraform env
Create, change and delete Terraform workspaces.

```bash
terraform workspace
```

### Subcommands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 [`terraform env delete`](#terraform-env-delete) | Delete a Terraform workspace 
 [`terraform env list`](#terraform-env-list) | List Terraform workspaces. 
 [`terraform env new`](#terraform-env-new) | Create a new Terraform workspace. 
 [`terraform env select`](#terraform-env-select) | Select a different Terraform workspace. 


### terraform env delete
Delete a Terraform workspace

```bash
terraform workspace delete [OPTIONS] NAME [DIR]
```

#### Options: 

Options | Description 
------------- | --------------------------------------------------------- 
`-force`      | remove a non-empty workspace. 



-----
### terraform env list
List Terraform workspaces.

```bash
terraform workspace list [DIR]
```


-----
### terraform env new
Create a new Terraform workspace.

```bash
terraform workspace new [OPTIONS] NAME [DIR]
```

#### Options: 

Options | Description 
------------------ | ---------------------------------------------------- 
`-state=path`      | Copy an existing state file into the new workspace. 



-----
### terraform env select
Select a different Terraform workspace.

```bash
terraform workspace select NAME [DIR]
```


-----
## terraform fmt
Rewrites all Terraform configuration files to a canonical format.
	If DIR is not specified then the current working directory will be used.
	If DIR is "-" then content will be read from STDIN.

```bash
terraform fmt [options] [DIR]
```

#### Options: 

Options | Description 
------------------ | ---------------------------------------------------- 
`-list=true`       | List files whose formatting differs (always false if using STDIN) 
`-write=true`      | Write result to source file instead of STDOUT (always false if using STDIN or -check) 
`-diff=false`      | Display diffs of formatting changes 
`-check=false`     | Check if the input is formatted. Exit status will be 0 if all input is properly formatted and non-zero otherwise. 



-----
## terraform get
Downloads and installs modules needed for the configuration given by PATH. This recursively downloads all modules needed, such as modules imported by modules imported by the root and so on. If a module is already downloaded, it will not be redownloaded or checked for updates unless the -update flag is specified.

```bash
terraform get [options] PATH
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`-update=false`       | If true, modules already downloaded will be checked for updates and updated if necessary. 
`-no-color`           | If specified, output won't contain any color. 



-----
## terraform graph
Outputs the visual execution graph of Terraform resources according to configuration files in DIR (or the current directory if omitted). The graph is outputted in DOT format. The typical program that can read this format is GraphViz, but many web services are also available to read this format. The -type flag can be used to control the type of graph shown. Terraform creates different graphs for different operations. See the options below for the list of types supported. The default type is "plan" if a configuration is given, and "apply" if a plan file is passed as an argument.

```bash
terraform graph [options] [DIR]
```

#### Options: 

Options | Description 
---------------- | ------------------------------------------------------ 
`-draw-cycles`   | Highlight any cycles in the graph with colored edges. This helps when diagnosing cycle errors. 
`-no-color`      | If specified, output won't contain any color. 
`-type=plan`     | Type of graph to output. Can be: plan, plan-destroy, apply, validate, input, refresh. 



-----
## terraform import
Import existing infrastructure into your Terraform state. This will find and import the specified resource into your Terraform state, allowing existing infrastructure to come under Terraform management without having to be initially created by Terraform. The ADDR specified is the address to import the resource to. Please see the documentation online for resource addresses. The ID is a resource-specific ID to identify that resource being imported. Please reference the documentation for the resource type you're importing to determine the ID syntax to use. It typically matches directly to the ID that the provider uses. The current implementation of Terraform import can only import resources into the state. It does not generate configuration. A future version of Terraform will also generate configuration. Because of this, prior to running terraform import it is necessary to write a resource configuration block for the resource manually, to which the imported object will be attached. This command will not modify your infrastructure, but it will make network requests to inspect parts of your infrastructure relevant to the resource being imported.

```bash
terraform import [options] ADDR ID
```

#### Options: 

Options | Description 
------------------------- | --------------------------------------------- 
`-backup=path`            | Path to backup the existing state file before modifying. Defaults to the "-state-out" path with ".backup" extension. Set to "-" to disable backup. 
`-config=path`            | Path to a directory of Terraform configuration files to use to configure the provider. Defaults to pwd. If no config files are present, they must be provided via the input prompts or env vars. 
`-allow-missing-config`   | Allow import when no resource configuration block exists. 
`-input=true`             | Ask for input for variables if not directly set. 
`-lock=true`              | Lock the state file when locking is supported. 
`-lock-timeout=0s`        | Duration to retry a state lock. 
`-no-color`               | If specified, output won't contain any color. 
`-provider=provider`      | Specific provider to use for import. This is used for specifying aliases, such as "aws.eu". Defaults to the normal provider prefix of the resource being imported. 
`-state=PATH`             | Path to the source state file. Defaults to the configured backend, or "terraform.tfstate" 
`-state-out=PATH`         | Path to the destination state file to write to. If this isn't specified, the source state file will be used. This can be a new or existing path. 
`-var 'foo=bar'`          | Set a variable in the Terraform configuration. This flag can be set multiple times. This is only useful with the "-config" flag. 
`-var-file=foo`           | Set variables in the Terraform configuration from a file. If "terraform.tfvars" or any ".auto.tfvars" files are present, they will be automatically loaded. 



-----
## terraform init
Initialize a new or existing Terraform working directory by creating initial files, loading any remote state, downloading modules, etc. This is the first command that should be run for any new or existing Terraform configuration per machine. This sets up all the local data necessary to run Terraform that is typically not committed to version control. This command is always safe to run multiple times. Though subsequent runs may give errors, this command will never delete your configuration or state. Even so, if you have important information, please back it up prior to running this command, just in case. If no arguments are given, the configuration in this working directory is initialized.

```bash
terraform init [options] [DIR]
```

#### Options: 

Options | Description 
---------------------- | ------------------------------------------------ 
`-backend=true`        | Configure the backend for this configuration. 
`-backend-config=path` | This can be either a path to an HCL file with key/value assignments (same format as terraform.tfvars) or a 'key=value' format. This is merged with what is in the configuration file. This can be specified multiple times. The backend type must be in the configuration itself. 
`-force-copy`          | Suppress prompts about copying state data. This is equivalent to providing a "yes" to all confirmation prompts. 
`-from-module=SOURCE`  | Copy the contents of the given module into the target directory before initialization. 
`-get=true`            | Download any modules for this configuration. 
`-get-plugins=true`    | Download any missing plugins for this configuration. 
`-input=true`          | Ask for input if necessary. If false, will error if input was required. 
`-lock=true`           | Lock the state file when locking is supported. 
`-lock-timeout=0s`     | Duration to retry a state lock. 
`-no-color`            | If specified, output won't contain any color. 
`-plugin-dir`          | Directory containing plugin binaries. This overrides all default search paths for plugins, and prevents the automatic installation of plugins. This flag can be used multiple times. 
`-reconfigure`         | Reconfigure the backend, ignoring any saved configuration. 
`-upgrade=false`       | If installing modules (-get) or plugins (-get-plugins), ignore previously-downloaded objects and install the latest version allowed within configured constraints. 
`-verify-plugins=true` | Verify the authenticity and integrity of automatically downloaded plugins. 



-----
## terraform output
Reads an output variable from a Terraform state file and prints the value. With no additional arguments, output will display all the outputs for the root module.  If NAME is not specified, all outputs are printed.

```bash
terraform output [options] [NAME]
```

#### Options: 

Options | Description 
------------------ | ---------------------------------------------------- 
`-state=path`      | Path to the state file to read. Defaults to "terraform.tfstate". 
`-no-color`        | If specified, output won't contain any color. 
`-module=name`     | If specified, returns the outputs for a specific module 
`-json`            | If specified, machine readable output will be printed in JSON format 



-----
## terraform plan
Generates an execution plan for Terraform. This execution plan can be reviewed prior to running apply to get a sense for what Terraform will do. Optionally, the plan can be saved to a Terraform plan file, and apply can take this plan file to execute this plan exactly. If a saved plan is passed as an argument, this command will output the saved plan contents. It will not modify the given plan.

```bash
terraform plan [options] [DIR-OR-PLAN]
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`-destroy`            | If set, a plan will be generated to destroy all resources managed by the given configuration and state. 
`-detailed-exitcode`  | Return detailed exit codes when the command exits. This will change the meaning of exit codes to: 0 - Succeeded, diff is empty (no changes) 1 - Errored 2 - Succeeded, there is a diff 
`-input=true`         | Ask for input for variables if not directly set. 
`-lock=true`          | Lock the state file when locking is supported. 
`-lock-timeout=0s`    | Duration to retry a state lock. 
`-module-depth=n`     | Specifies the depth of modules to show in the output. This does not affect the plan itself, only the output shown. By default, this is -1, which will expand all. 
`-no-color`           | If specified, output won't contain any color. 
`-out=path`           | Write a plan file to the given path. This can be used as input to the "apply" command. 
`-parallelism=n`      | Limit the number of concurrent operations. Defaults to 10. 
`-refresh=true`       | Update state prior to checking for differences. 
`-state=statefile`    | Path to a Terraform state file to use to look up Terraform-managed resources. By default it will use the state "terraform.tfstate" if it exists. 
`-target=resource`    | Resource to target. Operation will be limited to this resource and its dependencies. This flag can be used multiple times. 
`-var 'foo=bar'`      | Set a variable in the Terraform configuration. This flag can be set multiple times. 
`-var-file=foo`       | Set variables in the Terraform configuration from a file. If "terraform.tfvars" or any ".auto.tfvars" files are present, they will be automatically loaded. 



-----
## terraform providers
Prints out a tree of modules in the referenced configuration annotated with their provider requirements. This provides an overview of all of the provider requirements across all referenced modules, as an aid to understanding why particular provider plugins are needed and why particular versions are selected.

```bash
terraform providers [dir]
```


-----
## terraform push
Upload this Terraform module to an Atlas server for remote infrastructure management.

```bash
terraform push [options] [DIR]
```

#### Options: 

Options | Description 
- | --------------------------------------------------------------------- 
`` | -atlas-address=&#60;url&#62; An alternate address to an Atlas instance. Defaults to https://atlas.hashicorp.com -upload-modules=true If true (default), then the modules are locked at their current checkout and uploaded completely. This prevents Atlas from running "terraform get". -name=&#60;name&#62;         Name of the configuration in Atlas. This can also be set in the configuration itself. Format is typically: "username/name". -token=&#60;token&#62;       Access token to use to upload. If blank or unspecified, the ATLAS_TOKEN environmental variable will be used. -overwrite=foo       Variable keys that should overwrite values in Atlas. Otherwise, variables already set in Atlas will overwrite local values. This flag can be repeated. -var 'foo=bar'       Set a variable in the Terraform configuration. This flag can be set multiple times. -var-file=foo        Set variables in the Terraform configuration from a file. If "terraform.tfvars" or any ".auto.tfvars" files are present, they will be automatically loaded. -vcs=true            If true (default), push will upload only files committed to your VCS, if detected. -no-color           If specified, output won't contain any color. 



-----
## terraform refresh
Update the state file of your infrastructure with metadata that matches the physical resources they are tracking. This will not modify your infrastructure, but it can modify your state file to update metadata. This metadata might cause new changes to occur when you generate a plan or call apply next.

```bash
terraform refresh [options] [dir]
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`-backup=path`        | Path to backup the existing state file before modifying. Defaults to the "-state-out" path with ".backup" extension. Set to "-" to disable backup. 
`-input=true`         | Ask for input for variables if not directly set. 
`-lock=true`          | Lock the state file when locking is supported. 
`-lock-timeout=0s`    | Duration to retry a state lock. 
`-no-color`           | If specified, output won't contain any color. 
`-state=path`         | Path to read and save state (unless state-out is specified). Defaults to "terraform.tfstate". 
`-state-out=path`     | Path to write updated state file. By default, the "-state" path will be used. 
`-target=resource`    | Resource to target. Operation will be limited to this resource and its dependencies. This flag can be used multiple times. 
`-var 'foo=bar'`      | Set a variable in the Terraform configuration. This flag can be set multiple times. 
`-var-file=foo`       | Set variables in the Terraform configuration from a file. If "terraform.tfvars" or any ".auto.tfvars" files are present, they will be automatically loaded. 



-----
## terraform show
Reads and outputs a Terraform state or plan file in a human-readable form. If no path is specified, the current state will be shown.

```bash
terraform show [options] [path]
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`-module-depth=n`     | Specifies the depth of modules to show in the output. By default this is -1, which will expand all. 
`-no-color`           | If specified, output won't contain any color. 



-----
## terraform taint
Manually mark a resource as tainted, forcing a destroy and recreate on the next plan/apply. This will not modify your infrastructure. This command changes your state to mark a resource as tainted so that during the next plan or apply, that resource will be destroyed and recreated. This command on its own will not modify infrastructure. This command can be undone by reverting the state backup file that is created.

```bash
terraform taint [options] name
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`-allow-missing`      | If specified, the command will succeed (exit code 0) even if the resource is missing. 
`-backup=path`        | Path to backup the existing state file before modifying. Defaults to the "-state-out" path with ".backup" extension. Set to "-" to disable backup. 
`-lock=true`          | Lock the state file when locking is supported. 
`-lock-timeout=0s`    | Duration to retry a state lock. 
`-module=path`        | The module path where the resource lives. By default this will be root. Child modules can be specified by names. Ex. "consul" or "consul.vpc" (nested modules). 
`-no-color`           | If specified, output won't contain any color. 
`-state=path`         | Path to read and save state (unless state-out is specified). Defaults to "terraform.tfstate". 
`-state-out=path`     | Path to write updated state file. By default, the "-state" path will be used. 



-----
## terraform untaint
Manually unmark a resource as tainted, restoring it as the primary instance in the state.  This reverses either a manual 'terraform taint' or the result of provisioners failing on a resource. This will not modify your infrastructure. This command changes your state to unmark a resource as tainted.  This command can be undone by reverting the state backup file that is created, or by running 'terraform taint' on the resource.

```bash
terraform untaint [options] name
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`-allow-missing`      | If specified, the command will succeed (exit code 0) even if the resource is missing. 
`-backup=path`        | Path to backup the existing state file before modifying. Defaults to the "-state-out" path with ".backup" extension. Set to "-" to disable backup. 
`-lock=true`          | Lock the state file when locking is supported. 
`-lock-timeout=0s`    | Duration to retry a state lock. 
`-module=path`        | The module path where the resource lives. By default this will be root. Child modules can be specified by names. Ex. "consul" or "consul.vpc" (nested modules). 
`-no-color`           | If specified, output won't contain any color. 
`-state=path`         | Path to read and save state (unless state-out is specified). Defaults to "terraform.tfstate". 
`-state-out=path`     | Path to write updated state file. By default, the "-state" path will be used. 



-----
## terraform validate
Validate the terraform files in a directory. Validation includes a basic check of syntax as well as checking that all variables declared in the configuration are specified in one of the possible ways:     -var foo=...     -var-file=foo.vars     TF_VAR_foo environment variable     terraform.tfvars     default value If dir is not specified, then the current directory will be used.

```bash
terraform validate [options] [dir]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-check-variables=true` | If set to true (default), the command will check whether all required variables have been specified. 
`-no-color`             | If specified, output won't contain any color. 
`-var 'foo=bar'`        | Set a variable in the Terraform configuration. This flag can be set multiple times. 
`-var-file=foo`         | Set variables in the Terraform configuration from a file. If "terraform.tfvars" is present, it will be automatically loaded if this flag is not specified. 



-----
## terraform version



-----
## terraform workspace
Create, change and delete Terraform workspaces.

```bash
terraform workspace
```

### Subcommands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 [`terraform workspace delete`](#terraform-workspace-delete) | Delete a Terraform workspace 
 [`terraform workspace list`](#terraform-workspace-list) | List Terraform workspaces. 
 [`terraform workspace new`](#terraform-workspace-new) | Create a new Terraform workspace. 
 [`terraform workspace select`](#terraform-workspace-select) | Select a different Terraform workspace. 
 [`terraform workspace show`](#terraform-workspace-show) | Show the name of the current workspace. 


### terraform workspace delete
Delete a Terraform workspace

```bash
terraform workspace delete [OPTIONS] NAME [DIR]
```

#### Options: 

Options | Description 
------------- | --------------------------------------------------------- 
`-force`      | remove a non-empty workspace. 



-----
### terraform workspace list
List Terraform workspaces.

```bash
terraform workspace list [DIR]
```


-----
### terraform workspace new
Create a new Terraform workspace.

```bash
terraform workspace new [OPTIONS] NAME [DIR]
```

#### Options: 

Options | Description 
------------------ | ---------------------------------------------------- 
`-state=path`      | Copy an existing state file into the new workspace. 



-----
### terraform workspace select
Select a different Terraform workspace.

```bash
terraform workspace select NAME [DIR]
```


-----
### terraform workspace show
Show the name of the current workspace.

```bash
terraform workspace show
```


-----
## terraform debug
This command has subcommands for debug output management

```bash
terraform debug <subcommand> [options] [args]
```

### Subcommands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 [`terraform debug json2dot`](#terraform-debug-json2dot) | Translate a graph debug file to dot format.   This command takes a single json graph log file and converts it to a single   dot graph written to stdout. 


### terraform debug json2dot
Translate a graph debug file to dot format. This command takes a single json graph log file and converts it to a single dot graph written to stdout.

```bash
terraform debug json2dot input.json
```


-----
## terraform force-unlock
Manually unlock the state for the defined configuration. This will not modify your infrastructure. This command removes the lock on the state for the current configuration. The behavior of this lock is dependent on the backend being used. Local state files cannot be unlocked by another process.

```bash
terraform force-unlock LOCK_ID [DIR]
```

#### Options: 

Options | Description 
------------------------ | ---------------------------------------------- 
`-force`                 | Don't ask for input for unlock confirmation. 



-----
## terraform state
This command has subcommands for advanced state management. These subcommands can be used to slice and dice the Terraform state. This is sometimes necessary in advanced cases. For your safety, all state management commands that modify the state create a timestamped backup of the state prior to making modifications. The structure and output of the commands is specifically tailored to work well with the common Unix utilities such as grep, awk, etc. We recommend using those tools to perform more advanced state tasks.

```bash
terraform state <subcommand> [options] [args]
```

### Subcommands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 [`terraform state list`](#terraform-state-list) | List resources in the Terraform state.   This command lists resources in the Terraform state. The pattern argument   can be used to filter the resources by resource or module. If no pattern   is given, all resources are listed.   The pattern argument is meant to provide very simple filtering. For   advanced filtering, please use tools such as "grep". The output of this   command is designed to be friendly for this usage.   The pattern argument accepts any resource targeting syntax. Please   refer to the documentation on resource targeting syntax for more   information. 
 [`terraform state mv`](#terraform-state-mv) | This command will move an item matched by the address given to the  destination address. This command can also move to a destination address  in a completely different state file.  This can be used for simple resource renaming, moving items to and from  a module, moving entire modules, and more. And because this command can also  move data to a completely new state, it can also be used for refactoring  one configuration into multiple separately managed Terraform configurations.  This command will output a backup copy of the state prior to saving any  changes. The backup cannot be disabled. Due to the destructive nature  of this command, backups are required.  If you're moving an item to a different state file, a backup will be created  for each state file. 
 [`terraform state pull`](#terraform-state-pull) | Pull the state from its location and output it to stdout.   This command "pulls" the current state and outputs it to stdout.   The primary use of this is for state stored remotely. This command   will still work with local state but is less useful for this. 
 [`terraform state push`](#terraform-state-push) | Update remote state from a local state file at PATH.   This command "pushes" a local state and overwrites remote state   with a local state file. The command will protect you against writing   an older serial or a different state file lineage unless you specify the   "-force" flag.   This command works with local state (it will overwrite the local   state), but is less useful for this use case.   If PATH is "-", then this command will read the state to push from stdin.   Data from stdin is not streamed to the backend: it is loaded completely   (until pipe close), verified, and then pushed. 
 [`terraform state rm`](#terraform-state-rm) | Remove one or more items from the Terraform state.   This command removes one or more items from the Terraform state based   on the address given. You can view and list the available resources   with "terraform state list".   This command creates a timestamped backup of the state on every invocation.   This can't be disabled. Due to the destructive nature of this command,   the backup is ensured by Terraform for safety reasons. 
 [`terraform state show`](#terraform-state-show) | Shows the attributes of a resource in the Terraform state.   This command shows the attributes of a single resource in the Terraform   state. The address argument must be used to specify a single resource.   You can view the list of available resources with "terraform state list". 


### terraform state list
List resources in the Terraform state. This command lists resources in the Terraform state. The pattern argument can be used to filter the resources by resource or module. If no pattern is given, all resources are listed. The pattern argument is meant to provide very simple filtering. For advanced filtering, please use tools such as "grep". The output of this command is designed to be friendly for this usage. The pattern argument accepts any resource targeting syntax. Please refer to the documentation on resource targeting syntax for more information.

```bash
terraform state list [options] [pattern...]
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`-state=statefile`    | Path to a Terraform state file to use to look up Terraform-managed resources. By default it will use the state "terraform.tfstate" if it exists. 
`-id=ID`              | Restricts the output to objects whose id is ID. 



-----
### terraform state mv
This command will move an item matched by the address given to the
 destination address. This command can also move to a destination address
 in a completely different state file.
 This can be used for simple resource renaming, moving items to and from
 a module, moving entire modules, and more. And because this command can also
 move data to a completely new state, it can also be used for refactoring
 one configuration into multiple separately managed Terraform configurations.
 This command will output a backup copy of the state prior to saving any
 changes. The backup cannot be disabled. Due to the destructive nature
 of this command, backups are required.
 If you're moving an item to a different state file, a backup will be created
 for each state file.

```bash
terraform state mv [options] SOURCE DESTINATION
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`-backup=PATH`        | Path where Terraform should write the backup for the original state. This can't be disabled. If not set, Terraform will write it to the same path as the statefile with a ".backup" extension. 
`-backup-out=PATH`    | Path where Terraform should write the backup for the destination state. This can't be disabled. If not set, Terraform will write it to the same path as the destination state file with a backup extension. This only needs to be specified if -state-out is set to a different path than -state. 
`-state=PATH`         | Path to the source state file. Defaults to the configured backend, or "terraform.tfstate" 
`-state-out=PATH`     | Path to the destination state file to write to. If this isn't specified, the source state file will be used. This can be a new or existing path. 



-----
### terraform state pull
Pull the state from its location and output it to stdout. This command "pulls" the current state and outputs it to stdout. The primary use of this is for state stored remotely. This command will still work with local state but is less useful for this.

```bash
terraform state pull [options]
```


-----
### terraform state push
Update remote state from a local state file at PATH. This command "pushes" a local state and overwrites remote state with a local state file. The command will protect you against writing an older serial or a different state file lineage unless you specify the "-force" flag. This command works with local state (it will overwrite the local state), but is less useful for this use case. If PATH is "-", then this command will read the state to push from stdin. Data from stdin is not streamed to the backend: it is loaded completely (until pipe close), verified, and then pushed.

```bash
terraform state push [options] PATH
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`-force`              | Write the state even if lineages don't match or the remote serial is higher. 



-----
### terraform state rm
Remove one or more items from the Terraform state. This command removes one or more items from the Terraform state based on the address given. You can view and list the available resources with "terraform state list". This command creates a timestamped backup of the state on every invocation. This can't be disabled. Due to the destructive nature of this command, the backup is ensured by Terraform for safety reasons.

```bash
terraform state rm [options] ADDRESS...
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`-backup=PATH`        | Path where Terraform should write the backup state. This can't be disabled. If not set, Terraform will write it to the same path as the statefile with a backup extension. 
`-state=PATH`         | Path to the source state file. Defaults to the configured backend, or "terraform.tfstate" 



-----
### terraform state show
Shows the attributes of a resource in the Terraform state. This command shows the attributes of a single resource in the Terraform state. The address argument must be used to specify a single resource. You can view the list of available resources with "terraform state list".

```bash
terraform state show [options] ADDRESS
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`-state=statefile`    | Path to a Terraform state file to use to look up Terraform-managed resources. By default it will use the state "terraform.tfstate" if it exists.