---
title: "Lync Server 2013: configurare i criteri per il controllo dell'accesso degli utenti pubblici"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a967f186d924a199b007ceba8390bf968253ec72
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520413"
---
# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a>Configurazione di criteri per il controllo dell'accesso degli utenti pubblici in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-07_

La connettività di messaggistica istantanea pubblica consente agli utenti dell'organizzazione di utilizzare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider di servizi di messaggistica istantanea pubblica, tra cui la rete Windows Live di servizi Internet, Yahoo \! e AOL. È possibile configurare uno o più criteri di accesso utente esterno per controllare se gli utenti pubblici possono collaborare con gli utenti interni di Lync Server. La connettività per la messaggistica istantanea pubblica è una funzionalità aggiunta che si basa sulla configurazione della distribuzione e degli utenti. Dipende anche dal provisioning del servizio nel provider di messaggistica istantanea pubblico. Per informazioni su come eseguire il provisioning della distribuzione per l'utilizzo dei provider pubblici, vedere la guida sulla guida al provisioning della connettività per la messaggistica istantanea pubblica per Microsoft Lync Server, Office Communications Server e Live Communications Server: [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di arresto del servizio. Una data di fine vita del 2014 giugno per AOL e Yahoo! sono stati annunciati. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
> <LI>
> <P>Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo! Messaggero. La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</P>
> <LI>
> <P>Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</P></LI></UL>



</div>

Per accedere al sito di provisioning di connettività per messaggistica istantanea pubblica di Microsoft Lync Server, utilizzare il seguente collegamento: [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)

Per controllare l'accesso degli utenti pubblici, è possibile configurare i criteri a livello globale, di sito e di utente. Per informazioni dettagliate sui tipi di criteri che è possibile configurare, vedere [configurazione del supporto per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alla pianificazione. Le impostazioni criteri di Lync Server applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Lync Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.

Nel caso degli inviti di messaggistica istantanea, la risposta dipende dal software client. La richiesta viene accettata, a meno che i mittenti esterni siano esplicitamente bloccati da una regola configurata dall'utente, ovvero le impostazioni negli elenchi **Consenti** e **blocca** client dell'utente. Inoltre, gli inviti di messaggistica istantanea possono essere bloccati se un utente decide di bloccare tutti i messaggi istantanei provenienti da utenti che non sono presenti nell'elenco **Consenti** .

<div>


> [!NOTE]  
> È possibile configurare i criteri per controllare l'accesso degli utenti pubblici, anche se non è stata abilitata la Federazione per l'organizzazione. I criteri configurati, tuttavia, verranno applicati solo dopo aver abilitato la federazione per l'organizzazione. Per informazioni dettagliate sull'abilitazione della Federazione, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013</A> nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni. Inoltre, se si specifica un criterio utente per il controllo dell'accesso degli utenti pubblici, il criterio si applica solo agli utenti abilitati per Lync Server e configurati per l'utilizzo dei criteri. Per informazioni dettagliate sulla specifica degli utenti pubblici che possono accedere a Lync Server, vedere <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">assegnare un criterio di accesso utente esterno a un utente abilitato per Lync in Lync server 2013</A> nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.



</div>

Utilizzare la procedura seguente per configurare un criterio per il supporto dell'accesso da parte di utenti di uno o più provider di messaggistica istantanea pubblica.

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Per configurare un criterio di accesso esterno per il supporto dell'accesso degli utenti pubblici

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.

4.  Nella pagina **Criteri di accesso esterno** eseguire una delle operazioni seguenti:
    
      - Per configurare i criteri globali per il supporto dell'accesso degli utenti pubblici, fare clic sul criterio globale, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
      - Per creare un nuovo criterio sito fare clic su **Nuovo** e quindi su **Criteri sito**. In **Seleziona un sito** fare clic sul sito appropriato nell'elenco e quindi su **OK**.
    
      - Per creare nuovi criteri utente, fare clic su **Nuovo** e quindi su **Criteri utente**. In **nuovi criteri di accesso esterno**, creare un nome univoco nel campo **nome** che indica le coperture dei criteri utente, ad esempio **EnablePublicUsers** per i criteri utente che abilitano le comunicazioni per gli utenti pubblici.
    
      - Per modificare criteri esistenti, fare clic sui criteri appropriati indicati nella tabella, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.

5.  (Facoltativo) Se si desidera aggiungere o modificare una descrizione, specificare le informazioni per i criteri in **Descrizione**.

6.  Eseguire una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti pubblici per i criteri, selezionare la casella di controllo **Abilita comunicazioni con utenti pubblici** .
    
      - Per disabilitare l'accesso degli utenti pubblici per i criteri, deselezionare la casella di controllo **Abilita comunicazioni con utenti pubblici** .

7.  Fare clic su **Commit**.

Per abilitare l'accesso degli utenti pubblici, è necessario abilitare anche il supporto della federazione nell'organizzazione. Per ulteriori informazioni, vedere [Configure policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

Se si tratta di un criterio utente, è inoltre necessario applicare il criterio agli utenti pubblici che si desidera consentire la collaborazione con gli utenti pubblici. Per informazioni dettagliate, vedere [assegnazione di criteri per utente in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare o modificare provider federati SIP pubblici in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[Gestire i provider federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

