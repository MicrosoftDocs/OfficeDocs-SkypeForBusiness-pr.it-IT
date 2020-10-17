---
title: 'Lync Server 2013: integrazione di Lync Server e Outlook Web App 2013'
description: 'Lync Server 2013: integrazione di Lync Server e Outlook Web App 2013.'
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
ms.openlocfilehash: 0d9c7e91dba22f78325eaddc5b5d7469ccf4cc92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567392"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a><span data-ttu-id="3deaf-103">Integrazione di Microsoft Lync Server 2013 e Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="3deaf-103">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3deaf-104">_**Ultimo argomento modificato:** 2013-02-03_</span><span class="sxs-lookup"><span data-stu-id="3deaf-104">_**Topic Last Modified:** 2013-02-03_</span></span>

<span data-ttu-id="3deaf-105">Oltre all'integrazione con Microsoft Outlook 2013, Microsoft Lync Server 2013 può essere completamente integrato con Microsoft Outlook Web App 2013; tra le altre cose, questo aggiunge la messaggistica istantanea e la presenza in Outlook Web App e consente di condividere l'elenco di contatti unificato tra Outlook Web App e Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3deaf-105">In addition to integrating with Microsoft Outlook 2013, Microsoft Lync Server 2013 can be fully integrated with Microsoft Outlook Web App 2013; among other things, this adds instant messaging and presence to Outlook Web App, and enables your unified contact list to be shared between Outlook Web App and Microsoft Lync 2013.</span></span> <span data-ttu-id="3deaf-106">Per integrare Lync Server 2013 e Outlook Web App, è innanzitutto necessario verificare che Unified Communications Managed API 4,0 Runtime sia stato installato nel server back-end di Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3deaf-106">In order to integrate Lync Server 2013 and Outlook Web App, you must first verify that the Unified Communications Managed API 4.0 Runtime has been installed in your Microsoft Exchange Server 2013 backend server.</span></span> <span data-ttu-id="3deaf-107">Per integrare nm-server-w15-long e Outlook Web Access, è necessario prima di tutto verificare che Unified Communications Managed API 4.0 Runtime sia installato nel server back-end nm-exch-15-formal, controllando se nel Registro di sistema è presente il valore seguente:</span><span class="sxs-lookup"><span data-stu-id="3deaf-107">You can do this by looking for the existence of the following registry value:</span></span>

<span data-ttu-id="3deaf-108">HKEY \_ Local \_ Machine \\ System \\ CurrentControlSet \\ Services \\ MSExchange OWA \\ InstantMessaging \\ ImplementationDLLPath</span><span class="sxs-lookup"><span data-stu-id="3deaf-108">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath</span></span>

<span data-ttu-id="3deaf-109">Il ImplementationDLLPath deve puntare al percorso della cartella per il file Microsoft.Rtc.Internal.Ucweb.dll.</span><span class="sxs-lookup"><span data-stu-id="3deaf-109">The ImplementationDLLPath should point to the folder location for the file Microsoft.Rtc.Internal.Ucweb.dll.</span></span> <span data-ttu-id="3deaf-110">In caso contrario, o se il valore del registro di sistema non esiste, è necessario scaricare e installare il programma di installazione di UCMA runtime dall'area download Microsoft all'indirizzo <https://www.microsoft.com/download/details.aspx?id=34992> .</span><span class="sxs-lookup"><span data-stu-id="3deaf-110">If it does not, or if the registry value does not exist, then you should download and install the UCMA Runtime setup program from the Microsoft Download Center at <https://www.microsoft.com/download/details.aspx?id=34992>.</span></span> <span data-ttu-id="3deaf-111">Le informazioni su come installare il runtime di UCMA sono disponibili nella stessa pagina Web.</span><span class="sxs-lookup"><span data-stu-id="3deaf-111">Information on how to install the UCMA Runtime can be found on that same web page.</span></span>

