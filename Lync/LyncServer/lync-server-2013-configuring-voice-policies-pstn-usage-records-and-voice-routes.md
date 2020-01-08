---
title: Configurazione dei criteri vocali, dei record di utilizzo PSTN e delle route vocali
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring voice policies, PSTN usage records, and voice routes
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398272(v=OCS.15)
ms:contentKeyID: 48183573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbd0e6645fbc831f10b9573fe2ba9bb4400d73ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a>Configurazione dei criteri vocali, dei record di utilizzo PSTN e delle route vocali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-10_

I criteri vocali, i record di utilizzo PSTN e le route vocali sono correlati integralmente. Si configurano i criteri vocali selezionando un set di funzionalità di chiamata e quindi assegnando al criterio un set di record di utilizzo PSTN, che specificano i diritti autorizzati per gli utenti o i gruppi a cui è assegnato il criterio vocale. Alle route vocali vengono assegnati anche record di utilizzo PSTN, che servono per abbinare le route con gli utenti autorizzati ad usarli. Gli utenti possono quindi inserire solo chiamate che usano le route per cui hanno un record di utilizzo PSTN corrispondente.

Il flusso di lavoro consigliato per una nuova distribuzione di VoIP aziendale consiste nell'iniziare la configurazione di un criterio vocale che include i record di utilizzo PSTN appropriati e quindi associare le route appropriate a ogni record di utilizzo PSTN.

<div>


> [!NOTE]
> È anche possibile creare criteri vocali con l'ambito <EM>degli</EM> utenti e assegnarli a singoli utenti o gruppi.



</div>

Per la procedura dettagliata per eseguire ognuna di queste attività, vedere le procedure descritte in questa sezione.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Configurazione di criteri vocali e record utilizzo PSTN per autorizzare privilegi e funzionalità di chiamata in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [Visualizzare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)

  - [Configurazione di route vocali per le chiamate in uscita in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [Esportazione e importazione della configurazione di route vocali in Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [Testare il routing vocale in Lync Server 2013](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

