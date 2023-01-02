**What is a Security Operations Center (SOC)?**

The traditional definition of a SOC is a facility, place, or department that houses all of, or the primary core of, your business’s security operations.

What we mean by security operations is the continuous monitoring of a network, detection management, and incident response.

A modern SOC is a little different. Most of them you’ll still find in a facility or building, but it doesn’t have to be quite that strict of a definition.

For instance, there are now virtual SOCs (SOC as a service).

The core of a SOC is the team of security professionals whose sole aligned purpose is to meet a corporate or business security goal to manage, detect, and respond to cyber security risks.

24/7 SOC today are more accessible than they were in the past, partly due to the meteoric rise of cloud services. Another reason has been the constant drive to push security down to smaller business models.

One thing that does not change, no matter the SOC architecture, is the primary purpose: to be the center of the organization’s security.

**Internal SOC -** is a department of cyber security experts within an organization who fill many different roles of a SOC.

Generally, they’re going to be managing the corporate network and any internet presence they may have.

Their job is to be the nerve center for security within the company. They’re making sure they have visibility as systems get installed that come online, they can see them, scan them, inventory them, provide incident response on them, and run the tools for security on them as they require.

Creating that visibility, responding to those incidents, blocking things as need be, making sure that the IPS are updated, that they’re working, making sure that all the systems in the corporate network are updated and they have a lot of tools that give them these abilities.

The ultimate goal is to protect the “crown jewels” from unauthorized users.

**Managed SOC (SOC As A Service) -** if you don’t want to build an internal SOC, because either you don’t have the budget, you don’t know how, or you’re a smaller business and it doesn’t make sense to invest in a full-time SOC, then you may look into managed SOC model.

A managed SOC functions the exact same way as an internal SOC. The main difference is that a managed SOC is usually larger, so it can have more capacity than a corporate SOC.

The other side is it’s less expensive.

Now, a difference comes into how that SOC gets its information and how it’s able to do the things that it can do within your network.

**What are the benefits of a SOC?**

Having a SOC keeps you gile in the security sense.

_There are three main benefits of a SOC:_

1.  _**Centralizing the display of assets -**_ a SOC helps centralize the management of your security and security assets in one place so that it’s not spread out across the whole organization.
    
    Larger organizations typically have an internally managed SOC to:
    
    -   perform incident response
    -   monitor the fleet
    -   be the main point of contact for audits
    -   conduct vulnerability scans
    -   conduct penetration scans
    -   provide other security functions
2.  _**Collaborating across departments and functions -**_ ensures that everyone is secure. It´s also the job of a SOC to keep metrics of the security landscape within the organization and report that up to the CIO.
    
3.  _**Maximizing awareness to minimize costs -**_ SOCs are also responsible for reporting pertinent information to key stakeholders and decision-makers to maximize awareness, thereby helping businesses to keep costs down.
    

**How does a SOC work?**

1.  _**Get visibility of information systems -**_ foremost, a SOC needs to be able to see what’s going on in the information systems that they intend to protect. That’s really the most important thing. If you can’t see it, you can’t protect it. You can’t react to it.
    
2.  _**Define your goals -**_ the most important thing after visibility is defining your goal. Even if you don’t have a goal, at least if you can see what’s going on, you’re doing something right. But the goal is a really important part of creating, designing, or subscribing to, or deciding if you need a SOC. Furthermore, it addresses what the SOC is going to do.
    
    The simple answer is that a SOC will keep you secure, but you need to break it down further. If you’re running an internal SOC then you need to define its purpose such as:
    
    -   Blocking traffic/requests
    -   Monitoring systems
    -   Keeping ingress from the internet domain
    -   protecting internal corporate systems
    
    These are the kinds of things that you have to figure out in your goal of a SOC.
    
    Overall, steps one and two can switch off. If you’re a managed service you need to know the goal. If you are an internal SOC, you need to take inventory of everything, and then decide what you’re going to do with it.
    
3.  _**Monitor & Identify traffic -**_ you need to equip yourself with the tools to achieve your goals. Basic level one is monitoring and indentification.
    
    So, for that, you’re going to need some kind of a monitoring system, like an intrusion detection system (IDS). That could be one that sits on the network, looking at the enterprise assets internally. Or, it could be an IDS that is sitting between internet traffic and your web servers to see what’s going on from the internet zone inward.
    
    This gives you visibility, but you also need somewhere to see that information, sort through that information, and understand that information.

![[Screenshot 2022-03-07 at 13.29.59.png]]

That’s where a SIEM (Security Information and Event Management) solution comes into play. Splunk and Elastic Search are good examples of this technology.

You can build a number of different types of SIEMs, but they all generally serve the same purpose of ingesting all that information from some kind of log source, like an IDS, and providing that data to analysts and security experts.

From there, security analysts have the ability to run searches, and filter results, in order to look for threats.

Altough some professionals may argue that a SOC should really be reacting to threats and not just monitoring them.

However, you can have a monitor only SOC if that’s all you really think that you need in your business.

1.  _**Respond to cyber attacks & threats -**_ security analysts need to be able to do something with data collected from the SIEM. It could be as basic as blocking IPs from some bad source. In order to do this, you’ll need firewalls and an Intrusion Prevention System (IPS).
    
    This is where we get into advanced SOCs. Most perimeter tools go way beyond just a firewall in your traditional sense.
    
    If you’re in a cloud service, there are all kinds of application gateways, API connectors, cloud tools, and numerous other ways that traffic can enter your environment.
    
    And there are numerous different ways that you can protect that traffic coming in through there. So if you’re trying to block it, you need to be able to communicate with these tools.
    
    In some way, a lot of SOCs will use a tool that sits in an environment that can speak to all these configurations or build AWS or Azure configurations for themselves to act as a firewall.
    
    This is your first layer of response. Now that’s really basic. And these days SOCs are doing so much more than that because there’s also Threat Intelligence.
    
    There’s dynamic data science coming in here so that they can continuously update signatures and keep on top of current threats.
    
    And that’s a really important part of what a SOC does and how it works - it’s constantly moving.
    
2.  _**Report findings to stakeholders -**_ a SOC must report findings to the CISO, CIO, CFO, and/or CEO, so that they are aware of what happens within their business.
    
    This is typically delivered in the form of risk reports, and ensures that decision-makers in the business are:
    
    -   aware of what is happening
    -   aware of their current running risk
    -   aware of the dollar value of that risk
    
    The purpose of this reporting is to drive the company towards some kind of corporate security goals.
    

**Conclusion**

Cyber security for the modern internet is a lot like the Cold War; both sides are constantly improving and innovating their weapons and defenses to overcome the other.

There is no stopping the constant evolution of the internet or technology itself. Meanwhile, threat actors continue to move with the trends evolving their toolsets and techniques along the way.

For businesses and, more often every day, private citizens, it is important to understand that the tools of cyber security have greatly changed at an accelerated pace over the last few years. It is no longer sufficient to have client-side antivirus and firewalls to protect your IT.

Instead, modern security and safety mean continuous monitoring, scanning, and testing of your IT infrastructure to meet basic due diligence, and it is becoming ever more important to include response as a security discipline within the organization.