terraform-amitype
=================

Simple terraform module to allow you to look up the type of AMI
you need to use for a particular instance type.

You simply pass the module your ''instance_type'' and it outputs
an ''ami_type'' which will contain either 'hvm' or 'pv'.

You can then use this in your AMI lookup module to work out which
AMI you need

Use this in your terraform code like this:

    module "amitype" {
        source = "github.com/tdoran/terraform-amitype"
        instance_type = "m3.xlarge"
    }

And you can then reference:

    "${module.amitype.ami_type}"

which will return either 'hvm' or 'pv'
