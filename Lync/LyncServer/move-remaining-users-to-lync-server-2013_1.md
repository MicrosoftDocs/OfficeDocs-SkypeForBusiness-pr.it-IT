---
title: Spostare gli utenti rimanenti in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81d74c9cc578909061d098d349e685817b71e4d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500173"
---
# <a name="move-remaining-users-to-lync-server-2013"></a>Spostare gli utenti rimanenti in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-26_

È possibile spostare gli utenti nella nuova distribuzione di Lync Server 2013 utilizzando il pannello di controllo di Lync Server o Lync Server Management Shell. È necessario soddisfare alcuni requisiti per garantire una transizione agevole a Lync Server 2013. Per informazioni dettagliate sui prerequisiti per il completamento delle procedure descritte in questo argomento, vedere [configure clients for Migration](configure-clients-for-migration_1.md). Per la procedura dettagliata relativa allo spostamento degli utenti, vedere [la fase 6: spostare gli utenti nel pool pilota](phase-6-move-users-to-the-pilot-pool.md).

<div>


> [!IMPORTANT]  
> Non è possibile utilizzare lo snap-in utenti e computer di Active Directory o gli strumenti di amministrazione di Microsoft Office Communications Server 2007 R2 per spostare gli utenti dall'ambiente legacy a Lync Server 2013.



</div>

<div>


> [!IMPORTANT]  
> Il cmdlet <STRONG>Move-CsLegacyUser</STRONG> richiede nomi utente ben formati e senza spazi iniziali o finali. Non è possibile spostare un account utente utilizzando il cmdlet <STRONG>Move-CsLegacyUser</STRONG> se contiene spazi iniziali o finali.



</div>

Quando si sposta un utente in un pool di Lync Server 2013, i dati dell'utente vengono spostati nel database back-end associato al nuovo pool.

<div>


> [!IMPORTANT]  
> In questi dati sono incluse le riunioni attive create dall'utente legacy. Ad esempio, se un utente legacy ha configurato una conferenza <STRONG>riunione personale</STRONG> , la conferenza sarà ancora disponibile nel nuovo pool di Lync Server 2013, dopo lo spostamento dell'utente. I dettagli per l'accesso alla riunione continueranno a essere gli stessi URL<STRONG></STRONG>e ID conferenza. L'unica differenza è che la conferenza ora è ospitata nel pool di Lync Server 2013 e non nel pool di Office Communications Server 2007 R2.



</div>

<div>


> [!NOTE]  
> Gli utenti homing su Lync Server 2013 non richiedono la distribuzione contemporanea di client aggiornati. Le nuove funzionalità saranno disponibili per gli utenti solo dopo l'aggiornamento al nuovo software client.



</div>

<div>

## <a name="post-migration-task"></a>Attività di post-migrazione

1.  Dopo aver spostato gli utenti, verificare i criteri di conferenza loro assegnati.

2.  Per garantire che le riunioni organizzate dagli utenti ospitati in Lync Server 2013 funzionino perfettamente con gli utenti federati ospitati in Office Communications Server 2007 R2, i criteri di conferenza assegnati agli utenti migrati devono consentire ai partecipanti anonimi.

3.  I criteri di conferenza che consentono ai partecipanti anonimi **consentono ai partecipanti di invitare utenti anonimi** selezionati nel pannello di controllo di Lync Server 2013 e di disporre di **AllowAnonymousParticipantsInMeetings** impostato su **true** nell'output del cmdlet **Get-CsConferencingPolicy** in Lync Server Management Shell.

4.  Per informazioni dettagliate sulla configurazione dei criteri di conferenza mediante Lync Server Management Shell, vedere [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) nella documentazione di Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

