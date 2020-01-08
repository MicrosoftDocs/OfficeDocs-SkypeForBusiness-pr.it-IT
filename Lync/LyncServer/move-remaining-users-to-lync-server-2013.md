---
title: Spostare gli utenti rimanenti in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49733689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9d5c747a216ff5407a3150eb1cdcdfb94a3c73c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a>Spostare gli utenti rimanenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-29_

È possibile trasferire gli utenti nella nuova distribuzione di Lync Server 2013 tramite il pannello di controllo di Lync Server o Lync Server Management Shell. È necessario soddisfare alcuni requisiti per garantire una transizione fluida a Lync Server 2013. Per informazioni dettagliate sui prerequisiti per completare le procedure descritte in questo argomento, vedere [configurare i client per la migrazione](configure-clients-for-migration.md). Per informazioni dettagliate sullo spostamento degli utenti, vedere [la fase 4: spostare gli utenti del test nel pool pilota](phase-4-move-test-users-to-the-pilot-pool.md).

<div>


> [!IMPORTANT]  
> Non è possibile usare lo snap-in utenti e computer di Active Directory o gli strumenti di amministrazione di Lync Server 2010 per trasferire gli utenti dall'ambiente legacy a Lync Server 2013.



</div>

Quando si sposta un utente in un pool di Lync Server 2013, i dati per l'utente vengono spostati nel database back-end associato al nuovo pool.

<div>


> [!IMPORTANT]  
> Sono incluse le riunioni attive create dall'utente legacy. Ad esempio, se un utente legacy ha configurato una conferenza <STRONG>riunioni</STRONG> , la conferenza sarà ancora disponibile nel nuovo pool di Lync Server 2013 dopo lo spostamento dell'utente. I dettagli per accedere alla riunione saranno comunque lo stesso <STRONG>URL conferenza e ID conferenza</STRONG>. L'unica differenza è che la conferenza è ora ospitata nel pool di Lync Server 2013 e non nel pool di Lync Server 2010.



</div>

<div>


> [!NOTE]  
> Gli utenti homing in Lync Server 2013 non richiedono la distribuzione simultanea dei client aggiornati. Le nuove funzionalità saranno disponibili per gli utenti solo dopo aver eseguito l'aggiornamento al nuovo software client.



</div>

<div>

## <a name="post-migration-task"></a>Attività post-migrazione

1.  Dopo aver spostato gli utenti, verificare i criteri di conferenza assegnati.

2.  Per garantire che le riunioni organizzate dagli utenti ospitate in Lync Server 2013 funzionino in modo uniforme con gli utenti federati residenti in Lync Server 2010, i criteri di conferenza assegnati agli utenti migrati dovrebbero consentire ai partecipanti anonimi.

3.  I criteri di conferenza che consentono ai partecipanti anonimi **di consentire ai partecipanti di invitare utenti anonimi** selezionati nel pannello di controllo di Lync Server 2013 e hanno **AllowAnonymousParticipantsInMeetings** impostato su **true** nell'output del cmdlet **Get-CsConferencingPolicy** in Lync Server Management Shell.

4.  Per informazioni dettagliate sulla configurazione dei criteri di conferenza tramite Lync Server Management Shell, vedere [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) nella documentazione di Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

