---
title: 'Lync Server 2013: configurazione dei criteri di avvio del client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06119d5488b47adfe01a934aca9a55581feaf33e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="bc28b-102">Configurazione dei criteri di avvio del client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc28b-102">Configuring client bootstrapping policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc28b-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="bc28b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="bc28b-104">La console Gestione criteri di gruppo e l'Editor oggetti Criteri di gruppo sono strumenti usati per gestire i criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="bc28b-104">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="bc28b-105">Incluso nel modello di amministrazione di criteri di gruppo di Office sono i modelli amministrativi di Lync 2013. ADMX (ADMX) e ADML (ADML), che contengono le impostazioni dei criteri basate sul Registro di sistema configurate per gli oggetti Criteri di gruppo nel dominio.</span><span class="sxs-lookup"><span data-stu-id="bc28b-105">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="bc28b-106">I file ADML sono complementi specifici della lingua per i file ADMX.</span><span class="sxs-lookup"><span data-stu-id="bc28b-106">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="bc28b-107">Ogni file ADMX e ADML contiene le impostazioni dei criteri per una singola applicazione di Office.</span><span class="sxs-lookup"><span data-stu-id="bc28b-107">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="bc28b-108">Per altre informazioni, vedere "file dei modelli amministrativi di Office 2013 (ADMX, ADML)" nella documentazione di Office <http://go.microsoft.com/fwlink/p/?linkid=267516>2013 all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="bc28b-108">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="bc28b-109">Per Lync 2013, sono disponibili diversi criteri di avvio del client che è consigliabile configurare prima che gli utenti accedino al server per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="bc28b-109">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="bc28b-110">Ad esempio, i server e la modalità di sicurezza predefiniti che il client deve usare fino al completamento dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="bc28b-110">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="bc28b-111">È possibile usare criteri di gruppo per stabilire queste impostazioni nei registri computer degli utenti prima di accedere e iniziare a ricevere le impostazioni di provisioning in banda dal server.</span><span class="sxs-lookup"><span data-stu-id="bc28b-111">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="bc28b-112">Nella tabella seguente sono elencate le impostazioni dei criteri di gruppo disponibili per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="bc28b-112">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="bc28b-113">Impostazioni di criteri di gruppo per Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bc28b-113">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc28b-114">Impostazione di criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="bc28b-114">Group Policy setting</span></span></th>
<th><span data-ttu-id="bc28b-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc28b-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc28b-116">Specificare il server</span><span class="sxs-lookup"><span data-stu-id="bc28b-116">Specify Server</span></span><br />
<span data-ttu-id="bc28b-117">ConfigurationMode</span><span class="sxs-lookup"><span data-stu-id="bc28b-117">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="bc28b-118">Specifica in che modo Lync 2013 identifica il trasporto e il server da usare durante l'accesso.</span><span class="sxs-lookup"><span data-stu-id="bc28b-118">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="bc28b-119">In questa impostazione è necessario specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="bc28b-119">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc28b-120">ServerAddressExternal: specifica il nome del server o l'indirizzo IP usato dai client e dai contatti federati quando ci si connette dall'esterno del firewall esterno.</span><span class="sxs-lookup"><span data-stu-id="bc28b-120">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="bc28b-121">ServerAddressInternal: specifica il nome del server o l'indirizzo IP usato quando i client si connettono dall'interno del firewall dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bc28b-121">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="bc28b-122">Transport: specifica TCP (Transmission Control Protocol) o Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="bc28b-122">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc28b-123">Versioni del server aggiuntive supportate</span><span class="sxs-lookup"><span data-stu-id="bc28b-123">Additional server versions supported</span></span><br />
<span data-ttu-id="bc28b-124">(ConfiguredServerCheckValues)</span><span class="sxs-lookup"><span data-stu-id="bc28b-124">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="bc28b-125">Specifica un elenco di nomi di versione del server separati da punti e virgola a cui Lync Server 2013 accederà, oltre alle versioni del server supportate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bc28b-125">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc28b-126">Disabilitare il caricamento automatico dei log di errore di accesso (DisableAutomaticSendTracing)</span><span class="sxs-lookup"><span data-stu-id="bc28b-126">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="bc28b-127">Carica automaticamente i registri di errore di accesso in Lync Server per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="bc28b-127">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="bc28b-128">Nessun log viene caricato automaticamente se l'accesso è riuscito.</span><span class="sxs-lookup"><span data-stu-id="bc28b-128">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="bc28b-129">Se questo criterio non è configurato, si verifica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="bc28b-129">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="bc28b-130">Per gli utenti di Lync Online: i registri di errore di accesso vengono caricati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bc28b-130">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="bc28b-131">Per gli utenti locali di Lync: la finestra di dialogo di conferma viene visualizzata all'utente prima del caricamento.</span><span class="sxs-lookup"><span data-stu-id="bc28b-131">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="bc28b-132">Quando questa impostazione è disabilitata, i log di accesso vengono caricati automaticamente nel server Lync per gli utenti di Lync locale e Lync Online.</span><span class="sxs-lookup"><span data-stu-id="bc28b-132">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="bc28b-133">Quando questa impostazione è abilitata, i log di accesso non vengono mai caricati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bc28b-133">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc28b-134">Disabilitare il fallback HTTP per la connessione SIP</span><span class="sxs-lookup"><span data-stu-id="bc28b-134">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="bc28b-135">(DisableHttpConnect)</span><span class="sxs-lookup"><span data-stu-id="bc28b-135">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="bc28b-136">Impedisce a Lync Server di provare a connettersi al server tramite HTTP, se TLS o TCP non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="bc28b-136">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="bc28b-137">Per impostazione predefinita, Lync cerca prima di connettersi al server tramite TLS o TCP e, se nessuno di questi metodi di trasporto riesce, Lync prova a connettersi tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="bc28b-137">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="bc28b-138">Usare questo criterio per disabilitare il tentativo di connessione HTTP di fallback.</span><span class="sxs-lookup"><span data-stu-id="bc28b-138">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc28b-139">Richiedere le credenziali di accesso</span><span class="sxs-lookup"><span data-stu-id="bc28b-139">Require logon credentials</span></span><br />
<span data-ttu-id="bc28b-140">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="bc28b-140">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="bc28b-141">Richiede all'utente di specificare le credenziali di accesso per Lync anziché utilizzare automaticamente le credenziali di Windows durante l'accesso a un server SIP.</span><span class="sxs-lookup"><span data-stu-id="bc28b-141">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc28b-142">Disabilitare il controllo della versione del server</span><span class="sxs-lookup"><span data-stu-id="bc28b-142">Disable server version check</span></span><br />
<span data-ttu-id="bc28b-143">(DisableServerCheck)</span><span class="sxs-lookup"><span data-stu-id="bc28b-143">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="bc28b-144">Se si imposta questo criterio su 1, viene impedito a Lync di verificare il nome e la versione del server prima dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="bc28b-144">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="bc28b-145">Per impostazione predefinita, Lync effettua questi controlli prima di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="bc28b-145">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc28b-146">Abilitare l'uso di bit per scaricare i file del servizio Rubrica</span><span class="sxs-lookup"><span data-stu-id="bc28b-146">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="bc28b-147">(EnableBitsForGalDownload)</span><span class="sxs-lookup"><span data-stu-id="bc28b-147">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="bc28b-148">Consente a Lync di usare il servizio di trasferimento intelligente in background (BITS) per scaricare i file dei servizi Rubrica.</span><span class="sxs-lookup"><span data-stu-id="bc28b-148">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc28b-149">Configurare la modalità di sicurezza SIP</span><span class="sxs-lookup"><span data-stu-id="bc28b-149">Configure SIP security mode</span></span><br />
<span data-ttu-id="bc28b-150">(EnableSIPHighSecurityMode)</span><span class="sxs-lookup"><span data-stu-id="bc28b-150">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="bc28b-151">Consente a Lync di inviare e ricevere messaggi istantanei in modo più sicuro.</span><span class="sxs-lookup"><span data-stu-id="bc28b-151">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="bc28b-152">Questo criterio non ha alcun effetto sui servizi Windows .NET o Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="bc28b-152">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="bc28b-153">Se non si configura questa impostazione, Lync può usare qualsiasi trasporto.</span><span class="sxs-lookup"><span data-stu-id="bc28b-153">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="bc28b-154">Ma se non usa TLS e se il server autentica gli utenti, Lync deve usare l'autenticazione NTLM o Kerberos.</span><span class="sxs-lookup"><span data-stu-id="bc28b-154">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc28b-155">Scarica il ritardo iniziale della Rubrica globale</span><span class="sxs-lookup"><span data-stu-id="bc28b-155">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="bc28b-156">(GalDownloadInitialDelay)</span><span class="sxs-lookup"><span data-stu-id="bc28b-156">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="bc28b-157">Specifica il periodo di tempo prima che si verifichi il download dell'elenco indirizzi globale (GAL).</span><span class="sxs-lookup"><span data-stu-id="bc28b-157">Specifies the time period before a download of the global address list (GAL) occurs.</span></span> <span data-ttu-id="bc28b-158">Il valore predefinito è 60 minuti, quindi il server ritarda il download del file GAL per un periodo casuale compreso tra 0 e 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="bc28b-158">The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc28b-159">Evitare che gli utenti eseguano Microsoft Lync</span><span class="sxs-lookup"><span data-stu-id="bc28b-159">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="bc28b-160">(PreventRun)</span><span class="sxs-lookup"><span data-stu-id="bc28b-160">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="bc28b-161">Impedisce agli utenti di eseguire Lync.</span><span class="sxs-lookup"><span data-stu-id="bc28b-161">Prevents users from running Lync.</span></span> <span data-ttu-id="bc28b-162">È possibile configurare questa impostazione per i criteri in configurazione computer e configurazione utente, ma l'impostazione dei criteri in configurazione computer ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="bc28b-162">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc28b-163">Consentire l'archiviazione delle password degli utenti</span><span class="sxs-lookup"><span data-stu-id="bc28b-163">Allow storage of user passwords</span></span><br />
<span data-ttu-id="bc28b-164">(SavePassword)</span><span class="sxs-lookup"><span data-stu-id="bc28b-164">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="bc28b-165">Consente a Lync di archiviare le password.</span><span class="sxs-lookup"><span data-stu-id="bc28b-165">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc28b-166">Configurare la modalità di compressione SIP</span><span class="sxs-lookup"><span data-stu-id="bc28b-166">Configure SIP compression mode</span></span><br />
<span data-ttu-id="bc28b-167">SipCompression</span><span class="sxs-lookup"><span data-stu-id="bc28b-167">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="bc28b-168">Specifica quando attivare la compressione SIP.</span><span class="sxs-lookup"><span data-stu-id="bc28b-168">Specifies when to turn on SIP compression.</span></span> <span data-ttu-id="bc28b-169">Per impostazione predefinita, la compressione SIP è abilitata in base alla velocità della scheda.</span><span class="sxs-lookup"><span data-stu-id="bc28b-169">By default, SIP compression is enabled based on the adapter speed.</span></span> <span data-ttu-id="bc28b-170">Tieni presente che l'impostazione di questo criterio può causare un aumento dell'ora di accesso.</span><span class="sxs-lookup"><span data-stu-id="bc28b-170">Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc28b-171">Elenco domini attendibili</span><span class="sxs-lookup"><span data-stu-id="bc28b-171">Trusted Domain List</span></span><br />
<span data-ttu-id="bc28b-172">TrustModelData</span><span class="sxs-lookup"><span data-stu-id="bc28b-172">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="bc28b-173">Elenca i domini attendibili che non corrispondono al prefisso del dominio SIP del cliente.</span><span class="sxs-lookup"><span data-stu-id="bc28b-173">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bc28b-174">I criteri configurati nel server hanno la precedenza sulle impostazioni dei criteri di gruppo e le opzioni client configurate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="bc28b-174">Policies configured on the server take precedence over Group Policy settings and client options configured by the user.</span></span> <span data-ttu-id="bc28b-175">Nella tabella seguente viene riepilogato l'ordine in cui le impostazioni hanno la precedenza quando si verifica un conflitto.</span><span class="sxs-lookup"><span data-stu-id="bc28b-175">The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="bc28b-176">Precedenza dei criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="bc28b-176">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc28b-177">Precedenza</span><span class="sxs-lookup"><span data-stu-id="bc28b-177">Precedence</span></span></th>
<th><span data-ttu-id="bc28b-178">Posizione o metodo di impostazione</span><span class="sxs-lookup"><span data-stu-id="bc28b-178">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc28b-179">1</span><span class="sxs-lookup"><span data-stu-id="bc28b-179">1</span></span></p></td>
<td><p><span data-ttu-id="bc28b-180">Provisioning in-band di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc28b-180">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc28b-181">2</span><span class="sxs-lookup"><span data-stu-id="bc28b-181">2</span></span></p></td>
<td><p><span data-ttu-id="bc28b-182">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="bc28b-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc28b-183">3</span><span class="sxs-lookup"><span data-stu-id="bc28b-183">3</span></span></p></td>
<td><p><span data-ttu-id="bc28b-184">HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="bc28b-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc28b-185">4</span><span class="sxs-lookup"><span data-stu-id="bc28b-185">4</span></span></p></td>
<td><p><span data-ttu-id="bc28b-186">Finestra di dialogo Lync-Opzioni in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bc28b-186">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="bc28b-187">Per definire le impostazioni dei criteri di gruppo usando i file dei modelli amministrativi di Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bc28b-187">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="bc28b-188">Creare una cartella a livello radice per contenere tutti i file ADMX indipendenti dalla lingua.</span><span class="sxs-lookup"><span data-stu-id="bc28b-188">Create a root-level folder to contain all language-neutral ADMX files.</span></span> <span data-ttu-id="bc28b-189">Ad esempio, crea la cartella radice per l'archivio centrale nel controller di dominio in questa posizione:</span><span class="sxs-lookup"><span data-stu-id="bc28b-189">For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bc28b-190">In questa procedura si presuppone che si vogliano gestire più computer nel dominio.</span><span class="sxs-lookup"><span data-stu-id="bc28b-190">This procedure assumes that you want to manage multiple computers in your domain.</span></span> <span data-ttu-id="bc28b-191">In questo caso, i modelli vengono archiviati in un archivio centrale nella cartella SYSVOL del controller di dominio primario.</span><span class="sxs-lookup"><span data-stu-id="bc28b-191">In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller.</span></span> <span data-ttu-id="bc28b-192">In questo modo viene fornito un percorso di archiviazione centralizzato replicato per i modelli amministrativi del dominio.</span><span class="sxs-lookup"><span data-stu-id="bc28b-192">This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="bc28b-193">Creare una sottocartella per ogni lingua che verrà usata.</span><span class="sxs-lookup"><span data-stu-id="bc28b-193">Create a subfolder for each language that you’ll use.</span></span> <span data-ttu-id="bc28b-194">Queste sottocartelle conterranno i file di risorse ADML specifici della lingua.</span><span class="sxs-lookup"><span data-stu-id="bc28b-194">These subfolders will contain the language-specific ADML resource files.</span></span> <span data-ttu-id="bc28b-195">Ad esempio, creare una sottocartella per gli Stati Uniti in inglese (EN-US) in questa posizione:</span><span class="sxs-lookup"><span data-stu-id="bc28b-195">For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

