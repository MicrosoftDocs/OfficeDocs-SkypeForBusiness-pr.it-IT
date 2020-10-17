---
title: 'Lync Server 2013: definizione dei requisiti per Front End Server, messaggistica istantanea e presenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54629a270fcba5f6237deaaa1146108e16bafef7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504333"
---
# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Definizione dei requisiti per Front End Server, messaggistica istantanea e presenza in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-07_

L'attività principale di pianificazione per la messaggistica istantanea e la presenza è garantire che i Front End Server siano sufficienti per gli utenti.

<div>

## <a name="enabling-communication-with-external-users"></a>Abilitazione delle comunicazioni con gli utenti esterni

È possibile aumentare notevolmente i vantaggi derivanti dall'investimento in Lync Server, consentendo agli utenti di comunicare con utenti esterni. Gli utenti esterni possono essere:

  - **Utenti**     remoti Gli utenti dell'organizzazione, quando lavorano all'esterno dei firewall e utilizzano i laptop o altri dispositivi di Lync Server.

  - **Utenti federati**     Utenti provenienti da società con cui si lavora, che eseguono anche Lync Server. Per consentire agli utenti di mettersi facilmente in contatto con questi utenti, si creano relazioni federate con le relative società.

  - **Utenti pubblici**     Gli utenti di servizi di messaggistica istantanea pubblica, ad esempio i servizi di messaggistica istantanea forniti dalla rete Windows Live di servizi Internet, Yahoo \! e AOL, e gli utenti di provider e server che utilizzano il protocollo XMPP (Extensible Messaging and Presence Protocol), ad esempio Google Talk.
    
    <div>
    

    > [!NOTE]  
    > Si noti che potrebbe essere necessaria una licenza separata per la connettività per messaggistica istantanea pubblica con Windows Live, AOL e Yahoo!

    
    </div>
    
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

Per abilitare uno o tutti questi scenari, è necessario distribuire un server perimetrale per consentire le comunicazioni protette tra la distribuzione di Lync Server e gli utenti esterni. Gli utenti remoti e le organizzazioni remote dell'organizzazione saranno in grado di visualizzare gli altri utenti e comunicare tramite messaggistica istantanea. Per informazioni dettagliate sull'abilitazione della comunicazione con gli utenti esterni, vedere [Planning for External User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="archiving-im-content"></a>Contenuto di messaggistica istantanea di archiviazione

Lync Server fornisce caratteristiche che è possibile utilizzare se l'organizzazione deve rispettare le normative di conformità. È possibile utilizzare l'archiviazione per archiviare il contenuto dei messaggi di messaggistica istantanea per tutti gli utenti dell'organizzazione o solo per alcuni utenti specificati. Per informazioni dettagliate, vedere [Planning for archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) nella documentazione relativa alla pianificazione.

Se si dispone anche di Microsoft Exchange Server 2013 distribuito, è possibile integrare l'archiviazione dei dati di Exchange con l'archiviazione dei dati di Lync Server e utilizzare un singolo strumento per eseguire la ricerca di entrambi i tipi di dati archiviati. Per ulteriori informazioni, vedere [configurazione di Microsoft Lync server 2013 per l'utilizzo dell'archiviazione di Microsoft Exchange server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

