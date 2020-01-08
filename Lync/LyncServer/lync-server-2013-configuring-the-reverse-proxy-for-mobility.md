---
title: 'Lync Server 2013: Configurazione del proxy inverso per i dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the reverse proxy for mobility
ms:assetid: 3f4a9e33-77e4-4c18-a73f-24d4bec8ea9c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690011(v=OCS.15)
ms:contentKeyID: 48183946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 657ddf0711b0a14c9ce861a0f237977c9a2369c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-reverse-proxy-for-mobility-in-lync-server-2013"></a>Configurazione del proxy inverso per i dispositivi mobili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-03-20_

Se si vuole usare l'individuazione automatica per i client di dispositivi mobili, è necessario modificare una regola esistente o crearne una nuova per il proxy inverso, indipendentemente dal fatto che vengano aggiornati gli elenchi di nomi alternativi oggetto nei certificati di proxy inverso.

Se si decide di usare HTTPS per le richieste di servizio di individuazione automatica di Lync Server 2013 e aggiornare gli elenchi di nomi alternativi oggetto nei certificati proxy inverso, è necessario assegnare il certificato pubblico aggiornato al listener SSL (Secure Sockets Layer) il proxy inverso. Per informazioni dettagliate sulle voci di nome alternativo oggetto richieste, vedere [requisiti tecnici per la mobilità in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Devi quindi modificare il listener esistente per i servizi Web esterni o creare una nuova regola di pubblicazione Web per l'URL del servizio di individuazione automatica esterna. Se non si dispone già di una regola di pubblicazione Web per l'URL dei servizi Web di Lync Server 2013 esterno per il pool di front-end, è anche necessario pubblicare una regola.

<div>


> [!NOTE]  
> La regola di pubblicazione del proxy inverso e il listener possono servire sia i servizi Web esterni che il servizio di individuazione automatica, purché il certificato assegnato al listener contenga il nome dell'oggetto e i nomi alternativi oggetto per entrambi. Per informazioni dettagliate sulla configurazione predefinita del listener Web e della regola di pubblicazione, vedere <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configurare i server proxy inversi per Lync Server 2013</A> per ulteriori dettagli.



</div>

Se si decide di usare HTTP per le richieste di servizio di individuazione automatica iniziali in modo che non sia necessario aggiornare i nomi alternativi dell'oggetto per il proxy inverso, è necessario creare o modificare una regola di pubblicazione Web per la porta 80.

Le procedure descritte in questa sezione illustrano come creare o modificare le regole di pubblicazione Web in Microsoft Forefront Threat Management Gateway 2010 per l'individuazione automatica.

<div>


> [!NOTE]  
> Queste procedure presuppongono che sia stata installata la versione standard di Forefront Threat Management Gateway (TMG) 2010. Se si usa un altro proxy inverso, le procedure sono simili, ma sarà necessario eseguirne il mapping alla documentazione relativa al prodotto di terze parti.



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Per creare una regola di pubblicazione Web per l'URL di individuazione automatica esterna

1.  Fare clic sul pulsante **Start**, scegliere **programmi**, **Microsoft Forefront TMG**e quindi fare clic su **gestione di Forefront TMG**.

2.  Nel riquadro sinistro espandere **nomeserver**, fare clic con il pulsante destro del mouse su **criteri firewall**, scegliere **nuovo**e quindi fare clic su **regola pubblicazione sito Web**.

3.  Nella pagina **Welcome to the New Web Publishing Rule** Digitare un nome visualizzato per la nuova regola di pubblicazione, ad esempio LyncDiscoveryURL.

4.  Nella pagina **selezionare l'azione di regola** selezionare **Consenti**.

5.  Nella pagina **tipo di pubblicazione** selezionare **pubblica un singolo sito Web o bilanciamento del carico**.

6.  Nella pagina **sicurezza connessione server** selezionare **Usa SSL per connettersi al server Web pubblicato o alla server farm**.

7.  Nella pagina Internal **Publishing Details** , in **nome sito interno**, digitare il nome di dominio completo (FQDN) del pool di Director, ad esempio lyncdir01. contoso. local. Se si sta creando una regola per l'URL dei servizi Web esterni nel pool Front-End, digitare l'indirizzo VIP del servizio di bilanciamento del carico hardware (HLB) davanti al pool Front-end.

8.  Nella pagina **Dettagli pubblicazione interna** , in **percorso (facoltativo)**, digitare ** / ** il percorso della cartella da pubblicare e quindi selezionare **Inoltra l'intestazione host originale**.

9.  Nella pagina **Dettagli nome pubblico** eseguire le operazioni seguenti:
    
      - In **accetta richieste per**selezionare **questo nome di dominio**.
    
      - In **nome pubblico**Digitare **lyncdiscover.** \<SipDomain\> (l'URL del servizio di individuazione automatica esterna). Se si sta creando una regola per l'URL dei servizi Web esterni nel pool Front-End, digitare il nome di dominio completo per i servizi Web esterni nel pool Front-End, ad esempio lyncwebextpool01.contoso.com.
    
      - In **percorso**Digitare ** / **.

10. Nella pagina **Seleziona listener Web** , in **listener Web**, selezionare il listener SSL esistente con il certificato pubblico aggiornato.

11. Nella pagina **Delega autenticazione** selezionare **Nessuna delega, ma il client può eseguire l'autenticazione direttamente**.

12. Nella pagina **set** utenti selezionare **tutti gli utenti**.

13. Nella pagina **completamento della nuova creazione guidata regola Web Publishing** verificare che le impostazioni della regola di pubblicazione Web siano corrette e quindi fare clic su **fine**.

14. Nell'elenco Forefront TMG delle regole di pubblicazione Web fare doppio clic sulla nuova regola appena aggiunta per aprire le **Proprietà**.

15. Nella scheda **a** eseguire le operazioni seguenti:
    
      - Selezionare **Inoltra l'intestazione host originale invece di quella effettiva**.
    
      - **Le richieste di selezione sembrano provenire dal computer Forefront TMG**.

16. Nella scheda **bridging** configurare le operazioni seguenti:
    
      - Selezionare **server Web**.
    
      - Selezionare **reindirizza le richieste alla porta http**e digitare **8080** per il numero di porta.
    
      - Selezionare **reindirizza le richieste alla porta SSL**e digitare **4443** per il numero di porta.

17. Fare clic su **OK**.

18. Fare clic su **applica** nel riquadro dei dettagli per salvare le modifiche e aggiornare la configurazione.

19. Fare clic su **regola test** per verificare che la nuova regola sia configurata correttamente.

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a>Per modificare una regola di pubblicazione Web esistente per aggiungere la SAN e l'URL di individuazione automatica esterna

1.  Fare clic sul pulsante **Start**, scegliere **programmi**, **Microsoft Forefront TMG**e quindi fare clic su **gestione di Forefront TMG**.
    
    <div>
    

    > [!IMPORTANT]  
    > Si ripeterà la modifica per ogni regola di pubblicazione e listener che si ha. In genere, si tratta di una regola e di un listener per i pool Front-end e uno per i pool di direttori o di Director facoltativi, se sono stati distribuiti.

    
    </div>

2.  Nel riquadro sinistro espandere **nomeserver**, fare clic con il pulsante destro del mouse su **criteri firewall**e scegliere la regola applicabile. Nella scheda **attività** fare clic su **Modifica regola selezionata**.

3.  Nella scheda **nome pubblico** , in **questa regola si applica a**, selezionare **richieste per i siti Web seguenti**.

4.  Fare clic su **Aggiungi**, digitare il nome del nuovo sito di individuazione automatica, ad esempio "lyncdiscover.contoso.com", e quindi fare clic su **OK**.

5.  Nella scheda **listener** fare clic su **Seleziona certificato** e assegnare il nuovo certificato alle voci San di individuazione automatica aggiunte. Chiudere le proprietà listener e Publishing Web.

6.  Fare clic su **applica** nel riquadro dei dettagli per salvare le modifiche e aggiornare la configurazione.

7.  Fare clic su **regola test** per verificare che la nuova regola sia configurata correttamente.

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a>Per creare una regola di pubblicazione Web per la porta 80

1.  Fare clic sul pulsante **Start**, scegliere **programmi**, **Microsoft Forefront TMG**e quindi fare clic su **gestione di Forefront TMG**.

2.  Nel riquadro sinistro espandere **nomeserver**, fare clic con il pulsante destro del mouse su **criteri firewall**, scegliere **nuovo**e quindi fare clic su **regola pubblicazione sito Web**.

3.  Nella pagina **Welcome to the New Web Publishing Rule** Digitare un nome visualizzato per la nuova regola di pubblicazione, ad esempio Lync Autodiscover (http).

4.  Nella pagina **selezionare l'azione di regola** selezionare **Consenti**.

5.  Nella pagina **tipo di pubblicazione** selezionare **pubblica un singolo sito Web o bilanciamento del carico**.

6.  Nella pagina **sicurezza connessione server** selezionare **Usa connessioni non protette per connettersi al server Web pubblicato o alla server farm**.

7.  Nella pagina Internal **Publishing Details** , in **nome sito interno**, digitare l'indirizzo VIP del bilanciamento del carico hardware (HLB) davanti al pool Front-end.

8.  Nella pagina **Dettagli pubblicazione interna** , in **percorso (facoltativo)**, digitare ** / ** il percorso della cartella da pubblicare e quindi selezionare **Inoltra l'intestazione host originale invece di quella specificata nel campo nome sito interno**.

9.  Nella pagina **Dettagli nome pubblico** eseguire le operazioni seguenti:
    
      - In **accetta richieste per**selezionare **questo nome di dominio**.
    
      - In **nome pubblico**Digitare **lyncdiscover.** \<SipDomain\> (l'URL del servizio di individuazione automatica esterna).
    
      - In **percorso**Digitare ** / **.

10. Nella pagina **Seleziona listener** Web, in **listener Web**, selezionare un listener Web o usare la creazione guidata nuova definizione listener Web per crearne una nuova.

11. Nella pagina **Delega autenticazione** selezionare **Nessuna delega e il client non può eseguire l'autenticazione direttamente**.

12. Nella pagina **set** utenti selezionare **tutti gli utenti**.

13. Nella pagina **completamento della nuova creazione guidata regola Web Publishing** verificare che le impostazioni della regola di pubblicazione Web siano corrette e quindi fare clic su **fine**.

14. Nell'elenco Forefront TMG delle regole di pubblicazione Web fare doppio clic sulla nuova regola appena aggiunta per aprire le **Proprietà**.

15. Nella scheda **bridging** configurare le operazioni seguenti:
    
      - Selezionare **server Web**.
    
      - Selezionare **reindirizza le richieste alla porta http**e digitare **8080** per il numero di porta.
    
      - Verificare che l'opzione **Reindirizza richieste alla porta SSL** non sia selezionata.

16. Fare clic su **OK**.

17. Fare clic su **applica** nel riquadro dei dettagli per salvare le modifiche e aggiornare la configurazione.

18. Fare clic su **regola test** per verificare che la nuova regola sia configurata correttamente.

19. Verificare che l'URL del servizio di individuazione automatica esterna non sia definito in nessuna regola di pubblicazione Web.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare server proxy inversi per Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[Requisiti tecnici per i dispositivi mobili in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

