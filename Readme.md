# Classification of HTTP/HTTPS Forward Proxy
## Classification Basis: Whether the Proxy is Transparent to the Client
- Common Proxy: Here, the proxy address and port are manually configured in the browser or system environment variables on the client. For example, when you specify the IP address and port 3128 of the Squid server on the client.
- Transparent Proxy: There is no need for the proxy settings on the client. The "proxy" role is transparent to the client. For example, a Web Gateway device on an enterprise network is a transparent proxy.

## Classification Basis: Whether the Proxy Encrypts HTTPS
- Tunnel Proxy: This is a proxy that transparently transmits traffic. The proxy server specifically transmits the HTTPS traffic over TCP transparently. It does not decrypt or perceive the specific content of its proxy traffic. The client performs direct TLS/SSL interaction with the target server. This article describes the NGINX proxy mode pertaining to this type.
- Man-in-the-Middle (MITM) Proxy: The proxy server decrypts HTTPS traffic, uses a self-signed certificate to complete the TLS/SSL handshake with the client, and completes normal TLS interaction with the target server. Two TLS/SSL sessions are set up on the client-proxy-server link.


# NGINX Solution
- HTTP CONECT Tunnel(L7 Solution, Common Proxy, Tunnel Proxy)
- NGINX Stream(L4 Solution, Transparent Proxy, Tunnel Proxy)
