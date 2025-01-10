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

# fIX TUN ERROR
_________________________
Verifica che il dispositivo TUN esista:
Assicurati che il dispositivo TUN esista nel tuo host. Puoi verificarlo con:

bash

ls -l /dev/net/tun

Se non esiste, puoi crearlo con:

bash

sudo mkdir -p /dev/net
sudo mknod /dev/net/tun c 10 200
sudo chmod 666 /dev/net/tun

Controlla i permessi:
Assicurati che il container abbia i permessi necessari per accedere al dispositivo TUN. Puoi farlo con il comando chmod come mostrato sopra. 

________________________
