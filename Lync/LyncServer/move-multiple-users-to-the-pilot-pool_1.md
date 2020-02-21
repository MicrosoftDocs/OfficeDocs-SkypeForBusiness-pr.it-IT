---
title: Spostare più utenti nel pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 657c6e001fa15fa6c1c70076a257a620f0cef790
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>Spostare più utenti nel pool pilota

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

È possibile spostare più utenti dal pool di Office Communications Server 2007 R2 al pool pilota di Lync Server 2013 utilizzando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>Per spostare più utenti utilizzando il pannello di controllo di Lync Server 2013

1.  Aprire il **Pannello di controllo di Lync Server**.

2.  Nella scheda **Ricerca utenti** fare clic sul pulsante **Cerca**.

3.  Fare quindi clic su **Aggiungi filtro**.

4.  Creare un filtro in cui **l'utente di Office Communications Server** corrisponde a **True**.

5.  Fare clic su **trova** per cercare gli utenti legacy di Office Communications Server 2007 R2.

6.  Selezionare due utenti che si desidera spostare nel pool di Lync Server 2013. In questo esempio spostiamo gli utenti Chen Yang e Claus Hansen.
    
    ![Elenco utenti visualizzato dalla ricerca di utenti OCS](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "Elenco utenti visualizzato dalla ricerca di utenti OCS")  

7.  Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.

8.  Nell'elenco a discesa selezionare il pool Lync Server 2013.

9.  Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**. Fare clic su OK.
    
    ![Finestra di dialogo Sposta utenti, pool di registrazione di destinazione](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Finestra di dialogo Sposta utenti, pool di registrazione di destinazione")  

10. Verificare che la colonna **pool di registrazione** per gli utenti contenga ora il pool Lync Server 2013, che indica che gli utenti sono stati spostati correttamente.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>Per spostare più utenti utilizzando Lync Server 2013 Management Shell

1.  Aprire Lync Server 2013 Management Shell.

2.  Nella riga di comando digitare quanto segue e sostituire **User1** e **User2** con nomi utente specifici che si desidera spostare e sostituire **FQDN del\_pool** con il nome del pool di destinazione. In questo esempio spostiamo gli utenti Hao Chen e Katie Jordan.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Cmdlet di esempio per spostare un utente legacy](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Cmdlet di esempio per spostare un utente legacy")  

3.  Nella riga di comando digitare il comando seguente:
    
        Get-CsUser -Identity "User1"

4.  L'identità del **pool di registrazione** deve ora puntare al pool specificato come **FQDN\_del pool** nel passaggio precedente. La presenza di questa identità conferma che l'utente è stato correttamente spostato. Ripetere il passaggio per verificare che **User2** sia stato spostato.
    
    ![Output del cmdlet Get-UsUser-Identity di PowerShell](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output del cmdlet Get-UsUser-Identity di PowerShell")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>Per spostare tutti gli utenti contemporaneamente utilizzando Lync Server 2013 Management Shell

In questo esempio, tutti gli utenti sono stati restituiti al pool di Office Communications Server 2007 R2 (pool01.contoso.net). Se si utilizza Lync Server 2013 Management Shell, tutti gli utenti verranno spostati contemporaneamente sul pool Lync Server 2013 (pool02.contoso.net).

1.  Aprire **Lync Server 2013 Management Shell**.

2.  Nella riga di comando digitare quanto segue:
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Cmdlet di esempio per spostare tutti gli utenti legacy in un pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Cmdlet di esempio per spostare tutti gli utenti legacy in un pool")  

3.  Eseguire quindi **Get-CsUser** per uno degli utenti pilota.
    
        Get-CsUser -Identity "Hao Chen"

4.  L'identità del **pool di registrazione** per ogni utente ora punta al pool specificato come "FQDN\_del pool" nel passaggio precedente. La presenza di questa identità conferma che l'utente è stato spostato correttamente.

5.  Inoltre, è possibile visualizzare l'elenco di utenti nel pannello di controllo di Lync Server 2013 e verificare che il valore del pool di registrazione punti ora al pool di Lync Server 2013.
    
    ![Elenco utenti del pannello di controllo di Lync Server 2013](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Elenco utenti del pannello di controllo di Lync Server 2013")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

