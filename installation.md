**sudo apt-get update**

The sudo apt-get update command is used in Debian-based Linux distributions, such as Ubuntu, to refresh the package lists for repositories configured in the system. Here's what it does:

Updates Package Lists: It fetches the latest information about available packages from the repositories specified in the /etc/apt/sources.list file and in the /etc/apt/sources.list.d/ directory. This information includes details about the latest versions of packages, dependencies, and other metadata.

Doesn't Upgrade Packages: It's important to note that apt-get update does not upgrade the installed packages on your system; it only updates the package lists. To upgrade the installed packages, you would use sudo apt-get upgrade or sudo apt-get dist-upgrade after running apt-get update.

By regularly running sudo apt-get update, you ensure that your system has the latest information about available packages. This is crucial for several reasons:

Security: Keeping the package lists up-to-date allows you to receive information about security updates. If there are security vulnerabilities in the packages installed on your system, you'll be aware of them and can take appropriate actions.

Software Availability: You'll have access to the latest versions of software packages and can install new software as it becomes available in the repositories.

Dependency Resolution: Updated package lists help in resolving dependencies accurately when you install or upgrade packages.

In summary, running sudo apt-get update is a good practice to ensure that your system is aware of the latest software packages and updates available from the configured repositories.

**sudo apt install openjdk-8-jdk**

The command sudo apt install openjdk-8-jdk is used to install the OpenJDK 8 development kit on a Debian-based Linux system, such as Ubuntu. This command does the following:

sudo: It is used to run the command with superuser privileges, allowing you to perform system-level operations.

apt: It is the Advanced Package Tool for package management on Debian-based systems. The apt command is used for installing, upgrading, and managing software packages.

install: It is the action that tells apt you want to install a package.

openjdk-8-jdk: This is the name of the package you want to install. In this case, it's the OpenJDK 8 development kit, which includes the Java Development Kit (JDK) needed for Java software development.

So, when you run sudo apt install openjdk-8-jdk, the system will download and install the OpenJDK 8 development kit along with any necessary dependencies. After the installation is complete, you should have the required tools and libraries to develop Java applications using OpenJDK 8 on your system.

**sudo useradd -d /opt/nexus -s /bin/bash nexus**

The command you provided is a Unix/Linux command used to create a new user named "nexus" with the home directory set to "/opt/nexus" and the default shell set to "/bin/bash". Let me break down the command for you:

sudo: This is a command that allows a permitted user to execute a command as the superuser or another user, as specified by the security policy.

useradd: This is a command used to create a new user or update default new user information.

-d /opt/nexus: This option specifies the home directory of the new user. In this case, it is set to "/opt/nexus".

-s /bin/bash: This option sets the default shell for the new user to "/bin/bash".

nexus: This is the username of the new user being created.

So, the overall purpose of the command is to create a new user named "nexus" with a home directory of "/opt/nexus" and the default shell set to "/bin/bash". The use of sudo suggests that the command is being executed with elevated privileges, often requiring administrative rights.

**wget https://download.sonatype.com/nexus/3/nexus-3.64.0-04-unix.tar.gz**

The wget command you provided is used to download a file from a specified URL. In this case, the URL is pointing to a tarball (compressed archive) file of Nexus Repository Manager version 3.64.0-04 for Unix systems.

Here's a breakdown of the command:

tar: The command for manipulating tar archives.

-x: Extracts files from an archive.

-z: Allows tar to decompress the archive using gzip.

-f: Specifies the filename of the archive.

nexus-3.64.0-04-unix.tar.gz is the tarball file you downloaded in the previous step. When you run this tar command, it will extract the contents of the tarball in the current working directory.

After extracting the contents, you'll likely find a directory with the Nexus Repository Manager files. You can then proceed to set up and configure Nexus Repository Manager according to the instructions provided by Sonatype.


**sudo mv nexus-3.64.0-04 /opt/nexus**

**sudo mv sonatype-work /opt/**

**sudo chown -R nexus:nexus /opt/nexus /opt/sonatype-work**

Uncomment the option 'run_as_user' and change the value to 'nexus'. With this configuration, you will be running the Nexus application as the system user 'nexus'.

**sudo vi /opt/nexus/bin/nexus.rc**

Change the default max memory heap for your Nexus installation in the following options. You can change the size to '1024m' based on the memory that you have on your server.

-Xms1024m

-Xmx1024m

-XX:MaxDirectMemorySize=1024m

**sudo vi /opt/nexus/bin/nexus.vmoptions**

On a default installation, the Nexus Repository Manager can be run manually via the binary command 'nexus' that is available on the '/opt/nexus/bin' directory. But, to make it easier for managing Nexus, you will set up a systemd service file for Nexus.

Running Nexus with systemd service file, allows you to manage the nexus process via the systemctl command.

Now, create a new service file '/etc/systemd/system/nexus.service' using nano editor.



**sudo vi /etc/systemd/system/nexus.service**

**sudo systemctl daemon-reload**

**sudo systemctl status nexus.service**

**sudo systemctl start nexus.service**

**sudo systemctl status nexus.service**

**sudo apt-get install net-tools**

**sudo netstat -lntp**

**sudo systemctl status nexus.service**

**sudo netstat -lntp**

**sudo systemctl status nexus.service**

**sudo cat /opt/sonatype-work/nexus3/admin.password**


