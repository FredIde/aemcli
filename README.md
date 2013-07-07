# Command line tools to support Adobe Experience Manager (AEM/CQ)

## Tools

* `aem_pkg_upload [-i] server file`  
Upload a package, optionally installing it
* `aem_pkg_replicate server package`  
Replicate a package from an author server to replication agents
* `aem_pkg_download [-o file] server package`  
Download a package
* `aem_pkg_contents server package`  
List the contents of a package
* `aem_pkg_list server`  
List the packages on a server

## Options

The following options are used in one or more the tools.

* -h, --help: display usage
* -b: build the package first
* -i: install
* -d: dry-run
* -r: replicate any changes
* -o file: output to file

## Configuration

Configuration is in *~/.aemcli* using this format:
```bash
# Repository is a Maven repository that's used for releasing and deploying packages
repository=https://nexus.example.com/repository
# Default group that's used for packages
default_group=com.example.aem
# Short aliases may be used on the command line instead of the full server path
# format: aem_alias_ALIAS=URL
aem_alias_autdev01=http://aemautdev01.example.com:4502
aem_alias_wwwdev01=http://aemwwwdev01.example.com:4503
```

Server authentication is in *~/.netrc* using this format:
```
machine aemwwwdev01.example.com login admin password admin
machine aemautdev01.example.com login admin password admin
```

## Planned tools

Directly using the CRX API

* aem_pkg_build autdev01 [com.example.aem:]url-map
* aem_pkg_preview autdev01 [com.example.aem:]url-map
* aem_pkg_delete [-u] autdev01 [com.example.aem:]url-map
* aem_pkg_uninstall autdev01 [com.example.aem:]url-map
* aem_pkg_install [-d] [-r] autdev01 [com.example.aem:]url-map

Extensions

* aem_pkg_transfer [-b] autdev01 autdev02 com.example.aem:url-map
* aem_pkg_repo_deploy autdev01 [com.example.aem:]url-map[:version]
* aem_pkg_repo_release [-b] autdev01 com.example.aem:url-map

## References

* [Adobe Experience Manager - Managing Packages on the Command Line](http://dev.day.com/docs/en/cq/current/core/using_crx/content_import_and.html#Managing Packages on the Command Line)
