---
title: 'Lync Server 2013: integrazione di Lync Server e Outlook Web App 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31a25e1d0a6410171201af578d6b28f496468e06
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>Integrazione di Microsoft Lync Server 2013 e Microsoft Outlook Web App 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-03_

Oltre ad integrare Microsoft Outlook 2013, Microsoft Lync Server 2013 può essere completamente integrato con Microsoft Outlook Web App 2013; tra le altre cose, questo aggiunge la messaggistica istantanea e la presenza a Outlook Web App e consente di condividere l'elenco di contatti unificato tra Outlook Web App e Microsoft Lync 2013. Per integrare Lync Server 2013 e Outlook Web App, è prima di tutto necessario verificare che l'API Managed Communications Unified 4,0 Runtime sia stato installato nel server back-end di Microsoft Exchange Server 2013. A tale scopo, è possibile cercare l'esistenza del valore del registro di sistema seguente:

HKEY\_Local\_Machine\\System\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath

ImplementationDLLPath deve puntare al percorso della cartella per il file Microsoft. Rtc. Internal. UCWEB. dll. In <http://www.microsoft.com/en-us/download/details.aspx?id=34992>caso contrario o se il valore del registro di sistema non è presente, è consigliabile scaricare e installare il programma di configurazione di runtime di UCMA dall'area download Microsoft. Le informazioni su come installare il runtime di UCMA possono essere trovate nella stessa pagina Web.

**Compatibilità con le versioni precedenti**

Lync Server 2013 può essere integrato con le versioni di Microsoft Exchange Server 2010 sia per la messaggistica unificata che per Outlook Web App. Per altre informazioni, vedere l'articolo distribuzione della messaggistica unificata di Exchange locale per l'invio della segreteria [http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)telefonica di Lync Server 2010. Se si integra con Exchange 2010, non saranno disponibili funzionalità specifiche di Lync Server, ad esempio l'archivio contatti unificato e l'archiviazione Lync-to-Exchange.

Microsoft Lync 2013 può essere usato anche in combinazione con Exchange 2010 e Outlook 2010. Ancora una volta, tuttavia, le nuove funzionalità, ad esempio l'archivio contatti unificato e le foto ad alta risoluzione, non saranno disponibili per gli utenti di Lync 2013. Queste nuove funzionalità richiedono sia Lync Server 2013 che Exchange 2013.

**Creazione di un pool di applicazioni attendibili per Outlook Web App**

Se è stato installato il servizio di chiamata della messaggistica unificata di Microsoft Exchange e il servizio messaggistica unificata di Microsoft Exchange nello stesso computer, non è necessario creare un pool di applicazioni attendibili per Outlook Web App. Questo presuppone che il server in questione ospita un dial plan di messaggistica unificata di SipName. Se si usa un singolo computer per ospitare entrambi i servizi, è possibile passare alla sezione del documento che **consente la messaggistica istantanea in Outlook Web App**.

Lync Server 2013 può individuare in maniera automatica tutti i server Exchange che ospitano un dial plan di messaggistica unificata di SipName; questi server vengono aggiunti automaticamente all'elenco server noti di Lync Server. Non è necessario creare un pool di applicazioni attendibili e aggiungere questi server all'elenco dei server noti. In realtà, in questo modo l'integrazione di Outlook Web App smette di funzionare.

<div>


> [!NOTE]  
> Ciò è dovuto al fatto che la topologia di Lync Server includerà ora due voci per lo stesso computer: la voce individuazione automatica e la voce aggiunta manualmente. Per risolvere il problema e per riattivare l'uso di Outlook Web App, usare Windows PowerShell per rimuovere il pool attendibile e le voci di applicazione attendibili per il server. Per altre informazioni, vedere gli argomenti della Guida relativi ai cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> .



</div>

