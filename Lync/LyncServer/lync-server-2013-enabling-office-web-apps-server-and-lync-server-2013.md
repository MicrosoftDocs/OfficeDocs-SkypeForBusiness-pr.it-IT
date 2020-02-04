---
title: 'Lync Server 2013: Abilitazione di Office Web Apps Server e Lync Server 2013'
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
ms.openlocfilehash: 37715182ba704f71bad463044ec9b47cea8f777b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a>Configurazione dell'integrazione con Office Web Apps Server e Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-08-19_

Lync Server 2013 impiega Office Web Apps Server per gestire le presentazioni di PowerPoint. Per informazioni sui vantaggi di questo approccio, vedere [Panoramica delle conferenze Web in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).

Per usare questi nuovi amministratori delle funzionalità, è necessario installare Office Web Apps Server e configurare Lync Server 2013 per la comunicazione con Office Web Apps Server. Questa documentazione contiene informazioni su come configurare Lync Server 2013 per l'utilizzo con Office Web Apps Server. La documentazione non fornita contiene informazioni su come installare Office Web Apps Server stesso; per queste informazioni, vedere il sito Web Microsoft Office Web Apps Deployment <http://go.microsoft.com/fwlink/p/?linkid=257525>. Questa guida include informazioni complete sui prerequisiti per Office Web Apps Server; Tieni presente che il server Office Web Apps deve essere installato in un computer autonomo che non è in grado di eseguire Lync Server, Microsoft SQL Server o qualsiasi altra applicazione server. Non è necessario che nel computer sia installata una versione di Microsoft Office. Qualsiasi computer usato per eseguire Office Web Apps Server deve avere anche un set di software specifico installato (inclusi .NET Framework 4,5 e Windows PowerShell 3,0); questi requisiti, oltre a informazioni sulla configurazione di certificati e Internet Information Services (IIS), vengono descritti in dettaglio nel sito Web Microsoft Office Web Apps Deployment <http://go.microsoft.com/fwlink/p/?linkid=257525>.

<div>


> [!NOTE]  
> L'iterazione più recente di Office Web Apps Server è denominata Office Online Server, supportata da Lync Server 2013. Per altre informazioni, vedere la <A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">documentazione del server Office Online</A>.



</div>

Questo documento illustra le aree tematiche seguenti:

  - [Configurazione di Lync Server 2013 per l'utilizzo con Office Web Apps Server](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [Pubblicazione di Office Web Apps Server in Lync Server 2013 con un server proxy inverso](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [Convalida della configurazione di Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [Configurazione dei client di Lync Server 2013 per l'uso con Office Web Apps Server](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

