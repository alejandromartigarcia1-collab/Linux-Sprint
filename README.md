# Linux-Sprint

 ## 1. Promove Domain Controller
 
 We change the hostname with this command 

`sudo hostnamectl set-hostname ls12`
<img width="474" height="71" alt="imagen" src="https://github.com/user-attachments/assets/6932197e-3e60-4bac-ad15-ba54634bc41a" />

We proceed to edit this file an add the actual FQDN to the domain controller
**Command to edit files**

`sudo nano /etc/hosts` 
<img width="801" height="179" alt="imagen" src="https://github.com/user-attachments/assets/23de9c27-387b-4207-8132-0e11b7a36283" />


`ǹano /etc/netplan/00-installer-config.yaml`
<img width="800" height="329" alt="imagen" src="https://github.com/user-attachments/assets/6a502cc5-fdf7-454c-bbe3-8cf1e78978a4" />

Edit the network file
<img width="795" height="102" alt="imagen" src="https://github.com/user-attachments/assets/495f7dc0-e14f-49c1-9405-8be5337216b9" />


**Command to aplly de changes**:`sudo netplan apply`
<img width="631" height="131" alt="imagen" src="https://github.com/user-attachments/assets/e77da347-3d6d-4ac4-b232-ef60bb549406" />





<img width="798" height="341" alt="imagen" src="https://github.com/user-attachments/assets/09f7ee55-1976-4699-abee-e882b24fada9" />


<img width="623" height="53" alt="imagen" src="https://github.com/user-attachments/assets/683f6c83-ddb9-4143-b90e-cfaa1ea63084" />


<img width="382" height="20" alt="imagen" src="https://github.com/user-attachments/assets/596162ac-cb9f-49ff-94d7-e7bc392f9728" />


<img width="802" height="110" alt="imagen" src="https://github.com/user-attachments/assets/736ebab6-1fa6-430b-85e5-c3229df50664" />

<img width="407" height="28" alt="imagen" src="https://github.com/user-attachments/assets/772b9b80-3d01-4288-8f97-1aaa1ab82880" />


<img width="674" height="234" alt="imagen" src="https://github.com/user-attachments/assets/d2ea2c58-ae52-4299-82a5-d5eac2c8902e" />


<img width="797" height="40" alt="imagen" src="https://github.com/user-attachments/assets/74169420-b712-4ac3-87f7-0ebb8f2ca49d" />


<img width="766" height="222" alt="imagen" src="https://github.com/user-attachments/assets/814abeca-9769-4d4e-88b5-cb9654f418b9" />

<img width="719" height="177" alt="imagen" src="https://github.com/user-attachments/assets/10b47588-1973-4418-bb87-273d9ca4d8d5" />

<img width="721" height="180" alt="imagen" src="https://github.com/user-attachments/assets/f9cc1d19-d2c8-4180-92ca-478be067531e" />

<img width="801" height="183" alt="imagen" src="https://github.com/user-attachments/assets/a93d94f4-6e17-4ccc-8af1-0ba59aab0c09" />

<img width="802" height="126" alt="imagen" src="https://github.com/user-attachments/assets/303dc108-ff3a-42bf-a8e3-03280eb874c8" />


<img width="796" height="68" alt="imagen" src="https://github.com/user-attachments/assets/62c396aa-772e-42d2-b5ec-b89512604af5" />




<img width="578" height="39" alt="imagen" src="https://github.com/user-attachments/assets/faaa0ea9-a377-43bd-8c2c-7582223b0b7f" />


<img width="635" height="116" alt="imagen" src="https://github.com/user-attachments/assets/fc49ebbd-a635-4b78-bd18-c135e22feee5" />

<img width="515" height="28" alt="imagen" src="https://github.com/user-attachments/assets/7419dc0d-2085-4af4-ad25-f76d9b3a06cd" />


<img width="590" height="22" alt="imagen" src="https://github.com/user-attachments/assets/8e86ed15-e96c-49a4-9be7-f273cfba777e" />

We initialize the service and check its status to ensure it is functioning correctly.

<img width="425" height="43" alt="imagen" src="https://github.com/user-attachments/assets/bf81ba96-adbf-41c5-98e7-aae772bca9ca" />

<img width="805" height="578" alt="imagen" src="https://github.com/user-attachments/assets/cf3a6fef-17a1-4848-b401-f5a1131e90be" />


