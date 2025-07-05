# 🚀 lauching-ec2-mounting-ebs-vol

This project is part of my cloud computing & devops journey. I have launched an EC2 instance , created an independent EBS Volume , attached to it , mounted it, and entered data. Then unmounted it , dettached from that EC2 instacnce . Created a new EC2 instance to which i attached and mounted that independent EBS Volume for accessing the data created on this Volume on previous EC2 instance.

---

## 📸 Project Preview

![Linux shell Screenshot](./D:\Projects\lauching-ec2-mounting-ebs-vol\Screenshots\7_testing-mounted-data-from-project-ec2-on-testing-ec2.png)

---

## 🧰 Services & Tools Used

- AWS EC2 Service
- AWS EBS Service
- GitHub (Project documentation)

---

## 🧰 Steps to Launch EC2 instance & Mounting EBS volume

1. **Create an EC2 instance named as 'project-ec2'**
2. **Create an indipendent EBS Volume of 5 gb, Naming it as 'indie-vol'**
     - don't forget to keep its AZ same as the 'project-ec2' instance 
3. **Attach 'indie-vol' to 'project-ec2' instance**
4. **Accessing the EC2 instance via EC2 Instance Connect (browser-based SSH terminal) to execute Linux shell commands**
5. **Mounting 'indie-vol' on 'project-ec2'**
     -> Linux Commands :
      - lsblk : list blocks , shows the volumes and their storage
      - sudo su : login as root user
      - mkdir /test : a directory to mount the volume 
      - mkfs.ext4 /dev/test/ : formating the storage before usage
      - mount /dev/nvme1n1 /test : Mounting
      - mountpoint /test : Crosschecking the status 
      - cd /test
      - touch 2 ,4,3,42,5,64 : creating files
      - echo ""This file is created using project-ec2 instance" > data.txt
      - cd ..
      - umount /test : unmounting
6. **Detaching the 'indie-vol' from -project-ec2' instance**
7. **Creating the Another EC2 Instance 'test-ec2' for checking the data in the 'indie-vol'**
8. **Attaching the 'indie-vol' to 'test-ec2'**
9. **Accessing the EC2 instance via EC2 Instance Connect (browser-based SSH terminal) to execute Linux shell commands**
10. **Mounting the 'indie-vol' to 'test-ec2'**
      -> Linux commands :
       - Linux Commands :
       - lsblk : list blocks , shows the volumes and their storage
       - sudo su : login as root user
       - mkdir /test : a directory to mount the volume 
       - mount /dev/nvme1n1 /test : Mounting
       - mountpoint /test : Crosschecking the status 
       - cd /test
       - ls
       - cat data.txt
       -umount /test
11. **Detach 'indie-vol' from 'test-ec2'**


## 🧠 What I Learned
    - How to launch EC2 instances 
    - Create indepentdent EBS Volume
    - How to attach those EBS Volume to EC2 instance 
    - How To format and mount those storage to instanc
    - How the data is saved in EBS volumes even after detattching from instances
## 🙋‍♂️ Author
    -Prithvi Sarvaiya
    -This is part of my self-learning journey into cloud computing and Devops.
    -Feel free to connect: LinkedIn(www.linkedin.com/in/prithvi-cloud)
    - 💬 If you're a beginner, this is a great first cloud project to try. Feel free to fork or ask me questions!