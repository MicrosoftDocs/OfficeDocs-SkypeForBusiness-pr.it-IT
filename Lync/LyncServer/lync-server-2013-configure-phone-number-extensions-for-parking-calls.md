---
title: 'Lync Server 2013: configurare le estensioni dei numeri di telefono per le chiamate di parcheggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure phone number extensions for parking calls
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48185980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a8871454ed95b955558c441d567f68dd0974bd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520433"
---
# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a>Configurare le estensioni dei numeri di telefono per il parcheggio delle chiamate in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-10_

L'applicazione Parcheggio di chiamata utilizza i numeri di interno nella tabella orbit del parcheggio di chiamata per parcheggiare le chiamate. È necessario configurare la tabella orbit del parcheggio di chiamata con gli intervalli di numeri di interno riserve dall'organizzazione per le chiamate parcheggiate. Questi interni devono essere virtuali (ossia interni a cui non è assegnato alcun utente o telefono). Ogni pool di Lync Server in cui viene distribuita e configurata un'applicazione del parcheggio di chiamata può disporre di uno o più intervalli di Orbit. Gli intervalli di Orbit devono essere univoci a livello globale nella distribuzione di Lync Server.

<div>


> [!IMPORTANT]  
> È necessario selezionare la casella di controllo <STRONG>Abilita il parcheggio di chiamata</STRONG> nel criterio vocale prima di poter utilizzare il parcheggio di chiamata. Per impostazione predefinita, questa opzione non è selezionata.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Creare o modificare un intervallo di codici orbit del parcheggio di chiamata in Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [Eliminare un intervallo di codici orbit del parcheggio di chiamata in Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

