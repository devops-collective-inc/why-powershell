# Why PowerShell Remoting? (While We're Answering "Whys")

Another big question that comes along is, "why should we enable PowerShell Remoting?"

First, understand a couple of things - which are going to seem a bit rude. Sorry.
- PowerShell Remoting has been around since 2008. If you're seriously just asking yourself this now, then you're doing a poor job of managing your IT environment. Also released since 2008 were smart watches, Microsoft (formerly Windows) Azure, the Tesla Roadster, Disney's "Frozen," affordable LED light bulbs, and the iPhone 3G, 3GS, 4, 4S, 5, 5S, and 6 models. Just in case you missed those as well.
- Information technology is an industry of change. The perfectly reasonable decisions you made in 2003 are going to need to be periodically revisited, due to aforementioned change.

With that out of the way, let's briefly talk about...
## What is PowerShell Remoting?
Remoting is simply a way for management tools on one computer to talk to services on another computer, so that you can remotely manage those services. 

Remoting is based on HTTP, and uses a protocol called WS-Management (WS-MAN). It requires servers to have a single open port, and routes all incoming management traffic through that one port. WS-MAN traffic can be logged, can be proxied through security servers (provided by third parties), and can be completely encrypted by means of SSL. 

Like all HTTP traffic, Remoting is essentially transmitting text back and forth. Remoting simply specifies a way for that text to be laid out (predominantly in an XML variant) so that tools and services can understand each other.

Remoting does not in any way affect the security of your network under default conditions. It does not, by default, transmit usernames or passwords - encrypted or otherwise. In a non-domain environment, you can create an environment where passwords would be transmitted, but it really wants that to be encrypted by SSL, so you'd be using HTTPS.

Remoting doesn't in any way give anyone special privileges. The technology literally can't let someone do something they don't have permission to do, unless you've gone through a rather complex setup for something called _delegated administration_. In that case, you can enable specific users to perform specific tasks that they wouldn't normally be able to - but only through the specific channel and interface you've set up. 

## Comparing Remoting to what came before
Before Remoting, most Windows remote management was conducted over Remote Procedure Calls, or RPCs. These usually employed port-hopping, making them incredibly difficult to manage through a firewall. Contrast that with the one port you have to deal with in Remoting.

A lot of organizations today simply install management tools on servers, and then use Remote Desktop to "remotely manage." That's an incredibly poor idea, and is a major reason why Windows Server take so many patches, so many reboots, and other maladies. The code needed to support a full GUI, and therefore RDP, is massive - and that means patches are inevitable. Running management tools _on the server_, usually under administrator credentials, is opening the door to an attack.

In short, most organizations seem to be worred about the security "implications" of PowerShell Remoting. The implications are **significant** - Remoting is **much** more secure than what you've been doing. It's also more efficient, imposes less overhead on servers, and lets servers run with a leaner operating system that will require fewer patches, fewer reboots, and fewer service packs. Those servers will also boot faster, run fewer processes, run fewer services, and consume less storage space for the OS. Those servers will require less memory overhead for the OS, meaning you can pack more of 'em into a virtualization host. Sounds horrible, right?

## But here's the best reason
Quite simply, the main reason to enable Remoting is that _you haven't got any choice._ Microsoft has moved firmly in this direction, and enables Remoting by default on Windows Server 2012 and later. The company _disables_ Remote Desktop by default, which should tell you something. 

Further, in Nano Server, _logging onto the console isn't even an option_, whether you use Remote Desktop or not. There _is_ no local login. Remoting _is literally your only option_ for managing the server. That's going to be the case going forward.

Running a Windows environment without enabling Remoting - at least on servers - is like driving a car without wanting to depress the accelerator. It isn't much fun, and you aren't going to get very far.
