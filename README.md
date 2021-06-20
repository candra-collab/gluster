# gluster

hostnamectl set-hostname node1
nano /etc/hosts [change node and fill your ip address]
df -h
sudo apt install glusterfs-server
systemctl enable --now glusterfs
systemctl status glusterd
mkdir -p /home/gluster
gluster peer probe node2 | node 2 : gluster peer status
gluster peer status
volume :
gluster volume create storage transport tcp node1:/home/gluster node2:/home/gluster force
gluster volume start storage
gluster vvolume info
node1 :mount -t glusterfs node2:/storage /home/share-storage
node2: mount -t glusterfs node2:/storage /home/share-storage
