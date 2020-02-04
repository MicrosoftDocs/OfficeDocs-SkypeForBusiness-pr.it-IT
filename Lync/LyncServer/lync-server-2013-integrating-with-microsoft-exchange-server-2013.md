---
title: 'Lync Server 2013: integrazione con Microsoft Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1467f6a570f83908eb5809f9493303bdc91c169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Integrazione di Microsoft Lync Server 2013 e Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-07-09_

Exchange e Lync Server hanno una lunga storia di integrazione e compatibilità. Questa integrazione è più evidente all'interno della rispettiva applicazione client. Ad esempio, le informazioni sulla presenza di Lync possono essere segnalate in Microsoft Outlook; allo stesso modo, Lync può usare il calendario di Outlook per aggiornare automaticamente le informazioni sulla presenza. Ad esempio, Lync può cambiare lo stato in occupato ogni volta che il calendario mostra che è stata pianificata una riunione. Anche se non è necessario eseguire Exchange per eseguire Lync Server (o viceversa), non c'è dubbio che l'uso dei due prodotti conferisca alla stessa definizione del termine "Better Together".

Questo vale soprattutto per il rilascio di Microsoft Lync Server 2013 e Microsoft Exchange Server 2013. Oltre alle funzionalità, ad esempio messaggistica unificata e messaggi ISTANTANEi e presenza, disponibili in Microsoft Exchange Server 2010 e Microsoft Lync Server 2010, le versioni di 2013 dei prodotti server includono una serie di nuove funzionalità. Queste funzionalità includono elementi quali:

  - **Integrazione dell'archiviazione di Lync**. In Lync Server gli amministratori di 2013 hanno ancora la possibilità di archiviare le trascrizioni di messaggistica istantanea e Web Conferencing in SQL Server, allo stesso modo in cui queste trascrizioni sono state archiviate in Lync Server 2010. In alternativa, tuttavia, gli amministratori possono scegliere di archiviare le trascrizioni in Exchange 2013, archiviando tali trascrizioni nelle singole cassette postali degli utenti nello stesso modo in cui gli archivi di Exchange si scambiano le comunicazioni. Questo significa un unico repository per tutte le comunicazioni elettroniche (sia da Exchange che da Lync Server), che rende molto più semplice cercare e recuperare le comunicazioni archiviate in base alle esigenze.

  - **Archivio contatti unificato**. In Lync Server 2010 gli utenti dovevano mantenere elenchi di contatti distinti in Outlook e Lync; Infatti, per assicurarti di avere gli stessi contatti disponibili in entrambi i prodotti, hai dovuto mantenere gli elenchi di contatti duplicati, uno per Outlook e uno per Lync. Con Lync Server 2013, tuttavia, i contatti utente possono essere archiviati in Exchange 2013 e nell'archivio contatti unificato. L'uso di un singolo archivio contatti consente agli utenti di mantenere un solo set di contatti, con lo stesso set di contatti disponibile in Lync 2013, Outlook 2013 e Outlook Web Access 2013.

  - **Pianificazione delle riunioni di Lync da OWA**. Con Lync Server 2013 ed Exchange 2013 Integration, gli utenti possono pianificare le riunioni Lync da Outlook Web Access 2013.

  - **Foto ad alta risoluzione**. Lync 2010 può visualizzare solo le piccole foto dei contatti; Questo perché le foto sono state archiviate in Active Directory e Active Directory impone un pixel di 48 per la limitazione delle dimensioni di 48 pixel per le foto archiviate. Con Lync Server 2013, tuttavia, le foto possono essere archiviate in Microsoft Exchange; che consente di avere foto ad alta risoluzione grandi quanto 648 pixel per 648 pixel. Come ci si potrebbe aspettare, Lync 2013 è stato aggiornato per consentire la visualizzazione di queste fotografie ad alta risoluzione.

Tieni presente che queste nuove funzionalità richiedono l'uso di Lync Server 2013 ed Exchange 2013. Oltre a ciò, gli utenti che desiderano sfruttare pienamente queste nuove funzionalità devono avere account su Lync Server 2013 ed Exchange 2013 e devono usare le versioni più recenti del software client (ad esempio Lync 2013). Ad esempio, l'archivio contatti unificato non è disponibile per gli utenti residenti in Lync Server 2010; allo stesso modo, le foto ad alta risoluzione non possono essere visualizzate in Lync 2010.

Questa documentazione contiene informazioni su come integrare Lync Server 2013 ed Exchange 2013. includendo informazioni dettagliate sull'abilitazione di nuove funzionalità, ad esempio l'integrazione di archiviazione e l'archivio contatti unificato. Ciò che questa documentazione non fa è discutere la configurazione iniziale e le configurazioni di questi due prodotti. Per informazioni dettagliate sulla distribuzione di Lync Server 2013, vedere Lync Server 2013 Tech [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127)Center at. Per informazioni dettagliate sulla distribuzione di Exchange 2013, vedere Exchange 2013 Tech [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528)Center at.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

[Prerequisiti per l'integrazione di Microsoft Lync Server 2013 e Microsoft Exchange Server 2013](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Configurazione delle applicazioni partner in Microsoft Lync Server 2013 e Microsoft Exchange Server 2013](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Configurazione di Microsoft Lync Server 2013 per l'archiviazione di Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[Configurazione di Microsoft SharePoint Server 2013 per la ricerca di dati di Microsoft Lync Server 2013 archiviati](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[Configurazione di Microsoft Lync Server 2013 per l'uso dell'archivio contatti unificato](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Configurazione dell'uso di foto ad alta risoluzione in Microsoft Lync Server 2013](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Configurazione della messaggistica unificata di Microsoft Exchange Server 2013 per Microsoft Lync Server 2013 Voice mail](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Integrazione di Microsoft Lync Server 2013 e Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

