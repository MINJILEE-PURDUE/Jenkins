To install Jenkins on a Linux system, you can follow these general steps available on [Jenkins official documentation](https://www.jenkins.io/doc/book/installing/); The exact commands may vary depending on your Linux distribution. Here, This README.md provides instructions for Ubuntu, which uses the APT package manager. If you're using a different distribution, you might need to adjust the package manager commands accordingly.


```
sudo apt update
```

```
sudo apt install openjdk-11-jdk
```
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
then I will get this error: E: gnupg, gnupg2 and gnupg1 do not seem to be installed, but one of them is required for this operation

It seems there might be an issue with the GPG key retrieval. Let's try a different approach to manually import the GPG key and add it to the keyring.

sudo apt update
sudo apt install jenkins
sudo systemctl start jenkins
sudo systemctl enable jenkins
http://your_server_ip_or_domain:8080
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
