# Pickle Rick - TryHackMe CTF

![CTF IMG](https://github.com/wendelfraga/writeups-and-cbsnotes/blob/main/CTFS/TryHackMe/assets/pickle-rick-ctf.jpg)

- **Descrição:** Esse é um CTF tematizado que requer que você explore um webserver para encontrar 3 ingredientes/3 flags que ajudaram Rick a ser um humano novamente!
- **Categoria:** Exploração Web.
- **Nível:** Fácil.

## Passo 1: usar o nmap para saber as portas abertas

```python
 root@kali:~/pickle-rick-ctf# nmap -A -p- 10.10.46.162 -oN nmap.log 
```
- **Resultado:**

```python
 Starting Nmap 7.80 ( https://nmap.org ) at 2022-05-17 13:58 UTC
Nmap scan report for ip-10-10-46-162.eu-west-1.compute.internal (10.10.46.162)
Host is up (0.00070s latency).
Not shown: 65533 closed ports
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.6 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey:
|   2048 8a:4b:26:41:78:2f:ca:6e:c2:b5:38:b0:d5:0c:2b:34 (RSA)
|   256 6a:2c:68:6f:d4:ef:d4:6d:10:3c:16:54:c9:f1:36:ba (ECDSA)
|_  256 ff:14:2b:52:bb:b2:a6:cc:f7:44:d3:a2:ff:da:03:96 (ED25519)
80/tcp open  http    Apache httpd 2.4.18 ((Ubuntu))
|_http-server-header: Apache/2.4.18 (Ubuntu)
|_http-title: Rick is sup4r cool
MAC Address: 02:E9:E0:DF:B2:F1 (Unknown)
Device type: general purpose
Running: Linux 3.X
OS CPE: cpe:/o:linux:linux_kernel:3
OS details: Linux 3.10 - 3.13
Network Distance: 1 hop
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE
HOP RTT     ADDRESS
1   0.70 ms ip-10-10-46-162.eu-west-1.compute.internal (10.10.46.162)

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 13.43 seconds 
```

## Passo 2: analisar o código fonte e enumerar

![CTF IMG](https://github.com/wendelfraga/writeups-and-cbsnotes/blob/main/CTFS/TryHackMe/assets/pickle-rick1-ctf.JPG)

- **Já conseguimos encontrar uma informação válida, um nome de usuário:** ``` R1ckRul3s ``` 

Podemos rodar o nmap mais uma vez, só que agora usando um script de enumeração:

```python
 root@kali:~/pickle-rick-ctf# nmap --script=http-enum 10.10.46.162
```

- **Resultado:**

```python
 Starting Nmap 7.80 ( https://nmap.org ) at 2022-05-17 14:22 UTC
Nmap scan report for ip-10-10-46-162.eu-west-1.compute.internal (10.10.46.162)
Host is up (0.0014s latency).
Not shown: 998 closed ports
PORT   STATE SERVICE
22/tcp open  ssh
80/tcp open  http
| http-enum:
|   /login.php: Possible admin folder
|_  /robots.txt: Robots file
MAC Address: 02:E9:E0:DF:B2:F1 (Unknown)

Nmap done: 1 IP address (1 host up) scanned in 0.92 seconds
```

- Acessando o caminho ***/robots.txt*** encontramos -> ```Wubbalubbadubdub```
- Acessando o caminho ***/login.php*** temos uma tela de login que exige usuário e senha
