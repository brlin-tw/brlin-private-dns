# Private DNS service of Buo-ren Lin

Servicing resolution requests for the public and private domain names in my residence.

<https://gitlab.com/brlin/brlin-private-dns>  
[![The GitLab CI pipeline status badge of the project's `main` branch](https://gitlab.com/brlin/brlin-private-dns/badges/main/pipeline.svg?ignore_skipped=true "Click here to check out the comprehensive status of the GitLab CI pipelines")](https://gitlab.com/brlin/brlin-private-dns/-/pipelines) [![GitHub Actions workflow status badge](https://github.com/brlin-tw/brlin-private-dns/actions/workflows/check-potential-problems.yml/badge.svg "GitHub Actions workflow status")](https://github.com/brlin-tw/brlin-private-dns/actions/workflows/check-potential-problems.yml) [![pre-commit enabled badge](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white "This project uses pre-commit to check potential problems")](https://pre-commit.com/) [![REUSE Specification compliance badge](https://api.reuse.software/badge/gitlab.com/brlin/brlin-private-dns "This project complies to the REUSE specification to decrease software licensing costs")](https://api.reuse.software/info/gitlab.com/brlin/brlin-private-dns)

\#ansible \#dns \#bind

## Usage

This section explains on how to use this product:

### Prerequisites

The following prerequisites must be met before using this product:

* You need to have the following software installed on [the Ansible control node](https://docs.ansible.com/projects/ansible/latest/network/getting_started/basic_concepts.html#control-node):
    + Ansible  
      For the automation runtime itself.
    + [netaddr](https://netaddr.readthedocs.io/en/latest/)  
      Dependency of the brlin-tw.bind Ansible role, must be installed in the same environment as Ansible.
    + [dnspython](https://www.dnspython.org/)  
      Dependency of the brlin-tw.bind Ansible role, must be installed in the same environment as Ansible.
* You need to have SSH access to the managed nodes
* You need to have administrative privileges on the managed nodes.

### How to deploy

To deploy this product, follow these steps:

1. Download the release archive from [the Releases page](https://gitlab.com/brlin/brlin-private-dns/-/releases).
1. Extract the release archive to your preferred directory.
1. Navigate to the extracted directory and edit [the inventory files](inventory/) as needed to match your environment.
1. Launch a text terminal.
1. Run te following command to switch the working directory to the extracted directory:

    ```bash
    cd <extracted-directory>
    ```

   Replace the `<extracted-directory>` placeholder with the path to the directory where you extracted the release archive.
1. Run the Ansible playbook to deploy the product to the managed nodes:

    ```bash
    ansible-playbook -i inventory/production --ask-vault-pass playbooks/deploy-bind.yml
    ```

   Replace `inventory/production` if you're using a different inventory file.

   You may also need to provide the vault password when prompted, depending on your Ansible vault configuration.  Drop the `--ask-vault-pass` command option if you don't use Ansible vault.

## References

The following materials are referenced during the development of this project:

* [bertvv/ansible-role-bind: Sets up ISC BIND as an authoritative DNS server on several Linux distros & FreeBSD](https://github.com/bertvv/ansible-role-bind)  
  Explains on how to use the bertvv.bind Ansible role.

## Licensing

Unless otherwise noted([comment headers](https://reuse.software/spec-3.3/#comment-headers)/[REUSE.toml](https://reuse.software/spec-3.3/#reusetoml)), this product is licensed under [the 3.0 version of the GNU Affero General Public License license](https://www.gnu.org/licenses/agpl-3.0.html), or any of its more recent versions of your preference.

This work complies to [the REUSE Specification](https://reuse.software/spec/), refer to the [REUSE - Make licensing easy for everyone](https://reuse.software/) website for info regarding the licensing of this product.
