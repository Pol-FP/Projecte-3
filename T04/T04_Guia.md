# 🧭 **Serveis de Directori: LDAP**

📅 **Data:** 13/11/2025  
👤 **Autor:** Pol Castaño Meneses


#### 

## **1. Requeriments d'Infraestructura Inicial**

- Començarem actualitzant el nostre Ubuntu Server.  
![Captura1](img/1.png)
- Ara utilitzarem `sudo nano /etc/hosts`  
![Captura2](img/2.png)
- Canviarem el nom de la màquina i li posarem un domini.  
![Captura3](img/3.png)
- Comprovarem que el nom hagi sigut canviat amb:  
  `hostname -f`  
![Captura4](img/4.png)  
- Ara posarem dues interfícies de xarxa: una en **NAT** i l’altra en **adaptador només l’amfitrió**.  
![Captura5](img/5.png)
![Captura6](img/6.png)
- Configurarem l’adaptador de xarxa i posarem el segon adaptador amb **dhcp4**.  
![Captura7](img/7.png)
![Captura8](img/8.png)
- Ara aplicarem els canvis als adaptadors amb:  
  `sudo netplan apply`  
![Captura9](img/9.png)

## **2. Instal·lació i Configuració Base d'OpenLDAP**

- Ara instal·larem OpenLDAP amb la següent comanda:  
  `sudo apt install slapd ldap-utils -y`  
![Captura10](img/10.png)
- Un cop instal·lat, ens sortirà per posar-li una contrasenya per a l’administrador del directori LDAP.  
![Captura11](img/11.png)
![Captura12](img/12.png)
- Un cop finalitzada aquesta petita configuració, comprovarem amb: `systemctl status slapd` si s’ha instal·lat correctament.  
![Captura13](img/13.png)
- Ara, per veure si està ben configurat, utilitzarem: `sudo slapcat` amb el qual podrem observar el domini configurat.  
![Captura14](img/14.png)
- **EN CAS** que tinguem alguna cosa malament (com el nostre domini) o haguem posat una contrasenya que no volem, o si la volem canviar, utilitzarem:  
  `sudo dpkg-reconfigure slapd`  
![Captura15](img/15.png)
![Captura16](img/16.png)
![Captura17](img/17.png)
![Captura18](img/18.png)
![Captura19](img/19.png)
![Captura20](img/20.png)
![Captura21](img/21.png)
![Captura22](img/22.png)
- Ara crearem un fitxer `.ldif` per a la configuració dels nostres OUs amb:  
  `sudo nano nom_fitxer.ldif`   
![Captura23](img/23.png)
- Ara començarem a escriure el nostre fitxer de configuració amb el qual crearem les següents OUs dins del nostre directori LDAP.  
![Captura24](img/24.png)
- Per afegir aquestes OUs dins del nostre directori LDAP utilitzarem la comanda:  
  `ldapadd -D “cn=admin,dc=innovatech06,dc=test” -W -f innovatech06.ldif`   
  (el que posa a `dc=` depèn del nostre domini)  
![Captura25](img/25.png)
- Per buscar les OUs que hem creat dins del nostre directori LDAP utilitzarem:  
  `ldapsearch -xLLL -b “dc=innovatech06,dc=test”`  
![Captura26](img/26.png)

## **3. Gestió i Administració (LAM)**

- Instal·larem el gestor d’usuaris LDAP (LAM) amb:  
  `sudo apt install ldap-account-manager -y`  
![Captura27](img/27.png) 
- Obrirem una finestra al navegador que preferim i posarem la nostra IP de la interfície **Host-Only** amb un `/lam`. S’obrirà el panell gràfic.
![Captura28](img/28.png)
- Dins d’aquest panell gràfic, anirem a la part superior dreta a **LAM configuration**.  
![Captura29](img/29.png)
- Un cop aquí, seleccionarem **Edit server profiles**.  
![Captura30](img/30.png)
- Posarem les credencials per defecte:  
- **Password:** lam  
- **Profile name:** lam  
![Captura31](img/31.png)
- Anirem a **General settings** i canviarem la **list of valid users** per marcar quins usuaris poden entrar al LAM. Després, baixarem a **Tool settings** i posarem el nostre domini.  
![Captura32](img/32.png)
![Captura33](img/33.png)
- Li donem a **Account types** i posem a **LDAP suffix** el nom del nostre OU de **users** i **groups**, afegint el nostre domini.  
![Captura34](img/34.png) 
- Li donarem a **Save**.
![Captura35](img/35.png)  
- Un cop fet això, ens tornarà al login del LAM. Entrarem amb la contrasenya que vam posar al principi a l’admin de LDAP.  
![Captura36](img/36.png)
- Tindrem aquest menú de **Users**. Li donarem a **Accounts** a dalt a la dreta i anirem a **Groups**.  
![Captura37](img/37.png)
![Captura38](img/38.png)
- Dins de **Groups**, li donarem al botó blau **New group**.  
![Captura39](img/39.png)
- Li posarem el nom tech i premem el botó blau **Save**.  
![Captura40](img/40.png)
- Premem el botó groc **Create another group**.  
![Captura41](img/41.png)
- Crearem un altre grup que sigui manager.  
![Captura42](img/42.png)
![Captura43](img/43.png)
- Al menú de **Groups** podrem veure els dos grups que hem creat. Com a següent pas, li donarem a **Accounts** un altre cop i anirem a **Users**.  
![Captura44](img/44.png)
- Dins de **Users**, li donarem a **New user**.  
![Captura45](img/45.png)
- Aquí li posarem el nom al nostre usuari, en aquest cas tech01, amb el last name innovatech.  
![Captura46](img/46.png)
- Fem clic a **Unix**, on configurarem **username** i posarem com a **common name** tech01 innovatech. Com a pas addicional, activarem l’opció **create group with same name**, que ens crearà i posarà com a grup principal un nom igual que el de l’usuari.  
![Captura47](img/47.png)
- Li donarem a **Edit groups** i ens sortirà el següent menú. Això serveix per posar com a grup secundari el grup que vulguem; en aquest cas posarem `tech` com a grup secundari i li donem a **Back**.

