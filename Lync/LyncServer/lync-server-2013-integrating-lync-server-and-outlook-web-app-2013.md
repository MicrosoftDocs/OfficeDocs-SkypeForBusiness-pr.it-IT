---
title: 'Lync Server 2013: integrazione di Lync Server e Outlook Web App 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f5296207a960e02a5eabacb2329d673551803a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>Integrazione di Microsoft Lync Server 2013 e Microsoft Outlook Web App 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-03_

Oltre all'integrazione con Microsoft Outlook 2013, Microsoft Lync Server 2013 può essere completamente integrato con Microsoft Outlook Web App 2013; tra le altre cose, questo aggiunge la messaggistica istantanea e la presenza in Outlook Web App e consente di condividere l'elenco di contatti unificato tra Outlook Web App e Microsoft Lync 2013. Per integrare Lync Server 2013 e Outlook Web App, è innanzitutto necessario verificare che Unified Communications Managed API 4,0 Runtime sia stato installato nel server back-end di Microsoft Exchange Server 2013. Per integrare nm-server-w15-long e Outlook Web Access, è necessario prima di tutto verificare che Unified Communications Managed API 4.0 Runtime sia installato nel server back-end nm-exch-15-formal, controllando se nel Registro di sistema è presente il valore seguente:

HKEY\_Local\_Machine\\System\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath

Il ImplementationDLLPath deve puntare al percorso della cartella per il file Microsoft. Rtc. Internal. UCWEB. dll. In caso contrario, o se il valore del registro di sistema non esiste, è necessario scaricare e installare il programma di installazione di UCMA runtime dall'area download Microsoft <https://www.microsoft.com/download/details.aspx?id=34992>all'indirizzo. Le informazioni su come installare il runtime di UCMA sono disponibili nella stessa pagina Web.

**Compatibilità con le versioni precedenti**

Lync Server 2013 può essere integrato con le versioni di Microsoft Exchange Server 2010 di messaggistica unificata e Outlook Web App. Per ulteriori informazioni, vedere l'articolo Deploying on-premises Exchange Messaggistica unificata per fornire Lync [https://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)Server 2010 segreteria telefonica. Se si integra con Exchange 2010, non si disporranno di funzionalità specifiche di Lync Server, come l'archivio contatti unificato e l'archiviazione Lync-to-Exchange.

Microsoft Lync 2013 può essere utilizzato anche in combinazione con Exchange 2010 e Outlook 2010. Ancora una volta, tuttavia, le nuove funzionalità come l'archivio contatti unificato e le foto ad alta risoluzione non saranno disponibili per gli utenti di Lync 2013. Queste nuove funzionalità richiedono sia Lync Server 2013 sia Exchange 2013.

**Creazione di un pool di applicazioni attendibili per Outlook Web App**

Se il servizio di routing delle chiamate di messaggistica unificata di Microsoft Exchange e il servizio di messaggistica unificata di Microsoft Exchange sono stati installati nello stesso computer, non è necessario creare un pool di applicazioni attendibili per Outlook Web App. Si presuppone che il server in questione ospita un dial plan di messaggistica unificata di SipName. Se si utilizza un singolo computer per ospitare entrambi i servizi, è possibile passare alla sezione di questo documento che consente di abilitare la **messaggistica istantanea in Outlook Web App**.

Lync Server 2013 è in grado di individuare tutti i server Exchange che ospitano un dial plan di messaggistica unificata di SipName. questi server vengono aggiunti automaticamente all'elenco dei server noti di Lync Server. Non è necessario creare un pool di applicazioni attendibili e aggiungere questi server all'elenco dei server noti. In effetti, in questo modo l'integrazione di Outlook Web App smetterà di funzionare.

<div>


> [!NOTE]  
> Ciò è dovuto al fatto che la topologia di Lync Server avrà ora due voci per lo stesso computer: la voce di individuazione automatica e la voce aggiunta manualmente. Per risolvere il problema e per riattivare l'utilizzo di Outlook Web App, utilizzare Windows PowerShell per rimuovere il pool attendibile e le voci dell'applicazione attendibile per il server. Per ulteriori informazioni, vedere gli argomenti della Guida per i cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> .



