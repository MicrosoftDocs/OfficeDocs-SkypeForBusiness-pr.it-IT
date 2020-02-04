---
title: 'Lync Server 2013: Gestire gli annunci durante il ripristino di emergenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc987ea579bef4e2b02c8da210efe9a707c5900
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a>Gestire gli annunci durante il ripristino di emergenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Lync Server 2013 supporta gli annunci per le chiamate a numeri non assegnati durante le interruzioni. Il ripristino della funzionalità di annuncio durante un'interruzione è facoltativo. Se si sceglie di ripristinare gli annunci durante un'interruzione, è necessario ricreare la configurazione dell'annuncio nel pool di backup. Questa sezione descrive le operazioni da eseguire se si sceglie di ripristinare gli annunci durante il ripristino di emergenza.

Questa sezione si applica agli intervalli di numeri non assegnati che usano l'applicazione annuncio. Questa sezione non si applica agli intervalli di numeri non assegnati che usano l'operatore automatico di messaggistica UNIFICAta di Exchange.

<div>

## <a name="before-an-outage"></a>Prima di un'interruzione

Indipendentemente dal fatto che si scelga di usare gli annunci durante le interruzioni, è consigliabile eseguire backup distinti di tutti i file audio personalizzati configurati per l'applicazione di annuncio. Non viene eseguito il backup degli annunci personalizzati come parte del processo di ripristino di emergenza di Lync Server. Se non si accettano backup separati dei file e i file caricati nel server o nel pool sono danneggiati, danneggiati o eliminati, i file andranno perduti.

Se non si dispone di copie di backup di file audio personalizzati e i file audio originali non sono più disponibili, è possibile trovare i file audio configurati per un'applicazione di annuncio cercando nell'archivio file del server o del pool in cui si trovavano originariamente importato i file. È possibile copiare tutti i file audio configurati per l'applicazione di annuncio dall'archivio file.

**Per copiare i file audio dall'archivio file**

1.  Nella riga di comando eseguire:
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    Ad esempio:
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    Dove X-ApplicationServer-X si riferisce all'ID servizio del server applicazioni del pool, ad esempio 1-ApplicationServer-1 ")


</div>

<div>

## <a name="during-an-outage"></a>Durante un'interruzione

Per usare l'applicazione di annuncio durante un'interruzione, è necessario ricreare la configurazione dell'annuncio nel pool di backup eseguendo le attività descritte in questa sezione.

<div>


> [!NOTE]  
> È consigliabile eseguire queste attività dopo aver eseguito il failover nel pool di backup, perché non appena si esegue il passaggio 2, il pool di backup assume la proprietà degli intervalli di numeri non assegnati.



</div>

<div>


> [!NOTE]  
> Questi passaggi non sono necessari per gli intervalli di numeri che usano un numero di telefono dell'operatore automatico di Exchange UM.



</div>

**Per ricreare la configurazione dell'annuncio nel pool di backup**

1.  Per ricreare gli annunci distribuiti nel pool principale nel pool di backup, eseguire le operazioni seguenti:
    
    1.  Importare i file audio usati nel pool principale nel pool di backup usando il cmdlet **Import-CsAnnouncementFile** e specificando il pool di backup per il parametro Parent.
    
    2.  Ricreare ogni annuncio usando il cmdlet **New-CsAnnouncement** e specificando il pool di backup per il parametro Parent.
    
    <div>
    

    > [!NOTE]  
    > Per informazioni dettagliate sull'uso di questi parametri per creare annunci nel pool di backup, vedere <A href="lync-server-2013-create-an-announcement.md">creare un annuncio in Lync Server 2013</A>.

    
    </div>

2.  Dopo che tutti gli annunci vengono ricreati nel pool di backup, reindirizza tutti gli intervalli di numeri non assegnati che usano gli annunci nel pool principale per gli annunci ricreati nel pool di backup.
    
    Per ogni intervallo di numeri non assegnati che usa un annuncio nel pool principale, eseguire le operazioni seguenti:
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a>Dopo l'interruzione

Quando il pool primario diventa disponibile, è necessario reindirizzare gli intervalli di numeri non assegnati modificati per l'interruzione di nuovo nel pool principale.

<div>


> [!NOTE]  
> Questi passaggi non sono necessari per gli intervalli di numeri che usano un numero di telefono dell'operatore automatico di Exchange UM.



</div>

**Per ripristinare gli annunci nel pool principale**

1.  Se si dovesse ricompilare il pool principale durante il ripristino, è necessario ricreare gli annunci nel pool principale importando i file audio e creando annunci, proprio come nel pool di backup, ad eccezione del fatto che si specifica il pool principale per l'elemento padre parametro. Per informazioni dettagliate, vedere "durante un'interruzione" più indietro in questo argomento.

2.  Per ogni intervallo di numeri non assegnati modificato per l'interruzione, eseguire le operazioni seguenti:
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  Facoltativamente, rimuovere gli annunci ricreati nel pool di backup. Ottenere un elenco di annunci per l'applicazione di annuncio del pool di backup. Nella riga di comando eseguire:
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    Ad esempio:
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    Nell'elenco risultante individuare gli annunci che si desidera rimuovere e copiare i GUID. Per ogni annuncio che si vuole rimuovere, eseguire:
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    Ad esempio:
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

