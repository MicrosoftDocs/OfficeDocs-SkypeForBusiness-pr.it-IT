---
title: Spostare un singolo utente nel pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 051e5b0c550b76dc61aa7935ea8867cc282ddd24
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Spostare un singolo utente nel pool pilota

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

È possibile spostare un utente dal pool di Office Communications Server 2007 R2 al pool pilota di Lync Server 2013 utilizzando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell. Nell'esempio riportato di seguito, nella colonna pool di registrazione, ** \<Office Communications\> server** è il pool di Office Communications Server 2007 R2 e tutti e sei gli utenti sono connessi a questo pool. Utilizzare le procedure seguenti per spostare un utente nel pool di Lync Server 2013 utilizzando il pannello di controllo di Lync Server 2013 e Lync Server Management Shell.

![Cercare gli utenti OCS nel pannello di controllo di Lync Server](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Cercare gli utenti OCS nel pannello di controllo di Lync Server")

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Per spostare un utente utilizzando il pannello di controllo di Lync Server 2013

1.  Eseguire l'accesso al Front End Server con un account membro del gruppo RTCUniversalServerAdmins oppure membro del ruolo amministrativo CsAdministrator o CsUserAdministrator.

2.  Aprire il Pannello di controllo di Lync Server.

3.  Fare clic su **Utenti**.

4.  Nella scheda **Ricerca utente**, fare clic sul pulsante **Cerca**.

5.  Fare quindi clic su **Aggiungi filtro**.

6.  Creare un filtro in cui **l'utente di Office Communications Server** corrisponde a **True**.

7.  Fare clic su **trova** per cercare gli utenti legacy di Office Communications Server 2007 R2.
    
    ![Cercare gli utenti OCS nel pannello di controllo di Lync Server](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Cercare gli utenti OCS nel pannello di controllo di Lync Server")  

8.  Selezionare un utente che si desidera spostare nel pool di Lync Server 2013. In questo esempio, sposteremo l'utente Sara Davis.

9.  Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.

10. Nell'elenco a discesa selezionare il pool Lync Server 2013.

11. Fare clic su **Azione** e quindi su **Sposta utenti selezionati nel pool**. Fare clic su **OK**.
    
    ![Impostazione del pool di destinazione nella finestra di dialogo Sposta utenti](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Impostazione del pool di destinazione nella finestra di dialogo Sposta utenti")  

12. Verificare che la colonna **pool di registrazione** per l'utente contenga ora il pool Lync Server 2013, che indica che l'utente è stato spostato correttamente.

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Per spostare un utente utilizzando Lync Server 2013 Management Shell

1.  Aprire Lync Server Management Shell.

2.  Nella riga di comando digitare quanto segue:
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  Nella riga di comando, digitare quindi quanto segue:
    
        Get-CsUser -Identity "David Pelton"

4.  L'identità di **RegistrarPool** punta ora al pool di Lync Server 2013. La presenza di questa identità conferma che l'utente è stato spostato correttamente.
    
    ![Output del cmdlet Get-CsUser con filtro identità](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output del cmdlet Get-CsUser con filtro identità")  
    
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

