Pentesters use OSINT to research their targets, and threat intelligence specialists use OSINT to learn about cyber threats. OSINT is an important tool for both the Red Team and the Blue Team.

![[Screenshot 2022-03-08 at 14.44.45.png]]

Tip: to make sure you check all domains and subdomains. One great tool is: https://github.com/gfek/Lepus.

**Shodan -** is a search engine of publicly accessible network devices on the internet, such as servers and IoT devices.
It is possible to put a server, peripheral, or network appliance on the internet and configure it to be relatively private and difficult to fingerprint. But if a device is connected to the internet without careful security configuration, you'll probably be able to find it through Shodan with the right search query.

Using Shodan without a paid account will return a very limited number of search results. Paid accounts are a lot more useful if the sort of OSINT cyber research that you do requires discovering servers, network appliances, and IoT peripherals (such as cameras). There are different monthly service fees depending on whether you're freelancer, small business, or corporation.

**Maltego -** runs as a dedicated application which gives users access to a wide array of data sources for the purpose of OSINT, journalism research, and forensics purposes. There are over 58 data sources in Maltego, which include Google Maps geocoding, AlienVault OTX, ATII Hades Darkweb Intelligence, Blockchain.info, Crowdstrike, VirusTotal, among many others.
The value Maltego provides researchers with is not only in its vast collection of data sources, but also in how its platform can show users patterns and trends in data through highly customizable visualisation. Up to a million entities can be plotted in the graphs that Maltego can generate.
Of course, being able to take advantage of all Maltego's features isn't free. But if you don't want to pay for a subscription, the free Maltego Community Edition can still be very useful.

**Google Dorks -** isn’t its own application. Rather, it’s a technique for using the same Google search engine everyone else on the internet uses everyday. There are developers who have developed open source software tools for Google Dorking that you can try such as [Pagodo](https://awesomeopensource.com/project/opsdisk/pagodo) and [GoogleDorker](https://awesomeopensource.com/project/nerrorsec/GoogleDorker).

A typical Google Dorking strategy starts with using simpler search queries and then moves onto more complex queries. There are a number of search operators that can be used in Google search that can return more targeted results. Google provides a list of tips to refine your Google searches [here](https://support.google.com/websearch/answer/2466433).

A lot of websites are configured very poorly when it comes to cybersecurity. Google’s web crawler bots travel as much of the web as they access to explore. So Google Dorking can be a technique to find data like email addresses, logins, and financial identifiers which haven’t been properly secured.

[Here’s a great video about Google Dorking from Hak5](https://youtu.be/lESeJ3EViCo).

**Recon-ng -** is an open source web reconnaissance tool. Its power is amplified by the modules you can install with it. If you use Recon-ng effectively, you can save a lot of time in your online OSINT research.

Recon-ng can run from the command line. If you want to make Recon-ng useful for your purposes, choose the Marketplace option from the main menu and explore what’s available. There are a huge number of modules you can try, with more being improved and added all the time.

**Ahmia.fi -** is a search engine specifically for finding sites on the Tor Network, although the search engine itself is accessible on the “clearnet”. You will need the [Tor browser](https://www.torproject.org/download/) in order to open your Tor search results.

A lot of dark web markets and forums are on the Tor Network, so effective use of the [Ahmia.fi](http://Ahmia.fi) search engine can be a great tool.

**Wayback Machine -** is a search engine of webpages, many going way back into the 1990s.

And what’s really cool is that you can usually use links in the archived webpages to go to archives of those other webpages.

**TheHarvester -** is another useful open source reconnaissance tool that you can install from GitHub.

It can be used to acquire email addresses, hosts, subdomains, employee names, and open internet ports from various public sources such as search engines, PGP key servers, and Shodan. It’s amazing how much useful information people leave online without properly securing it.

When theHarvester is installed, you can esily run the application from your command line. There’s an especially rich set of options to explore data in DNS servers, they have all kinds of very useful information because they link domain names to specific IP addresses.

Some data sources that you can explore include LinkedIn, Bing, Google, and VirusTotal.

**TinEye -** is a powerful tool for researching images online. You can upload an image into TinEye and see if and how that image is being used on the web. If you have the URL of an image that’s on the web, you can also conduct research that way.

**OSINT Framework -** is the perfect web application if you aren’t sure which OSINT data sources you’ll need to use to find the information you want. So OSINT Framework presents you with a huge tree of potential data sources that you can explore.

Do you want malicious file analysis, usernames, geolocations, IP addresses, domain names, IRC, the Dark Web, metadata, threat intel, phone numbers, etc. Keep clicking through the tree until you find the source that you need.

**OSINT Framework may be your first step in all of your OSINT work!** 