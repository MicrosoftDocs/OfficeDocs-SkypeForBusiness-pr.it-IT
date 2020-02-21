---
title: Configurazione di Lync Server 2013 per l'utilizzo dell'archiviazione di Microsoft Exchange Server 2013
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
ms.openlocfilehash: 85a9a1d035994c143336abc83312fb56f67b927d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a>Configurazione di Microsoft Lync Server 2013 per l'utilizzo dell'archiviazione di Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-06-24_

Microsoft Lync Server 2013 fornisce agli amministratori la possibilità di archiviare la messaggistica istantanea e le trascrizioni di Web Conferencing nella cassetta postale di Microsoft Exchange Server 2013 di un utente anziché in un database di SQL Server. Se si abilita questa opzione, le trascrizioni vengono scritte nella cartella Eliminazioni della cassetta postale dell'utente. Questa cartella è nascosta e si trova nella cartella Elementi ripristinabili. Anche se questa cartella non è visibile agli utenti finali, la cartella viene indicizzata dal motore di ricerca di Exchange e può essere individuata utilizzando la ricerca di cassette postali di Exchange e/o Microsoft SharePoint Server 2013. Poiché le informazioni vengono memorizzate nella stessa cartella utilizzata dalla funzionalità di archiviazione sul posto di Exchange (responsabile della posta elettronica e di altre comunicazioni di Exchange), gli amministratori possono utilizzare un unico strumento per cercare tutte le comunicazioni elettroniche archiviate per un utente.

<div>


> [!IMPORTANT]  
> Per disabilitare completamente l'archiviazione della conversazione Lync, è inoltre necessario disabilitare la cronologia delle conversazioni di Lync. Per ulteriori informazioni, vedere i seguenti argomenti: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">gestione dell'archiviazione delle comunicazioni interne ed esterne in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>e <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.



</div>

