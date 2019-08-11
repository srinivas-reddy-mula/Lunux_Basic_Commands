##  Services discussion

* Service Types:
    * 1.Run when user requests
    * 2.Run all the time
        * foreground
        * background

* __*Service*__: is an application running all the time
    * __*Deamons*__: service which runs in the background 


* Adding user to group
    
    sudo usermod -aG <group_name> <username>
    ex:
        sudo usermod -aG docker msreddy

* website for systemctl commands
    * refer[here](https://www.digitalocean.com/community/tutorials/how-to-use-systemctl-to-manage-systemd-services-and-units#system-state-overview)
* systemctl commnads to know services 

    sudo systemctl list-units --help
    systemctl list-units --all
    sudo systemctl list-units --all --state=inactive
    sudo systemctl list-units --type=service
    systemctl list-unit-files

    * in centos the service has to be started by us manually 

        sudo systemctl start httpd.service

* To check status of any sevice in linux
    * one way / older way

        sudo service tomcat8 status
        sudo service mysql status

    * second way / new way

        sudo systemctl status tomcat8 
        sudo systemctl status mysql 


* To start an application when system restart

        sudo systemctl enable <application>
        sudo systemctl enable httpd
        sudo systemctl enable tomcat8

    * enable service means we are creating a symlink that service to systemd


## Systemd Service 
    '''
        cat /lib/systemd/system/mysql.service
    to check whether enabled or not
         systemctl is-enabled apache2
    to get dependencies
        systemctl list-dependencies tomcat8
    '''


## TO Make an application as a SERVICE

*   * 1. Create a user
    * 2. create password
    * 3. change ownership
    * 4. change permissions

*   change to
    * /etc/systemd/system inthat create application file_name as service
        * add 
            * unit
            * service
            * install