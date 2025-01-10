# Installare openvpn su docker


```
docker run --privileged -d --name openvpn-as --cap-add=NET_ADMIN -p 943:943 -p 8443:443 -p 1194:1194/udp -v ~/docker/openvpn-as:/openvpn openvpn/openvpn-as
```

```
# find the temporary password
docker logs openvpn-as | grep 'Auto-generated pass'
```

Open a web browser and navigate to https://DNSorIP:943/admin <br>
Login with the username openvpn and the Auto-generated password located earlier <br>
Now Active the licence <br>
Create a new account and import the profile <br>
