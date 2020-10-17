---
title: 'Lync Server 2013: configurazione dei criteri di avvio automatico dei client'
description: 'Lync Server 2013: configurazione dei criteri di avvio automatico dei client.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c03a9f7954d42f128dd6ae96296069ae5a515e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545632"
---
# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="fdb43-103">Configurazione dei criteri di avvio automatico dei client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdb43-103">Configuring client bootstrapping policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdb43-104">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="fdb43-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="fdb43-105">La console Gestione criteri di gruppo e l'Editor oggetti Criteri di gruppo sono strumenti che è possibile utilizzare per gestire i criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="fdb43-105">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="fdb43-106">Con il modello amministrativo di criteri di gruppo di Office sono inclusi i modelli amministrativi di Lync 2013. ADMX (ADMX) e ADML (ADML), che contengono le impostazioni dei criteri basati sul Registro di sistema che vengono configurate per gli oggetti Criteri di gruppo nel dominio.</span><span class="sxs-lookup"><span data-stu-id="fdb43-106">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="fdb43-107">I file ADML sono complementi specifici della lingua per i file ADMX.</span><span class="sxs-lookup"><span data-stu-id="fdb43-107">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="fdb43-108">Ogni file ADMX e ADML contiene le impostazioni dei criteri per una singola applicazione di Office.</span><span class="sxs-lookup"><span data-stu-id="fdb43-108">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="fdb43-109">Per ulteriori informazioni, vedere "file dei modelli amministrativi di Office 2013 (ADMX, ADML)" nella documentazione di Office 2013 all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=267516> .</span><span class="sxs-lookup"><span data-stu-id="fdb43-109">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="fdb43-110">Per Lync 2013, sono disponibili diversi criteri di avvio del client che è consigliabile configurare prima che gli utenti eseguano l'accesso al server per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="fdb43-110">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="fdb43-111">Ad esempio, i server e la modalità di sicurezza predefiniti che il client deve utilizzare fino al completamento dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="fdb43-111">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="fdb43-112">È possibile utilizzare criteri di gruppo per definire queste impostazioni nei registri dei computer degli utenti prima di accedere e iniziare a ricevere le impostazioni di provisioning in banda dal server.</span><span class="sxs-lookup"><span data-stu-id="fdb43-112">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="fdb43-113">Nella tabella seguente sono elencate le impostazioni di criteri di gruppo disponibili per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="fdb43-113">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="fdb43-114">Impostazione dei criteri di gruppo per Lync 2013</span><span class="sxs-lookup"><span data-stu-id="fdb43-114">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdb43-115">Impostazione dei criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="fdb43-115">Group Policy setting</span></span></th>
<th><span data-ttu-id="fdb43-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fdb43-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdb43-117">Specificare il server</span><span class="sxs-lookup"><span data-stu-id="fdb43-117">Specify Server</span></span><br />
<span data-ttu-id="fdb43-118">ConfigurationMode</span><span class="sxs-lookup"><span data-stu-id="fdb43-118">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="fdb43-119">Specifica il modo in cui Lync 2013 identifica il trasporto e il server da utilizzare durante l'accesso.</span><span class="sxs-lookup"><span data-stu-id="fdb43-119">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="fdb43-120">All'interno di questa impostazione, è necessario specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fdb43-120">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fdb43-121">ServerAddressExternal: specifica il nome o l'indirizzo IP del server utilizzato dai client e dai contatti federati quando si effettua la connessione dall'esterno del firewall esterno.</span><span class="sxs-lookup"><span data-stu-id="fdb43-121">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="fdb43-122">ServerAddressInternal: specifica il nome o l'indirizzo IP del server utilizzato quando i client si connettono dall'interno del firewall dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fdb43-122">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="fdb43-123">Transport: specifica il protocollo TCP (Transmission Control Protocol) o TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="fdb43-123">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb43-124">Versioni di server aggiuntive supportate</span><span class="sxs-lookup"><span data-stu-id="fdb43-124">Additional server versions supported</span></span><br />
<span data-ttu-id="fdb43-125">(ConfiguredServerCheckValues)</span><span class="sxs-lookup"><span data-stu-id="fdb43-125">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="fdb43-126">Specifica un elenco di nomi di versioni server separati da punti e virgola a cui Lync Server 2013 accederà, oltre alle versioni server supportate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fdb43-126">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb43-127">Disabilitare il caricamento automatico dei log degli errori di accesso (DisableAutomaticSendTracing)</span><span class="sxs-lookup"><span data-stu-id="fdb43-127">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="fdb43-128">Carica automaticamente i log degli errori di accesso a Lync Server per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="fdb43-128">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="fdb43-129">Se l'accesso ha esito positivo, non vengono caricati automaticamente i registri.</span><span class="sxs-lookup"><span data-stu-id="fdb43-129">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="fdb43-130">Se questo criterio non è configurato, si verifica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fdb43-130">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="fdb43-131">Per gli utenti di Lync Online: i log di errore di accesso vengono caricati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fdb43-131">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="fdb43-132">Per gli utenti locali di Lync: viene visualizzata una finestra di dialogo di conferma all'utente prima del caricamento.</span><span class="sxs-lookup"><span data-stu-id="fdb43-132">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="fdb43-133">Quando questa impostazione è disabilitata, i registri di accesso vengono caricati automaticamente nel server Lync per gli utenti di Lync locale e di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="fdb43-133">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="fdb43-134">Quando questa impostazione è abilitata, i registri di accesso non vengono mai caricati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fdb43-134">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb43-135">Disabilitare il fallback HTTP per la connessione SIP</span><span class="sxs-lookup"><span data-stu-id="fdb43-135">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="fdb43-136">(DisableHttpConnect)</span><span class="sxs-lookup"><span data-stu-id="fdb43-136">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="fdb43-137">Impedisce a Lync Server di tentare la connessione al server tramite HTTP, se TLS o TCP non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="fdb43-137">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="fdb43-138">Per impostazione predefinita, Lync tenta innanzitutto di connettersi al server tramite TLS o TCP e, se nessuno di questi metodi di trasporto ha esito positivo, Lync tenta di connettersi tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="fdb43-138">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="fdb43-139">Utilizzare questi criteri per disabilitare il tentativo di connessione HTTP di fallback.</span><span class="sxs-lookup"><span data-stu-id="fdb43-139">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb43-140">Richiedi credenziali di accesso</span><span class="sxs-lookup"><span data-stu-id="fdb43-140">Require logon credentials</span></span><br />
<span data-ttu-id="fdb43-141">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="fdb43-141">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="fdb43-142">Richiede all'utente di fornire le credenziali di accesso per Lync anziché utilizzare automaticamente le credenziali di Windows durante l'accesso a un server SIP.</span><span class="sxs-lookup"><span data-stu-id="fdb43-142">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb43-143">Disabilitare il controllo della versione del server</span><span class="sxs-lookup"><span data-stu-id="fdb43-143">Disable server version check</span></span><br />
<span data-ttu-id="fdb43-144">(DisableServerCheck)</span><span class="sxs-lookup"><span data-stu-id="fdb43-144">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="fdb43-145">Se si imposta questo criterio su 1, impedire a Lync di controllare il nome e la versione del server prima di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="fdb43-145">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="fdb43-146">Per impostazione predefinita, Lync effettua questi controlli prima di accedere.</span><span class="sxs-lookup"><span data-stu-id="fdb43-146">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb43-147">Abilitare l'utilizzo di bit per scaricare i file del servizio Rubrica</span><span class="sxs-lookup"><span data-stu-id="fdb43-147">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="fdb43-148">(EnableBitsForGalDownload)</span><span class="sxs-lookup"><span data-stu-id="fdb43-148">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="fdb43-149">Consente a Lync di utilizzare BITS (Background Intelligent Transfer Service) per scaricare i file dei servizi della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="fdb43-149">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb43-150">Configurare la modalità di sicurezza SIP</span><span class="sxs-lookup"><span data-stu-id="fdb43-150">Configure SIP security mode</span></span><br />
<span data-ttu-id="fdb43-151">(EnableSIPHighSecurityMode)</span><span class="sxs-lookup"><span data-stu-id="fdb43-151">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="fdb43-152">Consente a Lync di inviare e ricevere messaggi istantanei in modo più sicuro.</span><span class="sxs-lookup"><span data-stu-id="fdb43-152">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="fdb43-153">Tale criterio non produce alcun effetto sui servizi di Windows .NET o Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="fdb43-153">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="fdb43-154">Se non si configura questa impostazione di criterio, Lync può utilizzare qualsiasi trasporto.</span><span class="sxs-lookup"><span data-stu-id="fdb43-154">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="fdb43-155">Tuttavia, se non utilizza TLS e se il server esegue l'autenticazione degli utenti, Lync deve utilizzare l'autenticazione NTLM o Kerberos.</span><span class="sxs-lookup"><span data-stu-id="fdb43-155">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb43-156">Global Address Book scaricare il ritardo iniziale</span><span class="sxs-lookup"><span data-stu-id="fdb43-156">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="fdb43-157">(GalDownloadInitialDelay)</span><span class="sxs-lookup"><span data-stu-id="fdb43-157">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="fdb43-158">Specifica il periodo di tempo che deve trascorrere prima che si verifichi un download dell'elenco indirizzi globale.</span><span class="sxs-lookup"><span data-stu-id="fdb43-158">Specifies the time period before a download of the global address list (GAL) occurs.</span></span> <span data-ttu-id="fdb43-159">Il valore predefinito è 60 minuti, il che significa che il server ritarderà il download del file GAL per un periodo casuale compreso tra 0 e 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="fdb43-159">The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb43-160">Impedire agli utenti di eseguire Microsoft Lync</span><span class="sxs-lookup"><span data-stu-id="fdb43-160">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="fdb43-161">(PreventRun)</span><span class="sxs-lookup"><span data-stu-id="fdb43-161">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="fdb43-162">Impedisce l'esecuzione di Lync da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="fdb43-162">Prevents users from running Lync.</span></span> <span data-ttu-id="fdb43-163">È possibile configurare questa impostazione di criterio sia in Configurazione computer che in Configurazione utente, ma l'impostazione in Configurazione computer ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="fdb43-163">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb43-164">Consenti archiviazione delle password degli utenti</span><span class="sxs-lookup"><span data-stu-id="fdb43-164">Allow storage of user passwords</span></span><br />
<span data-ttu-id="fdb43-165">(SavePassword)</span><span class="sxs-lookup"><span data-stu-id="fdb43-165">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="fdb43-166">Consente a Lync di archiviare le password.</span><span class="sxs-lookup"><span data-stu-id="fdb43-166">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb43-167">Configurare la modalità di compressione SIP</span><span class="sxs-lookup"><span data-stu-id="fdb43-167">Configure SIP compression mode</span></span><br />
<span data-ttu-id="fdb43-168">SipCompression</span><span class="sxs-lookup"><span data-stu-id="fdb43-168">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="fdb43-p112">Specifica quando attivare la compressione SIP. Per impostazione predefinita, la compressione SIP è abilitata in base alla velocità della scheda. Tenere presente che l'impostazione di questo criterio potrebbe comportare un aumento del tempo di accesso.</span><span class="sxs-lookup"><span data-stu-id="fdb43-p112">Specifies when to turn on SIP compression. By default, SIP compression is enabled based on the adapter speed. Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb43-172">Elenco di domini attendibili</span><span class="sxs-lookup"><span data-stu-id="fdb43-172">Trusted Domain List</span></span><br />
<span data-ttu-id="fdb43-173">(TrustModelData)</span><span class="sxs-lookup"><span data-stu-id="fdb43-173">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="fdb43-174">Elenca i domini attendibili che non corrispondono al prefisso del dominio SIP del cliente.</span><span class="sxs-lookup"><span data-stu-id="fdb43-174">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fdb43-p113">I criteri configurati nel server hanno la priorità sulle impostazioni di Criteri di gruppo e sulle opzioni client configurate dall'utente. Nella tabella riportata di seguito viene riepilogato l'ordine di priorità delle impostazioni in caso di conflitto.</span><span class="sxs-lookup"><span data-stu-id="fdb43-p113">Policies configured on the server take precedence over Group Policy settings and client options configured by the user. The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="fdb43-177">Priorità di Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="fdb43-177">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdb43-178">Precedenza</span><span class="sxs-lookup"><span data-stu-id="fdb43-178">Precedence</span></span></th>
<th><span data-ttu-id="fdb43-179">Percorso o metodo di impostazione</span><span class="sxs-lookup"><span data-stu-id="fdb43-179">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdb43-180">1 </span><span class="sxs-lookup"><span data-stu-id="fdb43-180">1</span></span></p></td>
<td><p><span data-ttu-id="fdb43-181">Lync Server 2013 provisioning in-band</span><span class="sxs-lookup"><span data-stu-id="fdb43-181">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb43-182">2</span><span class="sxs-lookup"><span data-stu-id="fdb43-182">2</span></span></p></td>
<td><p><span data-ttu-id="fdb43-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="fdb43-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdb43-184">3</span><span class="sxs-lookup"><span data-stu-id="fdb43-184">3</span></span></p></td>
<td><p><span data-ttu-id="fdb43-185">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="fdb43-185">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdb43-186">4 </span><span class="sxs-lookup"><span data-stu-id="fdb43-186">4</span></span></p></td>
<td><p><span data-ttu-id="fdb43-187">La finestra di dialogo Lync-Opzioni in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="fdb43-187">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="fdb43-188">Per definire le impostazioni di criteri di gruppo mediante i file del modello amministrativo di Lync 2013</span><span class="sxs-lookup"><span data-stu-id="fdb43-188">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="fdb43-189">Creare una cartella di livello radice che contenga tutti i file ADMX indipendenti dalla lingua.</span><span class="sxs-lookup"><span data-stu-id="fdb43-189">Create a root-level folder to contain all language-neutral ADMX files.</span></span> <span data-ttu-id="fdb43-190">Ad esempio, creare la cartella radice per l'archivio centrale nel controller di dominio in questo percorso:</span><span class="sxs-lookup"><span data-stu-id="fdb43-190">For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fdb43-191">In questa procedura si presuppone che si desideri gestire più computer nel dominio.</span><span class="sxs-lookup"><span data-stu-id="fdb43-191">This procedure assumes that you want to manage multiple computers in your domain.</span></span> <span data-ttu-id="fdb43-192">In questo caso, i modelli vengono archiviati in un archivio centrale nella cartella SYSVOL del controller di dominio primario.</span><span class="sxs-lookup"><span data-stu-id="fdb43-192">In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller.</span></span> <span data-ttu-id="fdb43-193">In questo modo viene fornito un percorso di archiviazione centrale replicato per i modelli amministrativi di dominio.</span><span class="sxs-lookup"><span data-stu-id="fdb43-193">This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="fdb43-194">Creare una sottocartella per ogni lingua che verrà utilizzata.</span><span class="sxs-lookup"><span data-stu-id="fdb43-194">Create a subfolder for each language that you’ll use.</span></span> <span data-ttu-id="fdb43-195">Tali sottocartelle conterranno i file di risorse ADML specifici per la lingua.</span><span class="sxs-lookup"><span data-stu-id="fdb43-195">These subfolders will contain the language-specific ADML resource files.</span></span> <span data-ttu-id="fdb43-196">Ad esempio, creare una sottocartella per gli Stati Uniti (EN-US) in questa posizione:</span><span class="sxs-lookup"><span data-stu-id="fdb43-196">For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