</div>

Se questi due servizi sono in esecuzione su computer separati, dopo aver verificato che il runtime di Unified Communications Managed API 4,0 è stato installato, è necessario creare un pool di applicazioni attendibili di Lync Server e un'applicazione attendibile associata Outlook Web App; che consente di aggiungere il server all'elenco dei server noti. A tale scopo, eseguire innanzitutto un comando simile al seguente dall'interno di Lync Server Management Shell:

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

Nel comando precedente, atl-owa-001.litwareinc.com è il nome di dominio completo del pool di Outlook Web App. Questo deve essere lo stesso nome visualizzato nei campi nome soggetto e nome alternativo soggetto (SAN) del certificato che consente l'accesso a Outlook Web App. Analogamente, atl-cs-001.litwareinc.com è il nome di dominio completo del pool di Lync Server 2013 che ospiterà il nuovo pool di applicazioni attendibili. Si noti, inoltre, che il sito specificato, Redmond, rappresenta la SiteID del sito di Lync Server. SiteID non è necessariamente uguale al DisplayName del sito. è possibile recuperare SiteIDs per i siti di Lync Server eseguendo il comando seguente da Lync Server Management Shell:

    Get-CsSite | Select-Object DisplayName, SiteID

Dopo aver creato il pool di applicazioni attendibili, utilizzare un comando simile al seguente per configurare un'identità di applicazione e una porta per Outlook Web App:

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

Nel comando precedente, ApplicationID è un identificatore descrittivo usato per distinguere le applicazioni attendibili. Come ApplicationID si può usare qualsiasi stringa di testo che non comprenda spazi o altri caratteri non consentiti. Per creare un identificatore valido, assicurarsi di usare solo lettere e numeri. Anche il valore assegnato al parametro Port è a discrezione dell'amministratore e può corrispondere a qualsiasi porta di rete disponibile.

Dopo aver creato l'applicazione attendibile, è necessario eseguire il comando seguente per abilitare le modifiche apportate alla topologia di Lync Server:

    Enable-CsTopology

Tenere presente che è inoltre necessario aggiungere il server Accesso client e cassette postali di Exchange a tutti i dial plan URI SIP. In questo modo, verranno configurati i server come peer SIP attendibili con la topologia di ExUmRouting per Lync Server.

**Abilitazione della messaggistica istantanea in Outlook Web App**

Se Lync Server è stato configurato correttamente, è possibile iniziare a configurare Outlook Web App. Il primo passaggio del processo consiste nell'abilitare la messaggistica istantanea su tutte le directory virtuali di Outlook Web App nei server front end. Non è necessario abilitare la messaggistica istantanea per le directory virtuali nei server back-end. In effetti, si consiglia di non abilitare la messaggistica istantanea nei server back-end. La messaggistica istantanea può essere abilitata sui server Accesso client eseguendo il comando riportato di seguito dall'interno di Exchange Management Shell:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> Per impostazione predefinita, la messaggistica istantanea è abilitata quando si installa Outlook Web App. in altre condizioni, la proprietà InstantMessagingEnabled consente è impostata su true. Tuttavia, è comunque necessario eseguire il comando precedente per impostare il tipo di messaggistica istantanea su OCS. Per impostazione predefinita, InstantMessagingType è impostato su None.



</div>

Successivamente, è necessario aggiungere le due righe seguenti al file Web. config di Outlook Web App (questo file si trova in genere nella cartella\\C:\\Program\\Files Microsoft\\Exchange\\server\\V15 ClientAccess OWA). Queste due righe devono essere aggiunte sotto il \<nodo\> appSettings nel file Web. config e questa procedura deve essere eseguita solo nei server back-end in cui è stato installato Outlook Web App:

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

Nell'esempio precedente, il valore di IMCertificateThumbprint deve essere l'identificazione personale del certificato di Exchange 2013 installato nei server back-end. È possibile recuperare tali informazioni eseguendo il comando seguente da Exchange Management Shell:

    Get-ExchangeCertificate

