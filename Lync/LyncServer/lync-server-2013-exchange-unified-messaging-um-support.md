---
title: 'Lync Server 2013: supporto per la messaggistica unificata di Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e906b6194572d0ed7f797a2be64c7b66982436b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Supporto della messaggistica unificata di Exchange in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Lync Server 2013 supporta l'integrazione con la messaggistica unificata di Exchange per la combinazione di messaggi vocali e messaggi di posta elettronica in un'unica infrastruttura di messaggistica. In Exchange 2013, la messaggistica unificata di Exchange è costituita dal servizio di messaggistica unificata di Exchange, installato e eseguito nel server cassette postali, e dal router delle chiamate di messaggistica unificata, installato e eseguito sul server Accesso client. Per le distribuzioni di VoIP aziendale di Lync Server 2013, la messaggistica UNIFICAta di Exchange combina i messaggi vocali e i messaggi di posta elettronica in un singolo archivio accessibile da un telefono, ovvero Outlook Voice Access, o da un computer. La messaggistica unificata di Exchange e Lync Server 2013 interagiscono per fornire servizi di ricezione chiamata, Outlook Voice Access e operatore automatico agli utenti di VoIP aziendale.

Oltre al supporto per l'integrazione con distribuzioni locali della messaggistica unificata di Exchange, Lync Server 2013 supporta l'integrazione con la messaggistica unificata di Exchange ospitata. Questo consente di fornire la funzionalità di messaggistica vocale agli utenti di cui viene eseguita la migrazione in parte o completamente in un provider di servizi di Exchange ospitato, ad esempio Microsoft Exchange Online.

Lync Server 2013 supporta le versioni seguenti:

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (obbligatorio) o con il Service Pack più recente (scelta consigliata)

  - Microsoft Exchange Server 2007 con Service Pack 1 (SP1) (obbligatorio) o Service Pack più recente (scelta consigliata)

Non è possibile collocare la messaggistica unificata di Exchange con Lync Server 2013 o un database Lync Server 2013. È possibile installare la messaggistica unificata di Exchange e Lync Server 2013 in foreste separate.

<div>


> [!NOTE]  
> La messaggistica unificata di Exchange potrebbe non essere necessaria nelle distribuzioni di Enterprise Voice con integrazione PBX in quanto il sistema PBX può continuare a fornire a tutti gli utenti il servizio di segreteria telefonica e gli altri servizi correlati. Se il sistema PBX viene eventualmente ritirato, ad esempio se si distribuisce il trunking SIP per la connettività PSTN (Public Switched Telephone Network), è necessario riconfigurare la messaggistica unificata di Exchange per fornire alla segreteria telefonica gli utenti che in precedenza hanno utilizzato il dispositivo di segreteria telefonica PBX.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Componenti e topologie per la messaggistica unificata locale in Lync Server 2013](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Supporto per l'integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

