# Learning

# New_tools
Latest tools and buzz words
- service mesh
- robotic process automation/robot test automation -RTA
- Poll SCM : https://wiki.jenkins.io/display/JENKINS/PollSCM+Plugin
- stackstrom  :  https://stackstorm.com/
- [Google Training :](https://applieddigitalskills.withgoogle.com/c/middle-and-high-school/en/research-and-develop-a-topic/test-for-credibility/credibility-clues.html) 
- [Google Training - list of topics](https://applieddigitalskills.withgoogle.com/c/en/curriculum.html)
- Man pages is linux replaced with [tldr](https://opensource.com/article/21/6/tealdeer-linux?utm_medium=Email&utm_campaign=weekly&sc_cid=7013a000002wLfAAAU)
- du replaced with `dust` [disk utilization with rust tool](https://opensource.com/article/21/6/dust-linux?utm_medium=Email&utm_campaign=weekly&sc_cid=7013a000002wLfAAAU)
- [Rust Unix tool command replacements](https://opensource.com/article/21/7/rust-tools-linux?utm_medium=Email&utm_campaign=weekly&sc_cid=7013a000002wQ7rAAE)


### AI/ML/Tools/Chatbot :
- [Chatbot tools](https://www.mygreatlearning.com/blog/basics-of-building-an-artificial-intelligence-chatbot/)
- [ML Basic Challenges](https://www.machinehack.com/hackathon)
- [GH: AzatAI/cs_books: Computer science books Recommended by AzatAI. (Education ONLY)](https://github.com/AzatAI/cs_books)


### Training Tools: 
- [Free Python ML learning](https://www.mygreatlearning.com/academy?ambassador_code=BlogExitPopUp&arz=1#our-courses)


### [2D Software tool](https://itsfoss.com/enve-2d-animation/)

### OpenCV:
- [Python and OpenCV Course –Create Computer Vision Apps in the Cloud](https://www.freecodecamp.org/news/create-computer-vision-apps-in-the-cloud-with-opencv-and-python/amp/)


### Printer Management: on Rasberry Pi & Ubuntu X86/X64
- Install, Config `CUPS` RPM/db pkgs on your system. [https://programmersought.com/article/23111198205/] share more details with screenshot.
- PPD Files for EPSON L130 **did not worked** [PPD File which can be downloaded](https://raw.githubusercontent.com/endlessm/epson-inkjet-printer/master/201401w/ppds/EPSON_L130.ppd)
- In Ubuntu it should be able to work [Steps to install printer](https://www.maketecheasier.com/set-up-a-printer-in-linux/)
- `lsusb` will list the USB PRinters and owner would be `lp` for the file to which the USB Printer is attached.
- `lpadmin -p chaituprinter -E -v /dev/bus/usb/001/005 -P EPSON_L130.ppd` - Add Printer a name, in my case `chaituprinter`
- `lp /etc/hosts` will print the file `/etc/hosts` 
- [EPSON Linux Drivers for L130 Ink Jet Printer](http://download.ebz.epson.net/dsc/du/02/DriverDownloadInfo.do?LG2=EN&CN2=&DSCMI=129010&DSCCHK=3e1fee5f2316289cd249a8b25b6058d94eacfc1e)

