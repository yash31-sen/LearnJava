RDS:

can create 40 databases

allocated storage: 100TB can inch in organizational account

DB cluster: grp of dbs

Snapshot: dbs backup to protect from crash





Create db -> 2 options:

Standard create (all configuration we make) simple checkboxes



Easy Create (



30 gb storage free for free tier

never make db publicaly accessible

pswd auth

creating db can take upto 20 min after giving all configurations









Connecting EC2 to RDS

Need Client on EC2 and RDS is server

In url p is password and P is for port

if we make our rds private that is recommended so we have to register the ec2 instance or where ever we are accessing the db to RDS

Connected Compute Resource  -> select instance

as soon as we did this it will create a vpc with ec2 and rds

one more way to do this is to create a role with full access to RDS and cloudwatch (as it comes with rds) and then assign that role to ec2





in case of NOSQL we just have to give a partition key

RDS creates server but DynamoDB is server less

DynamoDB is quick





We can connect DynamoDB with lambda function as well

to create lambda ->

create from scratch, use blueprint,  container image , browse serverless app repository



one lambda function can have multiple events

in this as well have to provide the trust policy we can use roles for this





### Redshift:

It is a fully managed data warehousing solution in AWS

Used for analytics and reporting (OLAP use case)

Stores large amount of historical data (TB–PB scale)

It is optimized for fast query performance

Supports SQL based queries for analysis

Mostly used for read-heavy workloads (not transactional systems)

###### Architecture:

It has 2 main nodes:

Leader Node:

Acts as a coordinator

Receives query from client/user

Creates query execution plan

Distributes work to compute nodes

Combines results and returns final output

Compute Node:

Stores the actual data

Executes query parts sent by leader node

Works in parallel (MPP concept)

Sends results back to leader node

##### Storage:

Uses Columnar storage (column based storage)

Only required columns are scanned in query

Improves query speed and performance

Performance:

Uses Massively Parallel Processing (MPP)

Query is divided into multiple parts and executed parallelly

Supports data compression to improve performance

Scalability:

Cluster can be scaled by adding/removing compute nodes

Supports Elastic resize (faster scaling with less downtime)

Supports Concurrency scaling for multiple queries at same time

##### Backup:

Supports automated backups (snapshots)

Also supports manual snapshots

Data can be restored anytime from backup

Security:

IAM based authentication

VPC based secure network

Encryption at rest and in transit (SSL/TLS)

##### Connectivity:

Default port: 5439

Can connect using:

AWS Query Editor V1 / V2

JDBC / ODBC drivers

SQL clients like DBeaver, SQL Workbench

Monitoring:

Integrated with CloudWatch

##### Tracks:

CPU usage

Query performance

Storage usage

Cluster health

Use Case:

Data from RDS / S3 → loaded into Redshift → used for analytics dashboards

