---
title: "Volume storage"
teaching: 30
exercises: 0
questions:
- "How do you set up volumes to store data?"
objectives:
- "Create and configure a data volume for your instance."
keypoints:
- "You learned how to create a new volume for your instance."

---

### Two types of built-in storage
1. Root Volume - includes your home directory, and storage for the operating system of your virtual machine
2. Data Volume - a second hard drive you can add to your instance for working storage

Volumes are created and attached using the Nimbus web interface, then formatted and mounted.

## Create a volume
Go to **Volumes** then **Volumes**.  

![Nimbus Volumes Dashboard]({{ page.root }}/fig/Volumes_dashboard.png)

Click on **Create Volume**.  A pop-up will appear (see screenshot below). Enter a **Volume Name** and **Size (GiB)** for the volume, then click **Create Volume** at the bottom of the pop-up.

![Nimbus Create Volumes]({{ page.root }}/fig/Volumes_create.png)

You will now see the created data volume listed, and later we will attach this to our instance and prepare it for accepting data.

![Nimbus Configure Volumes]({{ page.root }}/fig/Volumes_manage.png)
