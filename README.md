🔰 Create High Availability Architecture with AWS CLI 🔰

🔅The architecture includes-

- Webserver configured on EC2 Instance

- Document Root(/var/www/html) made persistent by mounting on EBS Block Device.

- Static objects used in code such as pictures stored in S3

- Setting up Content Delivery Network using CloudFront and using the origin domain as S3 bucket.

- Finally place the Cloud Front URL on the webapp code for security and low latency.

LET'S START
# STEP 1 : 
![Screenshot 2020-10-27 12 34 09](https://user-images.githubusercontent.com/61896468/97419461-18caca80-1930-11eb-949e-21facdb35742.png)
# Firstly,we have configure aws cli by giving access key ,secret key and default region.

# STEP 2 :
![Screenshot 2020-10-27 12 36 51](https://user-images.githubusercontent.com/61896468/97419469-1b2d2480-1930-11eb-8267-c1aeebdac0e9.png)
# `Then we can run "aws --version" to check aws cli is installed or not.`

# STEP 3 :
![Screenshot 2020-10-27 12 40 56](https://user-images.githubusercontent.com/61896468/97419475-1d8f7e80-1930-11eb-8286-6917ab59030f.png)
#  Now we can create key pair for authentication of launched instances on aws.
# STEP 3 :
![Screenshot 2020-10-27 12 41 23](https://user-images.githubusercontent.com/61896468/97419483-1ff1d880-1930-11eb-9c7e-5ebadd916fd6.png)
# We can verify it from aws web console also.
# STEP 4 :
![Screenshot 2020-10-27 12 43 28](https://user-images.githubusercontent.com/61896468/97419489-21230580-1930-11eb-9015-da91ed845770.png)
# Then we have to create a security group ,here named as mysg.
# STEP 5 :
![Screenshot 2020-10-27 12 44 07](https://user-images.githubusercontent.com/61896468/97419491-22ecc900-1930-11eb-84de-d549b7deaf01.png)
# Again just quickly verified sg is created or not.
# STEP 6 :
![Screenshot 2020-10-27 12 51 53](https://user-images.githubusercontent.com/61896468/97419497-241df600-1930-11eb-848b-6e0a6be22a51.png)
# Now we can add add ingress rule on port 80 for web server on the top of created sg.
# STEP 7 :
![Screenshot 2020-10-27 12 52 58](https://user-images.githubusercontent.com/61896468/97419500-254f2300-1930-11eb-9a80-548bc4ec07ce.png)
# As we can see it is created with port 80 allowed.
# STEP 8 :
![Screenshot 2020-10-27 12 53 48](https://user-images.githubusercontent.com/61896468/97419505-2718e680-1930-11eb-9852-8e255dfa75aa.png)
# Describing sg gives more detail about security group likr cidr or alowed port or protocol.
# STEP 9 :
![Screenshot 2020-10-27 12 57 31](https://user-images.githubusercontent.com/61896468/97419512-284a1380-1930-11eb-986a-a0ec67d9b04c.png)
# Now we can launch instance by attaching newly created sg and key pair and its pending.
# STEP 10 :
![Screenshot 2020-10-27 12 58 13](https://user-images.githubusercontent.com/61896468/97419515-297b4080-1930-11eb-9053-8863bd43fdc0.png)
# Now its running.
# STEP 11 :
![Screenshot 2020-10-27 13 37 35](https://user-images.githubusercontent.com/61896468/97419518-2aac6d80-1930-11eb-8331-d5f701db6b54.png)
# Created a ebs volume of 1 gb for persistent storage of web server data and given tags also.
# STEP 12 :
![Screenshot 2020-10-27 13 38 29](https://user-images.githubusercontent.com/61896468/97419523-2bdd9a80-1930-11eb-811b-b5a3a26ac723.png)
# My volume is created and it is available to use.
# STEP 13 :
![Screenshot 2020-10-27 13 41 07](https://user-images.githubusercontent.com/61896468/97419527-2d0ec780-1930-11eb-8507-79b22e8c2e79.png)
# Now i can attach this ebs volume with my instance.
# STEP 14 :
![Screenshot 2020-10-27 13 41 34](https://user-images.githubusercontent.com/61896468/97419531-2e3ff480-1930-11eb-8e64-a2307db839a8.png)
# It is now in use.
# STEP 15 :
![Screenshot 2020-10-27 13 42 28](https://user-images.githubusercontent.com/61896468/97419534-2ed88b00-1930-11eb-9830-89019afcf21d.png)
# It is clearly shoeing the device name being attached.
# STEP 16 :
![Screenshot 2020-10-27 14 39 43](https://user-images.githubusercontent.com/61896468/97419538-30a24e80-1930-11eb-9ccf-796f95cd9005.png)
# Here it show volume id with status "attached".
# STEP 17 :
![Screenshot 2020-10-27 14 42 06](https://user-images.githubusercontent.com/61896468/97419541-326c1200-1930-11eb-8761-240046f4d4eb.png)
# Now i created a new bucket in s3 to store static images.
# STEP 18 :
![Screenshot 2020-10-27 14 55 14](https://user-images.githubusercontent.com/61896468/97419546-339d3f00-1930-11eb-931f-d16edcc6cb84.png)
# Now i copied my image or object in s3 bucket.
# STEP 19 :
![Screenshot 2020-10-27 14 56 54](https://user-images.githubusercontent.com/61896468/97419549-34ce6c00-1930-11eb-852f-f109f7ca9d2d.png)
# My bucket is visible here.
# STEP 20 :
![Screenshot 2020-10-27 14 57 03](https://user-images.githubusercontent.com/61896468/97419552-36982f80-1930-11eb-8086-7dc029eef625.png)
# My image is uploaded.
# STEP 21 :
![Screenshot 2020-10-27 15 48 19](https://user-images.githubusercontent.com/61896468/97419557-37c95c80-1930-11eb-9c4a-87d85b548132.png)
# Now i creted cloudfront web distribution for faster content delivery across the world from any of the location using origin as s3.
# STEP 22 :
![Screenshot 2020-10-27 15 52 31](https://user-images.githubusercontent.com/61896468/97419560-38fa8980-1930-11eb-99b9-434b2b446107.png)
# here i can see i have 1 gb ebs external storage.
# STEP 23 :
![Screenshot 2020-10-27 15 54 17](https://user-images.githubusercontent.com/61896468/97419562-39932000-1930-11eb-99ef-9db0fbba668b.png)
# To use this ebs volume , i created a partition.
# STEP 24 :
![Screenshot 2020-10-27 15 54 58](https://user-images.githubusercontent.com/61896468/97419567-3b5ce380-1930-11eb-8925-62f340107f7d.png)
# p option gives me partition name with size .
# STEP 25 :
![Screenshot 2020-10-27 15 55 42](https://user-images.githubusercontent.com/61896468/97419572-3c8e1080-1930-11eb-8303-8dfe766031bd.png)
# Now i formatted it with ext4 format type.
# STEP 26 :
![Screenshot 2020-10-27 15 58 12](https://user-images.githubusercontent.com/61896468/97419581-3e57d400-1930-11eb-9f36-62bf25987d60.png)
# Now i mounted this partition with /var/ww/html/ folder to make web server data persistent.
# STEP 27 :
![Screenshot 2020-10-27 16 08 50](https://user-images.githubusercontent.com/61896468/97419586-3ef06a80-1930-11eb-9b5f-ab6f0cb11f5e.png)
# Now click on edit public access settings of bucket.
# STEP 28 :
![Screenshot 2020-10-27 16 08 59](https://user-images.githubusercontent.com/61896468/97419588-40ba2e00-1930-11eb-91ff-2d31f1d0ccbe.png)
# Allow all public access so my client can access it.
# STEP 29 :
![Screenshot 2020-10-27 16 09 43](https://user-images.githubusercontent.com/61896468/97419593-41eb5b00-1930-11eb-90b2-2b2402fd67d3.png)
# Now i made my object as public.
# STEP 30 :
![Screenshot 2020-10-27 16 49 21](https://user-images.githubusercontent.com/61896468/97419603-444db500-1930-11eb-97e0-172cf226c863.png)
# Now i installed http software.
# STEP 31 :
![Screenshot 2020-10-27 16 49 39](https://user-images.githubusercontent.com/61896468/97419608-457ee200-1930-11eb-8869-3819ddf563d0.png)
# Now i started httpd services using systemctl.
# STEP 32 :
![Screenshot 2020-10-27 16 50 17](https://user-images.githubusercontent.com/61896468/97419615-4748a580-1930-11eb-8a0c-b9387f221d66.png)
# Disable selinux security to allow clients.
# STEP 33 :
![Screenshot 2020-10-27 16 51 34](https://user-images.githubusercontent.com/61896468/97419622-4879d280-1930-11eb-9c54-9dc0cb50f894.png)
# df -h to see all mounted partitions and /dev/xvdf1 is mounted to /var/www/html/ folder.
# STEP 34 :
![Screenshot 2020-10-27 17 17 53](https://user-images.githubusercontent.com/61896468/97419637-4c0d5980-1930-11eb-8b19-86b96169de98.png)
# i have put my code in web.html inside /var/ww/html.
# STEP 35 :
![Screenshot 2020-10-27 17 18 25](https://user-images.githubusercontent.com/61896468/97419641-4d3e8680-1930-11eb-864c-3c22feb1240d.png)
# Here is my website that is using ec2,ebs,s3,cloudfront for less latency and faster content delivery.
# 
