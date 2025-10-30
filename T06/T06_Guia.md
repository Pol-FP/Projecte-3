####
- Per començar, tindrem dos adaptadors de xarxa: un en mode NAT i l’altre en mode adaptador pont.  
  ![imagen1](img/image1.png)  
  ![imagen2](img/image2.png)  
- Farem clic a la barra inferior i seleccionarem la fletxa.  
  ![imagen3](img/image1.png)  
- Ara farem clic a **Wired Settings**.  
  ![imagen4](img/image2.png)  
- Anirem al segon adaptador de xarxa i el configurarem.  
  !img/image5.png  
- Anirem a la pestanya **IPv4**.  
  ![imagen6](img/image3.png)  
- Seleccionarem l’opció **Manual**, configurarem l’adreça IPv4 i la màscara de xarxa, i finalment farem clic a **Apply**.  
  ![imagen7](img/image4.png)  

- **Comanda 1: Consulta Bàsica de Registre A**  
  - Executa dig xtec.cat A  
  - Anàlisi: Identifica la IP de resposta, el valor TTL i el servidor que ha respost a la consulta.  
    !img/image8.png  
    El valor TTL és 557 i el servidor que ha respost és 83.247.151.214.  
- **Comanda 2: Consulta de Servidors de Noms (NS)**  
  - Executa dig tecnocampus.cat NS  
  - Anàlisi: Quins són els servidors de noms autoritatius per a aquest domini?  
    ![imagen9](img/image5.png)  
    Els servidors autoritatius apareixen a la secció Answer Section, a partir del final, com per exemple ns-1689.awdns-19.co.uk. i els següents.  
- **Comanda 3: Consulta Detallada SOA**  
  - Executa dig escolapia.cat SOA  
  - Anàlisi: Quina és la informació del correu de l'administrador i el número de sèrie del domini?  
    ![imagen10](img/image6.png)  
- **Comanda 4: Consulta resolució inversa**  
  - Executa comanda dig \-x 147.83.2.135  
  - Anàlisi: Quina informació sobre els registres s’obté?  
    ![imagen11](img/image7.png)  
    La informació dels registres que conté són de tipus PTR, que és l’oposat al registre A: mentre que un registre A associa un nom de domini amb una adreça IP, un registre PTR associa una adreça IP amb un nom de domini. També es pot apreciar que hi ha diversos noms de domini associats a la mateixa IP.

**Comprovació de Resolució amb nslookup (Multiplataforma)**

* **Comanda 1: Consulta Bàsica no Autoritativa**  
  * Seleccionar *type=A* i com a domini de consulta tecnocampus.cat  
  * Anàlisi: Per què indica que la resposta és no autoritativa?  
    ![imagen12](img/image8.png)  
    És degut al fet que, com hem fet consultes prèvies, totes les dades ja es troben a la memòria cau, i quan es recuperen d’aquesta cache, s’indica que és una resposta no autoritativa.  
* **Comanda 2: Consultes autoritatives**  
  * Escriure *server IP* i escriure la IP del primer servidor de noms del domini tecnocampus.cat que s’ha obtingut d’una consul anterior. A continuació, indiqueu que voleu consultar registres de tipus A i del domini tecnocampus.cat  
  * Anàlisi: Quines diferències s’observen a la resposta obtinguda amb la comanda 1?  
    ![image13](img/image9.png)  
    La diferència que puc observar és que no apareix la secció de **Non-authoritative answer**, ja que estem consultant directament el servidor autoritatiu.
