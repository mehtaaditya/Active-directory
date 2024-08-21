# Active-directory
##lab with entra id connect and how to setup and sync onprem identities

List of tasks completed in this Active directory/Entra ID lab
1. First i downloaded the latest version of windows server 2022 evaluation version and loaded it in virtual box and setup the win server machine
2. I added roles and feature to the server for Active Diretory domain services. I also added some features to add users and group option present in windows server manager
3. I configured Active Directory DS and named the forest as forestone.com and configures all the services needed shown in the below screenshots
4. After the AD server is up and running, i added users and groups in the active diretory forest
5. I then went ahead and downloaded Microsft Entra connect msi setup and added my global admin password for azure ad and administrator password for active diretory to setup the intial configurations
6. there was initially a problem in syncing the on prem server to entra and later i found that TLS must be turned on for the entra connect server. I went ahead and used the script above to enable TLS1.2 found in microsft learn docs.
7. Setup then concluded and the sync was succesfull and the onprem accounts started showing up in entra id (worker1) 
8. I made users which were later synced to Entra ID and changed the custom attributes which can be syncronized to Entra ID as per the demand.
9. Used password write back to reset password for on prem users
10. I register a .net app in app registration and configured the authentication return URL and sign out url. The app used is https://github.com/MicrosoftDocs/entra-docs/blob/main/docs/external-id/customers/sample-web-app-dotnet-sign-in.md#add-app-client-secret
11. I configures client secret for the app in the portal and used application id, tenant name and client secret in app setings.
12. Granted admin consent to the application and created a user flow to add custom attribute for user sign up process. Finally assocaited the app with the user flow

