---
title: 'Lync Server 2013: configurare la tabella di orbit del parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbeb465bd9ac4e62a51ab562238db9a6c0828f99
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a>Configurare la tabella di orbit del parcheggio di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-10_

Il parcheggio di chiamata utilizza le orbite per le chiamate. Prima che gli utenti possano parcheggiare e recuperare le chiamate, è necessario configurare la tabella di orbit del parcheggio di chiamata. È necessario specificare gli intervalli di numeri di interno (orbite) che l'organizzazione prenoterà per le chiamate al parcheggio e definire il routing per tali intervalli specificando il pool di parcheggio di chiamata che gestisce ogni intervallo. Quando si definiscono gli intervalli di codici orbit, l'obiettivo è quello di disporre di un numero sufficiente di codici orbit tale da evitare che uno stesso codice orbit venga riutilizzato troppo rapidamente, ma senza eccedere limitando il numero di interni disponibili per gli utenti o altri servizi. È possibile creare più intervalli di orbit del parcheggio di chiamata per ogni pool di Lync Server in cui è distribuita l'applicazione Parcheggio di chiamata. Ogni intervallo di orbit del parcheggio di chiamata deve disporre di un nome univoco globale e di un insieme univoco di estensioni.

<div>


> [!IMPORTANT]  
> Un intervallo di codici orbit include in genere al massimo 100 codici orbit. Ogni intervallo può essere più grande, purché sia più piccolo del massimo di 10.000 codici orbit per intervallo e ogni pool includa meno di 50.000 codici orbit. Se un intervallo è troppo piccolo, i codici orbit vengono riutilizzati più rapidamente.



</div>

Utilizzare blocchi di estensioni virtuali, ovvero a cui non sono assegnati utenti o telefoni, per gli intervalli di codici orbit.

<div>


> [!NOTE]  
> L'assegnazione dei numeri DID (Direct Inward Dialing) ai numeri orbitali nella tabella orbit del parcheggio di chiamata non è supportata.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

[Creare o modificare un intervallo di codici orbit del parcheggio di chiamata in Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

