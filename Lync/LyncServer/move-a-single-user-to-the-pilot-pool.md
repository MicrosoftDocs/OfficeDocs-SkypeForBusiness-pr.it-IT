---
title: Spostare un singolo utente nel pool pilota
description: Spostare un singolo utente nel pool pilota.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5f7396ed2d92c7015f01ff6cd6e90fd3998219d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574732"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Spostare un singolo utente nel pool pilota

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-26_

È possibile spostare un utente dal pool Lync Server 2010 al pool pilota di Lync Server 2013 utilizzando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell. Nell'esempio riportato di seguito, nella colonna pool di registrazione, **pool01.contoso.NET** è il pool Lync Server 2010 e tutti e sei gli utenti sono connessi al pool. Utilizzare le procedure seguenti per spostare un utente nel pool di Lync Server 2013 utilizzando il pannello di controllo di Lync Server 2013 e Lync Server Management Shell.

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Per spostare un utente utilizzando il pannello di controllo di Lync Server 2013

**Elenco di utenti nel Pannello di controllo di Lync Server 2013**

![Pannello di controllo di Lync Server, finestra di dialogo Sposta utente](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Pannello di controllo di Lync Server, finestra di dialogo Sposta utente")

1.  Eseguire l'accesso al Front End Server con un account membro del gruppo RTCUniversalServerAdmins oppure membro del ruolo amministrativo CsAdministrator o CsUserAdministrator.

2.  Aprire il **Pannello di controllo di Lync Server**.

3.  Fare clic su **Utenti**, su Cerca e quindi su **Trova**.

4.  Selezionare un utente che si desidera spostare nel pool di Lync Server 2013. In questo esempio, sposteremo l'utente Sara Davis.

5.  Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.

6.  Nell'elenco a discesa selezionare il pool Lync Server 2013.

7.  Fare clic su **Azione** e quindi su **Sposta utenti selezionati nel pool**. Fare clic su **OK**.
    
    ![Finestra di dialogo Sposta utenti, pool di registrazione di destinazione](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Finestra di dialogo Sposta utenti, pool di registrazione di destinazione")  

8.  Verificare che la colonna **pool di registrazione** per l'utente contenga ora il pool Lync Server 2013, che indica che l'utente è stato spostato correttamente.

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Per spostare un utente utilizzando Lync Server 2013 Management Shell

1.  Aprire Lync Server Management Shell.

2.  Nella riga di comando digitare quanto segue:
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  Nella riga di comando, digitare quindi quanto segue:
    
        Get-CsUser -Identity "David Pelton"

4.  L'identità di **RegistrarPool** punta ora al pool di Lync Server 2013. La presenza di questa identità conferma che l'utente è stato spostato correttamente.
    
    ![Output da Get-CsUser cmdlet con filtro identità](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output da Get-CsUser cmdlet con filtro identità")  
    
    <div>
    

    > [!NOTE]  
    > Per avere informazioni dettagliate sul cmdlet <STRONG>Get-CsUser</STRONG>, eseguire: <STRONG>Get-Help Get-CsUser –Detailed</STRONG>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