<span data-ttu-id="3deaf-112">**Compatibilità con le versioni precedenti**</span><span class="sxs-lookup"><span data-stu-id="3deaf-112">**Backward Compatibility**</span></span>

<span data-ttu-id="3deaf-113">Lync Server 2013 può essere integrato con le versioni di Microsoft Exchange Server 2010 di messaggistica unificata e Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="3deaf-113">Lync Server 2013 can be integrated with the Microsoft Exchange Server 2010 versions of both unified messaging and Outlook Web App.</span></span> <span data-ttu-id="3deaf-114">Per ulteriori informazioni, vedere l'articolo Deploying on-premises Exchange Messaggistica unificata per fornire Lync Server 2010 segreteria telefonica [https://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) .</span><span class="sxs-lookup"><span data-stu-id="3deaf-114">For more information, see the article Deploying On-Premises Exchange UM to Provide Lync Server 2010 Voice Mail at [https://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md).</span></span> <span data-ttu-id="3deaf-115">Se si integra con Exchange 2010, non si disporranno di funzionalità specifiche di Lync Server, come l'archivio contatti unificato e l'archiviazione Lync-to-Exchange.</span><span class="sxs-lookup"><span data-stu-id="3deaf-115">If you integrate with Exchange 2010 you will not have Lync Server specific features such as the unified contact store and Lync-to-Exchange archiving.</span></span>

<span data-ttu-id="3deaf-116">Microsoft Lync 2013 può essere utilizzato anche in combinazione con Exchange 2010 e Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="3deaf-116">Microsoft Lync 2013 can also be used in conjunction with Exchange 2010 and Outlook 2010.</span></span> <span data-ttu-id="3deaf-117">Ancora una volta, tuttavia, le nuove funzionalità come l'archivio contatti unificato e le foto ad alta risoluzione non saranno disponibili per gli utenti di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3deaf-117">Once again, however, new functionality such as the unified contact store and high-resolution photos will not be available to Lync 2013 users.</span></span> <span data-ttu-id="3deaf-118">Queste nuove funzionalità richiedono sia Lync Server 2013 sia Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="3deaf-118">These new capabilities require both Lync Server 2013 and Exchange 2013.</span></span>

<span data-ttu-id="3deaf-119">**Creazione di un pool di applicazioni attendibili per Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="3deaf-119">**Creating a Trusted Application Pool for Outlook Web App**</span></span>

<span data-ttu-id="3deaf-120">Se il servizio di routing delle chiamate di messaggistica unificata di Microsoft Exchange e il servizio di messaggistica unificata di Microsoft Exchange sono stati installati nello stesso computer, non è necessario creare un pool di applicazioni attendibili per Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="3deaf-120">If you have installed the Microsoft Exchange Unified Messaging Call Router service and the Microsoft Exchange Unified Messaging service on the same computer then there is no need to create a trusted application pool for Outlook Web App.</span></span> <span data-ttu-id="3deaf-121">Si presuppone che il server in questione ospita un dial plan di messaggistica unificata di SipName. Se si utilizza un singolo computer per ospitare entrambi i servizi, è possibile passare alla sezione di questo documento che consente di abilitare la **messaggistica istantanea in Outlook Web App**.</span><span class="sxs-lookup"><span data-stu-id="3deaf-121">(This assumes that the server in question is hosting a SipName UM dial plan.) If you are using a single computer to host both of these services then you can skip to the section of this document titled **Enabling Instant Messaging on Outlook Web App**.</span></span>

