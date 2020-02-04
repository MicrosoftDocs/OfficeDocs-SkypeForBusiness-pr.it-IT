---
title: 'Lync Server 2013: Supporto per la messaggistica unificata di Exchange'
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
ms.openlocfilehash: 8925bd8a07693800c49ff2d818d3677b33452b97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Supporto per la messaggistica unificata di Exchange in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Lync Server 2013 supporta l'integrazione con la messaggistica UNIFICAta di Exchange per combinare la messaggistica vocale e la messaggistica di posta elettronica in un'unica infrastruttura di messaggistica. In Exchange 2013 la messaggistica unificata di Exchange è costituita dal servizio di messaggistica unificata di Exchange, installato e eseguito nel server cassette postali, e dal router della chiamata di messaggistica unificata, installato e eseguito nel server Accesso client. Per le distribuzioni di VoIP aziendale di Lync Server 2013, la messaggistica UNIFICAta di Exchange combina la messaggistica vocale e la messaggistica di posta elettronica in un singolo archivio accessibile da un telefono (ovvero Outlook Voice Access) o da un computer. La messaggistica unificata di Exchange e Lync Server 2013 collaborano per fornire servizi di segreteria telefonica, Outlook Voice Access e operatore automatico agli utenti di VoIP aziendale.

Oltre al supporto per l'integrazione con distribuzioni locali della messaggistica unificata di Exchange, Lync Server 2013 supporta l'integrazione con la messaggistica unificata di Exchange ospitata. In questo modo puoi offrire agli utenti la messaggistica vocale se Esegui la migrazione di alcuni o tutti a un provider di servizi di Exchange ospitati, ad esempio Microsoft Exchange Online.

Lync Server 2013 supporta le versioni seguenti:

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (obbligatorio) o con il Service Pack più recente (consigliato)

  - Microsoft Exchange Server 2007 con Service Pack 1 (SP1) (obbligatorio) o Service Pack più recente (consigliato)

Non è possibile collocare la messaggistica unificata di Exchange con Lync Server 2013 o un database di Lync Server 2013. È possibile installare la messaggistica unificata di Exchange e Lync Server 2013 in foreste separate.

<div>


> [!NOTE]  
> La messaggistica unificata di Exchange potrebbe non essere necessaria per le distribuzioni VoIP aziendali con un PBX distribuito, perché il PBX può continuare a prestare servizi di segreteria telefonica e correlati a tutti gli utenti. Se alla fine si ritira il PBX, ad esempio se si distribuisce il trunking SIP per la connettività PSTN (Public Switched Telephone Network), è necessario riconfigurare la messaggistica unificata di Exchange per consentire agli utenti che hanno usato in precedenza il sistema di segreteria telefonica PBX.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Componenti e topologie per la messaggistica unificata locale in Lync Server 2013](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Supporto per l'integrazione di messaggistica unificata di Exchange ospitata in Lync Server 2013](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

