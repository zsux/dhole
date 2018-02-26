##install

  sudo docker run --detach     
    --hostname team.kdqugou.com    
     --publish 443:443 
     --publish 80:80 
     --publish 1022:22     
     --name gitlab     
     --restart always    
     --volume /srv/gitlab/config:/etc/gitlab    
     --volume /srv/gitlab/logs:/var/log/gitlab     
     --volume /srv/gitlab/data:/var/opt/gitlab     
     gitlab/gitlab-ce:latest


  docker run -d --name 
    gitlab-runner --restart always   
    -v /var/run/docker.sock:/var/run/docker.sock   
    -v /srv/gitlab-runner/config:/etc/gitlab-runner   
    gitlab/gitlab-runner:latest

#ci register

   gitlab-ci-multi-runner register
   
   
