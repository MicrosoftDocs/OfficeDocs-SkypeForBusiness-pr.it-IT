---
title: "Lync Server 2013: pianificazione dell'autenticazione a due fattori"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0738cb282ad2f1f375e89526fcdd1569a6707ad0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="22a09-102">Pianificazione dell'autenticazione a due fattori in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22a09-102">Planning for two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22a09-103">_**Ultimo argomento modificato:** 2015-04-06_</span><span class="sxs-lookup"><span data-stu-id="22a09-103">_**Topic Last Modified:** 2015-04-06_</span></span>

<span data-ttu-id="22a09-104">Di seguito è riportato un elenco di considerazioni sulla distribuzione durante la configurazione di un ambiente Microsoft Lync Server 2013 per il supporto dell'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="22a09-104">The following is a list of deployment considerations when configuring a Microsoft Lync Server 2013 environment to support two-factor authentication.</span></span>

<div>

## <a name="client-support"></a><span data-ttu-id="22a09-105">Supporto client</span><span class="sxs-lookup"><span data-stu-id="22a09-105">Client Support</span></span>

<span data-ttu-id="22a09-106">Gli aggiornamenti cumulativi di Lync 2013 per Lync Server 2013: luglio 2013 client desktop e tutti i client mobili attualmente supportano l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="22a09-106">The Lync 2013 Cumulative Updates for Lync Server 2013: July 2013 desktop client and all mobile clients currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="22a09-107">Requisiti della topologia</span><span class="sxs-lookup"><span data-stu-id="22a09-107">Topology Requirements</span></span>

<span data-ttu-id="22a09-108">I clienti sono fortemente incoraggiati a distribuire l'autenticazione a due fattori utilizzando Lync Server 2013 dedicato con aggiornamenti cumulativi per Lync Server 2013: luglio 2013 Edge, Director e pool di utenti.</span><span class="sxs-lookup"><span data-stu-id="22a09-108">Customers are strongly encouraged to deploy two-factor authentication using dedicated Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Edge, Director, and User Pools.</span></span> <span data-ttu-id="22a09-109">Per abilitare l'autenticazione passiva per gli utenti di Lync, è necessario che altri metodi di autenticazione siano disabilitati per altri ruoli e servizi, tra cui i seguenti:</span><span class="sxs-lookup"><span data-stu-id="22a09-109">To enable passive authentication for Lync users, other authentication methods must be disabled for other roles and services, including the following:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22a09-110">Tipo di configurazione</span><span class="sxs-lookup"><span data-stu-id="22a09-110">Configuration Type</span></span></th>
<th><span data-ttu-id="22a09-111">Tipo di servizio</span><span class="sxs-lookup"><span data-stu-id="22a09-111">Service Type</span></span></th>
<th><span data-ttu-id="22a09-112">Server Role</span><span class="sxs-lookup"><span data-stu-id="22a09-112">Server Role</span></span></th>
<th><span data-ttu-id="22a09-113">Tipo di autenticazione da disabilitare</span><span class="sxs-lookup"><span data-stu-id="22a09-113">Authentication Type to Disable</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22a09-114">Web Service</span><span class="sxs-lookup"><span data-stu-id="22a09-114">Web Service</span></span></p></td>
<td><p><span data-ttu-id="22a09-115">WebServer</span><span class="sxs-lookup"><span data-stu-id="22a09-115">WebServer</span></span></p></td>
<td><p><span data-ttu-id="22a09-116">Director</span><span class="sxs-lookup"><span data-stu-id="22a09-116">Director</span></span></p></td>
<td><p><span data-ttu-id="22a09-117">Kerberos, NTLM e certificato</span><span class="sxs-lookup"><span data-stu-id="22a09-117">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22a09-118">Web Service</span><span class="sxs-lookup"><span data-stu-id="22a09-118">Web Service</span></span></p></td>
<td><p><span data-ttu-id="22a09-119">WebServer</span><span class="sxs-lookup"><span data-stu-id="22a09-119">WebServer</span></span></p></td>
<td><p><span data-ttu-id="22a09-120">Front End</span><span class="sxs-lookup"><span data-stu-id="22a09-120">Front End</span></span></p></td>
<td><p><span data-ttu-id="22a09-121">Kerberos, NTLM e certificato</span><span class="sxs-lookup"><span data-stu-id="22a09-121">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22a09-122">Proxy</span><span class="sxs-lookup"><span data-stu-id="22a09-122">Proxy</span></span></p></td>
<td><p><span data-ttu-id="22a09-123">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="22a09-123">EdgeServer</span></span></p></td>
<td><p><span data-ttu-id="22a09-124">Edge</span><span class="sxs-lookup"><span data-stu-id="22a09-124">Edge</span></span></p></td>
<td><p><span data-ttu-id="22a09-125">Kerberos e NTLM</span><span class="sxs-lookup"><span data-stu-id="22a09-125">Kerberos and NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22a09-126">Proxy</span><span class="sxs-lookup"><span data-stu-id="22a09-126">Proxy</span></span></p></td>
<td><p><span data-ttu-id="22a09-127">Registrar</span><span class="sxs-lookup"><span data-stu-id="22a09-127">Registrar</span></span></p></td>
<td><p><span data-ttu-id="22a09-128">Front End</span><span class="sxs-lookup"><span data-stu-id="22a09-128">Front End</span></span></p></td>
<td><p><span data-ttu-id="22a09-129">Kerberos e NTLM</span><span class="sxs-lookup"><span data-stu-id="22a09-129">Kerberos and NTLM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="22a09-130">A meno che questi tipi di autenticazione non siano disabilitati a livello di servizio, tutte le altre versioni del client Lync non saranno in grado di accedere correttamente dopo che è stata abilitata l'autenticazione a due fattori all'interno della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="22a09-130">Unless these authentication types are disabled at the service level, all other versions of the Lync client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>

