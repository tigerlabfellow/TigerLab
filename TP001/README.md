# TigerProject001

MiniAmazon: Build your own multi-tier web application for selling books following TPC Benchmark

In July 1995, Amazon began service as an online bookstore. Suppose that you were Jeff Bezos and you are going to build your own multi-tier web application for selling books! In this project, you will understand the most commonly used multi-tier web application which includes a logic tier and a data tier. Users’ http requests such as browsing books and placing orders will be sent to the logic tier. The logic tier will then query a book database in the data tier. The database will response to the queries back to the logic tier and finally the logic tier will assemble the html page and response to the user. Anybody in the world will be able to access your MiniAmazon to browse books and place orders. Moreover, the construction details will strictly follow the industrial standard TPC Benchmark™ W (TPC-W) which is a transactional web benchmark.

Steps (on MacOS):

1.	Log in AWS. 
2.	Start EC2 service. 
3.	Launch an instance of Ubuntu Server 14.04 LTS (HVM). Note that, for compatibility issue, we need to use this specific version.
4.	Choose instance type: t2.micro
5.	In Step 6: Configure Security Group: Add a rule to open All TPC ports from anywhere
6.	Download the pem file as ~/Desktop/1404.pem
7.	Remember the IPv4 Public IP for your EC2 host, e.g., 52.41.122.234
8.	chmod 400 ~/Desktop/1404.pem
9.	log into your host: ssh -i ~/Desktop/1404.pem ubuntu@52.41.122.234  (note that you need to substitute 52.41.122.234 with your host’s ip)
10.	install tools: sudo apt-get install -y openjdk-7-jdk ant gcc git make tomcat7
11.	install mysql server: sudo apt-get install -y mysql-server
12.	remember your mysql server’s password (default to Tigerlabman)
13.	log into the mysql server (mysql -uroot -p -h127.0.0.1) and create a database called tpcw (create database tpcw;)
14.	git clone https://github.com/tigerlabfellow/TigerLab.git
15.	cd /home/ubuntu/TigerLab/TP001/java-tpcw
16.	sudo ant inst
17.	ant gendb
18.	sudo ant genimg
19.	open your browser and visit http://52.41.122.234:8080/tpcw/TPCW_home_interaction (note that you need to replace 52.41.122.234 with your host’s ip)
20.	Acknowledgement: part of the code comes from https://github.com/jopereira/java-tpcw.git

