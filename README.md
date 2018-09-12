# EKS Getting Started Configuration

Use this configuration to create an EKS cluster on AWS.

<br>
<br>

# 1 Usage

### 1.1 Clone

Execute in terminal: 

```
git clone https://github.com/sachsenhofer/terraform_eks.git
```

### 1.2 Init

Execute in terminal: 

```
terraform init
```

### 1.3 Plan

Execute in terminal: 

```
terraform plan
```

### 1.4 Apply

Execute in terminal: 

```
terraform apply
```

__Note:__ It takes about 10 minutes to create the resources.

### 1.5 Destroy

Execute in terminal: 

```
terraform destroy
```

__Note:__ It takes about 10 minutes to destroy the resources.

<br>
<br>

# 2 Execution plan

### 2.1 Execution plan

```
------------------------------------------------------------------------

An execution plan has been generated and is shown below.
Resource actions are indicated with the following symbols:
  + create

Terraform will perform the following actions:

  + aws_autoscaling_group.demo
      id:                                            <computed>
      arn:                                           <computed>
      availability_zones.#:                          <computed>
      default_cooldown:                              <computed>
      desired_capacity:                              "2"
      force_delete:                                  "false"
      health_check_grace_period:                     "300"
      health_check_type:                             <computed>
      launch_configuration:                          "${aws_launch_configuration.demo.id}"
      load_balancers.#:                              <computed>
      max_size:                                      "2"
      metrics_granularity:                           "1Minute"
      min_size:                                      "1"
      name:                                          "terraform-eks-demo"
      protect_from_scale_in:                         "false"
      service_linked_role_arn:                       <computed>
      tag.#:                                         "2"
      tag.3381877819.key:                            "kubernetes.io/cluster/terraform-eks-demo"
      tag.3381877819.propagate_at_launch:            "true"
      tag.3381877819.value:                          "owned"
      tag.4079220990.key:                            "Name"
      tag.4079220990.propagate_at_launch:            "true"
      tag.4079220990.value:                          "terraform-eks-demo"
      target_group_arns.#:                           <computed>
      vpc_zone_identifier.#:                         <computed>
      wait_for_capacity_timeout:                     "10m"

  + aws_eks_cluster.demo
      id:                                            <computed>
      arn:                                           <computed>
      certificate_authority.#:                       <computed>
      created_at:                                    <computed>
      endpoint:                                      <computed>
      name:                                          "terraform-eks-demo"
      role_arn:                                      "${aws_iam_role.demo-cluster.arn}"
      version:                                       <computed>
      vpc_config.#:                                  "1"
      vpc_config.0.security_group_ids.#:             <computed>
      vpc_config.0.subnet_ids.#:                     <computed>
      vpc_config.0.vpc_id:                           <computed>

  + aws_iam_instance_profile.demo-node
      id:                                            <computed>
      arn:                                           <computed>
      create_date:                                   <computed>
      name:                                          "terraform-eks-demo"
      path:                                          "/"
      role:                                          "terraform-eks-demo-node"
      roles.#:                                       <computed>
      unique_id:                                     <computed>

  + aws_iam_role.demo-cluster
      id:                                            <computed>
      arn:                                           <computed>
      assume_role_policy:                            "{\n  \"Version\": \"2012-10-17\",\n  \"Statement\": [\n    {\n      \"Effect\": \"Allow\",\n      \"Principal\": {\n        \"Service\": \"eks.amazonaws.com\"\n      },\n      \"Action\": \"sts:AssumeRole\"\n    }\n  ]\n}\n"
      create_date:                                   <computed>
      force_detach_policies:                         "false"
      max_session_duration:                          "3600"
      name:                                          "terraform-eks-demo-cluster"
      path:                                          "/"
      unique_id:                                     <computed>

  + aws_iam_role.demo-node
      id:                                            <computed>
      arn:                                           <computed>
      assume_role_policy:                            "{\n  \"Version\": \"2012-10-17\",\n  \"Statement\": [\n    {\n      \"Effect\": \"Allow\",\n      \"Principal\": {\n        \"Service\": \"ec2.amazonaws.com\"\n      },\n      \"Action\": \"sts:AssumeRole\"\n    }\n  ]\n}\n"
      create_date:                                   <computed>
      force_detach_policies:                         "false"
      max_session_duration:                          "3600"
      name:                                          "terraform-eks-demo-node"
      path:                                          "/"
      unique_id:                                     <computed>

  + aws_iam_role_policy_attachment.demo-cluster-AmazonEKSClusterPolicy
      id:                                            <computed>
      policy_arn:                                    "arn:aws:iam::aws:policy/AmazonEKSClusterPolicy"
      role:                                          "terraform-eks-demo-cluster"

  + aws_iam_role_policy_attachment.demo-cluster-AmazonEKSServicePolicy
      id:                                            <computed>
      policy_arn:                                    "arn:aws:iam::aws:policy/AmazonEKSServicePolicy"
      role:                                          "terraform-eks-demo-cluster"

  + aws_iam_role_policy_attachment.demo-node-AmazonEC2ContainerRegistryReadOnly
      id:                                            <computed>
      policy_arn:                                    "arn:aws:iam::aws:policy/AmazonEC2ContainerRegistryReadOnly"
      role:                                          "terraform-eks-demo-node"

  + aws_iam_role_policy_attachment.demo-node-AmazonEKSWorkerNodePolicy
      id:                                            <computed>
      policy_arn:                                    "arn:aws:iam::aws:policy/AmazonEKSWorkerNodePolicy"
      role:                                          "terraform-eks-demo-node"

  + aws_iam_role_policy_attachment.demo-node-AmazonEKS_CNI_Policy
      id:                                            <computed>
      policy_arn:                                    "arn:aws:iam::aws:policy/AmazonEKS_CNI_Policy"
      role:                                          "terraform-eks-demo-node"

  + aws_internet_gateway.demo
      id:                                            <computed>
      tags.%:                                        "1"
      tags.Name:                                     "terraform-eks-demo"
      vpc_id:                                        "${aws_vpc.demo.id}"

  + aws_launch_configuration.demo
      id:                                            <computed>
      associate_public_ip_address:                   "true"
      ebs_block_device.#:                            <computed>
      ebs_optimized:                                 <computed>
      enable_monitoring:                             "true"
      iam_instance_profile:                          "terraform-eks-demo"
      image_id:                                      "ami-02415125ccd555295"
      instance_type:                                 "m4.large"
      key_name:                                      <computed>
      name:                                          <computed>
      name_prefix:                                   "terraform-eks-demo"
      root_block_device.#:                           <computed>
      security_groups.#:                             <computed>
      user_data_base64:                              "${base64encode(local.demo-node-userdata)}"

  + aws_route_table.demo
      id:                                            <computed>
      propagating_vgws.#:                            <computed>
      route.#:                                       "1"
      route.~860154942.cidr_block:                   "0.0.0.0/0"
      route.~860154942.egress_only_gateway_id:       ""
      route.~860154942.gateway_id:                   "${aws_internet_gateway.demo.id}"
      route.~860154942.instance_id:                  ""
      route.~860154942.ipv6_cidr_block:              ""
      route.~860154942.nat_gateway_id:               ""
      route.~860154942.network_interface_id:         ""
      route.~860154942.vpc_peering_connection_id:    ""
      vpc_id:                                        "${aws_vpc.demo.id}"

  + aws_route_table_association.demo[0]
      id:                                            <computed>
      route_table_id:                                "${aws_route_table.demo.id}"
      subnet_id:                                     "${aws_subnet.demo.*.id[count.index]}"

  + aws_route_table_association.demo[1]
      id:                                            <computed>
      route_table_id:                                "${aws_route_table.demo.id}"
      subnet_id:                                     "${aws_subnet.demo.*.id[count.index]}"

  + aws_security_group.demo-cluster
      id:                                            <computed>
      arn:                                           <computed>
      description:                                   "Cluster communication with worker nodes"
      egress.#:                                      "1"
      egress.482069346.cidr_blocks.#:                "1"
      egress.482069346.cidr_blocks.0:                "0.0.0.0/0"
      egress.482069346.description:                  ""
      egress.482069346.from_port:                    "0"
      egress.482069346.ipv6_cidr_blocks.#:           "0"
      egress.482069346.prefix_list_ids.#:            "0"
      egress.482069346.protocol:                     "-1"
      egress.482069346.security_groups.#:            "0"
      egress.482069346.self:                         "false"
      egress.482069346.to_port:                      "0"
      ingress.#:                                     <computed>
      name:                                          "terraform-eks-demo-cluster"
      owner_id:                                      <computed>
      revoke_rules_on_delete:                        "false"
      tags.%:                                        "1"
      tags.Name:                                     "terraform-eks-demo"
      vpc_id:                                        "${aws_vpc.demo.id}"

  + aws_security_group.demo-node
      id:                                            <computed>
      arn:                                           <computed>
      description:                                   "Security group for all nodes in the cluster"
      egress.#:                                      "1"
      egress.482069346.cidr_blocks.#:                "1"
      egress.482069346.cidr_blocks.0:                "0.0.0.0/0"
      egress.482069346.description:                  ""
      egress.482069346.from_port:                    "0"
      egress.482069346.ipv6_cidr_blocks.#:           "0"
      egress.482069346.prefix_list_ids.#:            "0"
      egress.482069346.protocol:                     "-1"
      egress.482069346.security_groups.#:            "0"
      egress.482069346.self:                         "false"
      egress.482069346.to_port:                      "0"
      ingress.#:                                     <computed>
      name:                                          "terraform-eks-demo-node"
      owner_id:                                      <computed>
      revoke_rules_on_delete:                        "false"
      tags.%:                                        "2"
      tags.Name:                                     "terraform-eks-demo-node"
      tags.kubernetes.io/cluster/terraform-eks-demo: "owned"
      vpc_id:                                        "${aws_vpc.demo.id}"

  + aws_security_group_rule.demo-cluster-ingress-node-https
      id:                                            <computed>
      description:                                   "Allow pods to communicate with the cluster API Server"
      from_port:                                     "443"
      protocol:                                      "tcp"
      security_group_id:                             "${aws_security_group.demo-cluster.id}"
      self:                                          "false"
      source_security_group_id:                      "${aws_security_group.demo-node.id}"
      to_port:                                       "443"
      type:                                          "ingress"

  + aws_security_group_rule.demo-cluster-ingress-workstation-https
      id:                                            <computed>
      cidr_blocks.#:                                 "1"
      cidr_blocks.0:                                 "195.50.84.65/32"
      description:                                   "Allow workstation to communicate with the cluster API Server"
      from_port:                                     "443"
      protocol:                                      "tcp"
      security_group_id:                             "${aws_security_group.demo-cluster.id}"
      self:                                          "false"
      source_security_group_id:                      <computed>
      to_port:                                       "443"
      type:                                          "ingress"

  + aws_security_group_rule.demo-node-ingress-cluster
      id:                                            <computed>
      description:                                   "Allow worker Kubelets and pods to receive communication from the cluster control plane"
      from_port:                                     "1025"
      protocol:                                      "tcp"
      security_group_id:                             "${aws_security_group.demo-node.id}"
      self:                                          "false"
      source_security_group_id:                      "${aws_security_group.demo-cluster.id}"
      to_port:                                       "65535"
      type:                                          "ingress"

  + aws_security_group_rule.demo-node-ingress-self
      id:                                            <computed>
      description:                                   "Allow node to communicate with each other"
      from_port:                                     "0"
      protocol:                                      "-1"
      security_group_id:                             "${aws_security_group.demo-node.id}"
      self:                                          "false"
      source_security_group_id:                      "${aws_security_group.demo-node.id}"
      to_port:                                       "65535"
      type:                                          "ingress"

  + aws_subnet.demo[0]
      id:                                            <computed>
      arn:                                           <computed>
      assign_ipv6_address_on_creation:               "false"
      availability_zone:                             "us-west-2a"
      cidr_block:                                    "10.0.0.0/24"
      ipv6_cidr_block:                               <computed>
      ipv6_cidr_block_association_id:                <computed>
      map_public_ip_on_launch:                       "false"
      tags.%:                                        "2"
      tags.Name:                                     "terraform-eks-demo-node"
      tags.kubernetes.io/cluster/terraform-eks-demo: "shared"
      vpc_id:                                        "${aws_vpc.demo.id}"

  + aws_subnet.demo[1]
      id:                                            <computed>
      arn:                                           <computed>
      assign_ipv6_address_on_creation:               "false"
      availability_zone:                             "us-west-2b"
      cidr_block:                                    "10.0.1.0/24"
      ipv6_cidr_block:                               <computed>
      ipv6_cidr_block_association_id:                <computed>
      map_public_ip_on_launch:                       "false"
      tags.%:                                        "2"
      tags.Name:                                     "terraform-eks-demo-node"
      tags.kubernetes.io/cluster/terraform-eks-demo: "shared"
      vpc_id:                                        "${aws_vpc.demo.id}"

  + aws_vpc.demo
      id:                                            <computed>
      arn:                                           <computed>
      assign_generated_ipv6_cidr_block:              "false"
      cidr_block:                                    "10.0.0.0/16"
      default_network_acl_id:                        <computed>
      default_route_table_id:                        <computed>
      default_security_group_id:                     <computed>
      dhcp_options_id:                               <computed>
      enable_classiclink:                            <computed>
      enable_classiclink_dns_support:                <computed>
      enable_dns_hostnames:                          <computed>
      enable_dns_support:                            "true"
      instance_tenancy:                              "default"
      ipv6_association_id:                           <computed>
      ipv6_cidr_block:                               <computed>
      main_route_table_id:                           <computed>
      tags.%:                                        "2"
      tags.Name:                                     "terraform-eks-demo-node"
      tags.kubernetes.io/cluster/terraform-eks-demo: "shared"


Plan: 24 to add, 0 to change, 0 to destroy.

------------------------------------------------------------------------
```