Se questi due servizi sono in esecuzione su computer separati, dopo aver verificato che l'API Managed Communications 4,0 Runtime è stato installato, è necessario creare un pool di applicazioni attendibili di Lync Server e un'applicazione attendibile associata Outlook Web App; in questo modo si aggiungerà il server all'elenco dei server noti. A tale scopo, eseguire prima di tutto un comando simile all'interno di Lync Server Management Shell:

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

Nel comando precedente, atl-owa-001.litwareinc.com è il nome di dominio completo del pool di Outlook Web App; deve essere lo stesso nome visualizzato nei campi nome soggetto e nome alternativo oggetto (SAN) del certificato che consente di accedere a Outlook Web App. Allo stesso modo, atl-cs-001.litwareinc.com è il nome di dominio completo del pool di Lync Server 2013 che ospiterà il nuovo pool di applicazioni attendibili. Tieni presente che il sito specificato, Redmond, rappresenta il SiteID del sito di Lync Server. SiteID non è necessariamente uguale al DisplayName del sito. è possibile recuperare SiteIDs per i siti di Lync Server eseguendo il comando seguente da Lync Server Management Shell:

    Get-CsSite | Select-Object DisplayName, SiteID

Dopo aver creato il pool di applicazioni attendibili, usare un comando simile al seguente per configurare un'identità dell'applicazione e una porta per Outlook Web App:

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

Nel comando precedente, ApplicationID è semplicemente un identificatore amichevole usato per distinguere le applicazioni attendibili. ApplicationID può essere costituito da qualsiasi stringa di testo che non includa spazi vuoti o altri caratteri vietati. Per assicurarsi di creare un identificatore valido, è consigliabile usare solo lettere e numeri quando si specifica un ApplicationId. Anche il valore assegnato al parametro Port viene lasciato a discrezione dell'amministratore: può essere una qualsiasi porta di rete disponibile.

Dopo aver creato l'applicazione attendibile, è necessario eseguire il comando seguente per abilitare le modifiche alla topologia di Lync Server:

    Enable-CsTopology

Tieni presente che devi anche aggiungere il server di Exchange Client Access e cassette postali a tutti i dial plan URI SIP. A sua volta, verranno configurati i server come peer SIP attendibili con la topologia ExUmRouting per Lync Server.

**Abilitazione della messaggistica istantanea in Outlook Web App**

Con Lync Server configurato correttamente, è possibile iniziare a configurare Outlook Web App. Il primo passaggio di tale processo consiste nell'abilitare la messaggistica istantanea in tutte le directory virtuali di Outlook Web App nei server front-end. Non è necessario abilitare la messaggistica istantanea per le directory virtuali nei server di back-end. In realtà, è consigliabile non abilitare la messaggistica istantanea nei server back-end. La messaggistica istantanea può essere abilitata nei server di accesso client eseguendo il comando seguente da Exchange Management Shell:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> Per impostazione predefinita, la messaggistica istantanea è abilitata durante l'installazione di Outlook Web App; la proprietà InstantMessagingEnabled consente è impostata su true. Tuttavia, devi ancora eseguire il comando precedente per impostare il tipo di messaggistica istantanea su OCS. Per impostazione predefinita, InstantMessagingType è impostato su None.



</div>

È quindi necessario aggiungere le due righe seguenti al file Web. config di Outlook Web App (il file si trova in genere nella cartella C\\: Program\\files\\Microsoft Exchange\\server\\V15\\ClientAccess OWA). Queste due righe devono essere aggiunte sotto il \<nodo\> appSettings nel file Web. config e questa procedura deve essere eseguita solo nei server back-end in cui è stato installato Outlook Web App:

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

Nell'esempio precedente il valore di IMCertificateThumbprint deve essere l'identificazione personale del certificato di Exchange 2013 installato nei server back-end. Puoi recuperare queste informazioni eseguendo il comando seguente da Exchange Management Shell:

    Get-ExchangeCertificate

