---
title: Eseguire la migrazione dei numeri di accesso esterno
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b86db6e669fd5f52827591c25e5bb237bd9ee012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Eseguire la migrazione dei numeri di accesso esterno

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-26_

La migrazione dei numeri di accesso esterno richiede due passaggi: eseguire il cmdlet **Import-CsLegacyConfiguration** (completato in precedenza in [criteri di importazione e impostazioni](import-policies-and-settings.md)) per eseguire la migrazione dei dial plan e di altre impostazioni per i numeri di accesso per la chiamata in ingresso ed eseguire il cmdlet **Move-CsApplicationEndpoint** per eseguire la migrazione degli oggetti contatto.

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>Per eseguire la migrazione dei numeri di accesso esterno

1.  Aprire lo strumento di amministrazione di Office Communications Server 2007 R2.

2.  Nell'albero della console fare clic con il pulsante destro del mouse sul nodo della foresta, scegliere **Proprietà**e quindi fare clic su **Proprietà Operatore Conferenza**.

3.  Nella scheda **numeri di telefono di Access** fare clic su **serviti da pool** per ordinare i numeri di telefono di Access in base al pool associato e identificare tutti i numeri di accesso per il pool da cui si esegue la migrazione.

4.  Per identificare l'URI SIP per ogni numero di accesso, fare doppio clic sul numero di accesso per aprire la finestra di dialogo **modifica numero operatore di conferenza** e cercare in **URI SIP**.

5.  Aprire Lync Server Management Shell.

6.  Per trasferire ogni numero di accesso esterno a un pool ospitato in Lync Server 2013, eseguire:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  Nello strumento di amministrazione di Office Communications Server 2007 R2, nella scheda **numeri di telefono di Access** , verificare che nessun numero di accesso per la chiamata in ingresso rimanga per il pool di Office communications Server 2007 R2 da cui si esegue la migrazione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

