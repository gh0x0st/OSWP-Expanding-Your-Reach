# OSWP - Expanding Your Reach
![Alt text](https://github.com/gh0x0st/OSWP-Expanding-Your-Reach/blob/master/Screenshots/offsec-student-certified-emblem-rgb-oswp.png?raw=true "OSWP Logo")

This April of 2020, I successfully completed the Wireless Attacks (WIFU) course and passed the Offensive Security Wireless Professional (OSWP) exam. I wanted to take some time and give back to the OffSec community and share some helpful tips in the hopes it helps pave the way into someone else's success story. 

### Path to Success

1. Prerequisites
    * Do I understand how to use Kali Linux?
    * Which Linux operating system do I use?
    * What host system should I use?
    * How will I stay organized?
2. Course Material
3. Lab Setup
    * Operating System
    * Hardware
4. Exam Prep Strategy
    * Practice Report Writing
    * Skeleton Report

___

### 1. Prerequisites:

I would like to talk about things for you to do, or think about, before you sign up for the WiFu course. There is some carry over from my previous post on my OSCP journey, but regardless of the course, the concepts still apply. The WiFu course prepares you for the exam, so you need to focus on your own limitations leading up to the exam.

**Do I understand how to use Linux?**

I mean specifically how to navigate through the operating system, not executing the tools. If you're not comfortable with the basics of Linux, then you may find that you'll struggle a bit. There is a course and a free PDF called Kali Linux Revealed (https://www.kali.org/download-kali-linux-revealed-book/), created by the Offensive Security Team that will take care of this for you. 

This book is like killing two birds with one stone. It's a book on how to basically use Linux, within Kali. What better way to help learn general Linux concepts then with the folks that developed Kali? With it being free, you can't go wrong with this.

**Which Linux operating system do I use?**

For the course itself, it doesn't matter what operating system you use so long as the tools you need are installed. Just keep in mind that your exam machine is running BackTrack 5. You can use either the provided WiFu ISO (BT5) or even the latest Kali to complete the course exercises as the attacks and methods are not operating system dependent. Just be mindful about mon0 vs wlan0mon if you go with BT5 vs any newer distro. I went with the WiFu iso so I could experience the course on the system it was built on.

**What host system should I use?**

This is just my personal preference, but I used a hardened version of Windows 10 as my host OS and had VMWare Workstation Pro to serve up my BT5 VM. I encountered no issues with incorporating my Alfa Adapter with VMWare and everything was stable throughout my entire course. 

To connect your alfa adapter to your virtual machine in VMWare:
1. boot up your virtual machine
2. plug in the usb adapter to your host machine
3. when prompted by VMware connect to the device to your BT5 machine 

**How will I stay organized?**

**_Backups:_**

You should always use some sort of backup solution for your notes. You don't want to be in a position where your system crashes and youy lose your only copy of your notes or course materies. I used OneDrive so I could access the material on any of my devices.

**_Notes:_**

I have no objections to using CherryTree, Dradis, etc. I've always used OneNote and stuck to what I was comfortable with. Most importantly, make sure your solution is backed up somehow.  You don't have to get overly fancy or verbose with how you take notes, just make it detailed enough so that you understand why each command you're running is necessary. This is how I structured my notes.

![Alt text](https://github.com/gh0x0st/OSWP-Expanding-Your-Reach/blob/master/Screenshots/onenote.png?raw=true "OSWP Logo")

**_Terminal:_**

The screen utility is available for you on the exam machine and is recommend by OffSec. I found this to be a lot easier than having to manage multiple SSH sessions for different windows. I initially just used tabs on the terminal during the course exercises but ended up switching to screen cause it was easier than constantly managing tabs. 

If you're not familiar with screen, this tutorial video is very helpful: https://www.youtube.com/watch?v=hB6Y72DK8mc
___

### 2. Course Material

I thought the courseware was very well put together and easy to follow, including the videos. OffSec has always done a great job with the structure of their educational content and videos.

You frequently see people mention that their content is outdated, but I don't feel that's a relevant statement. For example, I can still drive around a local city and see WEP enabled wireless networks and it's 2020. Open authentication networks are still in abundance and most passwords are still too simple. Until these factors dissapear, this is still a relevant course.

Although it's not specifically mentioned, in a way they indirectly show you the door is when it comes to the possibly of assessing WPA2-Enterprise enabled networks. If you're looking at getting into wireless pen testing, then you should be able to think of a way to assess the enterprise without attacking the wireless directly after taking this course. Take a deeper look at rogue access points in this case. 
___

### 3. Lab Setup

**_Wireless Router_**

I purchased a D-Link DIR-601 Wireless-N 150 Home Router off Amazon and I was able to complete all the course tasks except for the Korek ChopChop method, however, the Fragmentation attack was successful so I didn't put too much time into finding a compatible AP for ChopChop. 

**_Adapter_**

For the wireless adapter, I used an Alfa AWUS036NHA that I also got off Amazon. This adapter works out of the box with BackTrack 5 and Kali. The only caveat is that you're restricted to the 2.4 GHz frequency, but that’s works perfectly with the router above.

![Alt text](https://github.com/gh0x0st/OSWP-Expanding-Your-Reach/blob/master/Screenshots/airmon-ng.png?raw=true "airmon-ng")

Additional Information:

	• Chipset: Atheros AR9271
	• Standards: IEEE 802.11b/g/n
	• Antenna: 5dBi / 9dBi
	• Frequency Range: 2.412-2.484 GHz 
	• Allows Monitor Mode
	• Allows Packet Injection

**_Victim_**

Throughout the course, I was using an Android device as the victim for the relevant scenarios. However, when I got to the section on WEP PSK I kept getting a broken SKA message during my airodump-ng capture. To get by this, I popped Kali Live on a spare laptop and used that as my victim machine going forward. If you're running into a scenario where you're just not capturing complete handshakes, swap to do a different victim.
___

### 4. Exam Prep Strategy

**_Practice Report Writing_**

One thing that OSCP has taught me is that you can never be too prepared and that carries over to this course as well. OffSec takes its reporting requirements very seriously and as penetration tester, you should too. This alone could turn a successful exam execution into a failed attempt because you didn't follow the reporting requirements. 

As you continue through the course, you're going to come across labs for you to do on your own. Take the time to actually do the labs to solidify the concepts in your mind. But this is where you can take it up a notch. With each attack summary, turn that into a an opportunity to write a pen test report on your home lab.

After you're done with your report, reset everything and try to reproduce your results using only your report. Can you replicate your attack successfully step-by-step? Do your explanations make sense? Do you have enough screenshots?

**_Skeleton Report_**

Now that you've documented some scenarios on paper you will have an idea of what you like to include in a report and incorporate that into their recommended template (https://support.offensive-security.com/oswp-exam-guide/). You may find that you like their report as is, but you may also like to add a few things here or there. You won't know until you start adding content.

This is a basic structure that I used when I wrote my lab summary reports and I ended up carrying it over with my exam report because the flow worked for me.

![Alt text](https://github.com/gh0x0st/OSWP-Expanding-Your-Reach/blob/master/Screenshots/skeleton.png?raw=true "skeleton report")

With all of this is said and done, just relax. This is a very enjoyable course and can open the doors to a lot security awareness opportunities and would definitely recommend everyone to give this course a shot.

Try Harder.
