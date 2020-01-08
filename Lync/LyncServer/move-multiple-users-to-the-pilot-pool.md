---
title: Trasferire più utenti nel pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc3104566841cc70eeee489a4b8812a6b8039a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>Trasferire più utenti nel pool pilota

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

È possibile trasferire più utenti dal pool di Lync Server 2010 al pool di piloti di Lync Server 2013 usando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>Per trasferire più utenti tramite il pannello di controllo di Lync Server 2013

1.  Aprire il **Pannello di controllo di Lync Server**.

2.  Fare clic su **utenti**, fare clic su Cerca e quindi su **trova**.

3.  Selezionare due utenti che si desidera trasferire nel pool di Lync Server 2013. In questo esempio verranno spostati gli utenti Chen Yang e Claus Hansen.
    
    ![Trasferire gli utenti in un pool di registri specifico](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "per trasferire gli utenti in un pool di registri specifico")  

4.  Nel menu **azione** selezionare **Trasferisci utenti selezionati in pool**.

5.  Nell'elenco a discesa selezionare il pool di Lync Server 2013.

6.  Fare clic su **azione** e quindi su **Trasferisci utenti selezionati in pool**. Fare clic su OK.
    
    ![Trasferire utenti, finestra di dialogo pool di registrar di destinazione](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png ", finestra di dialogo pool Registrar di destinazione")  

7.  Verificare che la colonna del **pool di registrar** per gli utenti contenga ora il pool di Lync Server 2013, che indica che gli utenti sono stati spostati correttamente.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>Per trasferire più utenti tramite Lync Server 2013 Management Shell

1.  Aprire Lync Server 2013 Management Shell.

2.  Nella riga di comando digitare le opzioni seguenti e sostituire **User1** e **User2** con nomi utente specifici che si desidera trasferire e sostituire il nome di **dominio completo del pool\_** con quello del pool di destinazione. In questo esempio verranno spostati gli utenti Hao Chen e Katie Jordan.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![Esempio di cmdlet PowerShell Get-CsUser](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "esempio di cmdlet PowerShell Get-CsUser")  

3.  Nella riga di comando digitare la seguente
    
        Get-CsUser -Identity "User1"

4.  L'identità del **pool di registrazione** deve ora puntare al pool specificato come **FQDN\_del pool** nel passaggio precedente. La presenza di questa identità conferma che l'utente è stato spostato correttamente. Ripetere il passaggio per verificare che **User2** sia stato spostato.
    
    ![Output di PowerShell Get-UsUser-cmdlet Identity]-(images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "output di PowerShell Get-UsUser-cmdlet Identity")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>Per trasferire tutti gli utenti contemporaneamente tramite Lync Server 2013 Management Shell

In questo esempio tutti gli utenti sono stati restituiti al pool di Lync Server 2010 (pool01.contoso.net). Usando Lync Server 2013 Management Shell, sposteremo tutti gli utenti contemporaneamente sul pool di Lync Server 2013 (pool02.contoso.net).

1.  Aprire **Lync Server 2013 Management Shell**.

2.  Nella riga di comando digitare quanto segue:
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![Cmdlet di PowerShell e risultati in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet e risultati in Management Shell")  

3.  Esegui quindi **Get-CsUser** per uno degli utenti pilota.
    
        Get-CsUser -Identity "Hao Chen"

4.  L'identità del **pool di registrar** per ogni utente ora punta al pool specificato come "\_FQDN del pool" nel passaggio precedente. La presenza di questa identità conferma che l'utente è stato spostato correttamente.

5.  Inoltre, è possibile visualizzare l'elenco degli utenti nel pannello di controllo di Lync Server 2013 e verificare che il valore del pool di registrazione punti ora al pool di Lync Server 2013.
    
    ![Lync server 2013 elenco utenti del pannello di controllo]di(images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 elenco utenti del pannello di controllo")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