</div>

<div>

## <a name="lync-service-discovery"></a><span data-ttu-id="22a09-131">Individuazione del servizio Lync</span><span class="sxs-lookup"><span data-stu-id="22a09-131">Lync Service Discovery</span></span>

<span data-ttu-id="22a09-132">I record DNS utilizzati dai client interni e/o esterni per individuare i servizi Lync devono essere configurati in modo da essere risolti in un server Lync che non è abilitato per l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="22a09-132">DNS records used by internal and/or external clients to discover Lync services should be configured to resolve to a Lync server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="22a09-133">Con questa configurazione, non è necessario che gli utenti provenienti da pool Lync che non sono abilitati per l'autenticazione a due fattori immettano un PIN per l'autenticazione, mentre gli utenti provenienti da pool Lync abilitati per l'accesso a due fattori dovranno immettere il proprio PIN per autenticare.</span><span class="sxs-lookup"><span data-stu-id="22a09-133">With this configuration, users from Lync Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Lync Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>

</div>

<div>

## <a name="exchange-authentication"></a><span data-ttu-id="22a09-134">Autenticazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="22a09-134">Exchange Authentication</span></span>

<span data-ttu-id="22a09-135">I clienti che hanno distribuito l'autenticazione a due fattori per Microsoft Exchange possono rilevare che alcune caratteristiche nel client Lync non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="22a09-135">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the Lync client are unavailable.</span></span> <span data-ttu-id="22a09-136">Questo è attualmente in fase di progettazione, in quanto il client Lync non supporta l'autenticazione a due fattori per le caratteristiche che dipendono dall'integrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="22a09-136">This is currently by design, as the Lync client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>

</div>

<div>

## <a name="lync-contacts"></a><span data-ttu-id="22a09-137">Contatti di Lync</span><span class="sxs-lookup"><span data-stu-id="22a09-137">Lync Contacts</span></span>

<span data-ttu-id="22a09-138">Gli utenti di Lync configurati per sfruttare la caratteristica archivio contatti unificato troveranno che i loro contatti non sono più disponibili dopo aver eseguito l'accesso con l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="22a09-138">Lync users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>