Si noti che il valore assegnato a imservername è il nome di dominio completo del pool di Lync Server in cui è stato creato il pool di applicazioni attendibili per Outlook Web App.

Il certificato usato per Outlook Web App deve essere un certificato considerato attendibile da Lync Server. Un modo per verificare che il certificato sia considerato attendibile sia da Lync Server che da Exchange consiste nell'usare l'autorità di certificazione interna per creare un certificato nel server delle cassette postali, verificando che il nome di dominio completo del server venga usato per l'oggetto e che questo FQDN venga visualizzato in t campo nome alternativo certificato. Dopo aver creato il certificato, è possibile importarlo nei server di back-end. Il risultato netto è che lo stesso certificato viene usato per due scopi: 1) comunicazione tra messaggistica unificata di Exchange e Lync Server; e 2) l'integrazione tra Outlook Web App e Lync Server.

Dopo aver aggiornato il file Web. config, è necessario eseguire il comando seguente nel server back-end di Exchange per riciclare il pool di Outlook Web App:

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

Se l'operazione di riciclo viene eseguita correttamente, in Exchange Management Shell verrà visualizzato il messaggio seguente:

    "MSExchangeOWAAppPool" successfully recycled

**Configurazione dei criteri cassetta postale di Outlook Web App**

A questo punto è possibile usare il comando seguente per configurare la messaggistica istantanea nel criterio della cassetta postale di Outlook Web App appropriato (o criteri). Ad esempio, questo comando viene eseguito in uno dei server delle cassette postali, consente la messaggistica istantanea sui criteri predefiniti:

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Questo comando consente di abilitare la messaggistica istantanea per tutti i criteri delle cassette postali di Outlook Web App:

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Dopo aver abilitato il criterio delle cassette postali, tutti gli utenti gestiti da tale criterio avranno l'integrazione completa tra Lync Server e Outlook Web App, purché:

  - L'utente ha una cassetta postale in Exchange 2013.

  - L'utente è stato abilitato per Lync Server 2013.

  - L'utente ha un indirizzo proxy SIP valido.

**Disabilitazione della messaggistica istantanea in Outlook Web App**

Come indicato in precedenza, la messaggistica istantanea è abilitata per impostazione predefinita in Outlook Web App. Ciò significa che, se non si integra Outlook Web App con Lync Server, gli utenti vedranno le icone di presenza vuote e un messaggio di errore ogni volta che accedono a Outlook Web App. Per evitare questo problema, usare il comando di Exchange Management Shell seguente per disabilitare la messaggistica istantanea in Outlook Web App:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**Verifica dell'integrazione con Outlook Web App**

Per verificare che la messaggistica istantanea e la presenza siano state integrate con Outlook Web App, accedere a Outlook Web App 2013. Nell'angolo in alto a destra della schermata verrà visualizzato il nome visualizzato di Exchange. Se accanto al proprio nome è presente un'icona presenza, ad esempio un'icona verde che indica che lo stato corrente è disponibile, che indica che è stato integrato correttamente Lync Server e Outlook Web App.

Dopo l'accesso iniziale a Outlook Web App, verificare se un evento con l'ID evento 112 (e l'origine MSExchange OWA) è stato scritto nel log eventi del server cassette postali. Questo evento indica che il gestore endpoint di messaggistica istantanea è stato inizializzato correttamente. Se la messaggistica istantanea non sembra funzionare, nel server delle cassette postali cercare i file di log nella cartella C:\\programmi\\Microsoft\\Exchange Server\\V15\\registrazione\\di OWA\\instantmessaging. Se la registrazione o le cartelle di InstantMessaging non sono presenti, che indica che l'integrazione non è riuscita. In questo caso, puoi usare l'analisi di SIPStack su Lync Server (tutti i livelli e tutti i contrassegni) per provare a determinare il motivo per cui l'integrazione non è riuscita.

</div>

<span> </span>

</div>

</div>

</div>

