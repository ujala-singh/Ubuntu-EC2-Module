# Ubuntu-EC2-Module
# static-proxy

Docker Container is at https://github.com/razorpay/containers/tree/static-proxy

>Static proxy containers running haproxy on alpine for forwarding traffic over a static IP to API servers.
>Timeouts are set to 600s
>This can only run in the razorpay-vpc since it uses the DNS server (10.1.0.2:53)
# Input variables
  ```
  AMI latest and name tag. These can be environment specific.
  - ami_name_tag      = "bionic-razor-base-prod-stand-alone"
  - ami_latest_tag    = "bionic-base-prod-stand-alone"
  - ami_vpc_tag       = "prod"
  ```
- *name*: name used by all resources
- subnet: List of all subnets to be spawn resources in. Must match count
- security-groups: List of all SGs. All are applied to all instances
- az: list of AZs to spawn instances. Must match count.
- environment: duh
- hostnames: DNS records will be created to point to this IP address. Make sure these hostnames are not repeated elswhere. Only if EIP is created
- instance_type: duh
- count: how many instances?
- create-eip: Whether or not to create an EIP allocation for these instances. Set to false to disable
- private-ips: List of all private IPs to be assigned to the instances. Must be in the correct subnet and match count
- private-ip: Whether or not to assign the given private IPs
