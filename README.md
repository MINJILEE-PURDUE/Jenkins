To install Jenkins on a Linux system, you can follow these general steps available on [Jenkins official documentation](https://www.jenkins.io/doc/book/installing/); The exact commands may vary depending on your Linux distribution. Here, This README.md provides instructions for Ubuntu, which uses the APT package manager. If you're using a different distribution, you might need to adjust the package manager commands accordingly.


### Step 1: Update Package Repositories
#### Before installing Jenkins, make sure your package repositories are up to date:

```
sudo apt update
```

### Step 2: Install Java
#### Jenkins requires Java to run. You can install OpenJDK, which is an open-source implementation of Java:

```
sudo apt install openjdk-11-jdk
```

### Step 3: Add Jenkins Repository and Key
#### Add the Jenkins repository and key to your system:

```
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
```

In the step 3, I've encountered an error while adding the Jenkins repository and key: E: gnupg, gnupg2 and gnupg1 do not seem to be installed, but one of them is required for this operation. It seems there might be an issue with the GPG key retrieval. I've tried to use this manually import the GPG key and add it to the keyring to solve this common troubleshooting steps:

### Step 1: Using HTTPS for the Jenkins Repository:
#### Since some systems may require using https instead of http for the Jenkins repository, I've tried modifying the repository URL.

```
sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
```

### Step 2: Alternative Key Retrieval Method:
#### The wget command might be causing issues. I've tried useing curl instead.


```
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 9B7D32F2D50582E6
```

Then restarted redoing it from scratch. The error encountering indicates that the GnuPG (GPG) tool, which is used for secure communication and data verification, is not installed on my system. To resolve this issue, I installed GPG.

### Step 1: Update Package Repositories again

```
sudo apt update
```

```
sudo apt install gnupg # Install GPG by running the this command
```

```
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
```

There is an error like this: "E: The repository 'http://pkg.jenkins.io/debian-stable binary/ Release' is not signed."  
The error message "The repository 'http://pkg.jenkins.io/debian-stable binary/ Release' is not signed" suggests that the GPG key used to sign the Jenkins repository is not being recognized or is missing. To resolve this issue, I've tried doing the alternative method of adding the Jenkins repository without GPG verification.


```
sudo nano /etc/apt/sources.list.d/jenkins.list
```

#### Open the /etc/apt/sources.list.d/jenkins.list file in a text editor. It can be anything but I've used the nano text editor for this. Replace the content of the file with the following line, which adds the Jenkins repository without GPG verification.

```
deb http://pkg.jenkins.io/debian-stable binary/
```

#### Still: E: The repository 'http://pkg.jenkins.io/debian-stable binary/ Release' is not signed. although I've changed the contents of the jenkins.list file
