---
title: What is Terraform
tree_state: 🌱
---

## Terraform
- declarative listing what resources from different cloud services. Terraform wrote backend code to communicate with the providers so all you need is basically a config file with a `.tf` extension. 
- You need to install terraform, then you run in terminal `terraform init` to configure terraform to work with your providers. Then run `terraform apply` to launch your configured resources from thhe providers.
- `terraform.tfstate` is created/edited on `apply` and it is an important file to keep because it keeps track of previous configs of the terraform resources, so that when you make a new push, it is able to deal with the old resources properly and replace them with the new ones.