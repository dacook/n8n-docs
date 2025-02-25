---
title: Customer.io
description: Documentation for the Customer.io node in n8n, a workflow automation platform. Includes details of operations and configuration, and links to examples and credentials information.
---

# Customer.io

The Customer.io node allows you to automate work in Customer.io, and integrate Customer.io with other applications. n8n has built-in support for a wide range of Customer.io features, including creating and updating customers, tracking events, and getting campaigns.

On this page, you'll find a list of operations the Customer.io node supports and links to more resources.

!!! note "Credentials"
    Refer to [Customer.io credentials](/integrations/builtin/credentials/customerio/) for guidance on setting up authentication. 

!!! note "Examples and templates"
    For usage examples and templates to help you get started, take a look at n8n's [Customer.io integrations](https://n8n.io/integrations/customerio/){:target="_blank" .external-link} list.


## Basic Operations

* Customer
    * Create/Update a customer.
    * Delete a customer.
* Event
    * Track a customer event.
    * Track an anonymous event.
* Campaign
    * Get
    * Get All
    * Get Metrics
* Segment
    * Add Customer
    * Remove Customer

## Example Usage

This workflow allows you to create a customer and add them to a segment in Customer.io. You can also find the [workflow](https://n8n.io/workflows/646) on n8n.io. This example usage workflow would use the following nodes.
- [Start](/integrations/builtin/core-nodes/n8n-nodes-base.start/)
- [Customer.io]()

The final workflow should look like the following image.

![A workflow with the Customer.io node](/_images/integrations/builtin/app-nodes/customerio/workflow.png)

### 1. Start node

The start node exists by default when you create a new workflow.

### 2. CustomerIo node (upsert: customer)

1. First of all, you'll have to enter credentials for the Customer.io node. You can find out how to do that [here](/integrations/builtin/credentials/customerio/).
2. Enter a customer id in the ***ID*** field.
3. Click on the ***Add Field*** button and select 'Custom Properties' from the dropdown list.
4. Click on the ***Choose Option To Add*** button.
5. Enter `name` in the ***Key*** field.
6. Enter the name of the customer in the ***Value*** field.
7. Click on ***Execute Node*** to run the node.

![Using the Customer.io node to create a new customer](/_images/integrations/builtin/app-nodes/customerio/customerio_node.png)


### 3. CustomerIo1 node (add: segment)

1. Select the credentials that you entered in the previous Customer.io node.
2. Select 'Segment' from the ***Resource*** field.
3. Click on the gears icon next to the ***Customer IDs*** field and click on ***Add Expression***.
4. Select the following in the ***Variable Selector*** section: Nodes > CustomerIo > Output Data > JSON > id. You can also add the following expression: `{{$node["CustomerIo"].json["id"]}}`.
4. Click on ***Execute Node*** to run the node.


![Using the Customer.io node to add the customer to a segment](/_images/integrations/builtin/app-nodes/customerio/customerio1_node.png)

