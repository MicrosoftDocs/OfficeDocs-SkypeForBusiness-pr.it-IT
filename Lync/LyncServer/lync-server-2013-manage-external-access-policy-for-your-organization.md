---
title: "Lync Server 2013: gestione dei criteri di accesso esterno per l'organizzazione"
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
ms.openlocfilehash: 3a7a3d612de9cf530e512031b7009a83ad9c391c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a>Gestire i criteri di accesso esterno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-07_

Dopo la distribuzione di uno o più server perimetrali, è necessario abilitare i tipi di accesso esterno che saranno supportati per l'organizzazione.

Per impostazione predefinita, non vi sono criteri configurati per supportare l'accesso utente esterno, inclusi l'accesso utente remoto e federato, anche se il supporto dell'accesso utente esterno è già stato abilitato per l'organizzazione. Per controllare l'uso dell'accesso utente esterno, è necessario configurare uno o più criteri, specificando il tipo di accesso utente esterno supportato per ogni criterio. Per la creazione e la configurazione sono disponibili gli ambiti di criteri seguenti. Per impostazione predefinita, i criteri globali possono essere creati ma non possono essere eliminati.

  - **Criteri globali il**   criterio globale viene creato quando si distribuiscono i server perimetrali. Per impostazione predefinita, nessuna opzione di accesso utente esterno è abilitata nel criterio globale. Per supportare l'accesso degli utenti esterni a livello globale, è necessario configurare i criteri globali per il supporto di uno o più tipi di opzioni di accesso utente esterno. Il criterio globale si applica a tutti gli utenti dell'organizzazione, ma i criteri di sito e i criteri utente eseguono l'override dei criteri globali. Se si elimina il criterio globale, non è possibile rimuoverlo. Al contrario, è necessario reimpostarlo sull'impostazione predefinita.

  - **Criteri sito è**   possibile creare e configurare uno o più criteri sito per limitare il supporto per l'accesso degli utenti esterni a siti specifici. La configurazione nel criterio sito ha la priorità sul criterio globale, ma solo per il sito specifico a cui si applica il criterio sito. Se ad esempio si abilita l'accesso degli utenti remoti nel criterio globale, è possibile specificare un criterio sito che disabilita l'accesso degli utenti remoti per un sito specifico. Per impostazione predefinita, un criterio sito viene applicato a tutti gli utenti del sito, ma è possibile assegnare un criterio utente a un utente per ignorare l'impostazione del criterio sito.

  - **Criteri utente è**   possibile creare e configurare uno o più criteri utente per limitare il supporto per l'accesso utente remoto a utenti specifici. La configurazione nel criterio utente ha la priorità sui criteri globale e sito, ma solo per gli utenti specifici a cui viene assegnato il criterio utente. Se ad esempio si abilita l'accesso degli utenti remoti nei criteri globale e sito, è possibile specificare un criterio utente che disabilita l'accesso degli utenti remoti e quindi assegnare tale criterio utente a utenti specifici. Se si crea un criterio utente, è necessario applicarlo a uno o più utenti per renderlo effettivo.

<div>


> [!IMPORTANT]  
> Le impostazioni criteri di Lync Server applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Lync Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.



</div>

Queste opzioni includono i tipi di accesso esterno seguenti:

  - **Abilitare le comunicazioni con gli utenti**   federati abilitare questa operazione se si desidera supportare l'accesso degli utenti ai domini partner federati. Questa impostazione consente di configurare la possibilità per gli utenti di comunicare con altri domini federati SIP, nonché di provider ospitati come Microsoft Office 365. Se si seleziona questa opzione, è possibile selezionare l'opzione che consente la comunicazione con i domini federati XMPP.
    
    Dopo aver selezionato **Abilita comunicazioni con utenti federati** è possibile selezionare, se si vuole, **Abilita le comunicazioni con gli utenti federati XMPP**. La federazione XMPP è una federazione con organizzazioni che usano il protocollo XMPP (eXtensible Messaging and Presence Protocol).
    
    <div>
    

    > [!NOTE]  
    > Se si Abilita la Federazione XMPP, è necessario selezionare anche per distribuire la <STRONG>Federazione XMPP</STRONG> nella sezione Configurazione pool di server perimetrali del generatore di topologie. La configurazione per la Federazione XMPP distribuisce un proxy XMPP nel server perimetrale e un gateway XMPP nel front end server.

    
    </div>

  - **Abilitare le comunicazioni con gli utenti**   remoti abilitare questa opzione se si desidera che gli utenti dell'organizzazione che si trovano all'esterno del firewall, ad esempio i telecommuter e gli utenti che viaggiano, siano in grado di connettersi a Lync Server tramite Internet.

  - **Abilitare le comunicazioni con gli utenti**   pubblici abilitare questa opzione se si desidera che gli utenti interni siano in grado di comunicare con i contatti dei provider di messaggistica istantanea pubblici, ad\!esempio quelli forniti da Windows Live, Yahoo e America Online (AOL).
    
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

<div>


> [!NOTE]  
> Oltre ad abilitare il supporto dell'accesso a utenti esterni, è inoltre necessario configurare i criteri per controllare l'uso dell'accesso agli utenti esterni nell'organizzazione prima che sia disponibile qualsiasi tipo di accesso esterno per gli utenti. Per informazioni dettagliate sulla creazione, la configurazione e l'applicazione di criteri per l'accesso degli utenti esterni, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013</A>.



</div>

**Per visualizzare i criteri di accesso esterno tramite i cmdlet di Windows PowerShell**

  - È possibile visualizzare i criteri di accesso esterno utilizzando Lync Server Management Shell e il cmdlet **Get-CsExternalAccessPolicy** . È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.
    
    Per visualizzare informazioni su tutti i criteri di accesso esterno, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsExternalAccessPolicy
    
    Il comando restituisce informazioni simili a quelle riportate di seguito:
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Configurare criteri per controllare l'accesso degli utenti federati in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [Configurare criteri per controllare l'accesso utente federato XMPP in Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [Configurazione di criteri per il controllo dell'accesso degli utenti remoti in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Configurazione di criteri per il controllo dell'accesso degli utenti pubblici in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [Assegnare un criterio di accesso utente esterno a un utente abilitato per Lync in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [Reimpostazione o eliminazione di criteri di accesso utente esterno in Lync Server 2013](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

