# openstack-opendaylight


mkdir Downloads
cd ~/Downloads/
wget http://ftp.wayne.edu/apache/maven/maven-3/3.3.3/binaries/apache-maven-3.3.3-bin.tar.gz
sudo mkdir -p /usr/local/apache-maven
sudo mv apache-maven-3.3.3-bin.tar.gz /usr/local/apache-maven
cd /usr/local/apache-maven
sudo tar -xzvf /usr/local/apache-maven/apache-maven-3.3.3-bin.tar.gz -C /usr/local/apache-maven/
sudo update-alternatives --install /usr/bin/mvn mvn /usr/local/apache-maven/apache-maven-3.3.3/bin/mvn 1
sudo update-alternatives --config mvn
curl https://raw.githubusercontent.com/opendaylight/odlparent/master/settings.xml --create-dirs -o ~/.m2/settings.xml
sudo apt-get update
sudo apt-get install curl
curl https://raw.githubusercontent.com/opendaylight/odlparent/master/settings.xml --create-dirs -o ~/.m2/settings.xml
sudo apt-get install software-properties-common
sudo apt-get install pkg-config gcc make ant g++ git libboost-dev libcurl4-openssl-dev libjson0-dev libssl-dev unixodbc-dev xmlstarlet
sudo add-apt-repository ppa:webupd8team/java -y
sudo apt-get update
sudo apt-get install oracle-java8-installer
vim ~/.bashrc
sudo apt-get install vim
vim ~/.bashrc
mkdir -p opendaylight
cd opendaylight/
git clone https://git.opendaylight.org/gerrit/netvirt.git netvirt
cd netvirt/
git checkout topic/routermanager
mvn clean install -Dskip.karaf=true -DskipTests
rm -fr ~/.m2/repository/*
mvn clean install -Dskip.karaf=true -DskipTests
sudo mkdir -p /opt/stack
sudo /usr/testbed/bin/mkextrafs -f /opt/stack
sudo lvs
sudo vgs
sudo pvs
sudo fdisk -l
sudo fdisk /dev/sdb
sudo fdisk -l
sudo pvcreate /dev/sdb1
sudo vgcreate vgpool /dev/sdb1
sudo lvcreate -L 40G -n lvdevstack vgpool
sudo vgs
sudo lvs
sudo pvs
sudo mkfs -t ext3 /dev/vgpool/lvdevstack
sudo mount -t ext3 /dev/vgpool/lvdevstack ~/devstack/
sudo chown svavilap devstack/
sudo ifconfig eth1:0 123.123.22.22
ifconfig
sudo apt-get install python-software-properties -y
sudo apt-get install software-properties-common -y
sudo add-apt-repository cloud-archive:liberty
sudo apt-get update
sudo apt-get install openvswitch-switch
sudo ovs-vsctl -v
sudo ovs-vsctl --version
git clone -b stable/liberty https://git.openstack.org/openstack-dev/devstack
cd devstack/
ls
vim local.conf
hostname
vim local.conf
./stack.sh
sudo ovs-vsctl show
sudo ovs-ofctl -O OpenFlow13 dump-flows br-int
source ~/devstack/devstack/openrc admin admin
keystone tenant-list
keystone tenant-create --name=l3tenant1 --enabled=true
keystone user-create --name=l3user1 --pass=l3user1 --email=l3user1@example.com
keystone user-role-add --user=l3user1 --role=Member --tenant=l3tenant1
source ~/devstack/openrc l3user1 l3tenant1
source ~/devstack/devstack/openrc l3user1 l3tenant1
export OS_PROJECT_NAME=l3tenant1
export OS_PASSWORD=l3user1
ssh-keygen -t rsa -b 2048 -N '' -f id_rsa_demo
nova keypair-add --pub-key  id_rsa_demo.pub  demo_key
neutron router-create l3tenant1router
neutron net-create net1
neutron subnet-create --name=subnet1-ipv6 net1 --ip_version 6 --ipv6_ra_mode slaac --ipv6_address_mode slaac 2001:db8:cafe:0::/64
neutron router-interface-add l3tenant1router subnet1-ipv6
neutron net-list
neutron subnet-list
neutron router-list
neutron router-port-list
neutron router-port-list 0493b160-2559-4e16-a591-a5e993ae65f2
sudo ip netns
nova image-list
nova boot --poll --flavor m1.nano --image 62440e0a-7786-49ec-b96f-484a60efd4c9 --nic net-id=bcb9f6c3-09c7-4ac8-802c-7774c65240be  --key-name demo_key 1_vm1_ipv6
neutron router-port-list 0493b160-2559-4e16-a591-a5e993ae65f2
nova list
neutron port-list
nova boot --poll --flavor m1.nano --image 62440e0a-7786-49ec-b96f-484a60efd4c9 --nic net-id=bcb9f6c3-09c7-4ac8-802c-7774c65240be  --key-name demo_key 1_vm2_ipv6
neutron port-list
