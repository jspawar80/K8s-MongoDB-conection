# Guide To access MongoDB from kubernetes cluster local using MongoDBCompass

## To download and install the AWS CLI on Windows using PowerShell, follow these steps:

1. Change the Current Directory.
- First, change to a directory where you have write permissions. For example, your user's Documents directory:
```
cd ~\Documents
```
2. Download the AWS CLI Installer:
- run the Invoke-WebRequest command:
```
Invoke-WebRequest -OutFile "AWSCLIV2.msi" -Uri "https://awscli.amazonaws.com/AWSCLIV2.msi"
```

3. Install the AWS CLI:
- Once the download is complete, run the installer with the following command:\
```
Start-Process msiexec.exe -Wait -ArgumentList '/i AWSCLIV2.msi /qn'
```
4. Restart your PowerShell

5. Verify the Installation:
- After the installation is complete, you can verify it by running:
```
aws --version
```

6. Configure AWS CLI:
- Finally, to start using the AWS CLI, you need to configure it with your credentials. You can do this by running:
```
aws configure
```
This command will prompt you to enter your AWS Access Key ID, Secret Access Key, default region name, and output format.


## To install kubectl on Windows using PowerShell, follow these steps:

Open PowerShell and run the following command to download the latest release of Kubectl 

1. Open PowerShell as Administrator:
- This step is important because creating a directory at the root of the C: drive usually requires elevated permissions.
- Create the Directory:
- In the PowerShell window, type the following command and press Enter: 
```
Set-Location C:\
New-Item -ItemType Directory -Path C:\bin
cd .\bin\
```
2. Download the Latest kubectl Binary:
- Open PowerShell and run the following command to download the latest release of kubectl. Make sure you are in the directory bin.
```
curl.exe -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.27.9/2024-01-04/bin/windows/amd64/kubectl.exe

Get-FileHash kubectl.exe
```
3. Set Up kubectl for EKS:
- Make sure your kubectl is configured to communicate with your EKS cluster. You can do this by running the AWS CLI command:
```
aws eks update-kubeconfig --name intelliflow-dev --region ap-southeast-1
```

4. Port Forwarding:
- forwarding port 27017 of the MongoDB service to 27017 on your local machine
```
kubectl port-forward service/mongodb 27017:27017.
```


## To install  MongoDB compass (GUI) on Windows using PowerShell and access the MongoDB, follow these steps:

1. Open this link to download MongoDB compass (GUI).
```
https://downloads.mongodb.com/compass/mongodb-compass-1.41.0-win32-x64.exe?_ga=2.45372004.137477373.1705411330-1784191706.1705411330
```
2. Install MongoDB and Open the MongoDB compass.

And copy this URl and paste into  MongoDB compass (GUI)

```
mongodb://username:password@localhost:27017/

```
make sure you have change the username and the password 

Make sure port is forwarding
