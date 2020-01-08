---
title: 'Lync Server 2013: concetti relativi ai servizi di conferenza comuni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 240415ccdf8c0ab9be2eaf10304973b62c302c79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a>Concetti relativi ai servizi di conferenza comuni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-19_

Diversi concetti sono comuni a tutti i tipi di conferenza. Queste sono descritte nelle sezioni seguenti.

<div>

## <a name="policies-and-bandwidth-management"></a>Criteri e gestione della larghezza di banda

Lync Server 2013 consente agli amministratori di impostare i criteri per i tipi di riunioni che gli utenti possono organizzare. Questo consente di applicare i criteri dell'organizzazione e controllare l'utilizzo della larghezza di banda. Puoi definire una vasta gamma di criteri per le riunioni e assegnarli a singoli utenti e gruppi di utenti. È anche possibile impostare i criteri che governano le conversazioni peer-to-peer. Per informazioni dettagliate sull'impostazione dei criteri di conferenza, vedere [criteri di conferenza in Lync Server 2013](lync-server-2013-conferencing-policies.md) nella documentazione Operations. Per informazioni dettagliate sulla gestione della larghezza di banda, vedere [Panoramica del controllo dell'ammissione alle chiamate in Lync server 2013](lync-server-2013-overview-of-call-admission-control.md) e [configurazione della larghezza di banda video in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

</div>

<div>

## <a name="archiving-and-compliance-features"></a>Caratteristiche di archiviazione e conformità

Lync Server 2013 offre funzionalità che è possibile usare se l'organizzazione deve seguire le regole di conformità. È possibile usare le funzionalità di archiviazione per archiviare i contenuti presentati nelle riunioni e anche il contenuto delle conversazioni istantanee e delle conferenze di messaggistica istantanea. Per informazioni dettagliate, vedere [pianificazione dell'archiviazione in Lync Server 2013](lync-server-2013-planning-for-archiving.md) nella documentazione relativa alla pianificazione. Puoi usare le caratteristiche di conformità del server di chat persistente per archiviare le conversazioni basate su più parti, che persistono nel tempo. Per informazioni dettagliate, vedere [pianificazione del server di chat persistente in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="monitoring-feature"></a>Funzionalità di monitoraggio

La funzionalità server di monitoraggio consente di acquisire record di dettagli chiamata (CDRs), che è possibile usare per tenere traccia degli utenti che parlano con altri utenti che usano Lync Server 2013. Per informazioni dettagliate sulla distribuzione e la configurazione del monitoraggio, vedere [distribuzione del monitoraggio in Lync Server 2013](lync-server-2013-deploying-monitoring.md).

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a>Abilitazione della partecipazione esterna alle conferenze

È possibile aumentare notevolmente i vantaggi offerti dall'investimento in servizi di conferenza di Lync Server 2013 consentendo agli utenti esterni di partecipare alle conferenze anche quando sono state invitate. Gli utenti esterni possono includere:

  - **Utenti remoti**   gli utenti dell'organizzazione, quando stanno lavorando all'esterno dei firewall e usano i loro laptop o altri dispositivi Lync Server 2013.

  - **Gli utenti federati**   degli utenti di aziende con cui si lavora e che eseguono anche Lync Server 2013. Per consentire agli utenti di contattare facilmente questi utenti, è possibile creare relazioni federate con queste società.

  - **Utenti anonimi**   tutti gli altri utenti esterni invitati in modo specifico dagli utenti a partecipare a conferenze specifiche. Un organizzatore della riunione nella tua azienda può inviare un invito di posta elettronica per una conferenza a un utente esterno. Il messaggio di posta elettronica include un collegamento a cui l'utente esterno può fare clic per partecipare alla conferenza.

Per abilitare uno o tutti questi scenari, è necessario distribuire un server perimetrale per facilitare le comunicazioni sicure tra la distribuzione di Lync Server 2013 e gli utenti esterni. La soluzione Lync Server 2013 che usa Edge Server offre elementi multimediali di qualità superiore rispetto ad altre soluzioni, ad esempio una rete privata virtuale (VPN). Per informazioni dettagliate, vedere [pianificazione per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

Inoltre, se si distribuiscono o meno i server perimetrali, è possibile abilitare gli utenti (ovvero all'interno o all'esterno dell'organizzazione) per effettuare la chiamata da telefoni PSTN standard per partecipare a conferenze audio locali. Questa operazione viene eseguita distribuendo i servizi di conferenza telefonica con accesso esterno di Lync Server 2013.

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a>Compatibilità tra i tipi di riunione e le versioni client

Se si vuole che Lync Server 2013 interagisca con le versioni precedenti di Office Communications Server e i relativi client, è necessario tenere presente i problemi seguenti:

  - Gli utenti che usano Lync Server 2013 non possono pianificare conferenze Live Meeting o modificare le riunioni migrate di questo tipo.

  - Gli utenti che usano Lync Server 2013 che devono partecipare a conferenze Live Meeting ospitati su server che utilizzano Office Communications Server 2007 R2 devono avere installato il client Live Meeting nel proprio computer, oltre a Lync Server 2013, per partecipare alle riunioni.

  - Quando si esegue la migrazione delle conferenze di Live Meeting a Lync Server 2013, il contenuto della riunione non viene migrato. Se il contenuto è necessario, deve essere caricato di nuovo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

