# Inventory Replenishment & Procurement Automation

An inventory replenishment and procurement automation workflow built during an n8n Hackathon using n8n, Google Sheets, Gmail, reorder-point logic, and human-in-the-loop approvals.

## Project Overview

This project automates the process of monitoring inventory levels, identifying replenishment needs, generating purchase requests, and routing high-value orders for human approval.

The goal was to reduce manual inventory checking and create a clearer, more consistent procurement workflow.

## Problem

Manual inventory management can require employees to repeatedly check stock levels, calculate replenishment needs, contact suppliers, and request approval for larger purchases.

Our team designed an automated workflow that:

* Reads inventory, usage, and supplier data
* Calculates replenishment requirements
* Identifies materials that need to be reordered
* Checks whether an open purchase order already exists
* Generates a draft purchase order
* Routes higher-value purchases for human approval
* Sends supplier notifications after approval

## Workflow

```text
Inventory + Usage + Supplier Data
              |
              v
     Calculate Replenishment
              |
              v
        Reorder Needed?
          /         \
        No           Yes
        |             |
      Record      Check Open PO
                      |
                      v
             Build Draft Purchase Order
                      |
                      v
             Order Value > AUD 1,000?
                /              \
              Yes               No
               |                 |
         Human Approval      Auto-Approve
                \              /
                 v            v
              Supplier Notification
```

## Reorder Point Logic

The workflow uses a reorder-point approach:

```text
Reorder Point = Average Daily Usage × Lead Time + Safety Stock
```

When inventory falls below the required level, the workflow calculates the replenishment quantity needed to restore inventory toward the target level.

## Human-in-the-Loop Approval

Purchase requests above AUD 1,000 are routed for human approval before the supplier order is sent.

This prevents higher-value purchases from being automatically executed without review.

## My Contribution

My contribution to the team project included:

* Designing the cosmetics inventory use case
* Mapping six raw materials to their corresponding suppliers
* Contributing to the inventory shortage and procurement workflow
* Working on the human-in-the-loop approval process
* Helping integrate supplier communication into the workflow
* Supporting the final workflow demonstration and presentation

## Tools Used

* n8n
* Google Sheets
* Gmail
* Workflow Automation
* GitHub
* Reorder Point Inventory Logic
* Human-in-the-Loop Approval

## What I Learned

Through this hackathon, I gained hands-on experience in:

* Designing multi-step automation workflows
* Translating business rules into workflow logic
* Working with inventory and supplier data
* Building approval controls into automated systems
* Connecting different tools through n8n
* Collaborating with a team under hackathon time constraints

## Future Improvements

Possible future improvements include:

* Adding demand forecasting
* Supporting multiple companies and inventory categories
* Adding supplier performance tracking
* Creating a real-time inventory dashboard
* Integrating invoice and delivery-note matching
* Adding AI-assisted supplier email processing