We changed the default permission and ownership of the /var/lib/samba/ntp_signd/ntp_signed directory for time synchronization
<img width="551" height="36" alt="imagen" src="https://github.com/user-attachments/assets/679df16d-dcf3-4dc0-a57d-f90c370f1872" />

`nano /etc/chrony/chrony.conf`
We add the following lines with the DNS IP and allow the subnet of our network
<img width="802" height="547" alt="imagen" src="https://github.com/user-attachments/assets/c45bda87-c6a5-475a-b388-c3a6e9b1752a" />

We initialize the service and check its status to ensure it is functioning correctly
<img width="403" height="44" alt="imagen" src="https://github.com/user-attachments/assets/b5083434-c798-4624-af01-14ffc8df1922" />

<img width="802" height="352" alt="imagen" src="https://github.com/user-attachments/assets/9ae21ca1-d1d7-4ce7-b330-76e6b7dfc0b1" />


Verify domain names 

`host -t A lab12.lan`

<img width="310" height="54" alt="imagen" src="https://github.com/user-attachments/assets/247487de-c970-45fb-9eba-92fb4864e103" />

`host -t A ls12.lab12.lan`

<img width="346" height="57" alt="imagen" src="https://github.com/user-attachments/assets/ea8f1764-f027-491b-8985-17e6bb6a413d" />


Verify that the Kerberos and LDAP service records point to the FQDN of our Samba Active Directory server.

`host -t SRV _kerberos._udp.lab12.lan`
<img width="515" height="38" alt="imagen" src="https://github.com/user-attachments/assets/302eea64-0d36-40fb-b392-70df9eec6fde" />

`host -t SRV _ldap._tcp.clockwork.local`

<img width="491" height="41" alt="imagen" src="https://github.com/user-attachments/assets/2d2826f8-0a65-426a-8e34-a5bebe87294e" />



Verify available resources in Active DIrectory Samba
`smbclient -L clockwork.local -N`

<img width="556" height="161" alt="imagen" src="https://github.com/user-attachments/assets/1d5e33aa-b4e7-43ef-9471-98e892ab747c" />


Verify authentication on the Kerberos server using the user manager

`kinit administrator@LAB12.LAN`

<img width="603" height="58" alt="imagen" src="https://github.com/user-attachments/assets/65c2f14b-cfbd-412e-a0db-99299a01f084" />

<img width="541" height="121" alt="imagen" src="https://github.com/user-attachments/assets/a5c53eb9-445a-4918-b86b-3d110ae71864" />



Log in to the server via SMB for checks

`sudo smbclient //localhost/netlogon -U 'administrator'`

<img width="591" height="78" alt="imagen" src="https://github.com/user-attachments/assets/e43de933-1169-4b0c-8d7e-92bc33ab8730" />

Change administrator user password

`sudo samba-tool user setpassword administrator`

<img width="710" height="40" alt="imagen" src="https://github.com/user-attachments/assets/b3070cd2-72e4-494f-bd14-5ac07cbbdc5a" />

Verify the integrity of the Samba configuration file

`testparm`

<img width="450" height="666" alt="imagen" src="https://github.com/user-attachments/assets/b18f299c-b956-4958-a56d-4489de8dbbb8" />

Verify the functionality of WINDOWS AD DC 2008

`sudo samba-tool domain level show`

<img width="500" height="107" alt="imagen" src="https://github.com/user-attachments/assets/6b95ef8c-59e5-4d96-870c-7acd9c31af06" />


## 2. Linux and Windows Client Integration

Update packages and the system

`sudo apt update` 
<img width="718" height="150" alt="imagen" src="https://github.com/user-attachments/assets/6f4f6456-baf5-4cd4-997c-9f9a413a53fa" />

`sudo apt upgrade`

<img width="1190" height="362" alt="imagen" src="https://github.com/user-attachments/assets/8a12c418-ac51-4d48-aa86-faed7b35be2c" />


We install ssh service

`sudo apt-get install ssh`

<img width="708" height="185" alt="imagen" src="https://github.com/user-attachments/assets/8745d1ea-bfbc-4469-8254-554181492278" />

Check SSH state
`sudo systemctl status ssh`

