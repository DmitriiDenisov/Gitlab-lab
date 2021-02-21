# Gitlab-lab


## Instructions on how to install your own GitLab

1. https://about.gitlab.com/install/#ubuntu
2. https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-gitlab-on-ubuntu-18-04

## Troubleshooting:

In case other services takes GitLab ports, in order to find it out `sudo gitlab-ctl tail` and see logs.

To nail it: 

1. Change unicorn port 8080 [Source](https://stackoverflow.com/questions/33254100/502-whoops-gitlab-is-taking-too-much-time-to-respond)

2. 

3. `gitlab-ctl reconfigure`

4. `sudo service gitlab restart`
