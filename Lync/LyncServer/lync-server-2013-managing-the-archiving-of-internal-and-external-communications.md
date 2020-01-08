---
title: Gestione dell'archiviazione delle comunicazioni interne ed esterne
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a9e3c0a0708075eecc28282021f98724325ff6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a>Gestione dell'archiviazione delle comunicazioni interne ed esterne in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-09_

In Lync Server 2013 si usano i criteri di archiviazione per abilitare e disabilitare l'archiviazione delle comunicazioni interne e delle comunicazioni esterne se non si usa l'integrazione con Microsoft Exchange o si hanno utenti non residenti in Exchange 2013 con le cassette postali inserite Blocco sul posto. Sono inclusi i seguenti criteri di archiviazione:

  - Un criterio globale creato per impostazione predefinita quando si distribuisce Lync Server 2013.

  - Criteri facoltativi a livello di sito e a livello di utente che è possibile creare e usare per specificare la modalità di implementazione dell'archiviazione per siti o utenti specifici.

I criteri di archiviazione sono stati inizialmente impostati quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare criteri dopo la distribuzione. Nel pannello di controllo di Lync Server 2013 è possibile usare la pagina **criteri di archiviazione** del gruppo **archiviazione e monitoraggio** per gestire i criteri a livello globale, a livello di sito e a livello di utente. Se si integra l'archiviazione di Lync Server con lo spazio di archiviazione di Exchange 2013, i criteri degli utenti di Exchange hanno la precedenza sui criteri di archiviazione di Lync Server 2013.

Per informazioni dettagliate sul modo in cui vengono implementati i criteri, inclusa la gerarchia dei criteri, vedere [come funziona l'archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, la documentazione di distribuzione o la documentazione operativa.

<div>


> [!NOTE]
> Per controllare l'implementazione dell'archiviazione, è necessario specificare le opzioni nelle configurazioni di archiviazione, ad esempio l'archiviazione di messaggi istantanei o di conferenza, l'uso delle opzioni di modalità critiche ed eliminazione. Per impostazione predefinita, nessuna opzione è abilitata nella configurazione di archiviazione globale o in qualsiasi configurazione di archiviazione di siti o pool. Devi specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione per le comunicazioni interne o esterne nei criteri di archiviazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">gestione delle opzioni di configurazione dell'archiviazione in Lync Server 2013 per l'organizzazione, i siti e i pool</A> nella documentazione Operations.<BR>Se si Abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange 2013 e le cassette postali vengono inserite nel blocco sul posto. Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurazione dei criteri per l'archiviazione in Lync server 2013 quando si usa l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Creazione di un criterio di archiviazione in Lync Server 2013 per abilitare o disabilitare l'archiviazione di comunicazioni interne o esterne per siti o utenti specifici](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)

  - [Modifica di un criterio di archiviazione in Lync Server 2013 per abilitare o disabilitare l'archiviazione di comunicazioni interne o esterne per l'organizzazione, i siti o gli utenti](lync-server-2013-changing-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-your-organization-sites-or-us.md)

  - [Applicazione di criteri di archiviazione agli utenti in Lync Server 2013](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [Configurazione dei criteri per l'archiviazione in Lync Server 2013 quando si usa l'integrazione di Exchange Server](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [Eliminazione di un criterio di archiviazione in Lync Server 2013](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