<img width="717" height="303" alt="imagen" src="https://github.com/user-attachments/assets/c11c775c-0c94-4d51-851d-04b056c48ee0" />


Change hostname
`sudo hostnamectl set-hostname lc12`
hostname -f


<img width="460" height="72" alt="imagen" src="https://github.com/user-attachments/assets/25069b5f-c4d4-47de-9ac9-8b4045a32060" />



Configure file /etc/hosts
`nano /etc/hosts`

<img width="347" height="23" alt="imagen" src="https://github.com/user-attachments/assets/3ee4ed8b-172b-4ece-8d48-652026784e09" />

<img width="716" height="243" alt="imagen" src="https://github.com/user-attachments/assets/c05ac32f-439f-407f-9eb9-3d8ac8382dce" />


We checked connectivity to the domain using the ping command
`ping lab12.lan`
<img width="663" height="152" alt="image" src="https://github.com/user-attachments/assets/845a1d93-cd53-4fb8-860e-e07a93489425" />

INSTALL ntpdate
`sudo apt-get install ntpdate`

<img width="713" height="427" alt="imagen" src="https://github.com/user-attachments/assets/7dc08504-a255-4d04-8e5c-2c6236345ab2" />

`sudo ntpdate -q lab12.lan`
`sudo ntpdate lab12.lan`


<img width="767" height="94" alt="imagen" src="https://github.com/user-attachments/assets/7d76e4a1-b8c6-4ea3-b908-e80dd6eaa96f" />

Install necessary packages

`sudo apt-get install samba krb5-config krb5-user winbind libpam-winbind libnss-winbind`

<img width="882" height="23" alt="imagen" src="https://github.com/user-attachments/assets/3c583e93-afa7-4d85-b9e2-b92c7ff5609b" />


<img width="768" height="199" alt="imagen" src="https://github.com/user-attachments/assets/b702a6f7-29b0-49a7-8575-866cc959bcf5" />


<img width="617" height="196" alt="imagen" src="https://github.com/user-attachments/assets/c52ba31b-8a79-4cc6-a450-1f96b6dba191" />


<img width="616" height="184" alt="imagen" src="https://github.com/user-attachments/assets/7c6d9a3c-66ec-4238-b29b-788c83a1c6fe" />



We verified authentication on the Kerberos server using the user manager

`kinit administrator@LAB12.LAN`
<img width="594" height="57" alt="imagen" src="https://github.com/user-attachments/assets/bbe0e8d6-a145-4305-9334-7fcaffa4f749" />

`klist`
<img width="520" height="119" alt="imagen" src="https://github.com/user-attachments/assets/0405eebe-9aeb-4fe1-9341-9ea3aec70157" />


Move the smb.conf file and create a backup
`mv /etc/samba/smb.conf /etc/samba/smb.conf.initial`

<img width="491" height="20" alt="imagen" src="https://github.com/user-attachments/assets/1e1fde2e-991e-472c-b80e-cea68e656273" />


Create an empty smb.conf file.

`nano /etc/samba/smb.conf`

<img width="422" height="17" alt="imagen" src="https://github.com/user-attachments/assets/6f795203-931c-4f2b-ac78-7b1a0f005ff3" />

We add the following lines
[global]
        workgroup = LAB12
        realm = LAB12.LAN
        netbios name = ud101
        security = ADS
        dns forwarder = 192.168.30.40

idmap config * : backend = tdb
idmap config *:range = 50000-1000000

   template homedir = /home/%D/%U
   template shell = /bin/bash
   winbind use default domain = true
   winbind offline logon = false
   winbind nss info = rfc2307
   winbind enum users = yes
   winbind enum groups = yes

  vfs objects = acl_xattr
  map acl inherit = Yes
  store dos attributes = Yes


<img width="732" height="386" alt="imagen" src="https://github.com/user-attachments/assets/a1ad0024-b608-4669-b422-be1df542a250" />

Restart all Samba daemons

`sudo systemctl restart smbd nmbd`
<img width="448" height="22" alt="imagen" src="https://github.com/user-attachments/assets/f31b2edb-98b2-4852-8404-7b7d35c33d5e" />


Stop unnecessary services

`sudo systemctl stop samba-ad-dc`
<img width="443" height="23" alt="imagen" src="https://github.com/user-attachments/assets/f3d6f5b9-de2e-4c7e-a46e-1dccca5e6ce2" />


