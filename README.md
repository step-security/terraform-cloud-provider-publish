<p align="center">
  <a href="https://github.com/step-security/terraform-cloud-provider-publish/actions"><img alt="terraform-cloud-provider-publish status" src="https://github.com/step-security/terraform-cloud-provider-publish/workflows/build-test/badge.svg"></a>
</p>

# Publish a terraform provider to a private registry

Use this action to publish a terraform provider to a terraform cloud private registry:rocket:

## Using the action

This action was designed to be used in conjuction with the example terraform code for 

An example use of the action:
```
-
    name: Publish provider
    uses: step-security/terraform-cloud-provider-publish@v1
    with:
        organization-name: terraform-organization
        organization-api-token: ${{ secrets.TF_CLOUD_TOKEN }}
        provider-directory: dist
        gpg-key: ${{ secrets.GPG_PUBLIC_KEY }}
``` 

### Inputs
#### organization-name
The name of the organization in terraform cloud

#### organization-api-token
Terraform cloud API Token with permission to publish providers to the organization 

#### provider-directory
The directory that contains all of the files neccessary to publish a provider.
This is based on the recommended [go releaser file](https://github.com/hashicorp/terraform-provider-scaffolding-framework/blob/main/.goreleaser.yml) from terraform

#### gpg-key
The public key used to sign the files in the provider-directory in ascii armor format


