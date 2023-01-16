# Write prepared data directly into JDBC-supported destinations using AWS Glue DataBrew

[AWS Glue DataBrew](https://aws.amazon.com/glue/features/databrew/) offers over 250 pre-built transformations to automate data preparation tasks (such as filtering anomalies, standardizing formats, and correcting invalid values) that would otherwise require days or weeks writing hand-coded transformations.

You can now write cleaned and normalized data directly into JDBC-supported databases and data warehouses without having to move large amounts of data into intermediary data stores. In just a few clicks, you can configure recipe jobs to specify the following output destinations: Amazon Redshift, Snowflake, Microsoft SQL Server, MySQL, Oracle Database, and PostgreSQL.

## Solution overview
The following diagram illustrates our solution architecture.
![Architecture](/image/BDB-2081-image001.png)

In our solution, DataBrew queries sales order data from an Amazon S3 data lake and performs the data transformation. Then the DataBrew job writes the final output to Amazon Redshift.

To implement the solution, you complete the following high-level steps:

   + Create your datasets.
   + Create a DataBrew project with the datasets.
   + Build a transformation recipe in DataBrew.
   + Run the DataBrew recipe.

## Prerequisites
To complete this solution, you should have an AWS account. Make sure you have the required permissions to create the resources required as part of the solution.

For our use case, we use a mock dataset. You can download the data files from repository.

Complete the following prerequisite steps:

    + On the Amazon S3 console, upload all three CSV files to an S3 bucket.
![Architecture](/image/BDB-2081-image003.png)
	+ Create the Amazon Redshift cluster to capture the product wise sales data.
	+ Set up a security group for Amazon Redshift.
	+ Create a schema in Amazon Redshift if required. For this post, we use the existing public schema.
	
## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

