# Cisco Modeling Labs VPNv6 over IPv4 MPLS lab

![alt text](./images/VPNv6 over MPLS IPv4.png "CML VPNv6 over IPv4 MPLS Lab)

This lab provides a working example of an 6VPE configuration between two PEs connected via an IPv4 MPLS network.  The Ubuntu host uses the external connector to provide access via the default system bridge in CML (Bridge0).  Either before or after importing the .yaml file to your CML instance, you will to edit the config on the ubuntu host.

Please check this section of the yaml file and update the bracketed config:

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