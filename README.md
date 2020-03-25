Network L3VPN PE Configuration
=========

This role will configure a PE router for L3VPN on various network vendors (still in development)

Requirements
------------
ncclient


Role Variables
--------------
* router_id: String
* bgp_global_asn: String
* provider_ibgp: Dict
  * group: Dict
    * name: String
    * local_address: String
    * import_policy: String
    * export_policy: String
    * asn: String
    * neighbors: List
      * ip: String
* routing_instances: List
  * name: String
  * rd: String
  * rt: String
  * bgp: Dict
    * group: Dict
      * name: String
      * type: String
      * neighbors: List
        * asn: String
        * ip: String
* logical_interfaces: List
  * routing_instance: String

Dependencies
------------

Example Playbook
----------------

    - hosts: vmx1
      roles:
         - { role: network_l3vpn_pe_config }

License
-------

BSD

Author Information
------------------

Marc Colburn
