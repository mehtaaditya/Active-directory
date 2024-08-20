# Active-directory
lab with entra id connect and how to setup and sync onprem identities
List of tasks completed in this Active directory/Entra ID lab
1. First i downloaded the latest version of windows server 2022 evaluation version and loaded it in virtual box and setup the win server machine
2. I added roles and feature to the server for Active Diretory domain services. I also added some features to add users and group option present in windows server manager
3. I configured Active Directory DS and named the forest as forestone.com and configures all the services needed shown in the below screenshots
4. After the AD server is up and running, i added users and groups in the active diretory forest
5. I then went ahead and downloaded Microsft Entra connect msi setup and added my global admin password for azure ad and administrator password for active diretory to setup the intial configurations
6. there was initially a problem in syncing the on prem server to entra and later i found that TLS must be turned on for the entra connect server. I went ahead and used the script above to enable TLS1.2 found in microsft learn docs.
7. Setup then concluded and the sync was succesfull and the onprem accounts started showing up in entra id (worker1) 
