---
title: 'Lync Server 2013: configurazione delle opzioni di archiviazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 243414dea5b7ca411e4511c3a82f269c9981147e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a>Configurazione delle opzioni di archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-10_

Nel pannello di controllo di Lync Server 2013, è possibile utilizzare le configurazioni di archiviazione per specificare la modalità di implementazione dell'archiviazione. Sono incluse le configurazioni di archiviazione seguenti:

  - Una configurazione globale creata per impostazione predefinita quando si distribuisce Lync Server 2013.

  - Configurazioni facoltative a livello di sito e di pool che possono essere create e utilizzate per specificare come deve essere implementata l'archiviazione per siti o pool specifici.

Le configurazioni di archiviazione vengono definite inizialmente al momento della distribuzione dell'archiviazione, ma è possibile modificarle, aggiungerle ed eliminarle dopo la distribuzione. Nel pannello di controllo di Lync Server 2013, è possibile utilizzare la pagina **Configurazione archiviazione** del gruppo di **archiviazione e monitoraggio** per gestire le configurazioni a livello globale, a livello di sito e a livello di pool. Per informazioni dettagliate sulla modalità di implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni. Per informazioni dettagliate su come gestire le configurazioni dopo la distribuzione, vedere [Managing Archiving Configuration Options in Lync Server 2013 per l'organizzazione, i siti e i pool](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) nella documentazione relativa alle operazioni.

<div>


> [!NOTE]  
> Per utilizzare l'archiviazione, è necessario configurare i criteri di archiviazione per specificare se abilitare l'archiviazione per le comunicazioni interne, per le comunicazioni esterne o per entrambi gli utenti ospitati in Lync Server 2013. Per impostazione predefinita, l'archiviazione non è abilitata per le comunicazioni interne o esterne. Prima di abilitare l'archiviazione nei criteri, è consigliabile specificare le configurazioni di archiviazione appropriate per la distribuzione e facoltativamente per siti e pool specifici, come descritto in questa sezione. Per informazioni dettagliate sull'abilitazione dell'archiviazione, vedere <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurazione e assegnazione dei criteri di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.<BR>Se non si utilizza l'integrazione di Microsoft Exchange per tutti gli utenti nella distribuzione, è necessario configurare i criteri di archiviazione per specificare se abilitare l'archiviazione per le comunicazioni interne, per le comunicazioni esterne o per entrambi. Per impostazione predefinita, l'archiviazione non è abilitata per le comunicazioni interne o esterne per l'archiviazione dei dati quando si utilizzano i database di archiviazione di Lync Server 2013. Prima di abilitare l'archiviazione in qualsiasi criterio, è necessario specificare le configurazioni di archiviazione appropriate per la distribuzione corrente e, facoltativamente, per siti e pool specifici, come illustrato in questa sezione. Per informazioni dettagliate sull'abilitazione dell'archiviazione per l'utilizzo con i database di archiviazione di Lync Server 2013, vedere <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurazione e assegnazione dei criteri di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Configurazione delle opzioni di archiviazione a livello globale in Lync Server 2013](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [Configurazione delle opzioni di archiviazione per un sito in Lync Server 2013](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [Configurazione delle opzioni di archiviazione per un pool in Lync Server 2013](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

