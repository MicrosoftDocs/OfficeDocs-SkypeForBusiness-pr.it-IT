---
title: Gestione delle impostazioni di configurazione del servizio di registrazione centralizzata
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cb3b16210b3fac64c0c5bd7886849da7dd0d065
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Gestione delle impostazioni di configurazione del servizio di registrazione centralizzata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Il servizio di registrazione centralizzato viene controllato e configurato tramite le impostazioni e i parametri creati e usati dal controller del servizio di registrazione centralizzato (CLSController) per inviare comandi all'agente del servizio di registrazione centralizzato del singolo computer ( CLSAgent). L'agente elabora i comandi inviati e (nel caso di un comando Start) usa la configurazione degli scenari, i provider, le dimensioni del log, la durata della traccia e i contrassegni per iniziare a raccogliere i log di traccia in base alle informazioni di configurazione fornite.

<div>


> [!IMPORTANT]
> Non tutti i cmdlet di Windows PowerShell elencati per il servizio di registrazione centralizzata sono progettati per l'uso con le distribuzioni locali di Lync Server 2013. Anche se potrebbero sembrare utili, i cmdlet seguenti non sono progettati per funzionare con le distribuzioni locali di Lync Server 2013: 
> <UL>
> <LI>
> <P><STRONG>Cmdlet CsClsRegion:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>e <A href="https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</P>
> <LI>
> <P><STRONG>Cmdlet CsClsSearchTerm:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> e <A href="https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</P>
> <LI>
> <P><STRONG>Cmdlet CsClsSecurityGroup:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>e <A href="https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</P></LI></UL>Le impostazioni definite in questi cmdlet non impediscono o causano alcun comportamento indesiderato, ma sono progettate per l'uso con Microsoft Office 365 e non restituiscono i risultati previsti nelle distribuzioni locali. Questo non significa che non sia possibile usare questi cmdlet in distribuzioni locali, ma il loro uso è un argomento più avanzato che non è incluso in questa documentazione.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

Gli argomenti in questa sezione definiscono le opzioni di configurazione, i parametri e le impostazioni per il servizio di registrazione centralizzato. Le informazioni su come configurare il servizio di registrazione centralizzato, su come recuperare le impostazioni di configurazione, la creazione di scenari, la gestione dei gruppi di sicurezza per il servizio di registrazione centralizzato, la ricerca e altro sono contenute negli argomenti seguenti.

  - [Gestione della configurazione del servizio di registrazione centralizzata di computer, siti e globale in Lync Server 2013](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [Configurazione dei provider per il servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [Configurazione di scenari per il servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Cmdlet di registrazione centralizzati in Lync Server 2013](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

