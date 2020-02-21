---
title: 'Lync Server 2013: visualizzare le impostazioni del server perimetrale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c76eb9580c7ee394e0e60e5d0f8cfe38dcae65e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a>Visualizzare le impostazioni del server perimetrale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-20_

Le configurazioni del server perimetrale generale devono essere esaminate in base ai dati del database di gestione della configurazione, per garantire che tutte le modifiche siano state documentate in base alle procedure di controllo delle modifiche definite.

Ulteriori controlli possono includere quelli descritti nelle sezioni seguenti:

<div>

## <a name="verify-the-allow-and-block-lists"></a>Verificare gli elenchi Consenti e blocca

Verificare gli elenchi URI SIP "Consenti" e "blocca" per i domini federati, per determinare se gli spazi dei nomi elencati sono ancora validi.

È possibile utilizzare Windows PowerShell per visualizzare gli elenchi consentiti e bloccati. Per esaminare i domini nell'elenco dei domini consentiti, eseguire il comando di Windows PowerShell seguente:

`Get-CsAllowedDomain`

Questo comando restituisce informazioni simili a quelle per i domini nell'elenco dei domini consentiti:

Identità: contoso.com

Dominio: contoso.com

ProxyFqdn

Commento

MarkForMonitoring: false

Commento

Per esaminare i domini nell'elenco dei domini bloccati, utilizzare questo comando:

`Get-CsBlockedDomain`

A sua volta, verranno ricevute informazioni come questa per ogni dominio bloccato:

Identità: tailspintoys.com

Dominio: tailspintoys.com

Windows PowerShell consente inoltre di verificare che sia possibile connettersi ai domini nell'elenco dei domini consentiti. Ad esempio, questo comando consente di verificare la connessione tra il server perimetrale (TargetFqdn) e il dominio federato contoso.com:

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

Questo comando consente di verificare la connessione tra il server perimetrale e tutti i domini trovati nell'elenco dei domini consentiti:

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>Verificare che più server perimetrali siano identici

Se in un array con bilanciamento del carico sono distribuiti più server perimetrali, è consigliabile verificare che tutti i server perimetrali della matrice siano configurati nello stesso modo.

È possibile visualizzare le impostazioni per i server perimetrali nel riquadro dei dettagli dell'estensione Lync Server 2013 per lo snap-in Gestione computer.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Get-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[Get-CsBlockedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

