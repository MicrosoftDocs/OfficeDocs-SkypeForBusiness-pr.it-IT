---
title: 'Lync Server 2013: concetti relativi alle conferenze comuni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2afd309f59a66a7117d43b930500a7807d493d1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a>Concetti relativi alle conferenze comuni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-19_

A tutti i tipi di conferenze sono comuni diversi concetti, illustrati nelle sezioni riportate di seguito.

<div>

## <a name="policies-and-bandwidth-management"></a>Criteri e gestione della larghezza di banda

Lync Server 2013 consente agli amministratori di impostare i criteri per i tipi di riunioni che gli utenti possono organizzare. In questo modo è possibile applicare i criteri dell'organizzazione e controllare l'utilizzo della larghezza di banda. È possibile definire un'ampia gamma di criteri di riunione e assegnarli a singoli utenti e gruppi di utenti. È inoltre possibile impostare criteri che controllano le conversazioni peer-to-peer. Per informazioni dettagliate sull'impostazione dei criteri di conferenza, vedere [Conferencing Policies in Lync Server 2013](lync-server-2013-conferencing-policies.md) nella documentazione relativa alle operazioni. Per informazioni dettagliate sulla gestione della larghezza di banda, vedere [Panoramica del controllo di ammissione di chiamata in Lync server 2013](lync-server-2013-overview-of-call-admission-control.md) e [configurazione della larghezza di banda video in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

</div>

<div>

## <a name="archiving-and-compliance-features"></a>Funzionalità di archiviazione e conformità

Lync Server 2013 fornisce caratteristiche che è possibile utilizzare se l'organizzazione deve rispettare le normative di conformità. È possibile utilizzare le funzionalità di archiviazione per archiviare il contenuto presentato nelle riunioni, nonché il contenuto delle conversazioni e delle conferenze istantanee. Per informazioni dettagliate, vedere [Planning for archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) nella documentazione relativa alla pianificazione. È possibile utilizzare le funzionalità di conformità del server Persistent Chat per archiviare conversazioni basate su un argomento che coinvolgono più persone e che vengono salvate in modo permanente. Per informazioni dettagliate, vedere [Planning for Persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="monitoring-feature"></a>Funzionalità di monitoraggio

La caratteristica Monitoring Server è in grado di acquisire record dettagli chiamata (CDRs), che è possibile utilizzare per rilevare gli utenti che parlano con gli altri utenti che utilizzano Lync Server 2013. Per informazioni dettagliate sulla distribuzione e sulla configurazione del monitoraggio, vedere [Deploying Monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a>Consentire la partecipazione esterna alle conferenze

È possibile aumentare notevolmente i vantaggi derivanti dall'investimento in Lync Server 2013 Conferencing, consentendo agli utenti esterni di partecipare alle conferenze anche quando sono state invitate. Gli utenti esterni possono essere:

  - **Utenti remoti**   gli utenti dell'organizzazione che lavorano all'esterno dei firewall e utilizzano i computer portatili o altri dispositivi di Lync Server 2013.

  - **Utenti federati gli**   utenti provenienti da società con cui si lavora, eseguono anche Lync Server 2013. Per consentire agli utenti di mettersi facilmente in contatto con questi utenti, si creano relazioni federate con le relative società.

  - **Utenti anonimi**   qualsiasi altro utente esterno invitato in modo specifico dagli utenti a partecipare a conferenze specifiche. L'organizzatore di una riunione può inviare un invito tramite posta elettronica per una conferenza a un utente esterno. Il messaggio di posta elettronica include un collegamento su cui l'utente esterno può fare clic per partecipare alla conferenza.

Per abilitare uno o più di questi scenari, è necessario distribuire un server perimetrale per consentire le comunicazioni sicure tra la distribuzione di Lync Server 2013 e gli utenti esterni. La soluzione Lync Server 2013 che utilizza i server perimetrali fornisce un supporto di qualità superiore rispetto ad altre soluzioni, ad esempio una rete privata virtuale (VPN). Per informazioni dettagliate, vedere [Planning for External User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

Inoltre, indipendentemente dal fatto che si decida o meno di distribuire server perimetrali, è possibile consentire agli utenti (interni o esterni all'organizzazione) di partecipare ad audioconferenze in locale chiamando da telefoni PSTN standard. Questa operazione viene eseguita distribuendo le conferenze telefoniche con accesso esterno di Lync Server 2013.

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a>Compatibilità tra tipi di riunioni e versioni client

Se si intende che Lync Server 2013 interoperano con le versioni precedenti di Office Communications Server e i relativi client, è necessario tenere conto dei problemi seguenti:

  - Gli utenti che utilizzano Lync Server 2013 non sono in grado di pianificare le conferenze di Live Meeting o di modificare le riunioni migrate di questo tipo.

  - Gli utenti che utilizzano Lync Server 2013 che devono partecipare a conferenze Live Meeting ospitate su server che eseguono Office Communications Server 2007 R2 devono disporre del client Live Meeting installato nel computer (oltre a Lync Server 2013) per partecipare a queste riunioni.

  - Quando si esegue la migrazione delle conferenze di Live Meeting a Lync Server 2013, il contenuto della riunione non viene migrato. Se il contenuto è necessario, è necessario caricarlo di nuovo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

