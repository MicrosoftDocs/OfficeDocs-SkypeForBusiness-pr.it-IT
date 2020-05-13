---
title: Gestione delle impostazioni di configurazione del servizio di registrazione centralizzato
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c6e156fbae7147b650c7360394cbd0d277b937b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Gestione delle impostazioni di configurazione del servizio di registrazione centralizzato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Il servizio di registrazione centralizzato è controllato e configurato dalle impostazioni e dai parametri creati e utilizzati dal controller del servizio di registrazione centralizzato (CLSController) per inviare comandi all'agente di servizio di registrazione centralizzato del singolo computer (CLSAgent). L'agente elabora i comandi che riceve e, in caso di un comando Start, utilizza la configurazione di scenari, provider, dimensione del log, durata della traccia e flag per iniziare a raccogliere i log di traccia in base alle informazioni di configurazione fornite.

<div>


> [!IMPORTANT]
> Non tutti i cmdlet di Windows PowerShell elencati per il servizio di registrazione centralizzato sono progettati per essere utilizzati con le distribuzioni locali di Lync Server 2013. Sebbene possano sembrare utili, i cmdlet seguenti non sono stati creati per funzionare con le distribuzioni locali di Lync Server 2013: 
> <UL>
> <LI>
> <P><STRONG>Cmdlet CsClsRegion:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A> e <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</P>
> <LI>
> <P><STRONG>Cmdlet CsClsSearchTerm:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> e <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</P>
> <LI>
> <P><STRONG>Cmdlet CsClsSecurityGroup:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A> e <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</P></LI></UL>Le impostazioni definite in questi cmdlet non impediscono o causano un comportamento avverso, ma sono progettate per l'utilizzo con Microsoft 365 e non restituiscono i risultati previsti nelle distribuzioni locali. Questo non significa che non si possono utilizzare nelle distribuzioni locali, ma il loro utilizzo è descritto in un argomento più avanzato che non è incluso in questa documentazione.


</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

Negli argomenti di questa sezione vengono definite le opzioni di configurazione, i parametri e le impostazioni per il servizio di registrazione centralizzato. Informazioni su come configurare il servizio di registrazione centralizzato, su come recuperare le impostazioni di configurazione, la creazione di scenari, la gestione dei gruppi di sicurezza per il servizio di registrazione centralizzato, la ricerca e altro ancora è contenuto negli argomenti seguenti.

  - [Gestione del computer, del sito e della configurazione del servizio di registrazione centralizzata globale in Lync Server 2013](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [Configurazione dei provider per il servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [Configurazione degli scenari per il servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Cmdlet per la registrazione centralizzata in Lync Server 2013](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

