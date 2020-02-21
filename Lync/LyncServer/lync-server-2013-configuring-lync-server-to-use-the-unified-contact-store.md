---
title: "Lync Server 2013: configurazione di Lync Server per l'utilizzo dell'archivio contatti unificato"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9875cb075f29f9f2efcb9328d1ac2d39d2f8ae89
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a>Configurazione di Microsoft Lync Server 2013 per l'utilizzo dell'archivio contatti unificato

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-07_

L'archivio contatti unificato consente agli utenti di gestire un singolo elenco contatti e quindi di disporre di tali contatti in più applicazioni, tra cui Microsoft Lync 2013, Microsoft Outlook 2013 e Microsoft Outlook Web App 2013. Quando si Abilita l'archivio contatti unificato per un utente, i contatti dell'utente non vengono archiviati in Microsoft Lync Server 2013 e quindi vengono recuperati utilizzando il protocollo SIP. Al contrario, i suoi contatti sono archiviati in Microsoft Exchange Server 2013 e vengono recuperati tramite i servizi Web di Exchange.

<div>


> [!NOTE]  
> Tecnicamente, le informazioni di contatto vengono memorizzate in una coppia di cartelle trovate nella cassetta postale di Exchange 2013 dell'utente. I contatti stessi sono archiviati in una cartella denominata Lync contacts, visibile agli utenti finali. i metadati relativi ai contatti sono archiviati in una sottocartella che non è visibile agli utenti finali.



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a>Abilitazione dell'archivio unificato per i contatti di un utente

Se è già stata configurata l'autenticazione da server a server tra Lync Server 2013 ed Exchange 2013, è stato anche abilitato l'utilizzo dell'archivio contatti unificato. non è necessaria alcuna configurazione aggiuntiva del server. Tuttavia, per spostare i contatti di un utente all'interno dell'archivio unificato è necessaria la configurazione di un ulteriore account utente. Per impostazione predefinita, i contatti dell'utente vengono conservati in Lync Server e non nell'archivio contatti unificato.

L'accesso all'archivio contatti unificato viene gestito utilizzando i criteri dei servizi utente di Lync Server. I criteri sono dotati di una proprietà singola (UcsAllowed), utilizzata per determinare il percorso in cui sono archiviati i contatti di un utente. Se un utente è gestito da un criterio dei servizi utente in cui UcsAllowed impostato è stato impostato su true ($True), i contatti dell'utente verranno archiviati nell'archivio contatti unificato. Se l'utente è gestito da un criterio dei servizi utente in cui UcsAllowed impostato è stato impostato su false ($False), i suoi contatti verranno archiviati in Lync Server.

