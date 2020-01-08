---
title: "Lync Server 2013: supporto per l'integrazione con Exchange e SharePoint"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c4d378337643adf79557bd4bbb649a01948de27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Supporto dell'integrazione di Exchange e SharePoint in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2017-01-18_

Lync Server 2013 e Lync 2013 possono comunicare in modo sicuro e trasparente con altre applicazioni e prodotti server, inclusi Office 2013, Exchange Server 2013, Exchange Server 2016 e SharePoint, se si integrano questi prodotti. L'integrazione di Lync Server 2013 e Office consente agli utenti di accedere in contesto alle funzionalità di messaggistica istantanea, presenza avanzata, telefonia e servizi di conferenza di Lync. Gli utenti di Office possono accedere alle funzionalità di Lync dall'interno del client di messaggistica e collaborazione di Outlook 2013 e di altre applicazioni di Office o da una pagina di SharePoint. Gli utenti possono anche visualizzare un record delle conversazioni di Lync nella cartella Cronologia conversazioni di Outlook. In caso di integrazione con Exchange 2013, Exchange 2016 o Exchange Online, Lync Server 2013 supporta anche le operazioni seguenti:

  - Archivio contatti unificato, che consente agli utenti di archiviare tutte le informazioni di contatto in Exchange o Exchange online in modo che le informazioni siano disponibili a livello globale in Lync 2013, Exchange, Outlook e Outlook Web App.

  - Cronologia delle conversazioni e cronologia delle conferenze Web archiviate nelle cartelle degli utenti di Exchange.

  - I contenuti archiviati da Lync, ad esempio messaggistica istantanea e contenuto della riunione, possono essere archiviati nello spazio di archiviazione di Exchange.

<div>


> [!NOTE]  
> Lync Server 2013 supporta l'integrazione con le versioni precedenti di Microsoft Exchange Server e SharePoint Server, ma non tutte le funzionalità sono supportate con queste versioni precedenti, come l'integrazione dello spazio di archiviazione di archiviazione con Microsoft Exchange.<BR>Se si esegue la migrazione degli utenti a Exchange 2013 o Exchange 2016, è possibile usare sia lo spazio di archiviazione di Exchange che quello di Lync Server su base provvisoria, mentre si completa la migrazione. L'uso definitivo sia dello spazio di archiviazione di Exchange che di Lync Server non è supportato.



</div>

L'integrazione di Lync Server 2013 con Exchange Server e SharePoint Server richiede l'autenticazione da server a server tra server che utilizzano Lync Server 2013, Exchange Server e SharePoint Server. Lync Server 2013 supporta il protocollo OAuth (Open Authorization) per l'autenticazione e l'autorizzazione da server a server. Per l'autenticazione da server a server locale tra due server Microsoft, non è necessario usare un server token di terze parti. Lync Server 2013, Exchange Server e SharePoint Server dispongono di un server token predefinito che può essere usato per scopi di autenticazione tra loro. Ad esempio, Lync Server 2013 può emettere e firmare un token di sicurezza da solo e usare il token per comunicare con Exchange. In questo caso, non è necessario usare un server di token di terze parti.

Lync Server 2013 supporta i due scenari di autenticazione da server a server. Questi includono la configurazione dell'autenticazione da server a server tra le operazioni seguenti:

  - Un'installazione locale di Lync Server 2013 e un'installazione locale di Exchange Server 2013, Exchange Server 2016 e/o SharePoint Server.

  - Una coppia di componenti di Office, ad esempio tra Microsoft Exchange 365 e Microsoft Lync Server 365, oppure tra Microsoft Lync Server 365 e Microsoft SharePoint 365.

<div>


> [!NOTE]  
> L'autenticazione da server a server tra un server locale e un componente di Office 365 non è supportata in questa versione di Lync Server 2013. Tra le altre cose, ciò significa che non è possibile configurare l'autenticazione da server a server tra un'installazione locale di Lync Server 2013 e Microsoft Exchange 365.



</div>

Per informazioni dettagliate sull'autenticazione da server a server, vedere [gestione dell'autenticazione da server a server (OAuth) e delle applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) nella documentazione relativa alle operazioni o alla documentazione relativa alla distribuzione.

</div>

<span> </span>

</div>

</div>

</div>