<span data-ttu-id="3deaf-122">Lync Server 2013 è in grado di individuare tutti i server Exchange che ospitano un dial plan di messaggistica unificata di SipName. questi server vengono aggiunti automaticamente all'elenco dei server noti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3deaf-122">Lync Server 2013 can autodiscover any Exchange servers that host a SipName UM dial plan; these servers are automatically added to the Lync Server Known Servers List.</span></span> <span data-ttu-id="3deaf-123">Non è necessario creare un pool di applicazioni attendibili e aggiungere questi server all'elenco dei server noti.</span><span class="sxs-lookup"><span data-stu-id="3deaf-123">There is no need to create a trusted application pool and add these servers to the Known Servers List.</span></span> <span data-ttu-id="3deaf-124">In effetti, in questo modo l'integrazione di Outlook Web App smetterà di funzionare.</span><span class="sxs-lookup"><span data-stu-id="3deaf-124">In fact, doing so will cause Outlook Web App integration to stop working.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3deaf-125">Ciò è dovuto al fatto che la topologia di Lync Server avrà ora due voci per lo stesso computer: la voce di individuazione automatica e la voce aggiunta manualmente.</span><span class="sxs-lookup"><span data-stu-id="3deaf-125">This is due to the fact that the Lync Server topology will now have two entries for the same computer: the autodiscovered entry, and the manually-added entry.</span></span> <span data-ttu-id="3deaf-126">Per risolvere il problema e per riattivare l'utilizzo di Outlook Web App, utilizzare Windows PowerShell per rimuovere il pool attendibile e le voci dell'applicazione attendibile per il server.</span><span class="sxs-lookup"><span data-stu-id="3deaf-126">To fix the problem, and to get Outlook Web App working again, use Windows PowerShell to remove the trusted pool and trusted application entries for the server.</span></span> <span data-ttu-id="3deaf-127">Per ulteriori informazioni, vedere gli argomenti della Guida per i cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> .</span><span class="sxs-lookup"><span data-stu-id="3deaf-127">See the help topics for the <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> cmdlets for more information.</span></span>



</div>

<span data-ttu-id="3deaf-128">Se questi due servizi sono in esecuzione su computer separati, dopo aver verificato che l'API Managed Communications Unified 4,0 Runtime è stato installato, è necessario creare un pool di applicazioni attendibili di Lync Server e un'applicazione attendibile associata a Outlook Web App. che consente di aggiungere il server all'elenco dei server noti.</span><span class="sxs-lookup"><span data-stu-id="3deaf-128">If these two services are running on separate computers then, after you have verified that the Unified Communications Managed API 4.0 Runtime has been installed, you must create a Lync Server trusted application pool and a trusted application associated with Outlook Web App; that will add the server to the Known Servers List.</span></span> <span data-ttu-id="3deaf-129">A tale scopo, eseguire innanzitutto un comando simile al seguente dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="3deaf-129">To do that, first run a command similar to this from within the Lync Server Management Shell:</span></span>

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

<span data-ttu-id="3deaf-130">Nel comando precedente, atl-owa-001.litwareinc.com è il nome di dominio completo del pool di Outlook Web App. Questo deve essere lo stesso nome visualizzato nei campi nome soggetto e nome alternativo soggetto (SAN) del certificato che consente l'accesso a Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="3deaf-130">In the preceding command, atl-owa-001.litwareinc.com is the fully qualified domain name of the Outlook Web App pool; this must be the same name that appears in the Subject Name and Subject Alternative Name (SAN) fields of the certificate that provides access to Outlook Web App.</span></span> <span data-ttu-id="3deaf-131">Analogamente, atl-cs-001.litwareinc.com è il nome di dominio completo del pool di Lync Server 2013 che ospiterà il nuovo pool di applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="3deaf-131">Likewise, atl-cs-001.litwareinc.com is the fully qualified domain name of the Lync Server 2013 pool that will host the new trusted application pool.</span></span> <span data-ttu-id="3deaf-132">Si noti, inoltre, che il sito specificato, Redmond, rappresenta la SiteID del sito di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3deaf-132">Note, too that the specified site, Redmond, represents the SiteID of the Lync Server site.</span></span> <span data-ttu-id="3deaf-133">SiteID non è necessariamente uguale al DisplayName del sito. è possibile recuperare SiteIDs per i siti di Lync Server eseguendo il comando seguente da Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="3deaf-133">The SiteID is not necessarily the same as the site's DisplayName; you can retrieve SiteIDs for your Lync Server sites by running the following command from the Lync Server Management Shell:</span></span>

    Get-CsSite | Select-Object DisplayName, SiteID

