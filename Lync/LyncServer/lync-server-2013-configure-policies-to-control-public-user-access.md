---
title: >
  Lync Server 2013: Configurare criteri per controllare l'accesso degli utenti pubblici
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
ms.openlocfilehash: b348abcce00eb57988c7aa5184c0cfb5ea302adb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a>Configurare criteri per controllare l'accesso degli utenti pubblici in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-07_

La connettività di messaggistica istantanea pubblica consente agli utenti dell'organizzazione di usare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider di servizi di messaggistica istantanea pubblici, tra cui la\!rete Windows Live di Internet Services, Yahoo e AOL. Si configurano uno o più criteri di accesso degli utenti esterni per controllare se gli utenti pubblici possono collaborare con gli utenti interni di Lync Server. La connettività di messaggistica istantanea pubblica è una caratteristica aggiunta che si basa sulla configurazione della distribuzione e degli utenti. Dipende anche dal provisioning del servizio presso il provider di messaggistica istantanea pubblica. Per informazioni su come eseguire il provisioning della distribuzione per l'uso dei provider pubblici, vedere la Guida introduttiva "Guida al provisioning della connettività per messaggistica istantanea pubblica per Microsoft Lync Server, Office Communications Server e Live Communications Server":[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di chiusura del servizio. Data di fine vita del 2014 giugno per AOL e Yahoo! è stato annunciato. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
> <LI>
> <P>Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo! Messenger. La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</P>
> <LI>
> <P>Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</P></LI></UL>



</div>

Per accedere al sito di provisioning della connettività di messaggistica istantanea pubblica di Microsoft Lync Server, usare il collegamento seguente:[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)

Per controllare l'accesso degli utenti pubblici, è possibile configurare i criteri a livello globale, sito e utente. Per informazioni dettagliate sui tipi di criteri che è possibile configurare, vedere [configurazione del supporto per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alla pianificazione. Le impostazioni dei criteri di Lync Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Lync Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza). Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.

In caso di inviti alla messaggistica istantanea, la risposta dipende dal software client. La richiesta viene accettata a meno che i mittenti esterni non siano esplicitamente bloccati da una regola configurata dall'utente, ovvero le impostazioni negli elenchi **Consenti** e **blocca** del client dell'utente. Inoltre, gli inviti di messaggistica istantanea possono essere bloccati se un utente sceglie di bloccare tutti i messaggi istantanei da utenti che non sono presenti nell'elenco **Consenti** .

<div>


> [!NOTE]  
> È possibile configurare i criteri per controllare l'accesso degli utenti pubblici, anche se non è stata abilitata la Federazione per l'organizzazione. Tuttavia, i criteri configurati sono attivi solo quando è abilitata la Federazione per l'organizzazione. Per informazioni dettagliate sull'abilitazione della Federazione, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">abilitare o disabilitare l'accesso remoto agli utenti in Lync Server 2013</A> nella documentazione relativa alla distribuzione o nella documentazione delle operazioni. Inoltre, se specifichi un criterio utente per controllare l'accesso degli utenti pubblici, il criterio si applica solo agli utenti abilitati per Lync Server e configurati per l'uso dei criteri. Per informazioni dettagliate su come specificare gli utenti pubblici che possono accedere a Lync Server, vedere <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">assegnare criteri di accesso degli utenti esterni a un utente abilitato a Lync in Lync Server 2013</A> nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.



</div>

Usare la procedura seguente per configurare un criterio per supportare l'accesso da parte di utenti di uno o più provider di messaggistica istantanea pubblici.

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Per configurare un criterio di accesso esterno per supportare l'accesso degli utenti pubblici

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **criteri di accesso esterno**.

4.  Nella pagina **criteri di accesso esterno** eseguire una delle operazioni seguenti:
    
      - Per configurare il criterio globale per supportare l'accesso degli utenti pubblici, fare clic sul criterio globale, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
      - Per creare un nuovo criterio sito, fare clic su **nuovo**e quindi su **criteri sito**. In **Seleziona un sito**fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.
    
      - Per creare un nuovo criterio utente, fare clic su **nuovo**e quindi su **criteri utente**. In **nuovi criteri di accesso esterno**, creare un nome univoco nel campo **nome** che indichi le informazioni relative ai criteri utente, ad esempio **EnablePublicUsers** , per un criterio utente che consente le comunicazioni per gli utenti pubblici.
    
      - Per modificare un criterio esistente, fare clic sul criterio appropriato elencato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  Opzionale Se si vuole aggiungere o modificare una descrizione, specificare le informazioni per il criterio in **Descrizione**.

6.  Esegui una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti pubblici al criterio, selezionare la casella di controllo **Abilita comunicazioni con gli utenti pubblici** .
    
      - Per disabilitare l'accesso degli utenti pubblici per il criterio, deselezionare la casella di controllo **Abilita comunicazioni con gli utenti pubblici** .

7.  Fare clic su **Commit**.

Per abilitare l'accesso degli utenti pubblici, devi anche abilitare il supporto per la Federazione nell'organizzazione. Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti federati in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

Se si tratta di un criterio utente, è necessario applicare il criterio anche agli utenti pubblici che si vuole poter collaborare con gli utenti pubblici. Per informazioni dettagliate, vedere [assegnazione di criteri per utente in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).

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

