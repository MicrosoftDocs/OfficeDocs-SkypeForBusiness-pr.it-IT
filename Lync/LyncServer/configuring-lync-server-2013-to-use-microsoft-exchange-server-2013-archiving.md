---
title: Configurazione di Lync Server 2013 per usare l'archiviazione di Microsoft Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b163b0ce3324455f8a80eca7be5c1423b302a3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a>Configurazione di Microsoft Lync Server 2013 per l'archiviazione di Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-06-24_

Microsoft Lync Server 2013 offre agli amministratori la possibilità di archiviare le trascrizioni di messaggistica istantanea e Web Conferencing nella cassetta postale di un utente di Microsoft Exchange Server 2013 anziché in un database di SQL Server. Se si abilita questa opzione, le trascrizioni vengono scritte nella cartella eliminazioni nella cassetta postale dell'utente. La cartella Purges è una cartella nascosta trovata nella cartella elementi ripristinabili. Anche se questa cartella non è visibile agli utenti finali, la cartella viene indicizzata dal motore di ricerca di Exchange e può essere scoperta usando la ricerca delle cassette postali di Exchange e/o Microsoft SharePoint Server 2013. Poiché le informazioni sono archiviate nella stessa cartella usata dalla funzionalità di blocco sul posto di Exchange (responsabile dell'archiviazione della posta elettronica e di altre comunicazioni di Exchange), gli amministratori possono usare un singolo strumento per cercare tutte le comunicazioni elettroniche archiviate per un utente.

<div>


> [!IMPORTANT]  
> Per disabilitare completamente l'archiviazione delle conversazioni di Lync, è anche necessario disabilitare la cronologia delle conversazioni di Lync. Per altre informazioni, vedere gli argomenti seguenti: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">gestione dell'archiviazione delle comunicazioni interne ed esterne in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>e <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.



</div>

Per archiviare le trascrizioni in Exchange 2013, è necessario iniziare configurando l'autenticazione da server a server tra i due server. Dopo aver effettuato l'autenticazione da server a server, è possibile eseguire le attività seguenti in Microsoft Lync Server 2013 (si noti che, a seconda delle impostazioni e della configurazione, potrebbe non essere necessario completare tutte queste attività):

1.  Abilitare l'archiviazione di Exchange modificando le impostazioni di configurazione dell'archiviazione di Lync Server. Questo passaggio è necessario per tutte le distribuzioni.

2.  Abilitare l'archiviazione per le comunicazioni interne e/o esterne per gli utenti. Questo passaggio è necessario per tutte le distribuzioni.

3.  Configurare la proprietà ExchangeArchivingPolicy per ogni utente. Questo passaggio è necessario solo in Lync Server e Exchange si trovano in foreste diverse.

<div>

## <a name="step-1-enabling-exchange-archiving"></a>Passaggio 1: abilitazione dell'archiviazione di Exchange

L'archiviazione in Lync Server viene gestita principalmente con le impostazioni di configurazione dell'archiviazione. Quando si installa Lync Server 2013 viene automaticamente assegnata una singola raccolta globale di queste impostazioni. Gli amministratori possono facoltativamente creare nuove raccolte di impostazioni di archiviazione nell'ambito del sito. Per impostazione predefinita, l'archiviazione non è abilitata nelle impostazioni globali, né l'archiviazione di Exchange è abilitata in queste impostazioni. Per usare gli amministratori dell'archiviazione di Exchange, è necessario configurare le proprietà EnableArchiving e EnableExchangeArchiving in queste impostazioni di configurazione. La proprietà EnableArchiving può essere impostata su uno dei tre valori possibili:

  - **Nessuno**. L'archiviazione è disabilitata. Questo è il valore predefinito. Se EnableArchiving è impostato su None, il database di archiviazione di Lync Server non verrà archiviato né in Exchange 2013.

  - **ImOnly**. Vengono archiviati solo le trascrizioni di messaggi istantanei. Se è abilitata l'archiviazione di Exchange, queste trascrizioni verranno archiviate in Exchange 2013. Se l'archiviazione di Exchange è disabilitata, queste trascrizioni verranno archiviate in Lync Server.

  - **ImAndWebConf**. Vengono archiviate sia le trascrizioni di messaggistica istantanea che le trascrizioni di conferenza Web. Se è abilitata l'archiviazione di Exchange, queste trascrizioni verranno archiviate in Exchange 2013. Se l'archiviazione di Exchange è disabilitata, queste trascrizioni verranno archiviate in Lync Server.

