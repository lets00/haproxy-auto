# HAproxy-auto

Configuração de um cenário de HA entre loadbalancers e serviços.

## Cenário de teste

[Link](https://drive.google.com/file/d/1xnbv2z_nI4R5Fh1MX_sGd9gU0LHK9eAb/view?usp=sharing)

* 3 infraestruturas para o load-balancer (HAProxy)
* 3 infraestruturas para o serviço HTTP (Ngnix)

Load-balancer configurado com keepalived para prover HA.

### Redes
* lxcbr0 - 10.0.3.0/24
* br-private: 192.168.100.0/24

**HAProxy1 (primary)**
interfaces:
eth0: 10.0.3.101/24
eth0.1: 10.0.3.254/24 (VIP)
eth1: 192.168.100.101/24

**HAProxy2 (standby)**
interfaces:
eth0: 10.0.3.102/24
eth1: 192.168.100.102/24

**HAProxy3 (standby)**
interfaces:
eth0: 10.0.3.103/24
eth1: 192.168.100.103/24

**Ngnix1**
interfaces:
eth0: 192.168.100.11/24

**Ngnix2**
interfaces:
eth0: 192.168.100.12/24

**Ngnix3**
interfaces:
eth0: 192.168.100.13/24

