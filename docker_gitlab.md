
# Docker installation
## Install Docker

See docker [[docker_installation]]

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

Get access to the ruby console (may need `sudo`):
```sh
gitlab-rails console
```

Change the password:
```ruby
user = User.where(id: 1).first 
user.password = 'new_password' 
user.password_confirmation = 'new_password' 
user.save!
```

## Create a personal access token programmatically

Get access to the ruby console (may need `sudo`):
```
gitlab-rails console
```

Set the token:
```ruby
user = User.find_by_username('automation-bot') 
token = user.personal_access_tokens.create(scopes: ['read_user', 'read_repository'], name: 'Automation token', expires_at: 365.days.from_now) 
token.set_token('token-string-here123') 
token.save!
```

It can also be done (may need `sudo`):
```sh
gitlab-rails runner "token = User.find_by_username('automation-bot').personal_access_tokens.create(scopes: ['read_user', 'read_repository'], name: 'Automation token', expires_at: 365.days.from_now); token.set_token('token-string-here123'); token.save!"
```
