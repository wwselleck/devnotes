# Home Networking
tl;dr Just read smallnetbuilder
## Hardware
### Routers
- 📝 [How To Buy A Wireless Router - 2018 Edition](https://www.smallnetbuilder.com/basics/wireless-basics/33177-how-to-buy-a-wireless-router-2018-edition?limitstart=0)
- Connected to wherever the internet source in the house is
- Consumer-grade routers usually have an access point built in, so the router does the router stuff and also the wifi-network stuff
- \# of Streams more important than class (AC-xxxx)
### Access Point
- Behind the router, connected to an ethernet port on the router to provide another access point for wifi connections
- Going to be the best bet for providing wifi to areas of a house that aren't near the main AP (usually the router)
### Powerline
- 📝 https://thewirecutter.com/reviews/best-powerline-networking-kit/
- If you can't do ethernet, powerline is probably the next best thing. You get two plugs, one for router -> powerline adapter -> wall, and one for wall->computer (or AP?).
- Varies widely with different adapters, the quality of the house's wiring, and different outlets
### Wireless Repeaters
- Connect via wifi to an AP, "extending" the range of the wifi
- Usually garbage, usually don't even bother.
- One non-garbage use case are wifi extenders that have an ethernet port, so you can just use it as a wifi->ethernet device for use with devices that don't have wifi (built PCs)
### Mesh
- More or less, just fancy wifi repeaters that work better together and allow a more seamless transition when you move around the house.
- Better than just throwing a wifi repeater somewhere, but not as good as having ethernet backed APs
- Sept 2018 - Orbi seems to be the best, eero second at a higher price.
- 📝 https://thewirecutter.com/reviews/best-wi-fi-mesh-networking-kits/

## DHCP
- When a new computer connects on the network, it needs a local IP address. A DHCP server (usually a part of the router) assigns IPs to devices (192.168.1.xxx or similar depending on the IP range)

## NAT
- Short for network address translation, translates public IPs to local IPs to properly route requests
