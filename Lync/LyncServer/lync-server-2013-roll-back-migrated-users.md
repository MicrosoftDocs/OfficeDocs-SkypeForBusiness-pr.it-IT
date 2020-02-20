---
title: 'Lync Server 2013: eseguire il rollback degli utenti migrati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbc2c46b462ec50c1f5796a9a6a03cd39f7b44dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a>Eseguire il rollback degli utenti migrati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-07_

Se è necessario eseguire il rollback della caratteristica archivio contatti unificato, eseguire il rollback dei contatti solo se l'utente viene spostato di nuovo in Exchange 2010 o Lync Server 2010. Per eseguire il rollback, disabilitare il criterio per l'utente e quindi eseguire il cmdlet **Invoke-CsUcsRollback**. La sola esecuzione di **Invoke-CsUcsRollback** non è sufficiente ad assicurare un rollback permanente, in quanto la migrazione dell'archivio contatti unificato verrà avviata di nuovo se il criterio non viene disabilitato. Ad esempio, se un utente viene eseguito il rollback perché Exchange 2013 viene eseguito il rollback a Exchange 2010 e quindi la cassetta postale dell'utente viene spostata in Exchange 2013, la migrazione dell'archivio contatti unificato verrà avviata di nuovo sette giorni dopo il rollback, purché l'archivio contatti unificato è ancora abilitato per l'utente nei criteri servizi utente.

<div>


> [!IMPORTANT]  
> Il cmdlet <STRONG>Move-CsUser</STRONG> esegue automaticamente il rollback dell'archivio contatti dell'utente da Exchange 2013 a Lync Server 2013 nei casi seguenti: 
> <UL>
> <LI>
> <P>Quando gli utenti vengono spostati da Lync Server 2013 a Lync Server 2010.</P>
> <LI>
> <P>Quando gli utenti eseguono la migrazione di spazi incrociati, ad esempio quando un utente viene spostato da Lync Online a Lync Server 2013 in locale o viceversa.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> L'importazione dei dati dell'archivio contatti unificato da un database di backup può danneggiare i dati dell'archivio e degli utenti se la modalità dell'archivio stesso è cambiata tra l'esportazione e l'importazione. Ad esempio: 
> <UL>
> <LI>
> <P>Se si esportano gli elenchi di contatti prima della migrazione dei contatti degli utenti a Exchange 2013 e successivamente, dopo la migrazione, vengono importati gli stessi dati, i dati degli archivi dei contatti unificati e gli elenchi di contatti verranno danneggiati.</P>
> <LI>
> <P>Se si esporta UserData dopo aver eseguito la migrazione degli utenti a Exchange 2013, eseguire il rollback della migrazione e quindi, per qualche motivo, i dati vengono importati dopo la migrazione, i dati dell'archivio contatti unificato e gli elenchi di contatti verranno danneggiati.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> Prima di spostare una cassetta postale di Exchange da Exchange 2013 a Exchange 2010, l'amministratore di Exchange deve verificare che l'amministratore di Lync Server abbia prima eseguito il rollback dei contatti utente di Lync Server da Exchange 2013 a Lync Server. Per eseguire il rollback dei contatti dell'archivio contatti unificato in Lync Server, vedere la procedura "per eseguire il rollback degli archivi di contatti unificati da Exchange 2013 a Lync Server 2013" più avanti in questa sezione.



</div>

Nella procedura seguente viene illustrato come eseguire il rollback dei contatti degli utenti. Se si utilizza il cmdlet **Move-CsUser** per spostare gli utenti tra lync Server 2013 e lync Server 2010, è possibile ignorare questi passaggi perché il cmdlet **Move-CsUser** esegue automaticamente il rollback dell'archivio contatti di unifed quando sposta gli utenti da Lync Server 2013 a Lync Server 2010. **Move-CsUser** non disattiva il criterio dell'archivio contatti unificato, quindi la migrazione all'archivio contatti unificato si ripeterà se l'utente viene spostato di nuovo su Lync Server 2013.

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>Per eseguire il rollback dei contatti utente da Lync Server 2013 a Lync Server 2010

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Disabilitare l'archivio contatti unificato per gli utenti di cui è necessario eseguire il rollback in modo che, dopo il rollback, non ne venga ripetuta la migrazione. Eseguire questo passaggio solo se si desidera essere certi che gli utenti non vengano ritrasferiti in futuro. Per disabilitare l'archivio contatti unificato per i singoli utenti, nella riga di comando digitare quanto segue:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Ad esempio:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Prima di spostare un utente da Lync Server 2013 a Lync Server 2010, eseguire il rollback dell'elenco contatti per gli utenti specificati in Lync Server.
    
    <div>
    

    > [!IMPORTANT]  
    > Se si ignora questo passaggio, l'elenco contatti andrà perso.

    
    </div>

4.  Eseguire il rollback degli utenti specificati. Nella riga di comando digitare quanto segue:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Ad esempio:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > Non è consigliabile utilizzare l'opzione –Force per forzare il rollback. Se si utilizza tale opzione, i contatti degli utenti andranno persi.

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>Per eseguire il rollback dei contatti dell'archivio contatti unificato da Exchange 2013 a Lync Server 2013

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Disabilitare l'archivio contatti unificato per gli utenti di cui è necessario eseguire il rollback in modo che, dopo il rollback, non ne venga ripetuta la migrazione. Per disabilitare l'archivio contatti unificato per i singoli utenti, nella riga di comando digitare quanto segue:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Ad esempio:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Eseguire il rollback degli utenti specificati. Nella riga di comando digitare quanto segue:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Ad esempio:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > È necessario innanzitutto eseguire il rollback dell'utente di Lync Server e quindi spostare la cassetta postale di Exchange 2013. L'amministratore di Exchange è bloccato dal rollback di Exchange fino al completamento del ripristino di Lync Server. Non è consigliabile utilizzare l'opzione –Force per forzare il rollback. Se si utilizza tale opzione, i contatti degli utenti andranno persi.

    
    </div>

4.  Dopo aver eseguito il rollback dell'utente a Lync Server, l'amministratore di Exchange può eseguire il rollback dell'utente di Exchange da Exchange 2013 a Exchange 2010.

</div>

</div>

<span> </span>

</div>

</div>

</div>

