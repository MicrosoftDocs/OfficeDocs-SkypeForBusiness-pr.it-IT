---
title: 'Lync Server 2013: eseguire transazioni sintetiche'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b77593ea062f83352592ebe32dbb81b99c1a9613
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a>Eseguire transazioni sintetiche in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-08-18_

Le transazioni sintetiche vengono in genere eseguite in due modi. Puoi usare i cmdlet CsHealthMonitoringConfiguration per configurare gli utenti di test per ogni pool di registrar. Questi utenti di test sono una coppia di utenti preconfigurati per l'uso con le transazioni sintetiche. In genere si tratta di account di test e non di account che appartengono a utenti effettivi. Con gli utenti di test configurati per un pool, è possibile eseguire una transazione sintetica in tale pool senza dover specificare le identità (e fornire le credenziali per) degli account utente coinvolti nel test.

In alternativa, è possibile eseguire una transazione sintetica usando gli account utente effettivi. Se ad esempio due utenti non possono scambiare messaggi istantanei, è possibile eseguire una transazione sintetica usando questi due account utente (invece di una coppia di account di test) e quindi provare a diagnosticare e risolvere il problema. Se si decide di eseguire una transazione sintetica con gli account utente effettivi, è necessario specificare i nomi di accesso e le password per ogni utente.

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione degli utenti e delle impostazioni di configurazione di testing node di Watcher in Lync Server 2013](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Istruzioni per la configurazione speciale per le transazioni sintetiche in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

