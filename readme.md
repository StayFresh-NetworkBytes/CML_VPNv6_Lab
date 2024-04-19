# Cisco Modeling Labs VPNv6 over IPv4 MPLS lab

![alt text](./images/VPNv6_over_MPLS_IPv4.png "CML VPNv6 over IPv4 MPLS Lab" )

This lab provides a working example of an 6VPE configuration between two PEs connected via an IPv4 MPLS network.  It consists of the following nodes:

6x Catalyst 8000v routers
2x Alpine Linux hosts (IPv5 test connectivity)
1x Ubuntu Host
1x External connector
1x unmanaged switch

The Ubuntu host uses the external connector to provide access via the default system bridge in CML (Bridge0).  Either before or after importing the .yaml file to your CML instance, you will to edit the config on the ubuntu host.

If you want to edit the YAML before importing to CML.  Please check the ubuntu-0 host section of the yaml file and replace the curly bracket config with your values:

                ethernets:
                  ens2:
                    dhcp4: false
                    addresses:
                      - {{your_ext_IP_addr}}
                    routes:
                      - to: default
                        via: {{your_ext_IP_GW}}
                    nameservers:
                      addresses:
                        - {{your_DNS_of_choice}}

Otherwise, if you import the configuration to CML without updating the yaml, select the Ubuntu-0 node, go to config and replace the curly brackets with your respective values.

Start the Lab and once booted, you should be able to ssh cisco@your_ip_address

Password for all the Ubuntu host and routers is s3cr3tpw1