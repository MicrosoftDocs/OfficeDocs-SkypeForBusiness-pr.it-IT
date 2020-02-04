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
ms.openlocfilehash: 6eaab70f2f6d651d6446aaa4a569277494b7a9ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a>Visualizzare le impostazioni del server perimetrale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-20_

Le configurazioni generali di Edge Server devono essere esaminate in base ai dati nel database di gestione della configurazione, per garantire che tutte le modifiche siano state documentate in base alle procedure di controllo delle modifiche definite.

Altri controlli potrebbero includere quelli descritti nelle sezioni seguenti:

<div>

## <a name="verify-the-allow-and-block-lists"></a>Verificare gli elenchi Consenti e blocca

Verificare gli elenchi URI SIP "Consenti" e "blocca" per i domini federati, per determinare se gli spazi dei nomi elencati sono ancora validi.

Puoi usare Windows PowerShell per visualizzare gli elenchi consentiti e bloccati. Per esaminare i domini nell'elenco dei domini consentiti, eseguire il comando di Windows PowerShell seguente:

`Get-CsAllowedDomain`

Questo comando restituisce informazioni simili a quelle per i domini nell'elenco dei domini consentiti:

Identità: contoso.com

Dominio: contoso.com

ProxyFqdn

Commento

MarkForMonitoring: false

Commento

Per esaminare i domini nell'elenco dei domini bloccati, usare questo comando:

`Get-CsBlockedDomain`

A sua volta, riceverai informazioni come questa per ogni dominio bloccato:

Identità: tailspintoys.com

Dominio: tailspintoys.com

Windows PowerShell consente inoltre di verificare che sia possibile connettersi ai domini nell'elenco dei domini consentiti. Questo comando, ad esempio, verifica la connessione tra il server perimetrale (TargetFqdn) e il dominio federato contoso.com:

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

Questo comando verifica la connessione tra l'Edge Server e tutti i domini trovati nell'elenco dei domini consentiti:

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>Verificare che più Edge Server siano identici

Se sono distribuiti più Edge Server in un array di bilanciamento del carico, è consigliabile verificare che tutti i server perimetrali della matrice siano configurati allo stesso modo.

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

