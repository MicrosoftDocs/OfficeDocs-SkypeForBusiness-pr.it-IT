---
title: 'Lync Server 2013: Configurazione delle password degli account di autenticazione Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06ca8bf5d1b3dc90b1ceacbe581e0426b5c0aaa9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a>Configurazione delle password degli account di autenticazione Kerberos in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2010-11-03_

Dopo aver creato l'oggetto computer per l'account di autenticazione Kerberos, è possibile configurare la password per l'account. Si esegue il cmdlet di Windows PowerShell per impostare la password dell'account Kerberos in un server. Puoi impostare la password per l'oggetto creato per l'autenticazione Kerberos. La password può essere impostata su un valore noto, ma per impostazione predefinita è una password casuale. La password è disponibile per tutte le origini di autenticazione Kerberos che usano l'account. Puoi usare i cmdlet di Windows PowerShell per configurare e gestire le password degli account Kerberos.

<div>


> [!NOTE]  
> L'oggetto account Kerberos è un oggetto computer, ma usa il parametro UserAccount per le operazioni nei cmdlet di Windows PowerShell a cui si fa riferimento. Tieni presente che non si tratta di un errore, ma del comportamento previsto del cmdlet quando viene usato con la creazione e la manutenzione dell'account Kerberos.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Impostare la password di un account di autenticazione Kerberos in un server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [Sincronizzare la password di un account di autenticazione Kerberos con IIS in Lync Server 2013](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

