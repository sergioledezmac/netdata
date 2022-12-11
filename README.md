# netdata
How to install Netdata in SUSE15 SP3 (with RPMs)

##Install the next RPM
 rpm -ivh libJudy1-1.0.5-1.2.x86_64.rpm 
 rpm -ivh libipmimonitoring6-1.6.2-7.28.x86_64.rpm 
 rpm -ivh libnetfilter_acct1-1.0.3-bp153.1.16.x86_64.rpm 
 rpm -ivh libprotobuf20-3.9.2-4.9.1.x86_6
 rpm -ivh netdata-1.31.0-bp153.2.3.1.x86_64.rpm
 
 Edit netdata.conf
 vi /etc/netdata/netdata.conf
 
                 [global]
                    run as user = netdata

                    # the default database size - 1 hour
                    history = 3600

                    # some defaults to run netdata with least priority
                    process scheduling policy = idle
                    OOM score = 1000

                [web]
                    web files owner = root   
                    web files group = root

                    # by default do not expose the netdata port
                    bind to = 10.0.0.100  #(Change IP of your Suse15)
                    
Add Chown files
sudo chown root:root -R /usr/share/netdata
sudo chown root:root -R /usr/share/netdata/web//index.html


now start netdata service
    systemctl start netdata.service

You can see with your IP:19999

Example:
http://10.0.0.100:19999/


Saludos!
 
 

 
