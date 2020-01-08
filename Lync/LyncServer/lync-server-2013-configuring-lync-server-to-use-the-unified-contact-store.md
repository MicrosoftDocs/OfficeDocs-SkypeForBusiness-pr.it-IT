---
title: "Lync Server 2013: configurazione di Lync Server per l'uso dell'archivio contatti unificato"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79c26321945444bcf5d450a7397fefb244223ec0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a>Configurazione di Microsoft Lync Server 2013 per l'uso dell'archivio contatti unificato

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-07_

L'archivio contatti unificato consente agli utenti di gestire un singolo elenco di contatti e quindi di avere i contatti disponibili in più applicazioni, tra cui Microsoft Lync 2013, Microsoft Outlook 2013 e Microsoft Outlook Web App 2013. Quando si Abilita l'archivio contatti unificato per un utente, i contatti dell'utente non vengono archiviati in Microsoft Lync Server 2013 e quindi recuperati tramite il protocollo SIP. I suoi contatti vengono invece archiviati in Microsoft Exchange Server 2013 e recuperati tramite i servizi Web di Exchange.

<div>


> [!NOTE]  
> Tecnicamente, le informazioni di contatto vengono archiviate in una coppia di cartelle presenti nella cassetta postale di Exchange 2013 dell'utente. I contatti sono archiviati in una cartella denominata contatti di Lync visibile agli utenti finali; i metadati relativi ai contatti vengono archiviati in una sottocartella non visibile agli utenti finali.



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a>Abilitazione dell'archivio contatti unificato per un utente

Se è già stata configurata l'autenticazione da server a server tra Lync Server 2013 ed Exchange 2013, è stato anche abilitato l'uso dell'archivio contatti unificato. non è necessaria alcuna configurazione del server aggiuntiva. Tuttavia, per trasferire i contatti di un utente nell'archivio contatti unificato è necessaria la configurazione di un account utente aggiuntivo. Per impostazione predefinita, i contatti utente vengono conservati in Lync Server e non nell'archivio contatti unificato.

L'accesso all'archivio contatti unificato viene gestito usando i criteri dei servizi utente di Lync Server. I criteri per i server degli utenti hanno una sola proprietà (UcsAllowed); Questa proprietà viene usata per determinare la posizione in cui vengono archiviati i contatti di un utente. Se un utente è gestito da un criterio dei servizi utente in cui UcsAllowed è stato impostato su true ($True), i contatti dell'utente verranno archiviati nell'archivio contatti unificato. Se l'utente è gestito da un criterio dei servizi utente in cui UcsAllowed è stato impostato su false ($False), i suoi contatti verranno archiviati in Lync Server.

Quando si installa Lync Server 2013, viene installato anche un criterio per i singoli servizi utente (configurato in ambito globale). Il valore UcsAllowed in questo criterio è impostato su true, quindi, per impostazione predefinita, i contatti utente verranno archiviati nell'archivio contatti unificato (supponendo che sia stato distribuito e configurato). Se si vuole eseguire la migrazione di tutti i contatti utente nell'archivio contatti unificato, non è necessario eseguire alcuna operazione.

Se si preferisce non eseguire la migrazione di tutti i contatti all'archivio contatti unificato, è possibile disabilitare l'archivio contatti unificato per tutti gli utenti impostando la proprietà UcsAllowed nel criterio globale su false:

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

Dopo aver disabilitato l'archivio contatti unificato nel criterio globale, è possibile creare un criterio per utente che consenta l'uso dell'archivio contatti unificato; in questo modo è possibile che alcuni utenti mantengano i propri contatti nell'archivio contatti unificato mentre altri utenti continuano a mantenere i contatti in Lync Server. Puoi creare criteri per i servizi utente per utente usando un comando simile al seguente:

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

Dopo aver creato il nuovo criterio, devi assegnare i criteri a qualsiasi utente che deve avere accesso all'archivio contatti unificato. I criteri per utente possono essere assegnati agli utenti usando comandi simili alla seguente:

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

Dopo che i criteri sono stati assegnati Lync Server inizierà a eseguire la migrazione dei contatti dell'utente nell'archivio contatti unificato. Una volta completata la migrazione, l'utente dovrà quindi archiviare i contatti in Exchange anziché in Lync Server. Se l'utente ha eseguito l'accesso a Lync 2013 al termine della migrazione, verrà visualizzata una finestra di messaggio e verrà richiesto di disconnettersi da Lync e quindi di accedere di nuovo per completare il processo. Agli utenti a cui non è stato assegnato questo criterio per utente non verranno trasferiti i contatti nell'archivio contatti unificato. Questo perché gli utenti vengono gestiti dal criterio globale e l'uso dell'archivio contatti unificato è stato disabilitato nel criterio globale.

È possibile verificare che i contatti di un utente siano stati correttamente migrati nell'archivio contatti unificato eseguendo il cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) da Lync Server Management Shell:

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