<span data-ttu-id="3deaf-134">Dopo aver creato il pool di applicazioni attendibili, utilizzare un comando simile al seguente per configurare un'identità di applicazione e una porta per Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="3deaf-134">After creating the trusted application pool, use a command similar to the following to configure an application Identity and a port for Outlook Web App:</span></span>

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

<span data-ttu-id="3deaf-p110">Nel comando precedente, ApplicationID è un identificatore descrittivo usato per distinguere le applicazioni attendibili. Come ApplicationID si può usare qualsiasi stringa di testo che non comprenda spazi o altri caratteri non consentiti. Per creare un identificatore valido, assicurarsi di usare solo lettere e numeri. Anche il valore assegnato al parametro Port è a discrezione dell'amministratore e può corrispondere a qualsiasi porta di rete disponibile.</span><span class="sxs-lookup"><span data-stu-id="3deaf-p110">In the preceding command, the ApplicationID is simply a friendly identifier used to distinguish trusted applications. The ApplicationID can be any text string that does not include blank spaces or other prohibited characters. (To ensure that you create a valid identifier, it is recommended that you use only letters and numbers when specifying an ApplicationId.) The value assigned to the Port parameter is also left to the administrator's discretion: this can be any available network port.</span></span>

<span data-ttu-id="3deaf-138">Dopo aver creato l'applicazione attendibile, è necessario eseguire il comando seguente per abilitare le modifiche apportate alla topologia di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="3deaf-138">After creating the trusted application you must run the following command to enable the changes to your Lync Server topology:</span></span>

    Enable-CsTopology

<span data-ttu-id="3deaf-139">Tenere presente che è inoltre necessario aggiungere il server Accesso client e cassette postali di Exchange a tutti i dial plan URI SIP.</span><span class="sxs-lookup"><span data-stu-id="3deaf-139">Note that you must also add your Exchange client access and mailbox server to all of your SIP Uri dial plans.</span></span> <span data-ttu-id="3deaf-140">In questo modo, verranno configurati i server come peer SIP attendibili con la topologia di ExUmRouting per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3deaf-140">In turn, this will configure the servers as trusted SIP peers with the ExUmRouting topology for Lync Server.</span></span>

<span data-ttu-id="3deaf-141">**Abilitazione della messaggistica istantanea in Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="3deaf-141">**Enabling Instant Messaging on Outlook Web App**</span></span>

<span data-ttu-id="3deaf-142">Se Lync Server è stato configurato correttamente, è possibile iniziare a configurare Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="3deaf-142">With Lync Server correctly configured you can then begin to configure Outlook Web App.</span></span> <span data-ttu-id="3deaf-143">Il primo passaggio del processo consiste nell'abilitare la messaggistica istantanea su tutte le directory virtuali di Outlook Web App nei server front end.</span><span class="sxs-lookup"><span data-stu-id="3deaf-143">The first step in that process is to enable instant messaging on all your Outlook Web App virtual directories on your front end servers.</span></span> <span data-ttu-id="3deaf-144">Non è necessario abilitare la messaggistica istantanea per le directory virtuali nei server back-end.</span><span class="sxs-lookup"><span data-stu-id="3deaf-144">(There is no need to enable instant messaging for the virtual directories on your backend servers.</span></span> <span data-ttu-id="3deaf-145">In effetti, si consiglia di non abilitare la messaggistica istantanea nei server back-end. La messaggistica istantanea può essere abilitata sui server Accesso client eseguendo il comando riportato di seguito dall'interno di Exchange Management Shell:</span><span class="sxs-lookup"><span data-stu-id="3deaf-145">In fact, it is recommended that you do not enable instant messaging on your backend servers.) Instant messaging can be enabled on the client access servers by running the following command from within the Exchange Management Shell:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> <span data-ttu-id="3deaf-146">Per impostazione predefinita, la messaggistica istantanea è abilitata quando si installa Outlook Web App. in altre condizioni, la proprietà InstantMessagingEnabled consente è impostata su true.</span><span class="sxs-lookup"><span data-stu-id="3deaf-146">By default, instant messaging is enabled when you install Outlook Web App; that is, the InstantMessagingEnabled property is set to True.</span></span> <span data-ttu-id="3deaf-147">Tuttavia, è comunque necessario eseguire il comando precedente per impostare il tipo di messaggistica istantanea su OCS.</span><span class="sxs-lookup"><span data-stu-id="3deaf-147">However, you must still run the preceding command in order to set the instant messaging type to OCS.</span></span> <span data-ttu-id="3deaf-148">Per impostazione predefinita, InstantMessagingType è impostato su None.</span><span class="sxs-lookup"><span data-stu-id="3deaf-148">By default, InstantMessagingType is set to None.</span></span>



