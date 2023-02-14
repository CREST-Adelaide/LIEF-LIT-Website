---
layout: page
title: BC-IoT Inventory
subtitle: Secure and decentralised tracking of experiment results based on IoT devices
---

# Context
This project proposes a blockchain-based inventory management system that can monitor the transfer, deployment and maintenance of devices without relying on trust through the inherent security, transparency and immutability properties that the blockchain provides. 

In particular, the IoT inventory management system aims to track and trace the relationship between IoT devices, experimental kits that they form, the experiments that they conduct, and the experiment results generated from those kits. The hardware inventories and the researchers conducting experiments can come from different organisations. The blockchain-based inventory management system provides a decentralised and trustworthy platform for coordinating and tracking the information among these entities. 

A prototype was developed based on the Ethereum blockchain and a service-based architecture. The prototype was demonstrated using the inventory management workflow of the ad-hoc IoT testbed instances at the University of Adelaide. 

# Architecture

## Conceptual and state model

![](/assets/img/BC-IoT-Inventory-Class-Diagram.png)

The inventory management process governed by the blockchain-based inventory tool concerns with the movement of IoT devices from **inventory** into collections of hardware called **test kits**. These test kits participate in **deployments** for the sake of carrying out an **experiment**. By the end of each experiment, the test kit generate experiment results, which are archived and made available to researchers. The figure above visualise the conceptual model underlying the system as a class diagram.

![](/assets/img/BC-IoT-Inventory-State-Diagram.png)

The state models, reflecting the life cycle of individual IoT device, test kits, deployments, and experiments are outlined in the diagrams above.

## Activity model

![](/assets/img/BC-IoT-Inventory-Activity-Diagram.png)

A general workflow supported by the IoT testbed is illustrated in the above activity diagram. The workflow involves three actors: researchers, the managers an IoT hardware inventory, and the blockchain-based inventory management system.

Researchers and IoT hardware inventory can come from different organisations, such as different sites of a distributed IoT testbed. The blockchain-based inventory management system provides a decentralised and trustworthy common platform for managing and securing the flow of hardware devices into testkits, the deployment of experiments onto the testkits, and the results of the experiments themselves. 

# Demonstration

[YouTube](https://youtu.be/oSqcAztyL68)

# Resources

[GitHub](https://github.com/CREST-Adelaide/LIEF-LIT-IoT-Inventory-Mgnt)