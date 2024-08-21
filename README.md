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
>>>>![image](https://github.com/user-attachments/assets/20ad771f-d2be-4865-b7fd-2fbe3ec430a7)








