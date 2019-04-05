# Personal Forensics Toolkit

## Prebuilt Platforms
Honestly I enjoy useing prebuilt VM's just because a lot of times they have tools I haven't used that I can practice with. The two I have experimented with so far are SANS SIFT Workstation and Samuri's Paladin Forensics Suite. These are both free and can be found at the following links for download:
SIFT: https://digital-forensics.sans.org/community/downloads
Paladin: https://sumuri.com/software/paladin/

## Individual tools
Although using prebuilt VM's can be easy for tool selection often times running programs on your computers native OS will be faster. Below I will list the tools I use most often as well as where to find them as well as a few tips that have been helpful for me.

### Autopsy
#### Description
Autopsy is an open sorce forensics GUI for "The Slueth Kit". These programs were developed to analyze data off of recovered computer drives.
#### Review
Personally I find Autopsy to be one of the best tools out there. I have used one other tool and for me autopsy has been easier to understand, navigate, and find online solutions to problems I have ran into that I could not come up with a solution of my own in reasonable time. So far I have not found anything that I cannot do in autopsy that was critical to success on my project. That said, no one tool is perfect and it isn't always accurate on its automated findings.
#### Dowload Link
https://www.sleuthkit.org/autopsy/download.php
#### Tips
1) The first thing I do is run the ingest for keyword searches, this will be very time consuming but can prove very helpful later.
2) On windows images I export the prefetch files for analysis.
3) If you have a timeline of when events were reported you can use the timeline module for autopsy to get events in a time series for analysis
4) Using the views (e.g. file types) can be helpful when looking for specific files that are or may be related to the incident.

### Windows Prefetch View
#### Description
WinPrefetchView is a program develped by nirsoft to display prefetch files from the windows system. Prefetch files are recently called files and applications by the comptuer itself.
#### Review
I have not sought out other programs for windows prefetch memory analysis as I have never seen a need. At first the program is a little odd but I found it to be simple yet not lacking in any way for prefecth analysis.
#### Downlaod Link
Site with download links: https://www.nirsoft.net/utils/win_prefetch_view.html
Direct download of 32-bit version: https://www.nirsoft.net/utils/winprefetchview-x32.zip
Direct download of 64-bit version: https://www.nirsoft.net/utils/winprefetchview-x64.zip
#### Tips
To set the location that winprefetchview points at is found under advanced options (it defaults to looking at the computer it is being ran on).

### Volatility
#### Description
Volatility is one of the dominant memory analysis tools in the forensics community. There are a few others I have heard of and have but have never used, like rekall. Volatility is open source as is rekall.
#### Review
When it is working Volatility is great. The only issue I have had is not always having a profile for the system, this only happened with a new updated but insecure windows machine used for a practice lab in a class.
#### Download Link
https://www.volatilityfoundation.org/26
#### Tips
1) start with using the kdbgscan command to get the profile for the memdump
2) Next I would run pstree to get a list of processes in a tree format
3) To check for processes that are using network connections use connscan. Using this can help you weed out valid and invalid traffic as well (e.g. a windows system process reaching out to unidentified hosts).

### Wireshark
#### Description
Wireshark is perhaps the most known network analysis tool out there. It can be used to filter and look through network traffic captures. 
#### Review
Wireshark does not have the advanced capabilities of an IDS like bro or snort, which I have never found very usefull in my work so far but in more practical circumstances they may be better fit for many aspects of analysis. As for the simple stuff I have done Wireshark has been easy to read and work with.
#### Download link
https://www.wireshark.org/download.html
#### Tips
Wireshark has a lot of tricks. My best advice is to follow suspicious streams so that you can see the whole stream but not to forget that good malware will chunck data it sends into broken streams so that it isn't as easy to figure out what it is doing. Use filters on the target IP, it may come with a lot of condiluted data and you can filter by the attacking IP you have identified but don't forget that one individual attack can come from several hosts.
