---
title: 'Lync Server 2013: configurare il database della posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15a9456cc79e02735fe94c24748674944722b49c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a>Configurare il database della posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-17_

Per consentire ai client di rilevare automaticamente la propria posizione all'interno di una rete, è prima di tutto necessario configurare il database della posizione. Se non si configura un database di posizione e la **posizione richiesta** nel criterio della posizione è impostata su **Sì** o su dichiarazione di non **responsabilità**, all'utente verrà richiesto di immettere manualmente una posizione.

Per configurare il database della posizione, verranno eseguite le attività seguenti:

1.  Popolare il database con un mapping degli elementi di rete alle posizioni. Se si usa un gateway ELIN (Emergency Location Identification Number), è necessario includere il numero ELIN nel \<campo\> CompanyName.

2.  Convalidare gli indirizzi rispetto alla guida di indirizzo Master Street (stradario) gestita dal provider di servizi E9-1-1.

3.  Pubblicare il database aggiornato.

<div>


> [!NOTE]  
> In alternativa, è possibile definire un database di origine della posizione secondario che può essere usato nella posizione del database delle posizioni. Per informazioni dettagliate, vedere <A href="lync-server-2013-configure-a-secondary-location-information-service.md">configurare un servizio informazioni sulla posizione secondaria in Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Compilare il database della posizione in Lync Server 2013](lync-server-2013-populate-the-location-database.md)

  - [Convalidare gli indirizzi in Lync Server 2013](lync-server-2013-validate-addresses.md)

  - [Pubblicare il database della posizione da Lync Server 2013](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

