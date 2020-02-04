---
title: "Lync Server 2013: Gestire i criteri di accesso esterno per l'organizzazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9ade02d1c7a3eae1d65cd62ba69684129105dce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a>Gestire i criteri di accesso esterno per l'organizzazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-07_

Dopo aver distribuito uno o più server perimetrali, è necessario abilitare i tipi di accesso esterno che verranno supportati per l'organizzazione.

Per impostazione predefinita, non sono configurati criteri per supportare l'accesso degli utenti esterni, incluso l'accesso degli utenti remoti, l'accesso degli utenti federati, anche se è già stato abilitato il supporto per l'accesso degli utenti esterni per l'organizzazione. Per controllare l'uso dell'accesso degli utenti esterni, è necessario configurare uno o più criteri, specificando il tipo di accesso utente esterno supportato per ogni criterio. Gli ambiti di criteri seguenti sono disponibili per la creazione e la configurazione. Per impostazione predefinita, il criterio globale viene creato, ma non può essere eliminato.

  - **Criteri globali il**   criterio globale viene creato quando si distribuisce un server perimetrale. Per impostazione predefinita, nel criterio globale non sono abilitate le opzioni di accesso degli utenti esterni. Per supportare l'accesso degli utenti esterni a livello globale, è possibile configurare il criterio globale per supportare uno o più tipi di opzioni di accesso degli utenti esterni. Il criterio globale si applica a tutti gli utenti dell'organizzazione, ma i criteri del sito e i criteri degli utenti eseguono l'override del criterio globale. Se elimini il criterio globale, non lo Rimuovi. Puoi invece reimpostarla sull'impostazione predefinita.

  - **Criteri sito è**   possibile creare e configurare uno o più criteri del sito per limitare il supporto per l'accesso degli utenti esterni a siti specifici. La configurazione dei criteri sito ha la precedenza sui criteri globali, ma solo per il sito specifico a cui i criteri si riferiscono. Ad esempio, se si Abilita l'accesso degli utenti remoti nel criterio globale, è possibile specificare un criterio per il sito che disabilita l'accesso degli utenti remoti per un sito specifico. Per impostazione predefinita, un criterio del sito viene applicato a tutti gli utenti del sito, ma è possibile assegnare un criterio utente a un utente per ignorare l'impostazione dei criteri del sito.

  - **Criteri**   per gli utenti è possibile creare e configurare uno o più criteri utente per limitare il supporto per l'accesso degli utenti remoti a un utente specifico. La configurazione nel criterio utente sostituisce il criterio globale e del sito, ma solo per gli utenti specifici a cui è assegnato il criterio utente. Ad esempio, se si Abilita l'accesso degli utenti remoti nei criteri globali e nei criteri del sito, è possibile specificare un criterio utente che disabilita l'accesso degli utenti remoti e quindi assegnare i criteri utente a utenti specifici. Se crei un criterio utente, devi applicarlo a uno o più utenti prima che abbia effetto.

<div>


> [!IMPORTANT]  
> Le impostazioni dei criteri di Lync Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Lync Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza). Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.



</div>

Queste opzioni includono i tipi di accesso esterno seguenti:

  - **Abilitare le comunicazioni con gli utenti**   federati abilitare questa operazione se si vuole supportare l'accesso degli utenti ai domini partner federati. Questa impostazione configura la possibilità per gli utenti di comunicare con altri domini federati SIP, nonché di provider ospitati come Microsoft Office 365. Se si seleziona questa impostazione, è possibile selezionare l'opzione per consentire la comunicazione con domini federati XMPP.
    
    Come opzione, puoi selezionare **Abilita comunicazioni con partner federativi XMPP** se per la prima volta scegli **Abilita comunicazioni con gli utenti federati**. La Federazione XMPP è una federazione con organizzazioni che usano il protocollo XMPP (Extensible Messaging and Presence Protocol).
    
    <div>
    

    > [!NOTE]  
    > Se abiliti la Federazione XMPP, devi anche selezionare per distribuire la <STRONG>Federazione XMPP</STRONG> nella sezione Configurazione pool di bordi di generatore di topologia. La configurazione della Federazione XMPP distribuisce un proxy XMPP nell'Edge Server e un gateway XMPP nel server front-end.

    
    </div>

  - **Abilitare le comunicazioni con gli utenti**   remoti abilitare questa opzione se si vuole che gli utenti dell'organizzazione che si trovano all'esterno del firewall, ad esempio i telelavoratori e gli utenti che viaggiano, possano connettersi a Lync Server tramite Internet.

  - **Abilitare le comunicazioni con gli utenti**   pubblici abilitare questa opzione se si vuole che gli utenti interni possano comunicare con i contatti del provider di messaggistica istantanea pubblici, ad esempio quelli forniti\!da Windows Live, Yahoo e America Online (AOL).
    
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

<div>


> [!NOTE]  
> Oltre ad abilitare il supporto per l'accesso degli utenti esterni, devi anche configurare i criteri per controllare l'uso dell'accesso degli utenti esterni nell'organizzazione prima che qualsiasi tipo di accesso utente esterno sia disponibile per gli utenti. Per informazioni dettagliate sulla creazione, la configurazione e l'applicazione di criteri per l'accesso degli utenti esterni, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">abilitare o disabilitare l'accesso remoto agli utenti in Lync Server 2013</A>.



</div>

**Per visualizzare i criteri di accesso esterno usando i cmdlet di Windows PowerShell**

  - Per visualizzare i criteri di accesso esterno, è possibile usare Lync Server Management Shell e il cmdlet **Get-CsExternalAccessPolicy** . Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.
    
    Per visualizzare informazioni su tutti i criteri di accesso esterno, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsExternalAccessPolicy
    
    Questo comando restituisce informazioni simili a quelle seguenti:
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Configurare criteri per controllare l'accesso utente federato in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [Configurare criteri per controllare l'accesso utente federato XMPP in Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [Configurare criteri per controllare l'accesso degli utenti remoti in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Configurare criteri per controllare l'accesso degli utenti pubblici in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [Assegnare criteri di accesso per gli utenti esterni a un utente abilitato per Lync in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [Reimpostazione o eliminazione dei criteri di accesso esterno degli utenti in Lync Server 2013](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

