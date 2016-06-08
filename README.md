# Sample dynamic AMI lookups using versioning using lambda

What's here:

* `lambda.json` is the cloudformation template that defines the lambda function. It contains a naive implementation of versioning (i.e. just node name + timestamp). We aren't able to share our more robust version (yet), but here's a hint: we use [this package](https://github.com/npm/node-semver) to make it happen.
  * The naive ami lookup function takes 3 paramters:
    - `NodeName`: the spec that you used to build the AMI (e.g. kafka, elasticsearch, myapp...)
    - `Region`: Current AWS Region ID
    - `AccountId`: AWS Account ID
* `sample.json` is an example of how one would use lambda as a custom resource to pull in the AMI dynamically to an AWS AutoScaling group.
