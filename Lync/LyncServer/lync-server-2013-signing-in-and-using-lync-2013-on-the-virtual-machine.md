---
title: 'Lync Server 2013: Accesso e utilizzo di Lync 2013 nella macchina virtuale'
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
ms.openlocfilehash: 40c5c18c4e991c3b53e37e090e7f2d960a32f71c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>Accesso e utilizzo di Lync 2013 nella macchina virtuale

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-03_

Dopo aver abilitato il plug-in VDI, i passaggi seguenti si verificano quando l'utente accede a Lync 2013.

1.  L'utente digita le proprie credenziali nel client Lync 2013 in uso nella macchina virtuale.

2.  Dopo che Lync rileva la disponibilità del plug-in VDI, Lync chiede all'utente di immettere di nuovo le proprie credenziali. In questa finestra di dialogo è consigliabile selezionare la casella di controllo **Salva la password** in modo che non venga richiesto di immettere le credenziali durante l'accesso successivo.

3.  Lync avvia l'associazione con il plug-in VDI. Prima del completamento dell'associazione, il client visualizza due icone nella barra di stato di Lync. L'icona nell'angolo in basso a sinistra indica che non sono disponibili dispositivi audio e l'icona lampeggiante in basso a destra indica che l'associazione VDI è in corso, come illustrato:
    
    ![Icona di VDI di Lync che indica la corretta associazione](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icona di VDI di Lync che indica la corretta associazione")  

4.  Dopo aver completato l'associazione VDI, le icone cambiano per indicare il dispositivo audio che verrà usato per le chiamate e il successo dell'associazione VDI:
    
    ![Icona di associazione VDI di Lync che indica la riuscita dell'operazione](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Icona di associazione VDI di Lync che indica la riuscita dell'operazione")  

5.  Dopo le coppie di Lync con il plug-in VDI, l'utente può vedere la propria presenza nei dispositivi compatibili con Lync connessi al computer locale. L'utente può ora inserire e rispondere alle chiamate come al solito.

</div>

<span> </span>

</div>

</div>

</div>

