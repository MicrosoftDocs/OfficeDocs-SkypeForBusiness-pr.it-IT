---
title: 'Lync Server 2013: esecuzione di transazioni sintetiche'
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
ms.openlocfilehash: 297e1ee6416fb534791a2459e10acaa87f86e205
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511093"
---
# <a name="running-synthetic-transactions-in-lync-server-2013"></a>Esecuzione di transazioni sintetiche in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-08-18_

Le transazioni sintetiche vengono in genere eseguite in due modi. È possibile utilizzare i cmdlet di CsHealthMonitoringConfiguration per configurare gli utenti di test per ogni pool di registrazione. Questi utenti di test sono una coppia di utenti preconfigurati per l'utilizzo con transazioni sintetiche. In genere si tratta di account di prova e non di account che appartengono a utenti effettivi. Con gli utenti di test configurati per un pool, è possibile eseguire una transazione sintetica su tale pool senza dover specificare le identità (e fornire le credenziali per) degli account utente coinvolti nel test.

In alternativa, è possibile eseguire una transazione sintetica utilizzando account utente effettivi. Ad esempio, se due utenti non sono in grado di scambiare messaggi istantanei, è possibile eseguire una transazione sintetica utilizzando questi due account utente (invece di una coppia di account di test) e quindi provare a diagnosticare e risolvere il problema. Se si decide di eseguire una transazione sintetica utilizzando account utente effettivi, è necessario specificare i nomi di accesso e le password di ogni utente.

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione degli utenti e delle impostazioni di configurazione del nodo Watcher in Lync Server 2013](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Istruzioni di installazione speciali per le transazioni sintetiche in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