Si noti, inoltre, che il valore assegnato a imservername è il nome di dominio completo del pool di Lync Server in cui è stato creato il pool di applicazioni attendibili per Outlook Web App.

Il certificato utilizzato per Outlook Web App deve essere un certificato considerato attendibile da Lync Server. Un modo per assicurarsi che il certificato sia considerato attendibile sia da Lync Server che da Exchange consiste nell'utilizzare l'autorità di certificazione interna per creare un certificato nel server cassette postali, assicurandosi che il nome di dominio completo del server sia utilizzato per l'oggetto Name e che questo FQDN venga visualizzato in t campo nome alternativo certificato. Dopo aver creato il certificato, è possibile importarlo nei server back-end. Il risultato netto è che lo stesso certificato viene utilizzato per due scopi: 1) comunicazione tra la messaggistica unificata di Exchange e Lync Server; e 2) l'integrazione tra Outlook Web App e Lync Server.

Dopo aver aggiornato il file Web. config, è necessario eseguire il comando riportato di seguito sul server back-end di Exchange per riciclare il pool di Outlook Web App:

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

Se l'operazione di riciclo ha esito positivo, verrà visualizzato il messaggio seguente in Exchange Management Shell:

    "MSExchangeOWAAppPool" successfully recycled

**Configurazione di criteri cassetta postale di Outlook Web App**

A questo punto è possibile utilizzare il seguente comando per configurare la messaggistica istantanea sul criterio cassetta postale di Outlook Web App appropriato (o sui criteri). Ad esempio, questo comando, eseguito su uno dei server cassette postali, consente di abilitare la messaggistica istantanea nel criterio predefinito:

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Questo comando consente di abilitare la messaggistica istantanea per tutti i criteri cassetta postale di Outlook Web App:

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Dopo che il criterio cassetta postale è stato abilitato, tutti gli utenti gestiti da tale criterio avranno una completa integrazione tra Lync Server e Outlook Web App, purché:

  - L'utente dispone di una cassetta postale su Exchange 2013.

  - L'utente è stato abilitato per Lync Server 2013.

  - Dispongano di un indirizzo proxy SIP.

**Disabilitazione della messaggistica istantanea in Outlook Web App**

Come indicato in precedenza, la messaggistica istantanea è abilitata per impostazione predefinita in Outlook Web App. Ciò significa che, se non si integra Outlook Web App con Lync Server, gli utenti visualizzeranno le icone di presenza vuote e un messaggio di errore ogni volta che accedono a Outlook Web App. Per evitare questo problema, utilizzare il seguente comando di Exchange Management Shell per disabilitare la messaggistica istantanea in Outlook Web App:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**Verifica dell'integrazione con Outlook Web App**

Per verificare che la messaggistica istantanea e la presenza siano state integrate con Outlook Web App, accedere a Outlook Web App 2013. Nell'angolo in alto a destra dello schermo è visibile il proprio nome visualizzato Exchange. Se accanto al nome è presente un'icona presenza, ad esempio un'icona verde che indica che lo stato corrente è disponibile, che indica che è stato integrato correttamente Lync Server e Outlook Web App.

Dopo aver eseguito l'accesso iniziale a Outlook Web App, controllare se un evento con l'ID evento 112 (e l'origine MSExchange OWA) è stato scritto nel registro eventi sul server cassette postali. Questo evento indica che il gestore endpoint di messaggistica istantanea è stato inizializzato correttamente. Se la messaggistica istantanea non sembra funzionare, nel server cassette postali individuare i file di registro nella cartella\\C: Program Files\\Microsoft\\Exchange Server\\V15\\Logging\\OWA\\instantmessaging. Se le cartelle logging o InstantMessaging non esistono che indicano che l'integrazione ha avuto esito negativo. In tal caso, è possibile utilizzare l'analisi di SIPStack su Lync Server (tutti i livelli e tutti i flag) per provare a determinare il motivo per cui l'integrazione non è riuscita.

</div>

<span> </span>

</div>

</div>

</div>

