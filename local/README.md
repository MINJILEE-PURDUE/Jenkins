### Environment Setup

| \ | Description |
| --- | --- |
| Processor | 1.6 GHz Dual-Core Intel Core i5 |
| Graphics | Intel UHD Graphics 617 1536 MB |
| Memory | 8 GB 2133 MHz LPDDR3 |

Note. Make sure that you have a enough memory to install Jenkins and Docker in the future work.


#### Install Jenkins
```
brew install jenkins-lts
```
If you have this error message: "Error: homebrew-core is a shallow clone. To `brew update`, first run: git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core fetch --unshallow This command may take a few minutes to run due to the large size of the repository. This restriction has been made on GitHub's request because updating shallow clones is an extremely expensive operation due to the tree layout and traffic of Homebrew/homebrew-core and Homebrew/homebrew-cask. We don't do this for you automatically to avoid repeatedly performing an expensive unshallow operation in CI systems (which should instead be fixed to not use shallow clones). Sorry for the inconvenience!"

#### Install Docker
Go visit official [Docker website](https://docs.docker.com/desktop/install/mac-install/)

Note. Since both Jenkins and Docker are hosted locally on my Mac, I should check to ensure that Jenkins has the necessary permissions to interact with Docker. Here are the steps to set up Jenkins to work with Docker on the Mac:

Install Docker Desktop:
Make sure Docker Desktop is installed on Mac. Download it from the official Docker website above.

Grant Docker Permissions to Jenkins:
Ensure that the Jenkins user (or the user running the Jenkins process) has the necessary permissions to access Docker. One common way to achieve this is to add the user to the docker group.