</div>

<span data-ttu-id="3deaf-149">Successivamente, è necessario aggiungere le due righe seguenti a Outlook Web App Web.config file (questo file si trova in genere nella cartella C: \\ Program Files \\ Microsoft \\ Exchange Server \\ V15 \\ ClientAccess \\ OWA).</span><span class="sxs-lookup"><span data-stu-id="3deaf-149">Next you must add the following two lines to Outlook Web App Web.config file (this file is typically located in the folder C:\\Program Files\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa).</span></span> <span data-ttu-id="3deaf-150">Queste due righe devono essere aggiunte sotto il \<AppSettings\> nodo nel file Web.config e questa procedura deve essere eseguita solo sui server back-end in cui è stato installato Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="3deaf-150">These two lines should be added under the \<AppSettings\> node in the Web.config file, and this procedure should be carried out only on the backend servers where Outlook Web App has been installed:</span></span>

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

<span data-ttu-id="3deaf-151">Nell'esempio precedente, il valore di IMCertificateThumbprint deve essere l'identificazione personale del certificato di Exchange 2013 installato nei server back-end.</span><span class="sxs-lookup"><span data-stu-id="3deaf-151">In the preceding example, the value for IMCertificateThumbprint must be the thumbprint for the Exchange 2013 certificate that is installed on your backend servers.</span></span> <span data-ttu-id="3deaf-152">È possibile recuperare tali informazioni eseguendo il comando seguente da Exchange Management Shell:</span><span class="sxs-lookup"><span data-stu-id="3deaf-152">You can retrieve that information by running the following command from the Exchange Management Shell:</span></span>

    Get-ExchangeCertificate

<span data-ttu-id="3deaf-153">Si noti, inoltre, che il valore assegnato a imservername è il nome di dominio completo del pool di Lync Server in cui è stato creato il pool di applicazioni attendibili per Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="3deaf-153">Note, too that the value assigned to IMServerName is the fully qualified domain name of the Lync Server pool where you created the trusted application pool for Outlook Web App.</span></span>

