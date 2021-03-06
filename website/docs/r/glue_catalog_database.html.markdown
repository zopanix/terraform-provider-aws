---
subcategory: "Glue"
layout: "aws"
page_title: "AWS: aws_glue_catalog_database"
description: |-
  Provides a Glue Catalog Database.
---

# Resource: aws_glue_catalog_database

Provides a Glue Catalog Database Resource. You can refer to the [Glue Developer Guide](http://docs.aws.amazon.com/glue/latest/dg/populate-data-catalog.html) for a full explanation of the Glue Data Catalog functionality

## Example Usage

```terraform
resource "aws_glue_catalog_database" "aws_glue_catalog_database" {
  name = "MyCatalogDatabase"
}
```

## Argument Reference

The following arguments are supported:

* `name` - (Required) The name of the database. The acceptable characters are lowercase letters, numbers, and the underscore character.
* `catalog_id` - (Optional) ID of the Glue Catalog to create the database in. If omitted, this defaults to the AWS Account ID.
* `description` - (Optional) Description of the database.
* `location_uri` - (Optional) The location of the database (for example, an HDFS path).
* `parameters` - (Optional) A list of key-value pairs that define parameters and properties of the database.

## Attributes Reference

In addition to all arguments above, the following attributes are exported:

* `id` - Catalog ID and name of the database
* `arn` - The ARN of the Glue Catalog Database.

## Import

Glue Catalog Databases can be imported using the `catalog_id:name`. If you have not set a Catalog ID specify the AWS Account ID that the database is in, e.g.

```
$ terraform import aws_glue_catalog_database.database 123456789012:my_database
```
