# HomeLab-setup
Through my passion of Devops and Technology, I have decided to create my own personal server where I can easily share files from.

**Project Overview**

Recently, I have been conducting research and developing my own home lab setup, this is to further support my devops journey. I hope for this to help me build upon previously accquired skills as well as provide me with the oppurtunity to learn more. From my conducted research this will help me learn a varitey of topics such as  vpn tunnelling to provide remote access using tailscale which uses mesh topology to my NA(Network Attached Setup) setup from anywhere via a secured channel, other topics include Local file sharing using SMB protocol, It could potentially also be useful to conduct a project in which I connect my home NAS to azure to demonstrate the simplisty

Along with this during my break of producing azure projects I have been attempting to learn the basics of python as well as familairse myself with terraform Syntax.

**Preperation**

Before even buying any products I needed to conduct some research into the best setup for what I wanted this NAS server for. looking at various videos on youtube and reading reviews and articles online allowed me to come to the conclusion that to get the server with the processing power I required and within budget specfications I needed to buy:

Mini computer I chose a GMKtec mini pc with a ryzen 7 16gb RAM and intergrated graphics 

DAS also known as Direct Attached Storage

I chose a DAS to essentially offload the pressure of the computer itself which otherwise would need to provide power to cool and run the hard drives. The purpose of this setup was not only for educational purposes but, to also provide a foundation for an entertainment center database where I could access all my films that were previously DVDs, it could also later be beneficial to provide a stepping stone for demonstrations of cloud computing intergration scenarios and AI system intergartion

There are various different operating systems I could have chosen, I decided to install truenas, this is a community and industry standard OS that provides a variety of features including valuable resources such as VM capabilties. This Operating system will provide insight into ZFS filesystems

**What I learnt**
Throughout this whole project(which will contuine to develop and grow) I have learnt a varitey of different things. There were a vast amount of oppurunities to learn from resolving communication issues to remote access setups.

Once the server was setup I could install my first hard drive, as i currently only have one it meant that it was difficult to justify using RAID format to ensure redundancy within my data however I will be installing two inudstry standard server specfic hard drives. Due to AI and datacenter demands there has been a dramatic spike within. 

![IMG_4798](https://github.com/user-attachments/assets/e287ffba-81d5-4e66-9dbb-f174d6a43038)

Above shows the DAS with the 1tb SSD I had previously accquired.


Once i have these Hard drives, this will alow me to use RAID technology to ensure that my data is protected and backed up to avoid any disruptions.

As previously said I installed truenas os onto the mini pc, this was installed using a bootable USB which was created using rufus(a diskimaging software), the process was quick and simple and straightforward. 

*Below shows photos of the setup process*

![IMG_4802](https://github.com/user-attachments/assets/ddf97673-c753-41ce-94a6-de1f63bd278d)

![IMG_4801](https://github.com/user-attachments/assets/d46b1f37-7051-4d9a-b6fa-257ac7e43480)

*Below shows the final setup both the display and what is shown on the web UI(IP address blurred out for privacy)*

![IMG_4804](https://github.com/user-attachments/assets/6e5b0c9b-e88a-4c48-9d6d-fdcffff47429)

<img width="1919" height="853" alt="image" src="https://github.com/user-attachments/assets/807b577e-b629-4fb4-a53a-80582e37d4ce" />

**Jellyfin setup**

![IMG_4845](https://github.com/user-attachments/assets/a02c0d58-912a-4b0a-91fe-5eea4f0f35ec)

Above shows a small plan of the architecture of how the current setup will occur, I have put each device into layers briefly following the OSI layer model

My first task was to create a dedicated space for the related files to be assoicated with I named this Livev1 and enabled SMB sharing to this folder.

<img width="909" height="427" alt="image" src="https://github.com/user-attachments/assets/3653b56d-9ebc-49bf-9fa0-78483f7c3bbc" />

*Above shows the SMB file share being enabled within the truenas share feature menu*

next was to create an assoicated smb "workgroup" under the credentials/group tab then a local user 

I needed to go to the ACL(Access Control List) settings to enable the new "JellyFinUser" user to be able to access this specfic SMB file

<img width="1221" height="557" alt="image" src="https://github.com/user-attachments/assets/1b84faaf-d014-4059-840c-d4e95b72e9ec" />
*Where I needed to go within the share feature to adjust the ACL settings

locate and download jelllyfin which will prompt a setup dialog.

<img width="950" height="704" alt="image" src="https://github.com/user-attachments/assets/f3e13dfe-a2bf-4d2b-b889-c840823613db" />

*Above shows using the discover app feature within truenas to find the jellyfin container app.*

