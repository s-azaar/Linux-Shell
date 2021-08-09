# Linux Task One




## Part One

    #pvcreate /dev/sda2
    #gvcreate -s 16M vg1 /dev/sda2
    #lvcreate -l 50 -n lv1 vg1
    #mkfs.ext4 /dev/vg1/lv1
    #mkdir -p /mnt/data
    #mount /dev/vg1/lv1 /mnt/data
    #echo "/dev/sda2 /mnt/data ext4 defaults 0 1" >> /etc/fstab

## Part Two

    #useradd --uid 601 --shell /sbin/nologin --password redhat user1
    #groupadd TraningGroup
    #usermod -aG TraningGroup user1
    #useradd user2 --password redhat
    #useradd user3 --password redhat
    #groupadd admin
    #usermod -aG admin user2
    #usermod -aG admin user3
    #usermod -aG admin user3

## Part Three

    #ssh-keygen -t rsa -b 4096
    #ssh-copy-id sazaar@192.168.1.108
    #ssh sazaar@192.168.1.108

## Part Four

    #cp /etc/fstab /var/tmp/admin
    #setfacl -m u:user1:rwx /var/tmp/admin
    #setfacl -m u:user2:--- /var/tmp/admin

## Part Five

    # vim /etc/selinux/config
    SELINUX=enforcing
    #

## Part Six

    #!/bin/bash
    sleep 600 &
    p_id=`pgrep sleep`
    kill $p_id


## Part Seven

    #sudo yum install tmux -y
    #sudo yum install httpd -y
    #sudo yum install mysql -y
    #mkdir /var/zabbix
    #wget https://repo.zabbix.com/zabbix/5.4/rhel/7/x86_64/zabbix-release-5.4-1.el7.noarch.rpm -P /var/zabbix
    #createrepo /var/zabbix
    #vim /etc/yum.repos.d/zabbix.repo
    [zabbix]
    name=Zabbix Local Repository
    baseurl=file:///var/zabbix/
    enabled=1
    gpgcheck=0

## Part Eight

    #sudo firewall-cmd --add-service={http,https} --permanent
    #sudo firewall-cmd --zone=public --add-rich-rule="rule family='ipv4' source address='192.168.1.155' port port=22 protocol=tcp reject"
    #sudo firewall-cmd --reload

## Part Nine

    #crontab -e
    30 1 * * * w | awk '{ print $3 $1 }' > log.txt


## Part Ten
    #sudo yum install mariadb
    #sudo iptables -A INPUT -p tcp --dport mysql -j ACCEPT
    #mysql -u root -p
    #create database studentdb;
    #grant all privileges on studentdb.* to 'user'@'192.168.204.193';
    #flush privileges;
    #mysql -h 192.168.204.119 -u user
    #use studentdb;
    #create table student ( 
		first_name varchar(50) NOT NULL,
		last_name varchar(50) NOT NULL,
		program_enrolled varchar(50) NOT NULL
	  );
    #insert into student (first_name, last_name, program_enrolled) values ('saleem', 'azaar', 'cse'), ('majid', 'idk', 'ee');
    #select * from student;
    MariaDB [studentdb]> SELECT * FROM STUDENT;
    +-----------+------------+------------------+
    | first_name | second_name | program_enrolled |
    +-----------+------------+------------------+
    | saleem    | azaar      | cse              |
    | majid     | idk        | ee               |
    +-----------+------------+------------------+
    2 rows in set (0.01 sec)
    #exit
    bye :)

    


