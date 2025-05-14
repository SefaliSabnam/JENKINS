# JENKINS Project

This project provides comprehensive guidance on:

* Jenkins Installation
* Jenkins-Maven Integration

## 1. Jenkins Installation

### Prerequisites

* Java Development Kit (JDK) installed (preferably OpenJDK 11 or above).
* System with internet access.

### Installation Steps

1. **Install Java:**

   ```bash
   sudo apt update
   sudo apt install openjdk-11-jdk -y
   java -version
   ```

2. **Download Jenkins:**

   ```bash
   wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
   sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
   sudo apt update
   sudo apt install jenkins -y
   ```

3. **Start and Enable Jenkins:**

   ```bash
   sudo systemctl start jenkins
   sudo systemctl enable jenkins
   ```

4. **Access Jenkins:**

   * Open a browser and go to `http://localhost:8080`.
   * Use the initial admin password:

     ```bash
     sudo cat /var/lib/jenkins/secrets/initialAdminPassword
     ```

5. **Complete Initial Setup:**

   * Install recommended plugins.
   * Set up an admin user.

## 2. Jenkins-Maven Integration

### Prerequisites

* Jenkins installed and running.
* Maven installed on the system.

### Installation Steps

1. **Install Maven on the System:**

   ```bash
   sudo apt install maven -y
   mvn -version
   ```

2. **Configure Maven in Jenkins:**

   * Go to Jenkins Dashboard > Manage Jenkins > Global Tool Configuration.
   * Under "Maven," click "Add Maven."
   * Provide a name (e.g., Maven 3.8.6) and set the MAVEN\_HOME path.

3. **Configure a Maven Job:**

   * Create a new "Maven Project" in Jenkins.
   * Set SCM (Git repository URL).
   * Define Build Goals (e.g., `clean install`).

## 3. Usage

* Use `jenkins installation` for installing Jenkins.
* Use `jenkins-maven` for Maven integration with Jenkins.

## 4. Troubleshooting

* **Jenkins not starting:** Ensure Java is properly installed.
* **Plugin issues:** Clear plugin cache: `sudo rm -rf /var/lib/jenkins/plugins/*` and restart Jenkins.

## 5. Author

* Created by \[SefaliSabnam].