La proprietà EnableExchangeArchiving è un valore booleano: imposta EnableExchangeArchiving su true ($True) per abilitare l'archiviazione di Exchange o impostare EnableExchangeArchiving su false ($False) per disabilitare l'archiviazione di Exchange. Ad esempio, questo comando consente l'archiviazione delle trascrizioni di messaggistica istantanea e consente inoltre l'archiviazione di Exchange:

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

Per disabilitare l'archiviazione di Exchange, usare un comando simile al seguente, che consente l'archiviazione di messaggistica istantanea, ma disabilita l'archiviazione in Exchange (in altre parole, le trascrizioni verranno archiviate in Lync Server):

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> Se la proprietà EnableArchiving è impostata su None, Lync Server non archivierà affatto le trascrizioni di messaggistica istantanea e Web Conferencing. In questo caso, il server ignorerà semplicemente il valore configurato per EnableExchangeArchiving.



</div>

L'archiviazione di Exchange può essere abilitata o disabilitata anche tramite il pannello di controllo di Lync Server. Per eseguire questa operazione, eseguire la procedura seguente:

1.  Nel pannello di controllo fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.

2.  Nella scheda **Configurazione archiviazione** fare doppio clic sulla raccolta di impostazioni di archiviazione da modificare, ad esempio la raccolta **globale** .

3.  Nel riquadro **Modifica impostazioni archiviazione** fare clic sull'elenco a discesa **Impostazioni archiviazione** e selezionare **sessioni** di messaggistica istantanea (per archiviare solo le sessioni di Instant Messaging) o sessioni di messaggistica istantanea **e conferenze Web** (per archiviare sia le sessioni di messaggistica istantanea che i servizi di conferenza Web).

4.  Dopo aver scelto gli elementi da archiviare, selezionare la casella di controllo **integrazione di Exchange Server** per abilitare l'archiviazione di Exchange. Per disabilitare l'archiviazione di Exchange, deselezionare questa casella di controllo.

<div>


> [!NOTE]  
> La casella di controllo <STRONG>integrazione di Exchange Server</STRONG> non sarà disponibile se l' <STRONG>impostazione di archiviazione</STRONG> è impostata per <STRONG>disabilitare l'archiviazione</STRONG>. Prima di tutto, è necessario abilitare l'archiviazione e quindi abilitare l'archiviazione di Exchange.



</div>

Se Lync Server 2013 e Exchange 2013 si trovano nella stessa foresta, l'archiviazione per singoli utenti (o almeno per gli utenti con account di posta elettronica in Exchange 2013) viene gestita usando i criteri di blocco sul posto di Exchange. Se si hanno utenti ospitati in una versione precedente di Exchange, l'archiviazione per tali utenti verrà gestita usando i criteri di archiviazione di Lync Server. Si noti che solo gli utenti con account in Exchange 2013 possono eseguire l'archiviazione delle trascrizioni di Lync in Exchange.

Se Lync Server 2013 e Exchange 2013 si trovano in foreste diverse, l'archiviazione per singoli utenti viene gestita configurando la proprietà ExchangeArchivingPolicy per ogni singolo account utente. Per altre informazioni, vedere passaggio 3.

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Passaggio 2: abilitazione dell'archiviazione delle comunicazioni interne e/o esterne

