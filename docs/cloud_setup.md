Supported Cloud Providers:

* [AWS](#aws)
* [GCP](#gcp)
* [Openstack](#openstack)
* [Azure](#azure)
* [Alibaba](#alibaba)

## AWS

**NOTE**: For clusters with AWS make sure [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html) is installed and properly [configured](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html) using an AWS account

## GCP
**NOTE**: For clusters with GCP make sure [GCP CLI](https://cloud.google.com/sdk/docs/install#linux) is installed.

A google service account is required to give proper authentication to GCP for node actions. See [here](https://cloud.google.com/docs/authentication/getting-started) for how to create a service account.

**NOTE**: A user with 'resourcemanager.projects.setIamPolicy' permission is required to grant project-level permissions to the service account.

After creating the service account you'll need to enable the account using the following: ```export GOOGLE_APPLICATION_CREDENTIALS="<serviceaccount.json>"```

## Openstack

**NOTE**: For clusters with Openstack Cloud, ensure to create and source the [OPENSTACK RC file](https://docs.openstack.org/newton/user-guide/common/cli-set-environment-variables-using-openstack-rc.html) to set the OPENSTACK environment variables from the server where Kraken runs.

## Azure

**NOTE**: For Azure node killing scenarios, make sure [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest) is installed

You will also need to create a service principal and give it the correct access, see [here](https://docs.openshift.com/container-platform/4.5/installing/installing_azure/installing-azure-account.html) for creating the service principal and setting the proper permissions

To properly run the service principal requires “Azure Active Directory Graph/Application.ReadWrite.OwnedBy” api permission granted and “User Access Administrator”

Before running you'll need to set the following:
1. Login using ```az login```

2. ```export AZURE_TENANT_ID=<tenant_id>```

3. ```export AZURE_CLIENT_SECRET=<client secret>```

4. ```export AZURE_CLIENT_ID=<client id>```

## Alibaba

See the [Installation guide](https://www.alibabacloud.com/help/en/doc-detail/121988.html?spm=a2c63.p38356.0.0.13f868799CwZPL) to install alicloud cli

1. ```export ALIBABA_ID=<access_key_id>```

2. ```export ALIBABA_SECRET=<access key secret>```

3. ```export ALIBABA_REGION_ID=<region id>```

Refer to [region and zone page](https://www.alibabacloud.com/help/en/doc-detail/188196.htm?spm=a2c63.p38356.0.0.440c5aa4G3MxVt#concept-2459516) to get the region id for the region your running on

Set cloud_type to either alibaba or alicloud in your node scenario yaml file
