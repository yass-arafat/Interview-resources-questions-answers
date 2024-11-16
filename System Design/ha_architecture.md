### Definition of HA Architecture
* HA architecture ensures that your systems are up and running and accessible to your users in the face of unforeseen circumstances such as hardware and software failures.
* Below are the four traits that a HA architecture must possess:
    - **Redundant hardware**: Lack of redundant hardware means no requests can be served until a server is restarted after a crash. When this happens, downtime is inevitable. Thus, your HA architecture must include backup hardware such as servers or server clusters that take over automatically in case of production hardware crashes.
    - **Redundant software and applications**: To prevent potential downtime whenever there are failures in the software and applications used in your production environment, it is crucial that your HA architecture includes backup software and applications.
    - **Redundant data**: Database servers that go offline for one reason or another can wreak havoc on your production environment. Your HA architecture should include provisions for backup database servers to which processing can be shifted whenever a production database server goes offline.
    - **No single point of failure**: A failure in a single component should not crash your entire infrastructure. With redundancy in hardware, software, and data, single points of failure are eliminated.

### How to Attain High Availability?
* **Redundancy**<br>
When adopting redundancy, you can choose from five models, with each model progressively more costly as more components are required.
    - **N+1 model:**<br>
      This requires an independent backup for each component in your infrastructure. It can be active/passive, meaning that the backup components are on standby and ready to take over when a main component goes down, or active/active, meaning the backup components are running simultaneously with the main components. Although this is the least costly model, it is not entirely redundant. Thus, it may not be entirely suitable for large systems.
    - **N+2 model:**<br>
      This is like the N+1 model but requires two backup components for each main component. If a backup component also fails, the other backup component takes over.
    - **2N model:**<br>
      This doubles the number of resources required to run the system. For example, if a system requires four servers to run, a 2N model adds another four servers to the system, putting the total number of servers at eight. Thus, the system always has the capacity to run, even if multiple components go down.
    - **2N+1 model:**<br>
      This is like the 2N model except that it adds another backup component that can take over when there are downtime issues with the additional capacity.
    - **Geographic redundancy:**<br>
      This is the most expensive model as it distributes systems in servers across multiple locations. When a location goes down, another site takes over, keeping your operations running. Given its costs, signing up with a cloud services provider with datacenters around the world is your best option if you decide to go with this model.
* **Data Backup and Recovery**<br>
    Regular, full data backups are required to ensure HA and should be included in your disaster recovery planning. Make sure to test your data backups regularly and see that they can be recovered in no time at all.<br>
    Moreover, you should replicate your data by storing them in secondary servers or standby instances across multiple locations. The data in these locations should always be synchronized with the data in your primary location. The other locations should be ready to take over when disaster strikes your primary location.
* **Automatic Failover with Failure Detection:**<br>
HA architecture with automatic failover looks like the following:
   1. There is a main system and a backup system known as the hot spare.
   2. Constant monitoring goes on between the main and backup systems.
   3. When the main system goes down, the backup system, or hot spare, takes over automatically. New requests are now handled by the backup system, which is now acting as if it is the main system.
   4. When the issues in the main system are resolved, it comes back online and resumes its original role. The hot spare goes back to being the backup
* **Load Balancing:**
   -  [File](load_balancer.md)