![Captura48](img/48.png)
- Tornarem al menú i li donarem al botó groc **Set password**.  
![Captura49](img/49.png)
- Dins del següent menú podrem posar una contrasenya; en aquest cas posarem una contrasenya genèrica i activarem l’opció **Force password change**. **IMPORTANT:** activar l’opció **Unix**.  
![Captura50](img/50.png)
- Un cop fet això, li tornarem a donar a **Save** i seguirem el mateix procés per crear un usuari amb el nom manager01.  
![Captura51](img/51.png)

## **4. Integració de Client (Client Zorin Desktop)**

- Configuració de xarxa de la màquina virtual.  
![Captura52](img/52.png)
![Captura53](img/53.png)
- En un terminal a la nostra màquina Zorin editarem el nom de la nostra màquina amb:  
  `sudo nano /etc/hosts`  
![Captura54](img/54.png)
- Com no tenim servidor DNS, a part de canviar el nom també posarem la IP de la nostra màquina servidor i el seu nom.  
![Captura55](img/55.png)
- Amb `sudo nano` també editarem l’arxiu `hostname`, però només posarem el nom curt de la màquina.  
![Captura56](img/56.png)
- Comprovarem amb: `hostname -f` que el nom ha sigut assignat correctament i amb `dig server.innovatech06.test` que resol el servidor.
![Captura57](img/57.png)
- Instal·larem els mòduls necessaris per usar **libpam** i **nss** amb la comanda:  
  `apt install libnss-ldap libpam-ldap ldap-utils nscd -y`  
![Captura58](img/58.png)
- En aquest pas posarem el nom complet del nostre servidor LDAP.  
![Captura59](img/59.png)
- En aquest pas haurem de col·locar el nostre domini.  
![Captura60](img/60.png)
- Seleccionarem la versió 3 de LDAP.  
![Captura61](img/61.png)
- Escollirem les següents opcions.  
![Captura62](img/62.png) 
![Captura63](img/63.png)
- Aquí posarem l’usuari administrador del nostre directori LDAP.  
![Captura64](img/64.png)
- Escriurem la nostra contrasenya del directori LDAP.  
![Captura65](img/65.png)
- Un cop acabada aquesta configuració inicial, farem una consulta des del client per veure si connecta correctament amb el servidor amb:  
  `ldapsearch -x -D ‘cn=admin,dc=innovatech06,dc=test’ -W -H ldap://server.innovatech06.test -b ‘dc=innovatech,dc=test’ ‘objectClass=posixAccount’ uid`  
![Captura66](img/66.png)
- Ara editarem l’arxiu `nsswitch.conf` per indicar que s’utilitzarà LDAP per usuaris i grups:  
  `sudo nano /etc/nsswitch.conf`  
![Captura67](img/67.png)
- A l’arxiu `/etc/pam.d/common-password` eliminarem a la quarta línia el terme `use authtok`. Editarem l’arxiu amb:  
  `sudo nano /etc/pam.d/common-password`   
![Captura68](img/68.png)
- Ara editarem l’arxiu `/etc/pam.d/common-session` amb la comanda i haurem d’afegir la següent línia:  
  `sudo nano /etc/pam.d/common-session`  
![Captura69](img/69.png)
- A continuació reiniciarem `nscd` amb:  
  `sudo systemctl restart nscd`  
![Captura70](img/70.png)
- Comprovarem que podem veure els usuaris de LDAP des del client amb:  
  `getent passwd | tail`  
![Captura71](img/71.png) 
- Ara editarem l’arxiu indicat que permetrà l’inici de sessió gràfica; haurem d’afegir la línia marcada amb una fletxa:  
  `sudo nano /etc/pam.d/gdm-launch-environment`  
![Captura72](img/72.png)
- Ara reiniciarem la màquina client i intentarem entrar amb un usuari del directori.  
![Captura73](img/73.png)
![Captura74](img/74.png)

- Com podem veure, es crea automàticament el directori personal.  
![Captura75](img/75.png)
- Amb `id` comprovarem que estem a l’usuari indicat.  
![Captura76](img/76.png)

