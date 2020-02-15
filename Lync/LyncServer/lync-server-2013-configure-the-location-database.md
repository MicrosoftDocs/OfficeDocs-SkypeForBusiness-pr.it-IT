---
title: 'Lync Server 2013: configurare il database delle posizioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f79587526172c7ccade1b74574b20657d1a82300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a>Configurare il database delle posizioni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-17_

Per consentire ai client di individuare automaticamente la propria posizione in una rete, è necessario innanzitutto configurare il database delle posizioni. Se non si configura un database delle posizioni e l'opzione **Posizione necessaria** nei criteri percorso è impostata su **Sì** o su **Dichiarazione di non responsabilità**, verrà chiesto all'utente di immettere manualmente una posizione.

Per configurare un database delle posizioni, eseguire le operazioni seguenti:

1.  Popolare il database con il mapping degli elementi di rete ai percorsi. Se si utilizza un gateway ELIN (Emergency Location Identification Number), è necessario includere il numero ELIN nel \<campo\> CompanyName.

2.  Convalidare gli indirizzi in base allo stradario generale gestito dal provider di servizi di emergenza.

3.  Pubblicare il database aggiornato.

<div>


> [!NOTE]  
> In alternativa, è possibile definire un database di origine delle posizioni secondario che può essere utilizzato al posto del database delle posizioni. Per informazioni dettagliate, vedere <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a Secondary Location Information Service in Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Popolare il database delle posizioni in Lync Server 2013](lync-server-2013-populate-the-location-database.md)

  - [Convalidare gli indirizzi in Lync Server 2013](lync-server-2013-validate-addresses.md)

  - [Pubblicare il database delle posizioni da Lync Server 2013](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

