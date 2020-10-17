---
title: Spostare più utenti nel pool pilota
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be7fd473b858c6a35b23f8aaa0c525875218d3f7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500233"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Spostare più utenti nel pool pilota

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

È possibile spostare più utenti dal pool Lync Server 2010 al pool pilota di Lync Server 2013 utilizzando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>Per spostare più utenti utilizzando il pannello di controllo di Lync Server 2013

1.  Aprire il **Pannello di controllo di Lync Server**.

2.  Fare clic su **Utenti**, su Cerca e quindi su **Trova**.

3.  Selezionare due utenti che si desidera spostare nel pool di Lync Server 2013. In questo esempio spostiamo gli utenti Chen Yang e Claus Hansen.
    
    ![Spostare gli utenti in un pool di registri specifico](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Spostare gli utenti in un pool di registri specifico")  

4.  Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.

5.  Nell'elenco a discesa selezionare il pool Lync Server 2013.

6.  Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**. Fare clic su OK.
    
    ![Finestra di dialogo Sposta utenti, pool di registrazione di destinazione](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Finestra di dialogo Sposta utenti, pool di registrazione di destinazione")  

7.  Verificare che la colonna **pool di registrazione** per gli utenti contenga ora il pool Lync Server 2013, che indica che gli utenti sono stati spostati correttamente.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>Per spostare più utenti utilizzando Lync Server 2013 Management Shell

1.  Aprire Lync Server 2013 Management Shell.

2.  Nella riga di comando digitare quanto segue e sostituire **User1** e **User2** con nomi utente specifici che si desidera spostare e sostituire ** \_ FQDN del pool** con il nome del pool di destinazione. In questo esempio spostiamo gli utenti Hao Chen e Katie Jordan.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![Esempio di cmdlet di Get-CsUser di PowerShell](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Esempio di cmdlet di Get-CsUser di PowerShell")  

3.  Nella riga di comando digitare il comando seguente:
    
        Get-CsUser -Identity "User1"

4.  L'identità del **pool di registrazione** deve ora puntare al pool specificato come ** \_ FQDN del pool** nel passaggio precedente. La presenza di questa identità conferma che l'utente è stato correttamente spostato. Ripetere il passaggio per verificare che **User2** sia stato spostato.
    
    ![Output del cmdlet PowerShell Get-UsUser-Identity](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output del cmdlet PowerShell Get-UsUser-Identity")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>Per spostare tutti gli utenti contemporaneamente utilizzando Lync Server 2013 Management Shell

In questo esempio, tutti gli utenti sono stati restituiti al pool di Lync Server 2010 (pool01.contoso.net). Se si utilizza Lync Server 2013 Management Shell, tutti gli utenti verranno spostati contemporaneamente sul pool Lync Server 2013 (pool02.contoso.net).

1.  Aprire **Lync Server 2013 Management Shell**.

2.  Nella riga di comando digitare quanto segue:
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![Cmdlet di PowerShell e risultati in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "Cmdlet di PowerShell e risultati in Management Shell")  

3.  Eseguire quindi **Get-CsUser** per uno degli utenti pilota.
    
        Get-CsUser -Identity "Hao Chen"

4.  L'identità del **pool di registrazione** per ogni utente ora punta al pool specificato come "FQDN del pool \_ " nel passaggio precedente. La presenza di questa identità conferma che l'utente è stato spostato correttamente.

5.  Inoltre, è possibile visualizzare l'elenco di utenti nel pannello di controllo di Lync Server 2013 e verificare che il valore del pool di registrazione punti ora al pool di Lync Server 2013.
    
    ![Elenco utenti del pannello di controllo di Lync Server 2013](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Elenco utenti del pannello di controllo di Lync Server 2013")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

