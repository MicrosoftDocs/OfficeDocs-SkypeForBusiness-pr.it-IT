---
title: 'Lync Server 2013: configurazione e assegnazione dei criteri di archiviazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7db876d03f7322fae5f3a55f88708fe4165a20ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a>Configurazione e assegnazione dei criteri di archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

In Lync Server 2013, è possibile utilizzare i criteri per abilitare e disabilitare l'archiviazione delle comunicazioni interne e delle comunicazioni esterne per gli utenti ospitati in Lync Server 2013. Sono inclusi i criteri di archiviazione seguenti:

  - Un criterio globale creato per impostazione predefinita quando si distribuisce Lync Server 2013.

  - Criteri a livello di sito e di utente facoltativi che è possibile creare e utilizzare per specificare la modalità di implementazione dell'archiviazione per siti o utenti specifici.

È inizialmente necessario impostare i criteri di archiviazione quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare criteri dopo la distribuzione. Nel pannello di controllo di Lync Server 2013, è possibile utilizzare la pagina **criteri di archiviazione** del gruppo di **archiviazione e monitoraggio** per gestire i criteri a livello globale, a livello di sito e a livello di utente.

<div>


> [!NOTE]  
> Per controllare l'implementazione dell'archiviazione, è necessario specificare le opzioni di configurazione dell'archiviazione, tra cui l'archiviazione (o meno) di messaggistica istantanea e conferenze, l'utilizzo della modalità critica e le opzioni di eliminazione. Per impostazione predefinita, nessuna delle opzioni nella configurazione dell'archiviazione globale o a livello di sito o pool è abilitata. Prima di abilitare l'archiviazione delle comunicazioni interne o esterne nei criteri di archiviazione è necessario specificare tutte le opzioni appropriate nelle configurazioni di archiviazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving Configuration Options in Lync Server 2013 per l'organizzazione, i siti e i pool</A> nella documentazione relativa alle operazioni.<BR>Se si integra l'archiviazione di Lync Server con l'archivio di Exchange 2013, i criteri utente di Exchange hanno la precedenza sui criteri di archiviazione di Lync Server 2013, ma solo per gli utenti che si trovano in Exchange 2013 che hanno le cassette postali inserite in archiviazione sul posto.



</div>

Per informazioni dettagliate sul modo in cui vengono implementati i criteri, inclusa la gerarchia dei criteri, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni. Per informazioni dettagliate su come gestire i criteri dopo la distribuzione, vedere [Managing the Archiving of Internal and External Communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) nella documentazione relativa alle operazioni.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Configurazione dei criteri globali per l'archiviazione in Lync Server 2013](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [Impostazione dei criteri di sito per l'archiviazione in Lync Server 2013](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [Configurazione dei criteri di archiviazione per gli utenti in Lync Server 2013](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

