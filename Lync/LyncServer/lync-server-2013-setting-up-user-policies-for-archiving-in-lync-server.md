---
title: "Lync Server 2013: impostazione dei criteri utente per l'archiviazione in Lync Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78a30684619a67fc1e48f3692a2bc40ccae55b14
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a>Configurazione dei criteri utente per l'archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-10_

L'abilitazione o disabilitazione dell'archiviazione per utenti specifici ospitati in Lync Server 2013 richiede la creazione e la configurazione di uno o più criteri utente e l'applicazione del criterio appropriato a specifici utenti o gruppi di utenti. I criteri utente hanno la precedenza sul sito e sui criteri globali, ma solo per gli utenti ospitati in Lync Server 2013.

Gli utenti sono sempre ospitati in Lync Server. Se l'integrazione di Microsoft Exchange è abilitata, gli utenti le cui cassette postali si trovano in Microsoft Exchange Server 2013 non è necessario che i criteri di archiviazione vengano gestiti in Lync Server. Questi utenti con archiviazione verranno gestiti tramite il blocco sul posto di Exchange.

Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, inclusa la gerarchia per i criteri globali, sito e utente, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.

<div>


> [!NOTE]  
> Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di conservazione sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange 2013. L'archiviazione per questi utenti richiede che abbiano le cassette postali archiviate sul posto. Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">impostazione dei criteri per l'archiviazione in Lync server 2013 quando si utilizza l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.<BR>Specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione. Per ulteriori informazioni, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Creazione e configurazione dei criteri utente per l'archiviazione in Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [Applicazione di un criterio di archiviazione di Lync Server a un utente in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

