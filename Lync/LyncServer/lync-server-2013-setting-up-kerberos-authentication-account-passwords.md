---
title: 'Lync Server 2013: impostazione delle password degli account di autenticazione Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21ed9f0b5bd8e9aecfb39a7dd9c159857d4b240e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a>Configurazione delle password degli account di autenticazione Kerberos in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2010-11-03_

Dopo aver creato l'oggetto computer per l'account di autenticazione Kerberos, è possibile configurare la password per l'account. È possibile eseguire il cmdlet di Windows PowerShell per impostare la password dell'account Kerberos in un server. È possibile impostare la password nell'oggetto creato per l'autenticazione Kerberos. La password può essere impostata su un valore noto, ma per impostazione predefinita è una password casuale. La password è disponibile per tutte le origini di autenticazione Kerberos che utilizzano l'account. È possibile utilizzare i cmdlet di Windows PowerShell per configurare e gestire le password degli account Kerberos.

<div>


> [!NOTE]  
> L'oggetto account Kerberos è un oggetto computer, ma utilizza il parametro accountutente per le operazioni nei cmdlet di Windows PowerShell a cui viene fatto riferimento. Si noti che questo non è un errore, ma il comportamento previsto del cmdlet quando viene utilizzato con la creazione e la manutenzione di account Kerberos.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Impostare la password di un account di autenticazione Kerberos in un server di Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [Sincronizzare la password di un account di autenticazione Kerberos con IIS in Lync Server 2013](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

