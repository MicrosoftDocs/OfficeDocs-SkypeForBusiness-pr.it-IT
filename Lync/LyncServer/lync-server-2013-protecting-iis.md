---
title: 'Lync Server 2013: Protezione di IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03d0f3e736284970bf22fe813093e0e54accd29e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a>Protezione di IIS in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-12-05_

In Microsoft Office Communications Server 2007 e Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) è stato eseguito con un account utente standard. Ciò può causare problemi: se la password è scaduta, è possibile perdere i servizi Web, un problema spesso difficile da diagnosticare. Per evitare il problema della scadenza delle password, Microsoft Lync Server 2013 consente di creare un account computer (per un computer che in realtà non esiste) che può fungere da entità di autenticazione per tutti i computer di un sito in cui è in esecuzione IIS. Poiché questi account utilizzano il protocollo di autenticazione Kerberos, vengono denominati account Kerberos e il nuovo processo di autenticazione è noto come autenticazione Web Kerberos. In questo modo è possibile gestire tutti i server IIS utilizzando un singolo account.

Per eseguire i server in questa entità di autenticazione, è necessario prima di tutto creare un account del computer usando il cmdlet New-CsKerberosAccount; Questo account viene quindi assegnato a uno o più siti. Dopo aver effettuato l'assegnazione, l'associazione tra l'account e il sito Lync Server 2013 viene abilitata eseguendo il cmdlet Enable-CsTopology. Tra le altre cose, viene creato il nome dell'entità servizio (SPN) obbligatorio in servizi di dominio Active Directory. I nomi SPN offrono alle applicazioni client un mezzo per individuare un particolare servizio. Per informazioni dettagliate, vedere [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) nella documentazione Operations.

<div>

## <a name="best-practices"></a>Procedure consigliate

Per aumentare la sicurezza di IIS, è consigliabile implementare un account Kerberos per IIS. Se non si implementa un account Kerberos, IIS viene eseguito con un account utente standard.

</div>

</div>

<span> </span>

</div>

</div>

</div>

