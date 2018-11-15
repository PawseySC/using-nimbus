---
title: "Using snapshots to save time"
teaching: 0
exercises: 0
questions:
- "What are snapshots and how are they used?"
objectives:
- "Make a snapshot of an existing virtual machine"
- "Recover a virtual machine from a snapshot"
- "Understand the caveats of snapshots in Nimbus"
---

## About Snapshots
> ## What are snapshots and how are they used?
>
> Snapshots, as the name implies, are a copy of a volume or an instance at a point in time which can then be used later. Here are two ways you can make use of them:
>
> - Create a snapshot of your instance and then use it to create a new instance, complete with any software you have installed and configuration changes you have made.
> - Create a snapshot of your data volume, then later create a new data volume from this snapshot. The new volume won't have any of the changes made since the snapshot was taken.

## Snapshot and Recreate Your Instance
Here is an overview of this procedure:
- Shut Off your instance
- __Create Snapshot__ of your instance
- __Create Volume__ from that snapshot
- __Upload to Image__ from that volume
- __Launch__ a new instance using that image

## 1. Shut Off your instance
To start with, shut off your instance so you will get a clean snapshot. Consider using the date as part of the name.
![Instance Shutdown]({{ page.root }}/fig/Instance_shutdown.png)

## 2. __Create Snapshot__ of your instance
Take a snapshot of your instance, and give it a name.
![Instance Shutdown]({{ page.root }}/fig/Instance_snapshot.png)
Once it is created, you will be taken to the Images page where you will see it listed.

## 3. __Create Volume__ from that snapshot
Click through to the Volumes > Snapshots page and create a temporary volume.
- Give it a name and leave the other fields
![Instance SnapshotVolume]({{ page.root }}/fig/Instance_snapshot_volume.png)

## 4. __Upload to Image__ from that volume
Back at the Volumes page, you will see your new volume created from the snapshot. Use it to create an image.
![Instance Image]({{ page.root }}/fig/Instance_image.png)
This process can take some time. Allow ten minutes for the image to upload. Once it is complete, you can delete the temporary volume.

## 5. __Launch__ a new instance using that image
You are now ready to launch a new instance from the image. Be careful to use the RAW image you have just created and named, not the 0 sized QCOW2 Snapshot from step 2.
![Instance ImageLaunch]({{ page.root }}/fig/Instance_image_launch.png)
Use appropriate settings for your new instance, like when you were creating your first instance.
