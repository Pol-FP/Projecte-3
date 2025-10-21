

#### 

**Index**

[**1\. Onigrama	2**](#introducció.)

1. # **Introducció.** {#introducció.}

A totes les persones ens importa la proteccio de les nostres dades i el principal metode per protegir aquesta informacio és amb contrasenya, el 81% de filtracions de dades pasen degut a contrasenye debils o reutilitzades principalment per la facilitat de trobar aquestes amb un atac de diccionari o metodes relacionats de brute force.  
La importancia de un gestor de contrasenyes es crucial per protegir contrasenyes degut a la seva efectivitat de mitigar posibilitats de que la teva contrasenya sigui robada

2. # **Avantatges i Inconvenients** 

| Característica | Bitwarden | KeePassXC |
| :---- | :---- | :---- |
| **Tipus de solució** | Gestió de contrasenyes en el núvol amb sincronització automàtica. | Gestió de contrasenyes local amb emmagatzematge en arxiu `.kdbx`. |
| **Sincronització** | Automàtica entre dispositius a través del núvol o servidor propi. | Manual mitjançant serveis de núvol com Dropbox o Google Drive. |
| **Model de seguretat** | Xifratge AES-256 amb PBKDF2 SHA-256/Argon2id; xifratge de coneixement nul (zero-knowledge). | Xifratge AES-256; emmagatzematge local sense dependència del núvol. |
| **Accés des de múltiples dispositius** | Aplicacions natives per a Windows, macOS, Linux, iOS i Android; extensions de navegador. | Aplicacions per a Windows, macOS i Linux; accés manual mitjançant arxiu `.kdbx`. |
| **Cost / Model Freemium** | Pla gratuït amb funcionalitats bàsiques; Premium per 10 $/any amb funcionalitats avançades. | Totalment gratuït; sense plans de subscripció. |
| **Codi obert** | Sí; codi disponible a GitHub. | Sí; codi disponible a GitHub. |
| **Portabilitat de l'arxiu** | No aplicable; dades emmagatzemades al núvol. | Arxiu `.kdbx` portàtil; es pot transferir entre dispositius. |
| **Compartició de contrasenyes** | Funcionalitats de compartició per a equips i famílies. | No nativa; possible mitjançant exportació/importació manual. |
| **Suport per a TOTP** | Sí; generador de TOTP integrat. | Sí; suport per a TOTP integrat. |

3. # **Gestor en línia vs Local**

## Seguretat

**Gestors en línia:**  
**Avantatges:** Utilitzen xifratge robust com AES-256 i protocols com PBKDF2 o Argon2id. Permeten accés segur des de múltiples dispositius amb sincronització automàtica i faciliten la recuperació de compte en cas de pèrdua d’un dispositiu.  
**Inconvenients:** Hi ha un risc potencial associat a bretxes de seguretat en els servidors dels proveïdors. També depenen completament de la seguretat i integritat del servei.

**Gestors locals:**  
**Avantatges:** L’usuari té control total sobre les seves dades, que es guarden localment sense necessitat d’un servidor extern. Això redueix el risc d’atacs externs al núvol.  
**Inconvenients:** Hi ha un risc de pèrdua de dades si el dispositiu falla o es perd, i es requereix fer còpies de seguretat de forma manual i constant.

## Usabilitat

**Gestors en línia:**  
**Avantatges:** Faciliten l’accés des de qualsevol dispositiu amb connexió a Internet. La sincronització és automàtica, la qual cosa aporta comoditat i estalvia temps. També permeten recuperar contrasenyes fàcilment si s’obliden.  
**Inconvenients:** Depenen de la connexió a Internet i poden tenir problemes d’accessibilitat si el servei cau o està fora de línia.

**Gestors locals:**  
**Avantatges:** Permeten accedir a les contrasenyes de manera immediata sense necessitat d’Internet. L’usuari té control complet sobre les dades.  
**Inconvenients:** La sincronització entre dispositius és manual, cosa que pot resultar complexa o incomoda per a alguns usuaris, sobretot els menys tècnics.

## Continuïtat del negoci

**Gestors en línia:**  
**Avantatges:** Són fàcilment escalables en entorns empresarials. El manteniment i les actualitzacions són gestionats pel proveïdor, i permeten accés remot als treballadors en entorns híbrids o distribuïts.  
**Inconvenients:** Depenen de la disponibilitat del servei extern, i existeix un risc si hi ha canvis en les condicions del servei o interrupcions imprevistes.

**Gestors locals:**  
**Avantatges:** No depenen de serveis externs, oferint més control sobre les dades i processos interns.  
**Inconvenients:** Cal gestionar internament el manteniment i les actualitzacions, i poden ser menys pràctics en entorns amb treballadors remots o molts dispositius diferents.

4. # **Recomanació final**

**Recomanació: Bitwarden per al personal tècnic**

Bitwarden és la millor opció perquè ofereix:

* **Sincronització automàtica i accés des de qualsevol dispositiu**, ideal per a equips amb mobilitat.  
* **Alta seguretat** amb xifratge fort i arquitectura de coneixement nul.  
* **Codi obert i auditat**, que garanteix transparència i confiança.  
* **Funcions empresarials avançades** com integració amb SSO i compartició segura.  
* **Fàcil d’utilitzar**, cosa que millora l’eficiència del personal tècnic.

En resum, Bitwarden combina seguretat, comoditat i escalabilitat, adaptant-se millor a les necessitats d’una empresa tècnica que necessita accés segur i flexible a les seves contrasenyes.

