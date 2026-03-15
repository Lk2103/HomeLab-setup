# HomeLab-setup

Through my passion for DevOps and technology, I have decided to create my own personal server where I can easily share files from.

## Goals

 - To Configure a fully functional NAS which could deliver my required needs:

    * Capable of being accessible anywhere via WebUI
    * Being accessible anywhere means that it is also required to be as secure as possible
    * Capable of functioning as a VM library,Jellyfin/Entertainment system and an archive for emulation games

Through accomplishing these goals I will learn a variety of skills such as:
* VPN tunnelling configuration
* SMB file sharing configuration
* Further improvement of researching complex procedures
* Firewall, Conditional Access and Credential skills

## Preparation

Before even buying any products, I needed to conduct some research into the best setup for what I wanted this NAS server for. looking at various videos on youtube and reading reviews and articles online allowed me to come to the conclusion that to get the server with the processing power I required and within budget specifications I needed to buy:

A mini computer I chose a GMKtec Mini pc with a Ryzen 7 16gb RAM and integrated graphics

DAS also known as Direct Attached Storage

I chose a DAS to essentially offload the hardware load of the computer itself which otherwise would need to provide power to cool and run the hard drives. The purpose of this setup was not only for educational purposes but, to also provide a foundation for an entertainment center database where I could access all my films that were previously DVDs, it could also later be beneficial to provide a stepping stone for demonstrations of cloud computing integration scenarios and AI system integration

There are various different Operating Systems that I could have chosen, I decided to install TrueNAS, this is a community supported and industry standard OS that provides a variety of features including valuable resources such as VM capabilities. This Operating system will provide insight into ZFS filesystems where I will have control over Volume allocation which benefits what I require from the Server.

## Research
Before proceeding with any of the decisions I made. Its important to conduct research and note down my findings, not only as best practice but, to avoid mistakes and delays in project deployment:

**Research regarding hardware configuration:**

Using various YouTube videos found by creators such as DammitJeff, Jimmy Tries World and Sean Aslam as well as using websites such as Tom's Hardware Reddit and TechRadar I produced a pros and cons list for each hardware setup to ensure I chose the correct hardware for my personal requirements Below you can see these lists outlining why I chose a Mini PC with DAS integration setup.

**Mini PC and DAS**
 
| Pros  | Cons|
|-------------  | ------------- |
| High Performance  | Increased clutter  |
| Lower Cost (Get more for your money)  | Increased Hardware |
| Choose your own OS  | Not usable straight out of the box (advanced Setup)  |
| Can allocate more hard drives not limited by case size|   |
| Small and compact |   |
| Low power footprint  |  |

**NAS(Built in One)**

| Pros  | Cons|
| ------------- | ------------- |
| Ready to use straight out of the box  | Limited Hard drive space  |
| Pre installed software to assist with needs | Power for hardware is all combined |
| Power efficient(Designed to run constantly) | If NAS dies may have to buy from same brand to recover data also known as RAID Lockin |
| Auto Backup | I want to choose own OS |
| | Limited Upgradability |

**Old laptop with External hard drives**

| Pros  | Cons|
| ------------- | ------------- |
| Essentially no cost  | Limited upgradability (storage,RAM, cant upgrade CPU)  |
| Recyling old hardware (good for the environment) | Batteries can become swollen NOT designed to be plugged in 24/7  |
| Built with battery protection (prevent data loss and corruption during surges) | Old hardware likely to fail sooner  |
| | Power efficiency not the best compared to other options  |
|| Not ideal in terms of finding a place to put it  |

*Copied from journal of projects*

It is important to take into account that I may potentially want to integrate AI into the server to produce an all round offline AI assistant (this requires a good processor and decent amount of RAM). This option also provides the biggest opportunity to learn.

## Production

Throughout this whole project (which will continue to develop and grow) I have learnt a variety of different things. There were a vast amount of opportunities to learn from resolving communication issues to remote access setups.

Once the server was setup I could install my first hard drive, as I currently only have one it meant that it was difficult to justify using RAID format to ensure redundancy within my data however I will be installing two industry standard server specific hard drives. Due to AI and data center demands there has been a dramatic spike within. 

![IMG_4798](https://github.com/user-attachments/assets/e287ffba-81d5-4e66-9dbb-f174d6a43038)

Above shows the DAS with the 1tb SSD I had previously acquired.


Once I have these Hard drives, this will allow me to use RAID technology to ensure that my data is protected and backed up to avoid any disruptions.

As previously said I installed TrueNAS os onto the mini pc, this was installed using a bootable USB which was created using Rufus(a disk imaging software), the process was quick and simple and straightforward. 

*Below shows photos of the setup process*

![IMG_4802](https://github.com/user-attachments/assets/ddf97673-c753-41ce-94a6-de1f63bd278d)

![IMG_4801](https://github.com/user-attachments/assets/d46b1f37-7051-4d9a-b6fa-257ac7e43480)

*Below shows the final setup both the display and what is shown on the web UI(IP address blurred out for privacy)*

![IMG_4804](https://github.com/user-attachments/assets/6e5b0c9b-e88a-4c48-9d6d-fdcffff47429)

<img width="1919" height="853" alt="image" src="https://github.com/user-attachments/assets/807b577e-b629-4fb4-a53a-80582e37d4ce" />

**Jellyfin setup**

![IMG_4845](https://github.com/user-attachments/assets/a02c0d58-912a-4b0a-91fe-5eea4f0f35ec)

Above shows a small plan of the architecture of how the current setup will occur, I have put each device into layers briefly following the OSI layer model

My first task was to create a dedicated space for the related files to be associated with I named this Livev1 and enabled SMB sharing to this folder.

<img width="909" height="427" alt="image" src="https://github.com/user-attachments/assets/3653b56d-9ebc-49bf-9fa0-78483f7c3bbc" />

*Above shows the SMB file share being enabled within the TrueNAS share feature menu*

next was to create an associated smb "workgroup" under the credentials/group tab then a local user 

I needed to go to the ACL(Access Control List) settings to enable the new "JellyFinUser" user to be able to access this specific SMB file

<img width="1221" height="557" alt="image" src="https://github.com/user-attachments/assets/1b84faaf-d014-4059-840c-d4e95b72e9ec" />

*Where I needed to go within the share feature to adjust the ACL settings*

locate and download jelllyfin which will prompt a setup dialog.

<img width="1103" height="599" alt="image" src="https://github.com/user-attachments/assets/fde46c62-3ebd-4156-a57e-51651a87d3e9" />
*Showing the app to the SMB storage that was allocated*

<img width="1910" height="818" alt="image" src="https://github.com/user-attachments/assets/710c55ed-f903-4b43-a7ec-9ee7f80f0c05" />
After completing the setup the Jellyfin server was enabled and running from the NAS, this could be accessed by web UI as shown above

Issues that occurred
When going through this setup some of the options were incorrectly selected, it was important to also ensure that the correct directory for storage was implemented to avoid errors.