<span data-ttu-id="3deaf-154">Il certificato utilizzato per Outlook Web App deve essere un certificato considerato attendibile da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3deaf-154">The certificate that you use for Outlook Web App must be a certificate that is trusted by Lync Server.</span></span> <span data-ttu-id="3deaf-155">Un modo per assicurarsi che il certificato sia considerato attendibile sia da Lync Server che da Exchange consiste nell'utilizzare l'autorità di certificazione interna per creare un certificato nel server cassette postali, assicurandosi che il nome di dominio completo del server sia utilizzato per l'oggetto Name e che questo FQDN venga visualizzato nel campo nome alternativo certificato.</span><span class="sxs-lookup"><span data-stu-id="3deaf-155">One way to ensure that the certificate will be trusted by both Lync Server and Exchange is to use your internal certificate authority to create a certificate on the mailbox server, making sure that the server FQDN is used for the subject name and that this FQDN appears in the certificate alternate name field.</span></span> <span data-ttu-id="3deaf-156">Dopo aver creato il certificato, è possibile importarlo nei server back-end.</span><span class="sxs-lookup"><span data-stu-id="3deaf-156">After the certificate has been created it can then be imported to your backend servers.</span></span> <span data-ttu-id="3deaf-157">Il risultato netto è che lo stesso certificato viene utilizzato per due scopi: 1) comunicazione tra la messaggistica unificata di Exchange e Lync Server; e 2) l'integrazione tra Outlook Web App e Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3deaf-157">The net result is that the same certificate is used for two purposes: 1) communication between Exchange unified messaging and Lync Server; and, 2) the integration between Outlook Web App and Lync Server.</span></span>

<span data-ttu-id="3deaf-158">Dopo aver aggiornato il file Web.config, è necessario eseguire il comando riportato di seguito sul server back-end di Exchange per riciclare il pool di Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="3deaf-158">After you have updated the Web.config file you should then run the following command on the Exchange backend server in order to recycle the Outlook Web App pool:</span></span>

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

<span data-ttu-id="3deaf-159">Se l'operazione di riciclo ha esito positivo, verrà visualizzato il messaggio seguente in Exchange Management Shell:</span><span class="sxs-lookup"><span data-stu-id="3deaf-159">If the recycle operation succeeds you will see the following message in the Exchange Management Shell:</span></span>

    "MSExchangeOWAAppPool" successfully recycled

<span data-ttu-id="3deaf-160">**Configurazione di criteri cassetta postale di Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="3deaf-160">**Configuring Outlook Web App Mailbox Policies**</span></span>

<span data-ttu-id="3deaf-161">A questo punto è possibile utilizzare il seguente comando per configurare la messaggistica istantanea sul criterio cassetta postale di Outlook Web App appropriato (o sui criteri).</span><span class="sxs-lookup"><span data-stu-id="3deaf-161">At this point you can use the following command to configure instant messaging on the appropriate Outlook Web App mailbox policy (or policies).</span></span> <span data-ttu-id="3deaf-162">Ad esempio, questo comando, eseguito su uno dei server cassette postali, consente di abilitare la messaggistica istantanea nel criterio predefinito:</span><span class="sxs-lookup"><span data-stu-id="3deaf-162">For example, this command, run on one of your mailbox servers, enables instant messaging on the Default policy:</span></span>

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="3deaf-163">Questo comando consente di abilitare la messaggistica istantanea per tutti i criteri cassetta postale di Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="3deaf-163">And this command enables instant messaging for all your Outlook Web App mailbox policies:</span></span>

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="3deaf-164">Dopo che il criterio cassetta postale è stato abilitato, tutti gli utenti gestiti da tale criterio avranno una completa integrazione tra Lync Server e Outlook Web App, purché:</span><span class="sxs-lookup"><span data-stu-id="3deaf-164">After the mailbox policy has been enabled then all users managed by that policy will have full integration between Lync Server and Outlook Web App, provided that:</span></span>

  - <span data-ttu-id="3deaf-165">L'utente dispone di una cassetta postale su Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="3deaf-165">The user has a mailbox on Exchange 2013.</span></span>

  - <span data-ttu-id="3deaf-166">L'utente è stato abilitato per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3deaf-166">The user has been enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="3deaf-167">Dispongano di un indirizzo proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="3deaf-167">The user has a valid SIP proxy address.</span></span>

<span data-ttu-id="3deaf-168">**Disabilitazione della messaggistica istantanea in Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="3deaf-168">**Disabling Instant Messaging in Outlook Web App**</span></span>

