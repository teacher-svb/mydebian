# mydebian

As the prerequisite, a new directory for docker should be prepared on a second partition (or a separate drive):
1. Make sure that a separate partition is mounted. In this example, a partition called “/dev/mapper/sisense_vg-sisense” mounted at “/second_drive”: 

2. Create a new docker directory:  
sudo mkdir /home/docker
3. Stop the docker service before making any changes in the configuration:  
sudo systemctl stop docker
4. Confirm that the docker engine is stopped:  
sudo systemctl docker status
5. If the docker engine is stopped, the old directory could be copied into a new place with:  
sudo rsync -avxP /var/lib/docker/ /home/docker/
6. Once /var/lib/docker is copied to a new place, move it to backup place:  
mv /var/lib/docker /var/lib/docker.bkp
7. Create a symbolic link to a new directory:  
sudo ln -s /second_drive/docker /var/lib/docker
8. Start docker with:  
sudo systemctl start docker
9. Test if it is up and running with:  
sudo systemctl status docker
10. If service is up and running, it is good to remove the old directory:  
rm -r /var/lib/docker.bkp
