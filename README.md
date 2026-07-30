# Ten Four Gost Docker Service

[GOST](https://github.com/ginuerzh/gost) is a simple tunnel written in golang.

### Why is this needed?

Some game servers are CPU intensive (e.g. Arma 3, Insurgency Sandstorm), and VPS with high CPU performance are often expensive. This service is used to expose game servers running on a local machine (with a more powerful CPU) to the public internet via a VPS with the help of VPN (like Tailscale or Zerotier)

This also allows me to run Rocket League local server and expose it to the internet because Rocket League doesn't have an official runnable dedicated server, requiring you to run the whole game client to host a server. This is not ideal for a VPS, as it will consume a lot of CPU and RAM resources.

### About Insurgency Sandstorm

I'm running Insurgency Sandstorm dedicated server inside an Ubuntu VM on my Windows PC. The reason why I do this is because it seems like you have to use the Tailscale on the VPS as an exit-node for the game server to be able to be discovered on the server browser, and I don't want to set the VPS as an exit-node on my Windows (got flagged as bots on many website!). This is the reason why the IP address on `docker-compose.yml` file for the Insurgency Sandstorm server is different from the Rocket League server