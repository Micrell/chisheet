
# Docker installation
## Install Docker

See docker [[installation]]

## Create Docker Compose file

```yaml
version: '3.6'
services:
  web:
    image: 'gitlab/gitlab-ce:latest'
    container_name: gitlab
    restart: always
    ports:
      - '80:80'
      - '443:443'
      - '2223:22'
    volumes:
      - 'gitlab_config:/etc/gitlab'
      - 'gitlab_logs:/var/log/gitlab'
      - 'gitlab_data:/var/opt/gitlab'
    shm_size: '2gb'

volumes:
  gitlab_config: {}
  gitlab_logs: {}
  gitlab_data: {}
```

## Get initial root password

Initial root password can be found in a tmp file in the docker (⚠️ Should be soon deprecated):
```sh
docker exec -it your-gitlab-container-name cat /etc/gitlab/initial_root_password
```

Otherwise, it can be found in logs:
```sh
docker logs your-gitlab-container-name 2>&1 | grep 'Password:'
```

## Change root password

Get access to the ruby console:
```sh
gitlab-rails console -e production
```

Change the password:
```ruby
user = User.where(id: 1).first 
user.password = 'new_password' 
user.password_confirmation = 'new_password' 
user.save!
```