Enable samba services

`sudo systemctl enable smbd nmbd`

<img width="789" height="115" alt="imagen" src="https://github.com/user-attachments/assets/40e8baea-f2ca-4ccf-8d62-90a8cb3c05d8" />


Join Ubuntu Desktop to SAMBA AD DC

`sudo net ads join -U administrator`
<img width="508" height="26" alt="imagen" src="https://github.com/user-attachments/assets/3b2bb6cc-2744-430e-a2d7-ccd375f9a1bc" />




List SAMBA AD teams
`sudo samba-tool computer list`

<img width="378" height="69" alt="imagen" src="https://github.com/user-attachments/assets/a01d1e3c-f5d4-4ff6-86ee-fa2bb2c84eaa" />



We verify from the client's own end whether the connection is valid
`net ads testjoin`
<img width="366" height="44" alt="imagen" src="https://github.com/user-attachments/assets/a041644d-4ec4-4a4c-8994-9337983a8d8c" />



CONFIGURE AD ACCOUNT AUTHENTICATION
Edit the Name Service Switch (NSS) configuration file.

`sudo nano /etc/nsswitch.conf`
<img width="425" height="28" alt="imagen" src="https://github.com/user-attachments/assets/b54fbe04-95e4-4777-ae2f-ee24d24b1a54" />

<img width="793" height="433" alt="imagen" src="https://github.com/user-attachments/assets/66a97ad6-0543-4690-a904-fe784cc8aa82" />


Restart winbind service

`sudo systemctl restart winbind`
<img width="433" height="19" alt="imagen" src="https://github.com/user-attachments/assets/6bd46a2c-e4e6-4c6f-9b01-5192b10c9838" />


Check if Ubuntu Desktop has been integrated into the domain.

`wbinfo -u`
`wbinfo -g`


<img width="322" height="364" alt="imagen" src="https://github.com/user-attachments/assets/c7bcc3ed-fb1e-4cea-932d-955fc72ce5eb" />



Verify the Winbind nsswitch module with the getent command.
`sudo getent passwd| grep administrator`
<img width="517" height="33" alt="imagen" src="https://github.com/user-attachments/assets/95b19adc-a219-4149-b6e1-7b84199324b3" />

`sudo getent group|grep 'domain admins'`
<img width="493" height="36" alt="imagen" src="https://github.com/user-attachments/assets/29377847-b312-491b-b851-243d74657580" />

`id administrator`

<img width="795" height="75" alt="imagen" src="https://github.com/user-attachments/assets/e54074c0-8cd9-4c56-baf7-712fb0b5cf42" />

We configured pam-auth-update to authenticate with domain accounts and to automatically create directories.

`sudo pam-auth-update`
<img width="350" height="21" alt="imagen" src="https://github.com/user-attachments/assets/af2a2bf9-b546-4041-9e0f-0dd874cf5000" />

<img width="757" height="445" alt="imagen" src="https://github.com/user-attachments/assets/9550ef33-07bc-4535-a19a-4452f580b0a6" />


Edit the /etc/pam.d/common-account file to automatically create directories.

`sudo nano /etc/pam.d/common-account`
<img width="487" height="24" alt="imagen" src="https://github.com/user-attachments/assets/d62dd0bb-be12-4df5-a74a-24218b4482de" />

Add to the end of the file.

session required pam_mkhomedir.so skel=/etc/skel/ umask=0022


<img width="786" height="532" alt="imagen" src="https://github.com/user-attachments/assets/cc293e06-9297-4a46-b06e-c7eb03e7379c" />


Log in with Samba4 AD account

`su administrator`

<img width="314" height="56" alt="imagen" src="https://github.com/user-attachments/assets/09dc6311-0fe8-4b0a-9486-51756e6f3be9" />


Authenticate with GUI

<img width="376" height="304" alt="imagen" src="https://github.com/user-attachments/assets/f93ecbd0-f72b-45df-8b78-7bd7f78fc32b" />

<img width="368" height="228" alt="imagen" src="https://github.com/user-attachments/assets/2201485a-1c2e-4724-939d-57872451b735" />


<img width="489" height="74" alt="imagen" src="https://github.com/user-attachments/assets/1405ea13-b647-4546-9346-570b5dd731b6" />


