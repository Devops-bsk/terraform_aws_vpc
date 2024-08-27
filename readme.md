
### AWS VPC MODULE 
This module creates following resources. I am usign HA, getting first 2 AZs automatically
* VPC
* Internet Gateway with VPC association
* 2 Public subnets in 1a and 1b
* 2 private subnets in 1a and 1b
* 2 database subnets in 1a and 1b
* Elastic IP
* NAT gateway in 1a public subnet
* Public Route table
* Private route table
* Database route table
* Subnets and route table associations
* VPC peering if user requests
* Adding the peering route in default VPC, if user don't provide acceptor vpc explicitly.
* Adding the peering routes in public, private and database route tables



### INPUTS 
* project_name (required)
* environment (required)
* vpc_cidr (Optional) - default is 10.0.0.0/16
* enable_dns_hostnames (optional) - default is true
* common_tags (optional) - better to provide
* vpc_tags (optional) 
* igw_tags (optional)
* public_subnet_cidr (required) - must provide 2 valid public subnets CIDR
* public subnets_tags (optional)
* private_subnet_cidr (required) - must provide 2 valid private subnets CIDR
* private subnets_tags (optional)
* database_subnet_cidr (required) - must provide 2 valid database subnets CIDR
* database subnets_tags (optional)
* nat_gateway_tags (optional)
* public_route_table_tags (optional)
* private_route_table_tags (optional)
* database_route_table_tags (optional)
* is_peering_required (optional) - default is false
* acceptor_vpc_id (optional) - default value is default vpc id
* vpc_peering_tags (optional) - default is empty, type is map


### OUTPUTS 
* vpc_id
* public_subnet_ids - 2 
* private_subnet_ids - 2
* database_subnet_ids - 2



### Note
* Tags
- common tags 
- project=roboshop
- terraform = true
- environment = dev

* Resource tags
- vpc ,subnet,nat tags
- merge common and resource tags, resource tags value is placed