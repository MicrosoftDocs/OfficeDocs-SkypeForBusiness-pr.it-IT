---
title: 'Lync Server 2013: configurazione del proxy inverso per i dispositivi mobili'
description: 'Lync Server 2013: configurazione del proxy inverso per i dispositivi mobili.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the reverse proxy for mobility
ms:assetid: 3f4a9e33-77e4-4c18-a73f-24d4bec8ea9c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690011(v=OCS.15)
ms:contentKeyID: 48183946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4e1a71f97bc1737299d54cc0f4c56f0f5981bef
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544182"
---
# <a name="configuring-the-reverse-proxy-for-mobility-in-lync-server-2013"></a>Configurazione del proxy inverso per i dispositivi mobili in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-03-20_

Se si desidera utilizzare l'individuazione automatica per i client dispositivo mobile, è necessario creare una nuova regola di pubblicazione Web o modificarne una esistente per il proxy inverso a seconda che si aggiornino o meno gli elenchi di nomi alternativi del soggetto nei certificati di proxy inverso.

Se si decide di utilizzare HTTPS per le richieste iniziali del servizio di individuazione automatica di Lync Server 2013 e si aggiornano gli elenchi dei nomi alternativi del soggetto nei certificati del proxy inverso, è necessario assegnare il certificato pubblico aggiornato al listener SSL (Secure Sockets Layer) sul proxy inverso. Per informazioni dettagliate sulle voci dei nomi alternativi del soggetto richieste, vedere [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Sarà quindi necessario modificare il listener esistente per i servizi Web esterni o creare una nuova regola di pubblicazione Web per l'URL del servizio di individuazione automatica esterno. Se non è già presente una regola di pubblicazione Web per l'URL dei servizi Web di Lync Server 2013 esterno per il pool Front End, è inoltre necessario pubblicare una regola.

<div>


> [!NOTE]  
> Il listener e la regola di pubblicazione del proxy inverso possono essere utilizzati sia per i servizi Web esterni che per il servizio di individuazione automatica, purché il certificato assegnato al listener contenga il nome soggetto e i nomi alternativi del soggetto di entrambi. Per informazioni dettagliate sulla configurazione predefinita del listener Web e della regola di pubblicazione, vedere <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.



</div>

Se si decide di utilizzare HTTP per le richieste iniziali del servizio di individuazione automatica in modo da non dover aggiornare i nomi alternativi del soggetto per il proxy inverso, sarà necessario creare o modificare una regola di pubblicazione Web per la porta 80.

Nelle procedure incluse in questa sezione viene descritto come creare o modificare le regole di pubblicazione Web in Microsoft Forefront Threat Management Gateway 2010 per l'individuazione automatica.

<div>


> [!NOTE]  
> Tali procedure partono dal presupposto che sia stata installata la Standard Edition di Forefront Threat Management Gateway (TMG) 2010. Se si sta usando un altro proxy inverso, le procedure sono simili, ma devono essere associate alla documentazione del prodotto di terze parti.



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Per creare una regola di pubblicazione Web per l'URL del servizio di individuazione automatica esterno

1.  Fare clic sul pulsante **Start**, scegliere **Programmi**, **Microsoft Forefront TMG** e quindi **Forefront TMG Management**.

2.  Nel riquadro sinistro espandere **NomeServer**, fare clic con il pulsante destro del mouse su **Criterio firewall**, scegliere **Nuovo** e quindi fare clic su **Regola di pubblicazione sito Web**.

3.  Nella pagina **Nuova regola di pubblicazione Web** digitare un nome visualizzato per la nuova regola di pubblicazione, ad esempio URLIndividuazioneLync.

4.  Nella pagina **Seleziona azione regola** selezionare **Consenti**.

5.  Nella pagina **Tipo di pubblicazione** selezionare **Pubblica un singolo sito Web o un sistema di bilanciamento del carico**.

6.  Nella pagina **Protezione connessione server** selezionare **Utilizzare SSL per connettersi al server Web pubblicato o alla server farm**.

7.  In **nome sito interno**della pagina **Dettagli pubblicazione interna** Digitare il nome di dominio completo (FQDN) del pool di server Director, ad esempio lyncdir01. contoso. local. Se si sta creando una regola per l'URL dei servizi Web esterni nel pool Front End, digitare l'indirizzo VIP del servizio di bilanciamento del carico hardware (HLB) davanti al pool Front end.

8.  In **percorso (facoltativo)** nella pagina **Dettagli pubblicazione interna** Digitare **/\*** come percorso della cartella da pubblicare e quindi selezionare **Inoltra l'intestazione host originale**.

9.  Nella pagina **Dettagli nome pubblico** eseguire le operazioni seguenti:
    
      - In **Accetta richieste per** selezionare **Nome dominio**.
    
      - In **nome pubblico**Digitare **lyncdiscover.**\<sipdomain\> (l'URL del servizio di individuazione automatica esterno). Se si sta creando una regola per l'URL dei servizi Web esterni nel pool Front End, digitare il nome di dominio completo per i servizi Web esterni nel pool Front End (ad esempio, lyncwebextpool01.contoso.com).
    
      - In **percorso**Digitare **/\*** .

10. In **Listener Web** nella pagina **Scegliere Listener Web** selezionare il listener SSL esistente con il certificato pubblico aggiornato.

11. Nella pagina **Delega autenticazione** selezionare **Nessuna delega, ma il client può eseguire l'autenticazione direttamente**.

12. Nella pagina **Gruppo di utenti** selezionare **Tutti gli utenti**.

13. Nella pagina **Completamento della Creazione guidata regola di pubblicazione sul Web** verificare che le impostazioni della regola di pubblicazione Web siano corrette e quindi fare clic su **Fine**.

14. Nell'elenco delle regole di pubblicazione Web di Forefront TMG fare doppio clic sulla nuova regola appena aggiunta per aprire **Proprietà**.

15. Nella scheda **Per** eseguire le operazioni seguenti:
    
      - Selezionare **Inoltra l'intestazione host originale e non quella effettiva (nel campo Nome sito interno)**.
    
      - Selezionare **Le richieste sembrano provenire dal computer Forefront TMG**.

16. Nella scheda **Bridging** eseguire le operazioni seguenti:
    
      - Selezionare **Server Web**.
    
      - Selezionare **Reindirizza richieste alla porta HTTP** e quindi digitare **8080** come numero di porta.
    
      - Selezionare **Reindirizza richieste alla porta SSL** e digitare **4443** come numero di porta.

17. Fare clic su **OK**.

18. Nel riquadro dei dettagli fare clic su **Applica** per salvare le modifiche e aggiornare la configurazione.

19. Fare clic su **Prova regola** per verificare che la nuova regola sia configurata correttamente.

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a>Per modificare una regola di pubblicazione Web esistente e aggiungere un nome soggetto alternativo e un URL di individuazione automatica esterno

1.  Fare clic sul pulsante **Start**, scegliere **Programmi**, **Microsoft Forefront TMG** e quindi **Forefront TMG Management**.
    
    <div>
    

    > [!IMPORTANT]  
    > Ripetere la modifica per ogni listener e regola di pubblicazione disponibile. In genere, si tratta di una regola e di un listener per i pool Front end e uno per i pool di amministratori o di server Director facoltativi, se sono stati distribuiti.

    
    </div>

2.  Nel riquadro sinistro espandere **NomeServer**, fare clic con il pulsante destro del mouse su **Criterio firewall** e quindi scegliere la regola applicabile. Nella scheda **Attività** fare clic su **Modifica regola selezionata**.

3.  Nella scheda **Nome pubblico**, nell'elenco **Questa regola di applica a** selezionare **Richieste per i seguenti siti Web**.

4.  Fare clic su **Aggiungi**, digitare il nome del nuovo sito di individuazione automatica (ad esempio lyncdiscover.contoso.com) e quindi fare clic su **OK**.

5.  Nella scheda **Listener** fare clic su **Seleziona certificato** e assegnare il nuovo certificato con le voci SAN di individuazione automatica aggiunte. Chiudere le proprietà del listener e di pubblicazione Web.

6.  Fare clic su **Applica** nel riquadro dei dettagli per salvare le modifiche e aggiornare la configurazione.

7.  Fare clic su **Prova regola** per verificare che la nuova regola sia configurata correttamente.

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a>Per creare una regola di pubblicazione Web per la porta 80

1.  Fare clic sul pulsante **Start**, scegliere **Programmi**, **Microsoft Forefront TMG** e quindi fare clic su **Forefront TMG Management**.

2.  Nel riquadro sinistro espandere **NomeServer**, fare clic con il pulsante destro del mouse su **Criterio firewall**, scegliere **Nuovo** e quindi fare clic su **Regola di pubblicazione sito Web**.

3.  Nella pagina **Nuova regola di pubblicazione Web** digitare un nome visualizzato per la nuova regola di pubblicazione, ad esempio Individuazione automatica Lync (HTTP).

4.  Nella pagina **Seleziona azione regola** selezionare **Consenti**.

5.  Nella pagina **Tipo di pubblicazione** selezionare **Pubblica un singolo sito Web o un sistema di bilanciamento del carico**.

6.  Nella pagina **Protezione connessione server** selezionare **Utilizzare connessioni non protette per connettersi al server Web pubblicato o alla server farm**.

7.  Nella pagina **Dettagli pubblicazione interna** , in **nome sito interno**, digitare l'indirizzo VIP del dispositivo di bilanciamento del carico hardware (HLB) di fronte al pool Front end.

8.  In **percorso (facoltativo)** nella pagina **Dettagli pubblicazione interna** Digitare **/\*** come percorso della cartella da pubblicare e quindi selezionare **Inoltra l'intestazione host originale invece di quella specificata nel campo nome sito interno**.

9.  Nella pagina **Dettagli nome pubblico** eseguire le operazioni seguenti:
    
      - In **Accetta richieste per** selezionare **Nome dominio**.
    
      - In **nome pubblico**Digitare **lyncdiscover.**\<sipdomain\> (l'URL del servizio di individuazione automatica esterno).
    
      - In **percorso**Digitare **/\*** .

10. In **Listener Web** nella pagina **Scegliere Listener Web** selezionare un listener Web oppure utilizzare la Creazione guidata definizione listener Web per crearne uno nuovo.

11. Nella pagina **Delega autenticazione** selezionare **Nessuna delega, ma il client può eseguire l'autenticazione direttamente**.

12. Nella pagina **Gruppo di utenti** selezionare **Tutti gli utenti**.

13. Nella pagina **Completamento della Creazione guidata regola di pubblicazione sul Web** verificare che le impostazioni della regola di pubblicazione Web siano corrette e quindi fare clic su **Fine**.

14. Nell'elenco delle regole di pubblicazione Web di Forefront TMG fare doppio clic sulla nuova regola appena aggiunta per aprire **Proprietà**.

15. Nella scheda **Bridging** eseguire le operazioni seguenti:
    
      - Selezionare **Server Web**.
    
      - Selezionare **Reindirizza richieste alla porta HTTP** e digitare **8080** come numero di porta.
    
      - Verificare che l'opzione **Reindirizza richieste alla porta SSL** non sia selezionata.

16. Fare clic su **OK**.

17. Nel riquadro dei dettagli fare clic su **Applica** per salvare le modifiche e aggiornare la configurazione.

18. Fare clic su **Prova regola** per verificare che la nuova regola sia configurata correttamente.

19. Verificare che l'URL del servizio di individuazione automatica esterno non sia definito in altre regole di pubblicazione Web.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione dei server proxy inversi per Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[Requisiti tecnici per i dispositivi mobili in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

