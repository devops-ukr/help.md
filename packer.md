# packer


```bash
packer [--version] [--help] <command> [<args>]
```

### Available Commands Are: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 [`packer build`](#packer-build) | Will execute multiple builds in parallel as defined in the template.   The various artifacts created by the template will be outputted. 
 [`packer fix`](#packer-fix) | Reads the JSON template and attempts to fix known backwards   incompatibilities. The fixed template will be outputted to standard out.   If the template cannot be fixed due to an error, the command will exit   with a non-zero exit status. Error messages will appear on standard error. 
 [`packer inspect`](#packer-inspect) | Inspects a template, parsing and outputting the components a template   defines. This does not validate the contents of a template (other than   basic syntax by necessity). 
 [`packer push`](#packer-push) | Push the given template and supporting files to a Packer build service such as   Atlas.   If a build configuration for the given template does not exist, it will be   created automatically. If the build configuration already exists, a new   version will be created with this template and the supporting files.   Additional configuration options (such as the Atlas server URL and files to   include) may be specified in the "push" section of the Packer template. Please   see the online documentation for more information about these configurables. 
 [`packer validate`](#packer-validate) | Checks the template is valid by parsing the template and also   checking the configuration with the various builders, provisioners, etc.   If it is not valid, the errors will be shown and the command will exit   with a non-zero exit status. If it is valid, it will exit with a zero   exit status. 
 [`packer version`](#packer-version) | Prints the Packer version, and checks for new release. 


## packer build
Will execute multiple builds in parallel as defined in the template. The various artifacts created by the template will be outputted.

```bash
packer build [options] TEMPLATE
```

#### Options: 

Options | Description 
- | --------------------------------------------------------------------- 
`-color=false` | Disable color output (on by default) 
`-debug` | Debug mode enabled for builds 
`-except=foo,bar,baz` | Build all builds other than these 
`-only=foo,bar,baz` | Build only the specified builds 
`-force` | Force a build to continue if artifacts exist, deletes existing artifacts 
`-machine-readable` | Machine-readable output 
`-on-error=[cleanup|abort|ask]` | If the build fails do: clean up (default), abort, or ask 
`-parallel=false` | Disable parallelization (on by default) 
`-var 'key=value'` | Variable for templates, can be used multiple times. 
`-var-file=path` | JSON file containing user variables. 



-----
## packer fix
Reads the JSON template and attempts to fix known backwards incompatibilities. The fixed template will be outputted to standard out. If the template cannot be fixed due to an error, the command will exit with a non-zero exit status. Error messages will appear on standard error.

```bash
packer fix [options] TEMPLATE
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`-validate=true`      | If true (default), validates the fixed template. 



-----
## packer inspect
Inspects a template, parsing and outputting the components a template defines. This does not validate the contents of a template (other than basic syntax by necessity).

```bash
packer inspect TEMPLATE
```

#### Options: 

Options | Description 
-------------------- | -------------------------------------------------- 
`-machine-readable`  | Machine-readable output 



-----
## packer push
Push the given template and supporting files to a Packer build service such as Atlas. If a build configuration for the given template does not exist, it will be created automatically. If the build configuration already exists, a new version will be created with this template and the supporting files. Additional configuration options (such as the Atlas server URL and files to include) may be specified in the "push" section of the Packer template. Please see the online documentation for more information about these configurables.

```bash
packer push [options] TEMPLATE
```

#### Options: 

Options | Description 
-------------------------- | -------------------------------------------- 
`-name=<name>`             | The destination build in Atlas. This is in a format "username/name". 
`-token=<token>`           | The access token to use to when uploading 
`-sensitive='var1,var2'`   | List of variables to mark as sensitive in Atlas UI. 
`-var 'key=value'`         | Variable for templates, can be used multiple times. 
`-var-file=path`           | JSON file containing user variables. 



-----
## packer validate
Checks the template is valid by parsing the template and also checking the configuration with the various builders, provisioners, etc. If it is not valid, the errors will be shown and the command will exit with a non-zero exit status. If it is valid, it will exit with a zero exit status.

```bash
packer validate [options] TEMPLATE
```

#### Options: 

Options | Description 
------------------------ | ---------------------------------------------- 
`-syntax-only`           | Only check syntax. Do not verify config of the template. 
`-except=foo,bar,baz`    | Validate all builds other than these 
`-only=foo,bar,baz`      | Validate only these builds 
`-var 'key=value'`       | Variable for templates, can be used multiple times. 
`-var-file=path`         | JSON file containing user variables. 



-----
## packer version
Prints the Packer version, and checks for new release.