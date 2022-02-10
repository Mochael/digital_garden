---
title: Using the AWS CLI
tree_state: 🌱
---

## Roles
Before you can do anything on aws you need to have a role with permissions to access AWS resources.

Using a profile:
1. Install and setup saml2aws 
2. Run `saml2aws login` with your credentials and select the proper role

To use the api-key information from a certain one of your AWS roles:
- you can run your `aws` command followed by `--profile <role_name>`
- you can also set your profile so that you don't have to specify it every time with `export AWS_PROFILE=<role_name>` 


Example of copying s3 file to local computer:
```
aws s3 cp <s3_path> <local_path> --recursive --profile <role_name>
```

