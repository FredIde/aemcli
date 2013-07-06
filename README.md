# Command line tools to support Adobe Experience Manager (AEM/CQ)

Configuration example

```
repository=https://nexus.example.com/repository
default_group=com.example.aem
aem_alias_autdev01=http://aemautdev01.example.com:4502
aem_alias_wwwdev01=http://aemwwwdev01.example.com:4503
```

## Planned tools

Directly using the CRX API

* aem_pkg_upload [-i|-d] [-f] autdev01 file
* aem_pkg_install [-d] [-r] autdev01 [com.example.aem:]url-map
* aem_pkg_build autdev01 [com.example.aem:]url-map
* aem_pkg_preview autdev01 [com.example.aem:]url-map
* aem_pkg_delete  autdev01 [com.example.aem:]url-map
* aem_pkg_uninstall autdev01 [com.example.aem:]url-map
* aem_pkg_replicate autdev01 [com.example.aem:]url-map
* aem_pkg_download [-o file] autdev01 [com.example.aem:]url-map
* aem_pkg_contents autdev01 [com.example.aem:]url-map
* aem_pkg_list autdev01

Extensions

* aem_pkg_transfer [-r] autdev01 autdev02 com.example.aem:url-map
* aem_pkg_repo_deploy autdev01 [com.example.aem:]url-map[:version]
* aem_pkg_repo_release [-r] autdev01 com.example.aem:url-map

Options

* -h, --help: display usage
* -r: rebuild the package
* -i: install
* -d: dry-run
* -o file: output to file

## References

* [Adobe Experience Manager - Managing Packages on the Command Line](http://dev.day.com/docs/en/cq/current/core/using_crx/content_import_and.html#Managing Packages on the Command Line)
