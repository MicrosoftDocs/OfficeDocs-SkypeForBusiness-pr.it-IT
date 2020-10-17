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
ms.openlocfilehash: 917ffc5103617c04a989ec91043a68fcce9f0320
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498523"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Integrazione di Microsoft Lync Server 2013 e Microsoft Exchange Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-07-09_

Exchange e Lync Server presentano una lunga cronologia di integrazione e compatibilità. L'integrazione è particolarmente visibile attraverso le rispettive applicazioni client. Ad esempio, le informazioni sulla presenza di Lync possono essere segnalate in Microsoft Outlook; Analogamente, Lync è in grado di utilizzare il calendario di Outlook per aggiornare automaticamente le informazioni sulla presenza. Ad esempio, Lync può modificare lo stato in occupato ogni volta che il calendario indica che è stata pianificata una riunione. Anche se non è necessario eseguire Exchange per l'esecuzione di Lync Server (o viceversa), non c'è dubbio che l'utilizzo dei due prodotti insieme incarna la definizione stessa del termine "meglio insieme".

Questo è particolarmente vero per la versione di Microsoft Lync Server 2013 e Microsoft Exchange Server 2013. Oltre alle funzionalità, ad esempio messaggistica unificata e presenza, che si trovano in Microsoft Exchange Server 2010 e Microsoft Lync Server 2010, le versioni 2013 dei prodotti server includono una serie di nuove funzionalità. Tali funzionalità includono elementi quali:

  - **Integrazione dell'archiviazione di Lync**. In Lync Server 2013 gli amministratori hanno ancora la possibilità di archiviare le trascrizioni di messaggistica istantanea e Web Conferencing in SQL Server (allo stesso modo in cui queste trascrizioni sono state archiviate in Lync Server 2010). In alternativa, tuttavia, gli amministratori possono scegliere di eseguire le trascrizioni archiviate in Exchange 2013, archiviando tali trascrizioni nelle singole cassette postali degli utenti nello stesso modo in cui Exchange archivia le comunicazioni. Questo significa che si tratta di un unico repository per tutte le comunicazioni elettroniche (sia da Exchange che Lync Server), in modo da semplificare la ricerca e il recupero delle comunicazioni archiviate in caso di necessità.

  - **Archivio unificato per i contatti**. In Lync Server 2010, gli utenti devono mantenere elenchi di contatti distinti in Outlook e Lync. Infatti, per assicurarsi di avere gli stessi contatti disponibili in entrambi i prodotti, è necessario mantenere gli elenchi di contatti duplicati, uno per Outlook e uno per Lync. Con Lync Server 2013, tuttavia, è possibile archiviare i contatti degli utenti in Exchange 2013 e nell'archivio contatti unificato. L'utilizzo di un singolo archivio contatti consente agli utenti di mantenere un solo gruppo di contatti, con lo stesso insieme di contatti disponibile in Lync 2013, Outlook 2013 e Outlook Web Access 2013.

  - **Pianificazione delle riunioni di Lync da OWA**. Con Lync Server 2013 e l'integrazione di Exchange 2013, gli utenti possono pianificare riunioni di Lync da Outlook Web Access 2013.

  - **Immagini ad alta risoluzione**. Lync 2010 è in grado di visualizzare solo foto di piccole dimensioni dei contatti; Ciò è dovuto al fatto che tali foto sono state archiviate in Active Directory e Active Directory impone un limite di 48 pixel per 48 pixel per le foto archiviate. Con Lync Server 2013, tuttavia, le foto possono essere archiviate in Microsoft Exchange. che consente di ottenere foto ad alta risoluzione di dimensioni massime di 648 pixel per 648 pixel. Come si può immaginare, Lync 2013 è stato aggiornato in modo da consentire la visualizzazione di queste fotografie ad alta risoluzione.

Tenere presente che queste nuove funzionalità richiedono l'utilizzo di Lync Server 2013 ed Exchange 2013. Inoltre, gli utenti che desiderano sfruttare al massimo queste nuove funzionalità devono disporre di account su Lync Server 2013 ed Exchange 2013 e devono utilizzare le versioni più recenti del software client (ad esempio, Lync 2013). Ad esempio, l'archivio contatti unificato non è disponibile per gli utenti che sono stati ospitati in Lync Server 2010; Analogamente, le foto ad alta risoluzione non possono essere visualizzate in Lync 2010.

In questa documentazione vengono fornite informazioni sull'integrazione di Lync Server 2013 ed Exchange 2013. e istruzioni dettagliate per l'abilitazione di nuove caratteristiche, tra cui l'integrazione dell'archiviazione e l'archivio unificato per i contatti. La documentazione non tratta della configurazione iniziale dei due prodotti. Per informazioni dettagliate sulla distribuzione di Lync Server 2013, vedere il Lync Server 2013 Tech Center all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127) . Per informazioni dettagliate sulla distribuzione di Exchange 2013, vedere Exchange 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528) .

<div>

## <a name="in-this-section"></a>Argomenti della sezione

[Prerequisiti per l'integrazione di Microsoft Lync Server 2013 e Microsoft Exchange Server 2013](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Configurazione delle applicazioni partner in Microsoft Lync Server 2013 e Microsoft Exchange Server 2013](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Configurazione di Microsoft Lync Server 2013 per l'utilizzo dell'archiviazione di Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[Configurazione di Microsoft SharePoint Server 2013 per la ricerca di dati di Microsoft Lync Server 2013 archiviati](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[Configurazione di Microsoft Lync Server 2013 per l'utilizzo dell'archivio contatti unificato](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Configurazione dell'utilizzo di foto ad alta risoluzione in Microsoft Lync Server 2013](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Configurazione della messaggistica unificata di Microsoft Exchange Server 2013 per la segreteria telefonica di Microsoft Lync Server 2013](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Integrazione di Microsoft Lync Server 2013 e Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