<span data-ttu-id="22a09-139">È consigliabile utilizzare il cmdlet **Invoke-CsUcsRollback** per rimuovere i contatti utente esistenti dall'archivio contatti unificato e archiviarli in Lync Server 2013 prima di abilitare l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="22a09-139">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Lync Server 2013 before enabling two-factor authentication.</span></span>

</div>

<div>

## <a name="skill-search"></a><span data-ttu-id="22a09-140">Ricerca skill</span><span class="sxs-lookup"><span data-stu-id="22a09-140">Skill Search</span></span>

<span data-ttu-id="22a09-141">I clienti che hanno configurato la funzionalità di ricerca Skill nell'ambiente Lync troveranno che questa funzionalità non funziona quando Lync è abilitato per l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="22a09-141">Customers who have configured the Skill Search feature in their Lync environment will find that this feature does not work when Lync is enabled for two-factor authentication.</span></span> <span data-ttu-id="22a09-142">Questo è in base alla progettazione, in quanto Microsoft SharePoint attualmente non supporta l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="22a09-142">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="lync-credentials"></a><span data-ttu-id="22a09-143">Credenziali di Lync</span><span class="sxs-lookup"><span data-stu-id="22a09-143">Lync Credentials</span></span>

<span data-ttu-id="22a09-144">Sono presenti diverse considerazioni sulla distribuzione che coinvolgono credenziali di Lync salvate che possono influire sugli utenti configurati per l'utilizzo dell'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="22a09-144">There are a number of deployment considerations involving saved Lync credentials which may impact users who are configured to use two-factor authentication.</span></span>

<div>

## <a name="deleting-saved-credentials"></a><span data-ttu-id="22a09-145">Eliminazione delle credenziali salvate</span><span class="sxs-lookup"><span data-stu-id="22a09-145">Deleting Saved Credentials</span></span>

<span data-ttu-id="22a09-146">Gli utenti del client desktop devono utilizzare l'opzione **delete my Sign-in info** nel client Lync ed eliminare la cartella del profilo SIP da%\\localappdata\\%\\Microsoft\\Office 15,0 Lync prima di tentare di firmare per la prima volta utilizzando l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="22a09-146">Desktop client users should use the **Delete my sign-in info** option in the Lync client and delete their SIP profile folder from %localappdata%\\Microsoft\\Office\\15.0\\Lync before attempting to sign for the first time using two-factor authentication.</span></span>

</div>

<div>

## <a name="disablentcredentials"></a><span data-ttu-id="22a09-147">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="22a09-147">DisableNTCredentials</span></span>

<span data-ttu-id="22a09-148">Con il metodo di autenticazione Kerberos o NTLM, le credenziali di Windows dell'utente vengono utilizzate automaticamente per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="22a09-148">With the Kerberos or NTLM authentication method, the user’s Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="22a09-149">In una distribuzione tipica di Lync Server 2013 in cui Kerberos e/o NTLM è abilitato per l'autenticazione, gli utenti non devono immettere le proprie credenziali ogni volta che accedono.</span><span class="sxs-lookup"><span data-stu-id="22a09-149">In a typical Lync Server 2013 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>

<span data-ttu-id="22a09-150">Se agli utenti vengono richieste involontariamente le credenziali prima che venga richiesto di immettere il proprio PIN, la chiave del registro di sistema **DisableNTCredentials** potrebbe essere involontariamente configurata nei computer client, possibilmente tramite criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="22a09-150">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>

<span data-ttu-id="22a09-151">Per impedire la richiesta aggiuntiva di credenziali, creare la seguente voce del registro di sistema nella workstation locale o utilizzare il modello di amministrazione di Lync da applicare a tutti gli utenti di un determinato pool utilizzando criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="22a09-151">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="22a09-152">Criteri\_\\software\_\\del\\computer locale di\\HKEY\\Microsoft\\Office 15,0 Lync</span><span class="sxs-lookup"><span data-stu-id="22a09-152">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="22a09-153">DWORD\_reg: DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="22a09-153">REG\_DWORD: DisableNTCredentials</span></span>