>>>>Download win server 2022 and run in on a vm or wherever possible and install AD DS and configure all the settings. To see all the process see link
>>>>You should also assign a static ip in the real environment for the AD DS
>>>>https://infrasos.com/how-to-setup-active-directory-on-windows-server-2022/
>>>>![Screenshot 2024-08-21 133451](https://github.com/user-attachments/assets/d22bfad8-7cf5-4279-828c-c6b506e08b1c)
After the delpoyment add users and groups to the domain
>>>>![VirtualBox_WINSERV(interface)_20_08_2024_11_39_44](https://github.com/user-attachments/assets/0aa4544c-4a45-4e66-8c7a-431137f720b5)
>>>>![VirtualBox_WINSERV(interface)_20_08_2024_12_42_31](https://github.com/user-attachments/assets/26d92491-57cf-4cfb-adfc-b8cfdbddde69)
>>>>![VirtualBox_WINSERV(interface)_20_08_2024_12_46_27](https://github.com/user-attachments/assets/3de9a1d0-6fa8-44a7-b45f-4a32353ac4dd)
>>>>![VirtualBox_WINSERV(interface)_20_08_2024_12_52_34](https://github.com/user-attachments/assets/a5b5d377-0e20-47ce-af4e-f15d4a631afd)
>>>>![VirtualBox_WINSERV(interface)_20_08_2024_12_53_28](https://github.com/user-attachments/assets/8143e029-403e-40ee-8259-8cb9a94f3bbf)
>>>>
>>>>Next installing microsoft Entra Connect and used the express settings for now.
>>>>![VirtualBox_WINSERV(interface)_20_08_2024_15_32_40](https://github.com/user-attachments/assets/f13058fc-fa57-491a-bb91-82c376d52b84)
>>>>![VirtualBox_WINSERV(interface)_20_08_2024_15_33_23](https://github.com/user-attachments/assets/2e61a581-068f-485f-98ed-98634f01b3dc)
>>>>Enter credentials
>>>>![VirtualBox_WINSERV(interface)_20_08_2024_15_33_45](https://github.com/user-attachments/assets/cd6becc6-7669-4202-964d-17ae01610e75)
>>>>![VirtualBox_WINSERV(interface)_20_08_2024_16_36_30](https://github.com/user-attachments/assets/6131ce49-cad0-4301-98a8-ebc25da8e85a)
>>>>![VirtualBox_WINSERV(interface)_20_08_2024_18_36_10](https://github.com/user-attachments/assets/96008e09-fa25-4008-b44e-a8c7698f923b)
>>>>On prem identities are now syncronized to Entra ID
>>>>![Screenshot 2024-08-20 184104](https://github.com/user-attachments/assets/dd4af6c8-39f4-4604-bce6-2bf1c3369f9e)
>>>>now i can use my on prem credentials ( worker1) to login to Entra ID
>>>>![Screenshot 2024-08-20 184153](https://github.com/user-attachments/assets/9000ffc7-4b90-45e6-9d20-d6f61373b8da)
>>>>Groups syncronized as well
>>>>![Screenshot 2024-08-20 192651](https://github.com/user-attachments/assets/076edea5-bb0b-42cd-9fcf-be9742891bbf)
>>>>we can also use domain filering rules to choose the custom attributes we want to sync to Entra ID
>>>>![VirtualBox_WINSERV(interface)_20_08_2024_20_15_19](https://github.com/user-attachments/assets/d0ef37dc-ad7c-40db-a5cf-29ec5ae38195)
>>>>Configuring pass thru sync as pash hash was already configures when we used express settings, Also enabling passwork write back feature( this feature will not work if on prem domain is not verified with DNS)
>>>>![VirtualBox_WINSERV(interface)_20_08_2024_20_15_51](https://github.com/user-attachments/assets/3c3b81dd-a62b-43e6-b270-e7c636a97ccc)
>>>>![VirtualBox_WINSERV(interface)_20_08_2024_20_17_17](https://github.com/user-attachments/assets/5c0ebd22-b1f3-436b-a6cd-fcfc2cff0fbc)
>>>>![VirtualBox_WINSERV(interface)_20_08_2024_20_19_54](https://github.com/user-attachments/assets/cccdf79f-4e13-43c3-acf9-a61f11a27572)
>>>>![VirtualBox_WINSERV(interface)_20_08_2024_22_21_13](https://github.com/user-attachments/assets/c6708053-8dc0-4dcd-bd62-23d7c2f01486)
>>>>made a new account to check sync process after the intial sync(worker2). Account appeared shortly afterwards
>>>>![Screenshot 2024-08-20 202222](https://github.com/user-attachments/assets/4fc59569-6aec-49c0-885a-059b4654d386)
>>>>password write back feature for onprem accounts
>>>>![Screenshot 2024-08-20 204807](https://github.com/user-attachments/assets/2746ce88-da2a-45bb-b0e6-9173bfd70336)
>>>>checking the sync status of the Entra connect in the portal
>>>>![Screenshot 2024-08-20 205343](https://github.com/user-attachments/assets/5719343f-dc20-4355-97d3-b78d45afeebe)
>>>>pass through agent running status(using 1 although three are recomended)
![Screenshot 2024-08-20 224708](https://github.com/user-attachments/assets/ee79eb0a-76c0-445e-8d9b-1748be5d0e43)
>>>>>pass through sync didnt work for me. after many hours of searching and trubleshotting i found this
>>>>![Screenshot 2024-08-20 234053](https://github.com/user-attachments/assets/2307f3c8-b83e-4caa-9260-c4320f262fdb)
>>>>Now lets register an app in Entra ID. Give it a name and return uri as blank for now
>>>>![Screenshot 2024-08-21 132645](https://github.com/user-attachments/assets/2b468035-4e0a-4a6e-9a31-cf713901e9a4)
>>>>adding client secret
>>>>>![Screenshot 2024-08-21 132324](https://github.com/user-attachments/assets/d69a92ce-6201-4083-9fc9-ad9c73dbbc57)
>>>>now add sign in uri and sign out uri as follows
![Screenshot 2024-08-21 132307](https://github.com/user-attachments/assets/298c7ace-fb9e-4e7e-a4b7-01a952fe5930)

>>>>![Screenshot 2024-08-21 132313](https://github.com/user-attachments/assets/63600554-2edb-4ec2-8ad9-9a2fb3cc3a38)

>>>>made a user flow to sign up and added custom attributes name place phonenumber etc
![Screenshot 2024-08-21 132324](https://github.com/user-attachments/assets/cfe0212f-2e2c-4c06-ac48-b9551500ed26)
>>>>
>>>>ran the application code of .net app changing the app setting and app secrets and tenant info
>>>>![Screenshot 2024-08-21 120928](https://github.com/user-attachments/assets/7c11e8cb-fe66-4969-8651-7ddbdb1033d2)
# LAB CONCLUDED