Quando si installa Lync Server 2013, viene installato anche un criterio per i servizi utente singoli (configurato nell'ambito globale). Il valore di UcsAllowed impostato in questo criterio è impostato su true, in modo che, per impostazione predefinita, i contatti utente vengano archiviati nell'archivio contatti unificato, presupponendo che sia stato distribuito e configurato. Se si desidera eseguire la migrazione di tutti i contatti utente nell'archivio contatti unificato, non è necessario eseguire alcuna operazione.

Se si preferisce non eseguire la migrazione di tutti i contatti nell'archivio contatti unificato, è possibile disabilitare l'archivio contatti unificato per tutti gli utenti impostando la proprietà UcsAllowed impostato nel criterio globale su false:

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

Dopo aver disabilitato l'archivio contatti unificato nel criterio globale, è possibile creare un criterio per utente che consenta l'utilizzo dell'archivio contatti unificato. in questo modo è possibile che alcuni utenti mantengano i propri contatti nell'archivio contatti unificato, mentre altri utenti continuano a mantenere i propri contatti in Lync Server. È possibile creare un criterio dei servizi utente per utente utilizzando un comando simile al seguente:

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

Dopo aver creato il nuovo criterio, bisognerà assegnarlo agli utenti ai quali si desidera concedere l'accesso all'archivio unificato per i contatti. I criteri "per utente" possono essere assegnati agli utenti attraverso un comando simile al seguente:

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

Dopo che il criterio è stato assegnato, Lync Server inizierà a eseguire la migrazione dei contatti dell'utente nell'archivio contatti unificato. Al termine della migrazione, l'utente riceverà i propri contatti archiviati in Exchange anziché in Lync Server. Se l'utente è connesso a Lync 2013 al termine della migrazione, viene visualizzata una finestra di messaggio e gli viene chiesto di disconnettersi da Lync e quindi di eseguire l'accesso per completare il processo. Gli utenti a cui non è stato assegnato il criterio per utente non avranno la migrazione dei contatti nell'archivio contatti unificato. Ciò è dovuto al fatto che gli utenti vengono gestiti dal criterio globale e l'utilizzo dell'archivio contatti unificato è stato disabilitato nei criteri globali.

È possibile verificare che i contatti di un utente siano stati correttamente migrati nell'archivio contatti unificato eseguendo il cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) dall'interno di Lync Server Management Shell:

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

Se il cmdlet Test-CsUnifiedContactStore è eseguito con successo, i contatti del sip:kenmyer@litwareinc.com sono stati migrati correttamente all'archivio unificato per i contatti.

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a>Rollback (ripristino) dell'archivio unificato per i contatti

Se è necessario rimuovere i contatti di un utente dall'archivio contatti unificato, ad esempio se l'utente deve essere reinstallato in Microsoft Lync Server 2010 e pertanto non è più in grado di utilizzare l'archivio contatti unificato, è necessario eseguire due operazioni. Per prima cosa, è necessario assegnare all'utente un nuovo criterio dei servizi utente, che vieti l'archiviazione dei contatti nell'archivio contatti unificato. (Ovvero, un criterio in cui la proprietà UcsAllowed impostato è stata impostata su $False). Se non si dispone di un criterio di questo tipo, è possibile crearne uno utilizzando un comando simile al seguente:

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

È quindi possibile assegnare il nuovo criterio "per utente" (NoUnifiedContactStore) attraverso un comando simile al seguente:

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

Questo comando assegna all'utente Ken Myer il nuovo criterio, e fa in modo che i contatti di Ken non vengano migrati all'archivio unificato per i contatti.

<div>


> [!NOTE]  
> In alcuni casi è possibile ottenere lo stesso risultato semplicemente annullando il criterio dei servizi utente dall'utente in questione. Supponiamo, ad esempio, che a Ken Myer sia assegnato un criterio dei servizi utente di tipo "per utente", che attiva l'archivio unificato per i contatti, e che il criterio globale proibisce l'utilizzo di quest'ultimo. In questo caso, è possibile annullare il criterio dei servizi utente di tipo "per utente" da Ken. In questo modo, Ken sarà gestito automaticamente dal criterio globale, e non avrà più accesso all'archivio unificato per i contatti.<BR>Per annullare l'assegnazione di un criterio per utente precedentemente assegnato, utilizzare lo stesso comando illustrato in precedenza, ma impostare il parametro PolicyName su un valore null:<BR>Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null



</div>

La terminologia "impedisce la migrazione dei contatti di Ken nell'archivio contatti unificato" è importante da tenere presente quando si lavora con l'archivio contatti unificato. Semplicemente assegnando a Ken un nuovo criterio dei servizi utente non sposterà i suoi contatti dall'archivio contatti unificato. Quando un utente accede a Lync Server 2013, il sistema verifica il criterio dei servizi utente dell'utente per verificare se i propri contatti devono essere conservati nell'archivio contatti unificato. Se la risposta è sì, ovvero se la proprietà UcsAllowed impostato è impostata su $True, i contatti verranno migrati nell'archivio contatti unificato, presupponendo che i contatti non siano già presenti nell'archivio contatti unificato. Se la risposta è No, Lync Server ignora semplicemente i contatti dell'utente e passa alla relativa attività successiva. Questo significa che Lync Server non sposterà automaticamente i contatti di un utente dall'archivio contatti unificato, indipendentemente dal valore della proprietà UcsAllowed impostato.

Questo significa anche che, dopo aver assegnato un nuovo criterio ai servizi utente, è necessario eseguire il cmdlet [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) per spostare i contatti dell'utente fuori da Exchange 2013 e viceversa in Lync Server 2013. Ad esempio, dopo avere assegnato a Ken Myer un nuovo criterio dei servizi utente, è possibile spostare i suoi contatti fuori dall'archivio unificato per i contatti, utilizzando il seguente comando:

    Invoke-CsUcsRollback -Identity "Ken Myer"

Se si modifica il criterio dei servizi utente ma non si esegue il cmdlet Invoke-CsUcsRollback, i contatti di Ken non saranno rimossi dall'archivio unificato per i contatti. Cosa succede se si esegue il cmdlet Invoke-CsUcsRollback ma non si modifica il criterio dei servizi utente di Ken Myer? In questo caso, i contatti di Ken vengono rimossi temporaneamente dall'archivio unificato per i contatti. È importante ricordare che questa rimozione è temporanea. Dopo che i contatti di Ken sono stati rimossi dall'archivio contatti unificato, Lync Server 2013 attenderà 7 giorni e quindi verificherà quali criteri di servizi utente sono stati assegnati a Ken. Se a Ken è ancora assegnato un criterio che consente l'utilizzo dell'archivio unificato per i contatti, i contatti saranno automaticamente spostati nuovamente nell'archivio unificato per i contatti. Per rimuovere temporaneamente i contatti dall'archivio unificato per i contatti, è necessario modificare il criterio dei servizi utente, oltre ad eseguire il cmdlet Invoke-CsUcsRollback.

A causa del numero elevato di variabili che possono influire sulla migrazione, è difficile stimare il tempo necessario prima che gli account vengano completamente migrati nell'archivio contatti unificato. Come regola generale, tuttavia, la migrazione non ha effetto immediato: anche quando si esegue la migrazione di un numero limitato di contatti potrebbe essere necessario 10 minuti o più prima che lo spostamento sia stato completato.

</div>

</div>

<span> </span>

</div>

</div>

</div>