<span data-ttu-id="3deaf-169">Come indicato in precedenza, la messaggistica istantanea è abilitata per impostazione predefinita in Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="3deaf-169">As noted previously, instant messaging is enabled by default in Outlook Web App.</span></span> <span data-ttu-id="3deaf-170">Ciò significa che, se non si integra Outlook Web App con Lync Server, gli utenti visualizzeranno le icone di presenza vuote e un messaggio di errore ogni volta che accedono a Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="3deaf-170">That means that, if you do not integrate Outlook Web App with Lync Server, users will see blank presence icons and an error message each time they log on to Outlook Web App.</span></span> <span data-ttu-id="3deaf-171">Per evitare questo problema, utilizzare il seguente comando di Exchange Management Shell per disabilitare la messaggistica istantanea in Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="3deaf-171">To prevent this problem, use the following Exchange Management Shell command to disable instant messaging in Outlook web App:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

<span data-ttu-id="3deaf-172">**Verifica dell'integrazione con Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="3deaf-172">**Verifying Integration With Outlook Web App**</span></span>

<span data-ttu-id="3deaf-173">Per verificare che la messaggistica istantanea e la presenza siano state integrate con Outlook Web App, accedere a Outlook Web App 2013.</span><span class="sxs-lookup"><span data-stu-id="3deaf-173">To verify that instant messaging and presence have been integrated with Outlook Web App, sign on to Outlook Web App 2013.</span></span> <span data-ttu-id="3deaf-174">Nell'angolo in alto a destra dello schermo è visibile il proprio nome visualizzato Exchange.</span><span class="sxs-lookup"><span data-stu-id="3deaf-174">In the upper right-hand corner of the screen, you will see your Exchange display name.</span></span> <span data-ttu-id="3deaf-175">Se accanto al nome è presente un'icona presenza, ad esempio un'icona verde che indica che lo stato corrente è disponibile, che indica che è stato integrato correttamente Lync Server e Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="3deaf-175">If there is a presence icon next to your name (for example, a green icon indicating that your current status is Available) that indicates that you have successfully integrated Lync Server and Outlook Web App.</span></span>

<span data-ttu-id="3deaf-176">Dopo aver eseguito l'accesso iniziale a Outlook Web App, controllare se un evento con l'ID evento 112 (e l'origine MSExchange OWA) è stato scritto nel registro eventi sul server cassette postali.</span><span class="sxs-lookup"><span data-stu-id="3deaf-176">After the initial sign-on to Outlook Web App, check to see if an event with the Event ID 112 (and the source MSExchange OWA) has been written to the event log on the mailbox server.</span></span> <span data-ttu-id="3deaf-177">Questo evento indica che il gestore endpoint di messaggistica istantanea è stato inizializzato correttamente.</span><span class="sxs-lookup"><span data-stu-id="3deaf-177">This event indicates that the Instant Messaging Endpoint Manager was successfully initialized.</span></span> <span data-ttu-id="3deaf-178">Se la messaggistica istantanea non sembra funzionare, nel server cassette postali individuare i file di registro nella cartella C: \\ Program Files \\ Microsoft \\ Exchange Server \\ V15 \\ Logging \\ owa \\ instantmessaging.</span><span class="sxs-lookup"><span data-stu-id="3deaf-178">If instant messaging does not appear to be working then, on the mailbox server, look for log files in the folder C:\\Program Files\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging.</span></span> <span data-ttu-id="3deaf-179">Se le cartelle logging o InstantMessaging non esistono che indicano che l'integrazione ha avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3deaf-179">If either the Logging or the InstantMessaging folders do not exist that indicates that integration has failed.</span></span> <span data-ttu-id="3deaf-180">In tal caso, è possibile utilizzare l'analisi di SIPStack su Lync Server (tutti i livelli e tutti i flag) per provare a determinare il motivo per cui l'integrazione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="3deaf-180">In that case, you can use SIPStack tracing on Lync Server (All Levels and All Flags) to try and determine why integration failed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

