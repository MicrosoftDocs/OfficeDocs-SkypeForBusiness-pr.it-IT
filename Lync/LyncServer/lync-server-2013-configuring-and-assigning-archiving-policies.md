---
title: 'Lync Server 2013: configurazione e assegnazione di criteri di archiviazione'
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
ms.openlocfilehash: 0d8cfb5b446456d99750529d883172ed3cb56e3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a>Configurazione e assegnazione di criteri di archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

In Lync Server 2013 si usano i criteri per abilitare e disabilitare l'archiviazione per comunicazioni interne e comunicazioni esterne per gli utenti residenti in Lync Server 2013. Sono inclusi i seguenti criteri di archiviazione:

  - Un criterio globale creato per impostazione predefinita quando si distribuisce Lync Server 2013.

  - Criteri facoltativi a livello di sito e a livello di utente che è possibile creare e usare per specificare la modalità di implementazione dell'archiviazione per siti o utenti specifici.

I criteri di archiviazione sono stati inizialmente impostati quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare criteri dopo la distribuzione. Nel pannello di controllo di Lync Server 2013 è possibile usare la pagina **criteri di archiviazione** del gruppo **archiviazione e monitoraggio** per gestire i criteri a livello globale, a livello di sito e a livello di utente.

<div>


> [!NOTE]  
> Per controllare l'implementazione dell'archiviazione, è necessario specificare le opzioni nelle configurazioni di archiviazione, ad esempio l'archiviazione di messaggi istantanei o di conferenza, l'uso delle opzioni di modalità critiche ed eliminazione. Per impostazione predefinita, nessuna opzione è abilitata nella configurazione di archiviazione globale o in qualsiasi configurazione di archiviazione di siti o pool. Devi specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione per le comunicazioni interne o esterne nei criteri di archiviazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">gestione delle opzioni di configurazione dell'archiviazione in Lync Server 2013 per l'organizzazione, i siti e i pool</A> nella documentazione Operations.<BR>Se si integra l'archiviazione di Lync Server con lo spazio di archiviazione di Exchange 2013, i criteri degli utenti di Exchange hanno la precedenza sui criteri di archiviazione di Lync Server 2013, ma solo per gli utenti residenti in Exchange 2013 che hanno inserito le cassette postali sul posto.



</div>

Per informazioni dettagliate sul modo in cui vengono implementati i criteri, inclusa la gerarchia dei criteri, vedere [come funziona l'archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, la documentazione di distribuzione o la documentazione operativa. Per informazioni dettagliate su come gestire i criteri dopo la distribuzione, vedere [gestione dell'archiviazione delle comunicazioni interne ed esterne in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) nella documentazione delle operazioni.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Configurazione dei criteri globali per l'archiviazione in Lync Server 2013](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [Configurazione dei criteri del sito per l'archiviazione in Lync Server 2013](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [Configurazione dei criteri di archiviazione per gli utenti in Lync Server 2013](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

