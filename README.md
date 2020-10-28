🔰 Create High Availability Architecture with AWS CLI 🔰

🔅The architecture includes-

- Webserver configured on EC2 Instance

- Document Root(/var/www/html) made persistent by mounting on EBS Block Device.

- Static objects used in code such as pictures stored in S3

- Setting up Content Delivery Network using CloudFront and using the origin domain as S3 bucket.

- Finally place the Cloud Front URL on the webapp code for security and low latency.

LET'S START

![Screenshot 2020-10-27 11 56 42](https://user-images.githubusercontent.com/61896468/97419450-16687080-1930-11eb-9040-79d750072f54.png)
![Screenshot 2020-10-27 12 05 29](https://user-images.githubusercontent.com/61896468/97419457-17999d80-1930-11eb-862a-adad2149bb41.png)
![Screenshot 2020-10-27 12 34 09](https://user-images.githubusercontent.com/61896468/97419461-18caca80-1930-11eb-949e-21facdb35742.png)
![Screenshot 2020-10-27 12 36 51](https://user-images.githubusercontent.com/61896468/97419469-1b2d2480-1930-11eb-8267-c1aeebdac0e9.png)
![Screenshot 2020-10-27 12 40 56](https://user-images.githubusercontent.com/61896468/97419475-1d8f7e80-1930-11eb-8286-6917ab59030f.png)
![Screenshot 2020-10-27 12 41 23](https://user-images.githubusercontent.com/61896468/97419483-1ff1d880-1930-11eb-9c7e-5ebadd916fd6.png)
![Screenshot 2020-10-27 12 43 28](https://user-images.githubusercontent.com/61896468/97419489-21230580-1930-11eb-9015-da91ed845770.png)
![Screenshot 2020-10-27 12 44 07](https://user-images.githubusercontent.com/61896468/97419491-22ecc900-1930-11eb-84de-d549b7deaf01.png)
![Screenshot 2020-10-27 12 51 53](https://user-images.githubusercontent.com/61896468/97419497-241df600-1930-11eb-848b-6e0a6be22a51.png)
![Screenshot 2020-10-27 12 52 58](https://user-images.githubusercontent.com/61896468/97419500-254f2300-1930-11eb-9a80-548bc4ec07ce.png)
![Screenshot 2020-10-27 12 53 48](https://user-images.githubusercontent.com/61896468/97419505-2718e680-1930-11eb-9852-8e255dfa75aa.png)
![Screenshot 2020-10-27 12 57 31](https://user-images.githubusercontent.com/61896468/97419512-284a1380-1930-11eb-986a-a0ec67d9b04c.png)
![Screenshot 2020-10-27 12 58 13](https://user-images.githubusercontent.com/61896468/97419515-297b4080-1930-11eb-9053-8863bd43fdc0.png)
![Screenshot 2020-10-27 13 37 35](https://user-images.githubusercontent.com/61896468/97419518-2aac6d80-1930-11eb-8331-d5f701db6b54.png)
![Screenshot 2020-10-27 13 38 29](https://user-images.githubusercontent.com/61896468/97419523-2bdd9a80-1930-11eb-811b-b5a3a26ac723.png)
![Screenshot 2020-10-27 13 41 07](https://user-images.githubusercontent.com/61896468/97419527-2d0ec780-1930-11eb-8507-79b22e8c2e79.png)
![Screenshot 2020-10-27 13 41 34](https://user-images.githubusercontent.com/61896468/97419531-2e3ff480-1930-11eb-8e64-a2307db839a8.png)
![Screenshot 2020-10-27 13 42 28](https://user-images.githubusercontent.com/61896468/97419534-2ed88b00-1930-11eb-9830-89019afcf21d.png)
![Screenshot 2020-10-27 14 39 43](https://user-images.githubusercontent.com/61896468/97419538-30a24e80-1930-11eb-9ccf-796f95cd9005.png)
![Screenshot 2020-10-27 14 42 06](https://user-images.githubusercontent.com/61896468/97419541-326c1200-1930-11eb-8761-240046f4d4eb.png)
![Screenshot 2020-10-27 14 55 14](https://user-images.githubusercontent.com/61896468/97419546-339d3f00-1930-11eb-931f-d16edcc6cb84.png)
![Screenshot 2020-10-27 14 56 54](https://user-images.githubusercontent.com/61896468/97419549-34ce6c00-1930-11eb-852f-f109f7ca9d2d.png)
![Screenshot 2020-10-27 14 57 03](https://user-images.githubusercontent.com/61896468/97419552-36982f80-1930-11eb-8086-7dc029eef625.png)
![Screenshot 2020-10-27 15 48 19](https://user-images.githubusercontent.com/61896468/97419557-37c95c80-1930-11eb-9c4a-87d85b548132.png)
![Screenshot 2020-10-27 15 52 31](https://user-images.githubusercontent.com/61896468/97419560-38fa8980-1930-11eb-99b9-434b2b446107.png)
![Screenshot 2020-10-27 15 54 17](https://user-images.githubusercontent.com/61896468/97419562-39932000-1930-11eb-99ef-9db0fbba668b.png)
![Screenshot 2020-10-27 15 54 58](https://user-images.githubusercontent.com/61896468/97419567-3b5ce380-1930-11eb-8925-62f340107f7d.png)
![Screenshot 2020-10-27 15 55 42](https://user-images.githubusercontent.com/61896468/97419572-3c8e1080-1930-11eb-8303-8dfe766031bd.png)
![Screenshot 2020-10-27 15 58 12](https://user-images.githubusercontent.com/61896468/97419581-3e57d400-1930-11eb-9f36-62bf25987d60.png)
![Screenshot 2020-10-27 16 08 50](https://user-images.githubusercontent.com/61896468/97419586-3ef06a80-1930-11eb-9b5f-ab6f0cb11f5e.png)
![Screenshot 2020-10-27 16 08 59](https://user-images.githubusercontent.com/61896468/97419588-40ba2e00-1930-11eb-91ff-2d31f1d0ccbe.png)
![Screenshot 2020-10-27 16 09 43](https://user-images.githubusercontent.com/61896468/97419593-41eb5b00-1930-11eb-90b2-2b2402fd67d3.png)
![Screenshot 2020-10-27 16 48 22](https://user-images.githubusercontent.com/61896468/97419597-43b51e80-1930-11eb-9ded-c7b4bab863ce.png)
![Screenshot 2020-10-27 16 49 21](https://user-images.githubusercontent.com/61896468/97419603-444db500-1930-11eb-97e0-172cf226c863.png)
![Screenshot 2020-10-27 16 49 39](https://user-images.githubusercontent.com/61896468/97419608-457ee200-1930-11eb-8869-3819ddf563d0.png)
![Screenshot 2020-10-27 16 50 17](https://user-images.githubusercontent.com/61896468/97419615-4748a580-1930-11eb-8a0c-b9387f221d66.png)
![Screenshot 2020-10-27 16 51 34](https://user-images.githubusercontent.com/61896468/97419622-4879d280-1930-11eb-9c54-9dc0cb50f894.png)
![Screenshot 2020-10-27 16 53 59](https://user-images.githubusercontent.com/61896468/97419625-49aaff80-1930-11eb-9ae2-4e97a7222fd2.png)
![Screenshot 2020-10-27 17 12 38](https://user-images.githubusercontent.com/61896468/97419630-4adc2c80-1930-11eb-9e93-ebd97350b61d.png)
![Screenshot 2020-10-27 17 17 53](https://user-images.githubusercontent.com/61896468/97419637-4c0d5980-1930-11eb-8b19-86b96169de98.png)
![Screenshot 2020-10-27 17 18 25](https://user-images.githubusercontent.com/61896468/97419641-4d3e8680-1930-11eb-864c-3c22feb1240d.png)
