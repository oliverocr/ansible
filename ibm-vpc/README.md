# IBM Cloud Ansible: VPC Virtual Private Cloud

This example creates a VPC with Ansible

## VPC Resources

The following VPC infrastructure resources will be created (Ansible modules in
parentheses):

* VPC (ibm_is_vpc)
* Subnet (ibm_is_subnet)

## Configuration Parameters

The following parameters can be set by the user:

* `name_prefix`: Prefix used to name created resources
* `total_ipv4_address_count`: Number of IPv4 addresses in VPC Subnet
* `zone`: IBM Cloud zone

## Running

### Set API Key and Region

1. [Obtain an IBM Cloud API key].

2. Export your API key to the `IC_API_KEY` environment variable:

    ```
    export IC_API_KEY=<YOUR_API_KEY_HERE>
    ```

    Note: Modules also support the 'ibmcloud_api_key' parameter, but it is
    recommended to only use this when encrypting your API key value.

3. Export desired IBM Cloud region to the 'IC_REGION' environment variable:

    ```
    export IC_REGION=<REGION_NAME_HERE>
    ```

    Note: Modules also support the 'region' parameter.

### Create

To create all resources and test public SSH connection to the VM:

1. Update variables in 'vars.yml'
2. Run the 'create' playbook:

    ```
    ansible-playbook create.yml
    ```

### Destroy

1. To destroy all resources run the 'destroy' playbook (resource names are read
   from 'vars.yml'):

    ```
    ansible-playbook destroy.yml
    ```

[retrieve available images]: #list-available-vsi-images-and-profiles
[retrieve available profiles]: #list-available-vsi-images-and-profiles
[Ansible search path]:https://docs.ansible.com/ansible/latest/dev_guide/overview_architecture.html#ansible-search-path
[Obtain an IBM Cloud API key]:https://cloud.ibm.com/docs/account?topic=account-userapikey&interface=ui
[Ansible search path]: https://docs.ansible.com/ansible/latest/dev_guide/overview_architecture.html#ansible-search-path
