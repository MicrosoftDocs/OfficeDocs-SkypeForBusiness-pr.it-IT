---
title: "Lync Server 2013: supporto per l'integrazione di Exchange e SharePoint"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4f96a5f5b1b4de3564da0dd9773a8472bd2b1a6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Supporto per l'integrazione di Exchange e SharePoint in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2017-01-18_

Lync Server 2013 e Lync 2013 sono in grado di comunicare in modo sicuro e senza problemi con altre applicazioni e prodotti server, tra cui Office 2013, Exchange Server 2013, Exchange Server 2016 e SharePoint, se si integrano questi prodotti. L'integrazione di Lync Server 2013 e Office consente agli utenti di accedere in modo contestuale alle funzionalità di messaggistica istantanea, presenza avanzata, telefonia e conferenza di Lync. Gli utenti di Office possono accedere alle funzionalità di Lync dall'interno del client di messaggistica e collaborazione di Outlook 2013 e di altre applicazioni di Office o da una pagina di SharePoint. Gli utenti possono inoltre visualizzare un record delle conversazioni di Lync nella cartella Cronologia conversazioni di Outlook. Se integrato con Exchange 2013, Exchange 2016 o Exchange Online, Lync Server 2013 supporta anche gli elementi seguenti:

  - Archivio contatti unificato, che consente agli utenti di archiviare tutte le informazioni di contatto in Exchange o Exchange online in modo che le informazioni siano disponibili a livello globale in Lync 2013, Exchange, Outlook e Outlook Web App.

  - Cronologia conversazioni e cronologia Web Conferencing, archiviata nelle cartelle degli utenti di Exchange.

  - L'archiviazione di contenuto di Lync, ad esempio il contenuto di messaggistica istantanea e riunione, può essere archiviata nell'archivio di Exchange.

<div>


> [!NOTE]  
> Lync Server 2013 supporta l'integrazione con le versioni precedenti di Microsoft Exchange Server e SharePoint Server, ma non tutte le funzionalità sono supportate con queste versioni precedenti, ad esempio l'integrazione dell'archiviazione di archiviazione con Microsoft Exchange.<BR>Se si esegue la migrazione degli utenti a Exchange 2013 o Exchange 2016, è possibile utilizzare sia l'archiviazione di Exchange che l'archiviazione di Lync Server su base provvisoria, mentre si completa la migrazione. L'utilizzo permanente sia dell'archiviazione di Exchange che di Lync Server non è supportato.



</div>

L'integrazione di Lync Server 2013 con Exchange Server e SharePoint Server richiede l'autenticazione da server a server tra i server che eseguono Lync Server 2013, Exchange Server e SharePoint Server. Lync Server 2013 supporta il protocollo OAuth (Open Authorization) per l'autenticazione e l'autorizzazione da server a server. Per l'autenticazione server-to-server locale tra due server Microsoft, non è necessario utilizzare un server token di terze parti. Lync Server 2013, Exchange Server e SharePoint Server dispongono di un server token incorporato che può essere utilizzato ai fini dell'autenticazione. Ad esempio, Lync Server 2013 può emettere e firmare un token di sicurezza e utilizzarlo per comunicare con Exchange. In questo caso, non è necessario utilizzare un server token di terze parti.

Lync Server 2013 supporta i due scenari di autenticazione da server a server. Questi includono la configurazione dell'autenticazione server-to-server tra:

  - Un'installazione locale di Lync Server 2013 e un'installazione locale di Exchange Server 2013, Exchange Server 2016 e/o SharePoint Server.

  - Una coppia di componenti di Office (ad esempio, tra Microsoft Exchange 365 e Microsoft Lync Server 365 o tra Microsoft Lync Server 365 e Microsoft SharePoint 365).

<div>


> [!NOTE]  
> L'autenticazione da server a server tra un server locale e un componente di Office 365 non è supportata in questa versione di Lync Server 2013. Tra le altre cose, ciò significa che non è possibile configurare l'autenticazione da server a server tra un'installazione locale di Lync Server 2013 e Microsoft Exchange 365.



</div>

Per informazioni dettagliate sull'autenticazione da server a server, vedere [Managing server-to-Server Authentication (OAuth) e le applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) nella documentazione relativa alla distribuzione o alla documentazione relativa alle operazioni.

</div>

<span> </span>

</div>

</div>

</div>

