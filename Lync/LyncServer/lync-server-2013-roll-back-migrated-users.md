---
title: 'Lync Server 2013: Eseguire il rollback degli utenti migrati'
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
ms.openlocfilehash: 5e8b8c53f835bbbaa363a91ef547dd1d301c8976
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a>Eseguire il rollback degli utenti migrati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-07_

Se è necessario eseguire il rollback della funzionalità archivio contatti unificato, ripristinare i contatti solo se l'utente viene spostato di nuovo in Exchange 2010 o Lync Server 2010. Per eseguire il rollback, disabilitare il criterio per l'utente e quindi il cmdlet **Invoke-CsUcsRollback** . Solo l'uso di **Invoke-CsUcsRollback** da solo non è sufficiente per garantire un rollback permanente, perché la migrazione dell'archivio contatti unificato verrà avviata di nuovo se il criterio non è disabilitato. Se ad esempio viene eseguito il rollback di un utente perché Exchange 2013 viene eseguito il rollback in Exchange 2010 e la cassetta postale dell'utente viene spostata in Exchange 2013, la migrazione dell'archivio contatti unificato verrà avviata di nuovo sette giorni dopo il rollback, purché l'archivio contatti unificato è ancora abilitato per l'utente nei criteri servizi utente.

<div>


> [!IMPORTANT]  
> Il cmdlet <STRONG>Move-CsUser</STRONG> esegue automaticamente il rollback dell'archivio contatti dell'utente da Exchange 2013 a Lync Server 2013 nelle situazioni seguenti: 
> <UL>
> <LI>
> <P>Quando gli utenti vengono spostati da Lync Server 2013 a Lync Server 2010.</P>
> <LI>
> <P>Quando gli utenti vengono migrati, ad esempio quando un utente viene spostato da Lync Online a Lync Server 2013 locale o viceversa.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> L'importazione di dati dell'archivio contatti unificati da un database di backup può causare il danneggiamento dei dati dell'archivio contatti unificati se la modalità archivio contatti unificata è cambiata tra l'esportazione e l'importazione. Ad esempio: 
> <UL>
> <LI>
> <P>Se si esportano elenchi di contatti prima che i contatti degli utenti vengano migrati a Exchange 2013 e quindi, dopo la migrazione, importino gli stessi dati, i dati dell'archivio contatti unificato e gli elenchi di contatti saranno danneggiati.</P>
> <LI>
> <P>Se si esporta UserData dopo la migrazione degli utenti a Exchange 2013, eseguire il rollback della migrazione e quindi, per qualche motivo, importare i dati dopo la migrazione, i dati dell'archivio contatti unificati e gli elenchi di contatti saranno danneggiati.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> Prima di trasferire una cassetta postale di Exchange da Exchange 2013 a Exchange 2010, l'amministratore di Exchange deve verificare che l'amministratore di Lync Server abbia prima eseguito il rollback dei contatti utente di Lync Server da Exchange 2013 a Lync Server. Per ripristinare i contatti degli archivi di contatti unificati in Lync Server, vedere procedura "per ripristinare i contatti dell'archivio contatti unificati da Exchange 2013 a Lync Server 2013" più avanti in questa sezione.



</div>

La procedura seguente descrive come eseguire il rollback dei contatti utente. Se si usa il cmdlet **Move-CsUser** per spostare gli utenti tra lync Server 2013 e lync Server 2010, è possibile ignorare questi passaggi perché il cmdlet **Move-CsUser** esegue automaticamente il rollback dell'archivio contatti di unifed quando sposta gli utenti da Lync Server 2013 a Lync Server 2010. **Move-CsUser** non Disabilita i criteri archivio contatti unificati, quindi la migrazione all'archivio contatti unificato si ripresenta se l'utente viene spostato di nuovo in Lync Server 2013.

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>Per ripristinare i contatti utente da Lync Server 2013 a Lync Server 2010

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Disabilitare l'archivio contatti unificato per consentire agli utenti di eseguire il rollback in modo che non vengano rimigrati dopo il rollback. Eseguire questo passaggio solo se si vuole verificare che gli utenti non vengano rimigrati in futuro. Per disabilitare l'archivio contatti unificato per singoli utenti, nella riga di comando digitare:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Ad esempio:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Prima di spostare un utente da Lync Server 2013 a Lync Server 2010, eseguire il rollback dell'elenco contatti per gli utenti specificati in Lync Server.
    
    <div>
    

    > [!IMPORTANT]  
    > Se questo passaggio viene omesso, l'elenco contatti verrà perso.

    
    </div>

4.  Eseguire il rollback degli utenti specificati. Nella riga di comando digitare:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Ad esempio:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > Non è consigliabile usare l'opzione – Force per forzare il rollback. Se si usa questa opzione, i contatti degli utenti andranno perduti.

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>Per eseguire il rollback dei contatti dell'archivio contatti unificati da Exchange 2013 a Lync Server 2013

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Disabilitare l'archivio contatti unificato per consentire agli utenti di eseguire il rollback in modo che non vengano rimigrati dopo il rollback. Per disabilitare l'archivio contatti unificato per singoli utenti, nella riga di comando digitare:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Ad esempio:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Eseguire il rollback degli utenti specificati. Nella riga di comando digitare:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Ad esempio:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > Prima di tutto, è necessario eseguire il rollback dell'utente di Lync Server e quindi la cassetta postale di Exchange 2013. L'amministratore di Exchange viene bloccato dal rollback di Exchange fino al completamento del ripristino di Lync Server. Non è consigliabile usare l'opzione – Force per forzare il rollback. Se si usa questa opzione, i contatti degli utenti andranno perduti.

    
    </div>

4.  Dopo aver eseguito il rollback dell'utente a Lync Server, l'amministratore di Exchange può eseguire il rollback dell'utente di Exchange da Exchange 2013 a Exchange 2010.

</div>

</div>

<span> </span>

</div>

</div>

</div>

