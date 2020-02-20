---
title: 'Lync Server 2013: attivazione del server Office Web Apps e di Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7da09c42c296aa842cd82693a63c5ec6efc4964
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a>Configurazione dell'integrazione con Office Web Apps Server e Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-08-19_

Lync Server 2013 utilizza il server Office Web Apps per gestire le presentazioni di PowerPoint. Per informazioni sui vantaggi di questo approccio, vedere [Overview of Web Conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).

Per poter utilizzare questi nuovi amministratori delle funzionalità, è necessario installare il server Office Web Apps e configurare Lync Server 2013 per la comunicazione con il server Office Web Apps. In questa documentazione vengono fornite informazioni su come configurare Lync Server 2013 per l'utilizzo con il server Office Web Apps. La documentazione non fornita contiene informazioni su come installare il server Office Web Apps stesso. per tali informazioni, vedere il sito Web di distribuzione di Microsoft Office <https://go.microsoft.com/fwlink/p/?linkid=257525>Web Apps all'indirizzo. Tale guida include informazioni complete sui prerequisiti per il server Office Web Apps. Si noti che il server Office Web Apps deve essere installato in un computer autonomo che non esegue Lync Server, Microsoft SQL Server o qualsiasi altra applicazione server. (Non è necessario che nel computer sia installata alcuna versione di Microsoft Office). Qualsiasi computer utilizzato per eseguire il server Office Web Apps deve disporre anche di un insieme specifico di software installato (inclusi .NET Framework 4,5 e Windows PowerShell 3,0). tali requisiti, oltre alle informazioni sulla configurazione dei certificati e di Internet Information Services (IIS), vengono illustrati in dettaglio nel sito Web Microsoft Office Web <https://go.microsoft.com/fwlink/p/?linkid=257525>Apps Deployment all'indirizzo.

<div>


> [!NOTE]  
> L'ultima iterazione del server Office Web Apps è denominata Office Online Server, che è supportato da Lync Server 2013. Per ulteriori informazioni, fare riferimento alla <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">documentazione di Office Online Server</A>.



</div>

In questo documento sono riportate le aree tematiche seguenti:

  - [Configurazione di Lync Server 2013 per l'utilizzo con il server Office Web Apps](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [Pubblicazione del server Office Web Apps in Lync Server 2013 utilizzando un server proxy inverso](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [Convalidare la configurazione del server Office Web Apps in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [Configurazione dei client di Lync Server 2013 per l'utilizzo con il server Office Web Apps](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

