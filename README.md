# yum-repos

The purpose of this role is to simplify management of Yum repos.

## Requirements

Currently, it only supports few repos for CentOS 7, Confluent repositories (with configurable URLs) and DP S3 repo.

Tested with Ansible 2.9.x.

## Role Variables

`yr_repos`: a list, which specifies repositories to be present on the managed node.

Currently supported repositories:

* `confluent_platform` (Available then as `confluent`)
* `confluent_dist` (Available then as `confluent.dist`)
For the two above, confluent package path can be configured with `yr_confluent_repo_url`. Defaults to confluent default url.

For CentOS7:
* `centos_epel` (Available then as `epel`)
* `centos_epel_debuginfo` (Available then as `debuginfo`)
* `centos_epel_source` (Available then as `epel.source`)


## Example Playbook

    - hosts: confluent
      roles:
         - role: yum-repos
           vars:
             yr_enabled_repos:
               - "confluent_platform"
               - "confluent_dist"

## License

See LICENSE file.
