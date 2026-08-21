# Lab 4 – Working with Amazon Elastic Block Store (EBS)

## Author

* **Name**: VIMALRAJ B
* **Register Number**: 212224230304
* **Date of Submission**: 21/08/26

---

## Objective

The objective of this experiment is to understand how Amazon Elastic Block Store (EBS) provides persistent block-level storage for EC2 instances. This lab focuses on creating and attaching an EBS volume, formatting and mounting it on an EC2 instance, storing data, and verifying data persistence after instance reboot.

---

## Prerequisites

* Basic understanding of cloud computing concepts
* AWS account or AWS Academy Lab access
* An existing EC2 instance (Amazon Linux 2 preferred)
* Basic knowledge of Linux commands

---

## Tools Used

* AWS Management Console
* Amazon EC2
* Amazon EBS
* SSH Client (Terminal / PuTTY)

---

## Tasks Performed

### Task 1: Explore Amazon EBS

Explore the Amazon EBS service through the EC2 dashboard. Observe different volume types such as General Purpose SSD (gp2/gp3), Provisioned IOPS SSD, Throughput Optimized HDD, and Cold HDD.

---

### Task 2: Create an EBS Volume

Create a new EBS volume in the same Availability Zone as the EC2 instance. Choose an appropriate size and volume type.

---

### Task 3: Attach EBS Volume to EC2 Instance

Attach the created EBS volume to the running EC2 instance as an additional block device.

---

### Task 4: Format the EBS Volume

Connect to the EC2 instance using SSH and format the attached volume with a file system (for example, ext4).

---

### Task 5: Mount the EBS Volume

Mount the formatted volume to a directory in the EC2 instance (for example, /data or /mnt/ebs).

---

### Task 6: Store Data in EBS Volume

Create files and directories inside the mounted EBS volume and store sample data.

---

### Task 7: Verify Data Persistence

Reboot the EC2 instance and verify that the data stored in the EBS volume is still available after reboot.

---

## Workflow (Student Explanation)

First, I logged in to the AWS Management Console.

I navigated to the EC2 Dashboard.

I explored the Elastic Block Store (EBS) section under EC2.

I observed different volume types such as General Purpose SSD (gp2/gp3), Provisioned IOPS SSD, Throughput Optimized HDD, and Cold HDD.

I clicked on “Volumes” and selected “Create Volume.”

I chose the required volume type (General Purpose SSD – gp3).

I entered the desired storage size (for example, 8 GB).

I selected the same Availability Zone as my running EC2 instance.

I clicked on “Create Volume” to create the EBS volume.

After the volume was created, I selected the volume and clicked on “Attach Volume.”

I selected my running EC2 instance and attached the volume as a new device (for example, /dev/xvdf).

I connected to my EC2 instance using SSH from the terminal.

I checked the attached disk using the command lsblk to verify the new volume.

I formatted the attached volume using the command:
sudo mkfs -t ext4 /dev/xvdf

I created a directory to mount the volume using:
sudo mkdir /mnt/ebs

I mounted the volume to the directory using:
sudo mount /dev/xvdf /mnt/ebs

I verified that the volume was mounted successfully using the df -h command.

I created sample files inside the mounted directory using:
sudo touch /mnt/ebs/sample.txt

I stored some sample data inside the file.

I rebooted the EC2 instance from the AWS Console.

After rebooting, I reconnected to the instance using SSH.

I checked the mounted directory and verified that the stored data was still available.

This confirmed that the EBS volume provides persistent storage even after instance reboot.


## Output Screenshots (Attach 3)

### Screenshot 1: EBS Volume Created

<img width="1363" height="596" alt="Screenshot 2026-08-21 225736" src="https://github.com/user-attachments/assets/4c96d488-1926-42e7-b5e1-e5da4b5d3883" />


### Screenshot 2: EBS Volume Attached to EC2

<img width="1364" height="597" alt="image" src="https://github.com/user-attachments/assets/7544e5de-d5aa-46ac-93f3-4d2cf20ac209" />



<img width="757" height="520" alt="image" src="https://github.com/user-attachments/assets/bc7ab9e6-76f7-4705-8e7a-bcc0de5684b6" />


<img width="696" height="387" alt="image" src="https://github.com/user-attachments/assets/717c6785-2ecc-40c2-8dd4-e15d3293f81a" />


<img width="912" height="257" alt="image" src="https://github.com/user-attachments/assets/7cad1e40-f699-4164-915e-f137928d86af" />


### Screenshot 3: Mounted Volume with Data

<img width="1361" height="603" alt="image" src="https://github.com/user-attachments/assets/a5cfcb14-eb9c-43c7-9b5a-bcda9429e708" />


<img width="1354" height="589" alt="image" src="https://github.com/user-attachments/assets/509027b8-54a0-4ca3-8b3c-03f4eb60e61c" />


<img width="1356" height="593" alt="image" src="https://github.com/user-attachments/assets/a9f062e4-9666-4082-aa13-5ece06a5cb00" />


## Result / Conclusion

This experiment demonstrated how Amazon EBS provides persistent storage for EC2 instances. By creating, attaching, formatting, and mounting an EBS volume, and by verifying data after reboot, the concept of durable block storage in the cloud was clearly understood.
