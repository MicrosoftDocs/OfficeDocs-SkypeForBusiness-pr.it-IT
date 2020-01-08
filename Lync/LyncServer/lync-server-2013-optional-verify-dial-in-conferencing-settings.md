---
title: 'Lync Server 2013: (Facoltativo) Verificare le impostazioni delle conferenze telefoniche con accesso esterno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 177d8516dcb91272eca2a70b89026fc0e175a73a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a>(Facoltativo) Verificare le impostazioni delle conferenze telefoniche con accesso esterno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2010-11-02_

Come verifica finale della configurazione dei servizi di conferenza telefonica con accesso esterno, è possibile cercare piani di chiamata con un'area dei servizi di conferenza telefonica con accesso esterno non utilizzata da qualsiasi numero di Access e per i numeri di Access che non hanno specificato un'area di conferenza telefonica con chiamata in ingresso. Questo passaggio è facoltativo.

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>Per trovare i piani di chiamata con un'area di conferenza telefonica con accesso esterno che non viene usata da un numero di Access

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo **Cs-ServerAdministrator** o **CsAdministrator** .

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire la procedura seguente al prompt dei comandi:
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    Questo cmdlet restituisce tutti i dial plan che hanno un'area di conferenza telefonica con accesso esterno che non viene usata da un numero di Access.

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a>Per trovare i numeri di accesso senza aree assegnate

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo **Cs-ServerAdministrator** o **CsAdministrator** .

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire la procedura seguente al prompt dei comandi:
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    Questo cmdlet restituisce tutti i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso che non sono associati a un'area geografica.

</div>

</div>

<span> </span>

</div>

</div>

</div>

