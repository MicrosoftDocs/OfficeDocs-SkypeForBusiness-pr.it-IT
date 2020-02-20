---
title: Eseguire la migrazione dei numeri di accesso esterno
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fcc5b7dac5c9769d92afc86e7036f7e410f2278
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Eseguire la migrazione dei numeri di accesso esterno

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-26_

La migrazione dei numeri di accesso esterno richiede due passaggi: l'esecuzione del cmdlet **Import-CsLegacyConfiguration** (completata in precedenza in [criteri e impostazioni di importazione](import-policies-and-settings.md)) per eseguire la migrazione di dial plan e altre impostazioni dei numeri di accesso esterno e l'esecuzione del cmdlet **Move-CsApplicationEndpoint** per eseguire la migrazione degli oggetti contatto.

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>Per eseguire la migrazione dei numeri di accesso esterno

1.  Aprire lo strumento di amministrazione di Office Communications Server 2007 R2.

2.  Nell'albero della console fare clic con il pulsante destro del mouse sul nodo della foresta, scegliere **Proprietà** e quindi fare clic su **Operatore Conferenza**.

3.  Nella scheda **Numeri di accesso** fare clic su **Servito dal pool** per ordinare i numeri telefonici di accesso in base al pool associato e identificare tutti i numeri di accesso per il pool da cui si sta eseguendo la migrazione.

4.  Per identificare l'URI SIP per ogni numero di accesso, fare doppio clic sul numero di accesso per aprire la finestra di dialogo **Modifica numero Operatore Conferenza**. L'URI è indicato in **URI SIP**.

5.  Aprire Lync Server Management Shell.

6.  Per spostare ogni numero di accesso esterno in un pool ospitato in Lync Server 2013, eseguire:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  Nello strumento di amministrazione di Office Communications Server 2007 R2, nella scheda **numeri di accesso** , verificare che non rimangano numeri di accesso esterno per il pool di Office communications Server 2007 R2 da cui si esegue la migrazione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