Dopo aver abilitato l'archiviazione e l'archiviazione di Exchange, è necessario modificare i criteri di archiviazione appropriati per verificare che le sessioni utente vengano effettivamente archiviate. Tieni presente che l'abilitazione dell'archiviazione (passaggio 1) non fa sì che Lync Server inizi a archiviare le trascrizioni di messaggistica istantanea e Web Conferencing. Devi invece usare i criteri di archiviazione per abilitare l'archiviazione interna e/o esterna. Quando si installa Lync Server 2013 si installa anche un singolo criterio di archiviazione globale che contiene due proprietà:

  - **ArchiveInternal**. Quando impostato su true ($True) indica che verranno archiviate sessioni di comunicazione interne che coinvolgono solo gli utenti che hanno account di Active Directory nell'organizzazione.

  - **ArchiveExternal**. Se impostato su true ($True) indica che verranno archiviate le sessioni di comunicazione interne (sessioni che coinvolgono almeno un utente che non ha un account di Active Directory nell'organizzazione).

Per impostazione predefinita, entrambi i valori di proprietà sono impostati su false, quindi non vengono archiviati né sessioni di comunicazione interne né esterne. Per modificare il criterio globale, è possibile usare Lync Server Management Shell e il cmdlet Set-CsArchivingPolicy. Questo comando consente l'archiviazione di sessioni di comunicazione interne ed esterne:

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

In alternativa, puoi usare il nuovo-CsArchivingPolicy per creare un nuovo criterio nell'ambito del sito o dell'ambito per utente. Ad esempio, questo comando crea un nuovo criterio di archiviazione per utente denominato RedmondArchivingPolicy:

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

Se si crea un criterio per utente, sarà necessario assegnare i criteri agli utenti appropriati. Ad esempio:

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

I criteri di archiviazione possono essere gestiti anche tramite il pannello di controllo di Lync Server. Nel pannello di controllo fare clic su **monitoraggio e archiviazione** e quindi su **criteri di archiviazione**. Per modificare un criterio esistente, fare doppio clic sul criterio (ad esempio, globale) e quindi nel riquadro **modifica criteri di archiviazione** selezionare o deselezionare le caselle di controllo **Archivia comunicazioni interne** e **Archivia comunicazioni esterne** in base alle esigenze. Per creare un nuovo criterio di archiviazione, fare clic su **nuovo** e quindi selezionare criteri **sito** o **criteri utente**. Se crei un nuovo criterio utente, devi accedere agli account utente appropriati (dalla scheda **utenti** ) e assegnare agli utenti il nuovo criterio.

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Passaggio 3: configurazione della proprietà ExchangeArchivingPolicy

Se Lync Server 2013 e Exchange 2013 si trovano in foreste diverse, non è sufficiente abilitare semplicemente l'archiviazione di Exchange nelle impostazioni di configurazione dell'archiviazione; Ciò non comporterà l'archiviazione di trascrizioni di messaggistica istantanea e Web Conferencing in Exchange. Devi invece configurare anche la proprietà ExchangeArchivingPolicy in ognuno degli account utente di Lync Server pertinenti. Questa proprietà può essere impostata su uno dei quattro valori possibili:

1.  Non inizializzati. Indica che l'archiviazione sarà basata sulle impostazioni di blocco sul posto configurate per la cassetta postale di Exchange dell'utente; Se il blocco sul posto non è stato abilitato nella cassetta postale dell'utente, l'utente avrà le sue trascrizioni di messaggistica e web conferenza archiviate in Lync Server.

2.  **UseLyncArchivingPolicy**. Indica che le trascrizioni di messaggistica istantanea e di conferenza Web dell'utente devono essere archiviate in Lync Server anziché in Exchange.

3.  **Noarchiving**. Indica che le trascrizioni di messaggistica istantanea e Web Conferencing dell'utente non devono essere archiviate affatto. Tieni presente che questa impostazione sostituisce tutti i criteri di archiviazione di Lync Server assegnati all'utente.

4.  **ArchivingToExchange**. Indica che le trascrizioni di messaggistica istantanea e Web Conferencing dell'utente devono essere archiviate in Exchange indipendentemente dalle impostazioni di blocco sul posto che hanno o non sono state assegnate alla cassetta postale dell'utente.

Ad esempio, per configurare un account utente in modo che le trascrizioni di messaggistica istantanea e Web Conferencing vengano sempre archiviate in Exchange, è possibile usare un comando simile a quello di Lync Server Management Shell:

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

Se si vogliono impostare gli stessi criteri di archiviazione per un gruppo di utenti, ad esempio tutti gli utenti ospitati in un pool di registrar specificato, è possibile usare un comando simile al seguente:

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

Tieni presente che devi usare Lync Server Management Shell (e Windows PowerShell) per configurare il valore della proprietà ExchangeArchivingPolicy. Questa proprietà non viene esposta agli amministratori nel pannello di controllo di Lync Server.

Se si vuole visualizzare un elenco di tutti gli utenti a cui è stato assegnato un criterio di archiviazione specifico, è possibile usare un comando simile al seguente, che restituisce il nome visualizzato di Active Directory di tutti gli utenti che hanno il set di proprietà ExchangeArchivingPolicy per non inizializzare:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

Analogamente, questo comando restituisce il nome visualizzato degli utenti che non hanno la proprietà ExchangeArchivingPolicy impostata su UseLyncArchivingPolicy:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