Per archiviare le trascrizioni in Exchange 2013, è necessario iniziare configurando l'autenticazione da server a server tra i due server. Dopo aver effettuato l'autenticazione da server a server, è possibile eseguire le attività seguenti in Microsoft Lync Server 2013 (si noti che, a seconda dell'installazione e della configurazione, potrebbe non essere necessario completare tutte queste attività):

1.  Abilitare l'archiviazione di Exchange modificando le impostazioni di configurazione dell'archiviazione di Lync Server. Questo passaggio è obbligatorio per tutte le distribuzioni.

2.  Abilitare l'archiviazione per le comunicazioni interne e/o esterne per gli utenti. Questo passaggio è obbligatorio per tutte le distribuzioni.

3.  Configurare la proprietà ExchangeArchivingPolicy per ogni utente. Questo passaggio è necessario solo in Lync Server e Exchange si trovano in foreste diverse.

<div>

## <a name="step-1-enabling-exchange-archiving"></a>Passaggio 1: abilitazione dell'archiviazione di Exchange

L'archiviazione in Lync Server viene gestita principalmente utilizzando le impostazioni di configurazione dell'archiviazione. Quando si installa Lync Server 2013, viene automaticamente assegnata una singola raccolta globale di queste impostazioni. Gli amministratori possono facoltativamente creare nuove raccolte di impostazioni di archiviazione nell'ambito del sito. Per impostazione predefinita, l'archiviazione non è abilitata nelle impostazioni globali e non è abilitata per l'archiviazione di Exchange in queste impostazioni. Per poter utilizzare gli amministratori di archiviazione di Exchange, è necessario configurare le proprietà EnableArchiving e EnableExchangeArchiving nelle impostazioni di configurazione. La proprietà EnableArchiving può essere impostata su uno di tre possibili valori:

  - **Nessuna**. L'archiviazione è disabilitata. Questo è il valore predefinito. Se EnableArchiving è impostato su None, nel database di archiviazione di Lync Server o in Exchange 2013 non verrà archiviato nulla.

  - **Imsolo**. Vengono archiviate solo le trascrizioni dei messaggi istantanei. Se è abilitata l'archiviazione di Exchange, queste trascrizioni verranno archiviate in Exchange 2013. Se l'archiviazione di Exchange è disabilitata, queste trascrizioni verranno archiviate in Lync Server.

  - **ImAndWebConf**. Vengono archiviate sia le trascrizioni dei messaggi istantanei sia quelle di Web Conferencing. Se è abilitata l'archiviazione di Exchange, queste trascrizioni verranno archiviate in Exchange 2013. Se l'archiviazione di Exchange è disabilitata, queste trascrizioni verranno archiviate in Lync Server.

La proprietà EnableExchangeArchiving è un valore booleano: impostare EnableExchangeArchiving su true ($True) per abilitare l'archiviazione di Exchange o impostare EnableExchangeArchiving su false ($False) per disabilitare l'archiviazione di Exchange. Ad esempio, questo comando consente di abilitare l'archiviazione delle trascrizioni di messaggistica istantanea e di abilitare anche l'archiviazione di Exchange:

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

Per disabilitare l'archiviazione di Exchange, utilizzare un comando simile al seguente, che consente l'archiviazione di messaggistica istantanea ma disabilita l'archiviazione in Exchange (in altre parole, le trascrizioni verranno archiviate in Lync Server):

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> Se la proprietà EnableArchiving è impostata su None, Lync Server non archivierà affatto la messaggistica istantanea e le trascrizioni di Web Conferencing. In tal caso, il server ignorerà semplicemente il valore configurato per EnableExchangeArchiving.



</div>

L'archiviazione di Exchange può anche essere abilitata (o disattivata) utilizzando il pannello di controllo di Lync Server. A tale scopo, completare la procedura seguente:

1.  Nel Pannello di controllo fare clic su **Monitoraggio e archiviazione** e quindi su **Configurazione archiviazione**.

2.  Nella scheda **Configurazione archiviazione** fare doppio clic sulla raccolta delle impostazioni di archiviazione da modificare (ad esempio la raccolta **Globale**).

3.  Nel riquadro **Modifica impostazione di archiviazione** fare clic sull'elenco a discesa **Impostazione di archiviazione** e selezionare **Archivia sessioni di messaggistica istantanea** per archiviare solo le sessioni di messaggistica istantanea o su **Archivia sessioni di messaggistica istantanea e Web Conferencing** per archiviare sia le sessioni di messaggistica istantanea sia quelle di Web Conferencing.

4.  Dopo aver scelto gli elementi da archiviare, selezionare la casella di controllo **integrazione di Exchange Server** per abilitare l'archiviazione di Exchange. Per disabilitare l'archiviazione di Exchange, deselezionare questa casella di controllo.

<div>


> [!NOTE]  
> La casella di controllo <STRONG>Integrazione Exchange Server</STRONG> non sarà disponibile se <STRONG>Impostazione di archiviazione</STRONG> è impostata su <STRONG>Disabilita archiviazione</STRONG>. È innanzitutto necessario abilitare l'archiviazione e quindi abilitare l'archiviazione di Exchange.



</div>

Se Lync Server 2013 e Exchange 2013 si trovano nella stessa foresta, l'archiviazione per singoli utenti (o almeno per gli utenti che dispongono di account di posta elettronica su Exchange 2013) viene gestita utilizzando i criteri di blocco sul posto di Exchange. Se si dispone di utenti ospitati in una versione precedente di Exchange, l'archiviazione per tali utenti verrà gestita utilizzando i criteri di archiviazione di Lync Server. Si noti che solo gli utenti con account su Exchange 2013 possono eseguire l'archiviazione delle trascrizioni di Lync in Exchange.

Se Lync Server 2013 e Exchange 2013 sono ubicati in foreste diverse, l'archiviazione per singoli utenti viene gestita configurando la proprietà ExchangeArchivingPolicy per ogni singolo account utente. Per ulteriori informazioni, vedere il passaggio 3.

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Passaggio 2: Abilitazione dell'archiviazione delle comunicazioni interne e/o esterne

Dopo aver abilitato l'archiviazione (e l'archiviazione di Exchange), è necessario modificare i criteri di archiviazione corretti per garantire che le sessioni degli utenti vengano effettivamente archiviate. Si noti che l'abilitazione dell'archiviazione (passaggio 1) non consente a Lync Server di avviare l'archiviazione delle trascrizioni di messaggistica istantanea e Web Conferencing. È invece necessario utilizzare i criteri di archiviazione per abilitare l'archiviazione interna e/o esterna. Quando si installa Lync Server 2013, viene installato anche un singolo criterio di archiviazione globale contenente due proprietà:

  - **ArchiveInternal**. Se impostata su True ($True), indica che verranno archiviate le sessioni di comunicazione interna che interessano solo gli utenti con account Active Directory attivi nell'organizzazione.

  - **ArchiveExternal**. Se impostata su True ($True), indica che verranno archiviate le sessioni di comunicazione esterna (sessioni che interessano almeno un utente che non ha un account Active Directory attivo nell'organizzazione.

Per impostazione predefinita, i valori di entrambe queste proprietà sono impostati su False, pertanto non vengono archiviate le sessioni di comunicazione né interna né esterna. Per modificare il criterio globale, è possibile utilizzare Lync Server Management Shell e il cmdlet Set-CsArchivingPolicy. Questo comando abilita l'archiviazione delle sessioni di comunicazione sia interna sia esterna:

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

In alternativa, è possibile utilizzare New-CsArchivingPolicy per creare un nuovo criterio nell'ambito del sito o per utente. Ad esempio, questo comando crea un nuovo criterio di archiviazione per utente denominato RedmondArchivingPolicy:

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

Se si crea un criterio per utente, sarà quindi necessario assegnarlo agli utenti appropriati. Ad esempio:

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

I criteri di archiviazione possono essere gestiti anche utilizzando il pannello di controllo di Lync Server. Nel Pannello di controllo, fare clic su **Monitoraggio e archiviazione**, quindi su **Criteri di archiviazione**. Per modificare criteri esistenti, fare doppio clic sui criteri (ad esempio Globale), quindi nel riquadro **Modifica criteri di archiviazione** selezionare o deselezionare le caselle di controllo **Archivia comunicazioni interne** e **Archivia comunicazioni esterne** secondo le esigenze. Per creare un nuovo criterio di archiviazione, fare clic su **nuovo** e quindi selezionare criteri **sito** o criteri **utente**. Se si creano nuovi criteri utente, è quindi necessario accedere agli account utente appropriati (dalla scheda **Utenti**) e assegnare a tali utenti i nuovi criteri.

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Passaggio 3: Configurazione della proprietà ExchangeArchivingPolicy

Se Lync Server 2013 e Exchange 2013 sono ubicati in foreste diverse, non è sufficiente abilitare semplicemente l'archiviazione di Exchange nelle impostazioni di configurazione dell'archiviazione. Questo non provocherà la messaggistica istantanea e le trascrizioni di Web Conferencing che vengono archiviate in Exchange. Al contrario, è necessario configurare anche la proprietà ExchangeArchivingPolicy in ognuno degli account utente di Lync Server rilevanti. Questa proprietà può essere impostata su uno di quattro possibili valori:

1.  Inizializzato. Indica che l'archiviazione si baserà sulle impostazioni del blocco sul posto configurate per la cassetta postale di Exchange dell'utente. Se non è stato abilitato il blocco sul posto nella cassetta postale dell'utente, l'utente dovrà archiviare le proprie trascrizioni di messaggistica e Web Conferencing in Lync Server.

2.  **UseLyncArchivingPolicy**. Indica che le trascrizioni di messaggistica istantanea e Web Conferencing dell'utente devono essere archiviate in Lync Server anziché in Exchange.

3.  **Noarchiving**. Indica che le trascrizioni di messaggistica istantanea e Web Conferencing non devono essere archiviate. Si noti che questa impostazione sostituisce tutti i criteri di archiviazione di Lync Server assegnati all'utente.

4.  **ArchivingToExchange**. Indica che le trascrizioni di messaggistica istantanea e Web Conferencing dell'utente devono essere archiviate in Exchange indipendentemente dalle impostazioni del blocco sul posto che hanno o non sono state assegnate alla cassetta postale dell'utente.

Ad esempio, per configurare un account utente in modo che le trascrizioni di messaggistica istantanea e Web Conferencing vengano sempre archiviate in Exchange, è possibile utilizzare un comando simile al seguente da Lync Server Management Shell:

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

Per impostare gli stessi criteri di archiviazione per un gruppo di utenti (ad esempio tutti gli utenti ospitati in un pool di registrazione specificato), è possibile utilizzare un comando simile al seguente:

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

Tenere presente che è necessario utilizzare Lync Server Management Shell (e Windows PowerShell) per configurare il valore della proprietà ExchangeArchivingPolicy. Questa proprietà non è esposta agli amministratori del pannello di controllo di Lync Server.

Per visualizzare un elenco di tutti gli utenti a cui è stato assegnato un criterio di archiviazione specifico, è possibile utilizzare un comando simile al seguente che restituisce il nome visualizzato di Active Directory di tutti gli utenti la cui proprietà ExchangeArchivingPolicy è impostata su Uninitialized:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

In modo analogo, questo comando restituisce il nome visualizzato degli utenti la cui proprietà ExchangeArchivingPolicy non è impostata su UseLyncArchivingPolicy:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

