---
title: 'Lync Server 2013: accesso e utilizzo di Lync 2013 nella macchina virtuale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e638fd734f00633b22664b4d4862733eb6d078da
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>Accesso e utilizzo di Lync 2013 nella macchina virtuale

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-03_

Dopo aver abilitato il plug-in VDI, quando l'utente accede a Lync 2013, vengono eseguiti i passaggi seguenti.

1.  L'utente digita le proprie credenziali nel client Lync 2013 in esecuzione nella macchina virtuale.

2.  Dopo che Lync ha rilevato la disponibilità del plug-in VDI, Lync richiede all'utente di immettere nuovamente le proprie credenziali. In questa finestra di dialogo è consigliabile che l'utente selezioni la casella di controllo **Salva la password** in modo che non venga richiesta di nuovo l'immissione delle credenziali per gli accessi successivi.

3.  Lync inizia l'accoppiamento con il plug-in VDI. Prima che l'associazione sia completata, il client visualizza due icone nella barra di stato di Lync. L'icona in basso a sinistra indica che non sono disponibili dispositivi audio e l'icona intermittente in basso a destra indica che l'associazione VDI è in corso, come illustrato di seguito:
    
    ![Icona di Lync VDI che mostra un accoppiamento corretto](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icona di Lync VDI che mostra un accoppiamento corretto")  

4.  Dopo il completamento dell'associazione VDI, le icone cambiano per indicare il dispositivo audio che verrà utilizzato per le chiamate e indicare il corretto completamento dell'associazione VDI:
    
    ![Icona pairing VDI di Lync con esito positivo](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Icona pairing VDI di Lync con esito positivo")  

5.  Dopo le coppie di Lync con il plug-in VDI, l'utente può visualizzare la propria presenza nei dispositivi compatibili con Lync che sono connessi al computer locale. L'utente può ora inserire e rispondere alle chiamate come al solito.

</div>

<span> </span>

</div>

</div>

</div>

