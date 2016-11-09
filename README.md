# terraform-bluegreen
Terraform module to setup blue / green deployments

### Variables

See the [blue-green/variables.tf](blue-green/variables.tf) file.

### Outputs

* `blue_asg_id`: (Number) blue autoscaling group id
* `green_asg_id`: (Number) green autoscaling group id

### Example

```
module "bluegreen" {
  source = "github.com/skyscrapers/terraform-bluegreen//blue-green"
  project = "example"
  name = "app"
  environment = "production"
  blue_ami = "ami-blabla"
  green_ami = "ami-blabla"
  loadbalancers = []
  blue_max_size = "5"
  blue_min_size = "2"
  blue_desired_capacity = "2"
  green_max_size = "0"
  green_min_size = "0"
  green_desired_capacity = "0"
  security_groups = []
}
```
