# Gitlab-lab


## Instructions on how to install your own GitLab

1. https://about.gitlab.com/install/#ubuntu
2. https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-gitlab-on-ubuntu-18-04

## Config:

`sudo vim /etc/gitlab/gitlab.rb`

## Troubleshooting:


In order to find out problem run `sudo gitlab-ctl tail` and search for errors.

In case other services takes GitLab ports (for example, unicorn can't use 8080 port):

1. Change unicorn port 8080 in Config file [Source](https://stackoverflow.com/questions/33254100/502-whoops-gitlab-is-taking-too-much-time-to-respond)

2. `gitlab-ctl reconfigure`

3. `sudo gitlab-ctl restart`

In case error `This error usually means that PostgreSQL's request for a shared memory segment exceeded available memory, swap space, or huge pages. To reduce the request size (currently 4292984832 bytes), reduce PostgreSQL's shared memory usage, perhaps by reducing shared_buffers or max_connections.`

1. Change parameter in config `postgresql['shared_buffers'] = "256MB"` and extend memory, for example up to "500MB"

2. `gitlab-ctl reconfigure`

3. `sudo gitlab-ctl restart`
