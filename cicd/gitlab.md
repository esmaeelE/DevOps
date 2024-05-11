# gitlab for CI/CD

* [Fast with docker-compose](https://github.com/sameersbn/docker-gitlab)

 ---


 # Install latest version on Debian 12

* [Tutorial](https://kifarunix.com/how-to-install-gitlab-on-ubuntu-24-04-with-ssl-tls/#installing-gitlab-on-ubuntu-24-04)

```
curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | sudo bash
curl -L "https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh" | sudo bash
sudo apt install gitlab-runner gitlab-cli gitlab-ce
sudo gitlab-ctl reconfigure
sudo gitlab-rake "gitlab:password:reset"

```
