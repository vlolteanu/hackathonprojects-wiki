## MobileInsight Challenges

### What’s MobileInsight?

MobileInsight (short for MI, hereafter) is an on-phone tool to gain open access to operational cellular network operation information which remained closed before. It allows researcher, developers and users to obtain below-IP (L1/L2) cellular-specific networking information at runtime from their own smartphones, with no need of operators’ permission to use their network data or using special instruments. It empowers real-time network monitoring, detection, predication and analytics on the device end and thus helps to boost cellular networking performance, efficiency, reliability, and so on.

* Website: http://www.mobileinsight.net/
* Github: https://github.com/mobile-insight
* Tutorial (videos and slides): http://www.mobileinsight.net/tutorial-video.html
* First-use doc tutorial:   http://www.mobileinsight.net/tutorials.html

### Technical Skills Required

MI is suitable to any student, developer and researcher in networking. Participants are required to have

1. Basic networking background (TCP/IP network stack, L2/L1, control-/data-plane, throughput, RTT, packet loss)
1. Python programming (core and sample codes in Python)

Participants are encouraged to have the following skills or experience

* Linux or Mac OS x (all-in-one VM in Linux) and shell commands (e.g, awk, good for quick data processing)
* Tcpdump/wireshark (TCP/IP packet dumping and analysis, complementing MI)
* Basic Android programming (optional, mainly for fancy UI and widgets)

### Hackathon Projects

Our Hackathon challenge is to understand latency over LTE. It consists of three progressive projects which can be chosen by every participant based on their interests.

**Project 1 (easy)**: Collect L1/L2 information from MI and extract PHY-layer information (bandwidth, radio resource blocks, modulation, etc.) and MAC-layer information (retransmission, sequence etc.) and other options of your interests

**Project 2 (medium)**: Visualize the L1/L2 analytics in project 1 on the desktop. Monitor their changes over time and under special events (e.g., handoff); Display basic statistics (percentiles over sliding windows) and perform anomaly detection.

**Project 3 (advanced)**:  Extract the L1/L2 network latency out of above information. Compare with higher-layer latency analysis using tcpdump (RTT in TCP) and build a full-stack latency analyzer (optional).

-------

_Note 1_: MI supports two main use modes: (1) Mobile only: run it on phone only (data collection and online analytics), and (2) Mobile+desktop: run mobile app to collect data at runtime but upload data to the desktop for offline data analytics. Hackathon projects will run at mode 2 (mobile + desktop) while they are easily portable to mode 1 (mobile only).

 

_Note 2_: MI can be used to understand more than latency, including but not limited to throughput, loss, network dynamics, handoffs etc. If you are interested in other problems, please feel free to contact us.

 

_Note 3_: You are encouraged to run MI before you come to Hackathon. Please read MI’s website (http://www.mobileinsight.net/) and go through the tutorial in 1-3 hours.  MI’s mobile app runs on rooted Android phones mainly over Qualcomm chipsets. A large variety of phone models are supported. If you don’t have such a phone, please keep me posted and I will bring several MI-ready phones for Hackathon’s use.   


### Contact us:

Prof. Peng will participate and supervise all the participants at the Hackathon event. If anyone has technical questions in advance, please directly contact her (chunyi@purdue.edu) and the MI support team (support@mobileinsight.net)