Se Test-CsUnifiedContactStore ha esito positivo, significa che i contatti per l'utente sip:kenmyer@litwareinc.com sono stati migrati nell'archivio contatti unificato.

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a>Rollback dell'archivio contatti unificato

Se è necessario rimuovere i contatti di un utente dall'archivio contatti unificato, ad esempio se l'utente deve essere reinstallato in Microsoft Lync Server 2010 e quindi non può più usare l'archivio contatti unificato, è necessario eseguire due operazioni. Prima di tutto, devi assegnare all'utente un nuovo criterio per i servizi utente, uno che impedisce l'archiviazione dei contatti nell'archivio contatti unificato. Ovvero un criterio in cui la proprietà UcsAllowed è stata impostata su $False. Se non si dispone di un criterio di questo tipo, è possibile crearne uno usando un comando simile al seguente:

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

Puoi quindi assegnare questo nuovo criterio per utente (NoUnifiedContactStore) usando un comando come questo:

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

Il comando precedente assegna il nuovo criterio all'utente Ken e impedisce inoltre che i contatti di Ken vengano migrati nell'archivio contatti unificato.

<div>


> [!NOTE]  
> In alcuni casi è possibile ottenere lo stesso effetto netto semplicemente deselezionando i criteri dei servizi utente correnti dell'utente. Supponiamo ad esempio che Ken ha un criterio per i servizi utente per utente che Abilita l'archivio contatti unificato, ma il criterio globale vieta l'uso dell'archivio contatti unificato. In questo caso, puoi annullare l'assegnazione dei criteri per i servizi per utente di Ken. Quando si esegue questa operazione, Ken verrà gestito automaticamente dal criterio globale e quindi non potrà più accedere all'archivio contatti unificato.<BR>Per annullare l'assegnazione di un criterio per utente assegnato in precedenza, USA lo stesso comando illustrato prima, ma questa volta imposta il parametro PolicyName su un valore null:<BR>Grant-CsUserServicesPolicy-Identity "Ken"-PolicyName $Null



</div>

La terminologia "impedisce la migrazione dei contatti di Ken all'archivio contatti unificato" è importante da tenere presente quando si lavora con l'archivio contatti unificato. Semplicemente assegnando a Ken un nuovo criterio per i servizi utente non sposterà i suoi contatti dall'archivio contatti unificato. Quando un utente accede a Lync Server 2013, il sistema controlla i criteri dei servizi utente dell'utente per verificare se i propri contatti devono essere conservati nell'archivio contatti unificato. Se la risposta è sì, ovvero se la proprietà UcsAllowed è impostata su $True, i contatti verranno migrati nell'archivio contatti unificato, presupponendo che i contatti non siano già presenti nell'archivio contatti unificato. Se la risposta è No, Lync Server ignora semplicemente i contatti dell'utente e passa alla relativa attività successiva. Ciò significa che Lync Server non sposterà automaticamente i contatti di un utente dall'archivio contatti unificato, indipendentemente dal valore della proprietà UcsAllowed.

Ciò significa anche che, dopo aver assegnato un nuovo criterio ai servizi utente, devi quindi eseguire il cmdlet [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) per trasferire i contatti dell'utente da Exchange 2013 e tornare a Lync Server 2013. Ad esempio, dopo aver assegnato a Ken un nuovo criterio per i servizi utente, è possibile rimuovere i contatti dall'archivio contatti unificato usando il comando seguente:

    Invoke-CsUcsRollback -Identity "Ken Myer"

Se si modificano i criteri dei servizi utente ma non si esegue il cmdlet Invoke-CsUcsRollback, i contatti di Ken non verranno rimossi dall'archivio contatti unificato. Cosa succede se si esegue Invoke-CsUcsRollback ma non si modificano i criteri dei servizi utente di Ken? In questo caso, i contatti di Ken verranno temporaneamente rimossi dall'archivio contatti unificato. Il fatto che questa rimozione sia temporanea è importante da ricordare. Dopo che i contatti di Ken sono stati rimossi dall'archivio contatti unificato, Lync Server 2013 attenderà 7 giorni e quindi verificherà che il criterio dei servizi utente sia stato assegnato a Ken. Se a Ken viene ancora assegnato un criterio che consente all'utente dell'archivio contatti unificato, i suoi contatti verranno automaticamente spostati nell'archivio contatti. Per rimuovere definitivamente i contatti dall'archivio contatti unificato, è necessario modificare i criteri dei servizi utente oltre a eseguire il cmdlet Invoke-CsUcsRollback.

A causa del numero elevato di variabili che possono influire sulla migrazione, è difficile stimare il tempo necessario prima che gli account vengano completamente migrati nell'archivio contatti unificato. Come regola generale, tuttavia, la migrazione non viene applicata immediatamente: anche quando si esegue la migrazione di un numero limitato di contatti potrebbe essere necessario 10 minuti o più prima del completamento dello spostamento.

</div>

</div>

<span> </span>

</div>

</div>

</div>