<span data-ttu-id="22a09-154">Valore: 0x0</span><span class="sxs-lookup"><span data-stu-id="22a09-154">Value: 0x0</span></span>

</div>

<div>

## <a name="savepassword"></a><span data-ttu-id="22a09-155">SavePassword</span><span class="sxs-lookup"><span data-stu-id="22a09-155">SavePassword</span></span>

<span data-ttu-id="22a09-156">Quando un utente accede a Lync per la prima volta, all'utente viene richiesto di salvare la propria password.</span><span class="sxs-lookup"><span data-stu-id="22a09-156">When a user signs in to Lync for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="22a09-157">Se selezionata, questa opzione consente di archiviare il certificato client dell'utente nell'archivio certificati personale e le credenziali di Windows dell'utente da archiviare in Gestione credenziali del computer locale.</span><span class="sxs-lookup"><span data-stu-id="22a09-157">If selected, this option allows the user’s client certificate to be stored in the personal certificate store and the user’s Windows credentials to be stored in the Credential Manager of the local computer.</span></span>

<span data-ttu-id="22a09-158">L'impostazione del registro di sistema **SavePassword** deve essere disattivata quando Lync è configurato per supportare l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="22a09-158">The **SavePassword** registry setting should be disabled when Lync is configured to support two-factor authentication.</span></span> <span data-ttu-id="22a09-159">Per impedire agli utenti di salvare le password, modificare la voce del registro di sistema seguente nella workstation locale o utilizzare il modello di amministrazione di Lync per applicarlo a tutti gli utenti di un determinato pool utilizzando criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="22a09-159">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="22a09-160">Software\_\\utente\_\\corrente di HKEY\\Microsoft\\Office\\15,0 Lync</span><span class="sxs-lookup"><span data-stu-id="22a09-160">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="22a09-161">DWORD\_reg: SavePassword</span><span class="sxs-lookup"><span data-stu-id="22a09-161">REG\_DWORD: SavePassword</span></span>

<span data-ttu-id="22a09-162">Valore: 0x0</span><span class="sxs-lookup"><span data-stu-id="22a09-162">Value: 0x0</span></span>

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="22a09-163">Riproduzione di token AD FS 2,0</span><span class="sxs-lookup"><span data-stu-id="22a09-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="22a09-164">AD FS 2,0 fornisce una funzionalità denominata rilevamento della riproduzione di token, in base al quale è possibile rilevare più richieste di token utilizzando lo stesso token e quindi eliminarle.</span><span class="sxs-lookup"><span data-stu-id="22a09-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="22a09-165">Quando questa funzionalità è abilitata, il rilevamento della riproduzione di token protegge l'integrità delle richieste di autenticazione sia nel profilo passivo WS-Federation che nel profilo WebSSO SAML assicurandosi che lo stesso token non venga mai utilizzato più di una volta.</span><span class="sxs-lookup"><span data-stu-id="22a09-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>

<span data-ttu-id="22a09-166">Questa funzionalità deve essere abilitata in situazioni in cui la sicurezza è un problema molto elevato, ad esempio quando si utilizzano i chioschi.</span><span class="sxs-lookup"><span data-stu-id="22a09-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="22a09-167">Per ulteriori informazioni sul rilevamento della riproduzione di token, vedere procedure consigliate per la pianificazione e la distribuzione sicure [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215)di ad FS 2,0 all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="22a09-167">For more information about token replay detection, see Best Practices for Secure Planning and Deployment of AD FS 2.0 at [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215).</span></span>

</div>

<div>

## <a name="external-user-access"></a><span data-ttu-id="22a09-168">Accesso utente esterno</span><span class="sxs-lookup"><span data-stu-id="22a09-168">External User Access</span></span>

<span data-ttu-id="22a09-169">La configurazione di un proxy AD FS o di un proxy inverso per il supporto dell'autenticazione a due fattori di Lync dalle reti esterne non è illustrata in questi argomenti.</span><span class="sxs-lookup"><span data-stu-id="22a09-169">Configuring an AD FS Proxy or Reverse Proxy to support Lync two-factor authentication from external networks is not covered in these topics.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

