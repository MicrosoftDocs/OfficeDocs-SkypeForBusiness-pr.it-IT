---
title: "Lync Server 2013: pianificazione per l'autenticazione a due fattori"
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
ms.openlocfilehash: e610990182e01c0e9e2d7199bd3a34f70fbe3132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="55f58-102">Pianificazione dell'autenticazione a due fattori in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55f58-102">Planning for two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55f58-103">_**Argomento Ultima modifica:** 2015-04-06_</span><span class="sxs-lookup"><span data-stu-id="55f58-103">_**Topic Last Modified:** 2015-04-06_</span></span>

<span data-ttu-id="55f58-104">Di seguito è riportato un elenco di considerazioni sulla distribuzione quando si configura un ambiente di Microsoft Lync Server 2013 per supportare l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="55f58-104">The following is a list of deployment considerations when configuring a Microsoft Lync Server 2013 environment to support two-factor authentication.</span></span>

<div>

## <a name="client-support"></a><span data-ttu-id="55f58-105">Supporto client</span><span class="sxs-lookup"><span data-stu-id="55f58-105">Client Support</span></span>

<span data-ttu-id="55f58-106">Gli aggiornamenti cumulativi di Lync 2013 per Lync Server 2013: client desktop di luglio 2013 e tutti i client mobili supportano attualmente l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="55f58-106">The Lync 2013 Cumulative Updates for Lync Server 2013: July 2013 desktop client and all mobile clients currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="55f58-107">Requisiti di topologia</span><span class="sxs-lookup"><span data-stu-id="55f58-107">Topology Requirements</span></span>

<span data-ttu-id="55f58-108">I clienti sono fortemente incoraggiati a distribuire l'autenticazione a due fattori con Lync Server dedicato 2013 con gli aggiornamenti cumulativi per Lync Server 2013: luglio 2013 Edge, Director e pool di utenti.</span><span class="sxs-lookup"><span data-stu-id="55f58-108">Customers are strongly encouraged to deploy two-factor authentication using dedicated Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Edge, Director, and User Pools.</span></span> <span data-ttu-id="55f58-109">Per abilitare l'autenticazione passiva per gli utenti di Lync, è necessario disabilitare altri metodi di autenticazione per altri ruoli e servizi, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="55f58-109">To enable passive authentication for Lync users, other authentication methods must be disabled for other roles and services, including the following:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55f58-110">Tipo di configurazione</span><span class="sxs-lookup"><span data-stu-id="55f58-110">Configuration Type</span></span></th>
<th><span data-ttu-id="55f58-111">Tipo di servizio</span><span class="sxs-lookup"><span data-stu-id="55f58-111">Service Type</span></span></th>
<th><span data-ttu-id="55f58-112">Ruolo del server</span><span class="sxs-lookup"><span data-stu-id="55f58-112">Server Role</span></span></th>
<th><span data-ttu-id="55f58-113">Tipo di autenticazione da disabilitare</span><span class="sxs-lookup"><span data-stu-id="55f58-113">Authentication Type to Disable</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55f58-114">Servizio Web</span><span class="sxs-lookup"><span data-stu-id="55f58-114">Web Service</span></span></p></td>
<td><p><span data-ttu-id="55f58-115">WebServer</span><span class="sxs-lookup"><span data-stu-id="55f58-115">WebServer</span></span></p></td>
<td><p><span data-ttu-id="55f58-116">Director</span><span class="sxs-lookup"><span data-stu-id="55f58-116">Director</span></span></p></td>
<td><p><span data-ttu-id="55f58-117">Kerberos, NTLM e certificato</span><span class="sxs-lookup"><span data-stu-id="55f58-117">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55f58-118">Servizio Web</span><span class="sxs-lookup"><span data-stu-id="55f58-118">Web Service</span></span></p></td>
<td><p><span data-ttu-id="55f58-119">WebServer</span><span class="sxs-lookup"><span data-stu-id="55f58-119">WebServer</span></span></p></td>
<td><p><span data-ttu-id="55f58-120">Front-end</span><span class="sxs-lookup"><span data-stu-id="55f58-120">Front End</span></span></p></td>
<td><p><span data-ttu-id="55f58-121">Kerberos, NTLM e certificato</span><span class="sxs-lookup"><span data-stu-id="55f58-121">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55f58-122">Proxy</span><span class="sxs-lookup"><span data-stu-id="55f58-122">Proxy</span></span></p></td>
<td><p><span data-ttu-id="55f58-123">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="55f58-123">EdgeServer</span></span></p></td>
<td><p><span data-ttu-id="55f58-124">Bordo</span><span class="sxs-lookup"><span data-stu-id="55f58-124">Edge</span></span></p></td>
<td><p><span data-ttu-id="55f58-125">Kerberos e NTLM</span><span class="sxs-lookup"><span data-stu-id="55f58-125">Kerberos and NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55f58-126">Proxy</span><span class="sxs-lookup"><span data-stu-id="55f58-126">Proxy</span></span></p></td>
<td><p><span data-ttu-id="55f58-127">Registrar</span><span class="sxs-lookup"><span data-stu-id="55f58-127">Registrar</span></span></p></td>
<td><p><span data-ttu-id="55f58-128">Front-end</span><span class="sxs-lookup"><span data-stu-id="55f58-128">Front End</span></span></p></td>
<td><p><span data-ttu-id="55f58-129">Kerberos e NTLM</span><span class="sxs-lookup"><span data-stu-id="55f58-129">Kerberos and NTLM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="55f58-130">A meno che questi tipi di autenticazione non siano disabilitati a livello di servizio, tutte le altre versioni del client Lync non saranno in grado di accedere correttamente quando l'autenticazione a due fattori è abilitata all'interno della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="55f58-130">Unless these authentication types are disabled at the service level, all other versions of the Lync client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>

</div>

<div>

## <a name="lync-service-discovery"></a><span data-ttu-id="55f58-131">Individuazione di servizi Lync</span><span class="sxs-lookup"><span data-stu-id="55f58-131">Lync Service Discovery</span></span>

<span data-ttu-id="55f58-132">I record DNS usati dai client interni e/o esterni per individuare i servizi Lync devono essere configurati per la risoluzione in un server Lync non abilitato per l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="55f58-132">DNS records used by internal and/or external clients to discover Lync services should be configured to resolve to a Lync server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="55f58-133">Con questa configurazione, gli utenti provenienti da pool Lync non abilitati per l'autenticazione a due fattori non saranno necessari per immettere un PIN da autenticare, mentre agli utenti provenienti da pool Lync abilitati per l'autenticazione a due fattori verrà richiesto di immettere il proprio PIN per autenticare.</span><span class="sxs-lookup"><span data-stu-id="55f58-133">With this configuration, users from Lync Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Lync Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>

</div>

<div>

## <a name="exchange-authentication"></a><span data-ttu-id="55f58-134">Autenticazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="55f58-134">Exchange Authentication</span></span>

<span data-ttu-id="55f58-135">I clienti che hanno distribuito l'autenticazione a due fattori per Microsoft Exchange potrebbero non essere disponibili per alcune funzionalità del client Lync.</span><span class="sxs-lookup"><span data-stu-id="55f58-135">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the Lync client are unavailable.</span></span> <span data-ttu-id="55f58-136">Questa funzionalità è attualmente in fase di progettazione, poiché il client Lync non supporta l'autenticazione a due fattori per le caratteristiche che dipendono dall'integrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="55f58-136">This is currently by design, as the Lync client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>

</div>

<div>

## <a name="lync-contacts"></a><span data-ttu-id="55f58-137">Contatti di Lync</span><span class="sxs-lookup"><span data-stu-id="55f58-137">Lync Contacts</span></span>

<span data-ttu-id="55f58-138">Gli utenti di Lync configurati per sfruttare la caratteristica archivio contatti unificato troveranno che i loro contatti non sono più disponibili dopo l'accesso con l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="55f58-138">Lync users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>

<span data-ttu-id="55f58-139">È consigliabile usare il cmdlet **Invoke-CsUcsRollback** per rimuovere i contatti utente esistenti dall'archivio contatti unificato e archiviarli in Lync Server 2013 prima di abilitare l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="55f58-139">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Lync Server 2013 before enabling two-factor authentication.</span></span>

</div>

<div>

## <a name="skill-search"></a><span data-ttu-id="55f58-140">Ricerca di abilità</span><span class="sxs-lookup"><span data-stu-id="55f58-140">Skill Search</span></span>

<span data-ttu-id="55f58-141">I clienti che hanno configurato la funzionalità Ricerca competenze nell'ambiente Lync troveranno che questa caratteristica non funziona quando Lync è abilitato per l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="55f58-141">Customers who have configured the Skill Search feature in their Lync environment will find that this feature does not work when Lync is enabled for two-factor authentication.</span></span> <span data-ttu-id="55f58-142">In base alla progettazione, poiché in Microsoft SharePoint non è attualmente supportata l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="55f58-142">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="lync-credentials"></a><span data-ttu-id="55f58-143">Credenziali di Lync</span><span class="sxs-lookup"><span data-stu-id="55f58-143">Lync Credentials</span></span>

<span data-ttu-id="55f58-144">Sono disponibili diverse considerazioni sulla distribuzione che includono credenziali di Lync salvate che possono influire sugli utenti configurati per l'uso dell'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="55f58-144">There are a number of deployment considerations involving saved Lync credentials which may impact users who are configured to use two-factor authentication.</span></span>

<div>

## <a name="deleting-saved-credentials"></a><span data-ttu-id="55f58-145">Eliminazione delle credenziali salvate</span><span class="sxs-lookup"><span data-stu-id="55f58-145">Deleting Saved Credentials</span></span>

<span data-ttu-id="55f58-146">Gli utenti del client desktop devono usare l'opzione **Elimina le informazioni di accesso** nel client Lync ed eliminare la cartella del profilo SIP da% LocalAppData\\%\\Microsoft\\Office\\15,0 Lync prima di provare a firmare per la prima volta con l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="55f58-146">Desktop client users should use the **Delete my sign-in info** option in the Lync client and delete their SIP profile folder from %localappdata%\\Microsoft\\Office\\15.0\\Lync before attempting to sign for the first time using two-factor authentication.</span></span>

</div>

<div>

## <a name="disablentcredentials"></a><span data-ttu-id="55f58-147">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="55f58-147">DisableNTCredentials</span></span>

<span data-ttu-id="55f58-148">Con il metodo di autenticazione Kerberos o NTLM, le credenziali di Windows dell'utente vengono usate automaticamente per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="55f58-148">With the Kerberos or NTLM authentication method, the user’s Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="55f58-149">In una distribuzione tipica di Lync Server 2013 in cui è abilitato Kerberos e/o NTLM per l'autenticazione, gli utenti non devono immettere le proprie credenziali ogni volta che eseguono l'accesso.</span><span class="sxs-lookup"><span data-stu-id="55f58-149">In a typical Lync Server 2013 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>

<span data-ttu-id="55f58-150">Se agli utenti vengono richieste involontariamente le credenziali prima che venga chiesto di immettere il PIN, la chiave del registro di sistema **DisableNTCredentials** potrebbe essere configurata involontariamente nei computer client, possibilmente tramite criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="55f58-150">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>

<span data-ttu-id="55f58-151">Per evitare la richiesta aggiuntiva per le credenziali, creare la voce del registro di sistema seguente nella workstation locale o usare il modello amministrativo di Lync per applicare tutti gli utenti per un pool specifico tramite criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="55f58-151">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="55f58-152">Criteri\_\\di\_HKEY\\del\\software locale\\di\\Microsoft\\Office 15,0 Lync</span><span class="sxs-lookup"><span data-stu-id="55f58-152">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="55f58-153">DWORD\_reg: DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="55f58-153">REG\_DWORD: DisableNTCredentials</span></span>

<span data-ttu-id="55f58-154">Valore: 0x0</span><span class="sxs-lookup"><span data-stu-id="55f58-154">Value: 0x0</span></span>

</div>

<div>

## <a name="savepassword"></a><span data-ttu-id="55f58-155">SavePassword</span><span class="sxs-lookup"><span data-stu-id="55f58-155">SavePassword</span></span>

<span data-ttu-id="55f58-156">Quando un utente accede a Lync per la prima volta, all'utente viene chiesto di salvare la propria password.</span><span class="sxs-lookup"><span data-stu-id="55f58-156">When a user signs in to Lync for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="55f58-157">Se selezionata, questa opzione consente di archiviare il certificato client dell'utente nell'archivio dei certificati personali e le credenziali di Windows dell'utente da archiviare in Gestione credenziali del computer locale.</span><span class="sxs-lookup"><span data-stu-id="55f58-157">If selected, this option allows the user’s client certificate to be stored in the personal certificate store and the user’s Windows credentials to be stored in the Credential Manager of the local computer.</span></span>

<span data-ttu-id="55f58-158">L'impostazione del registro di sistema **SavePassword** deve essere disabilitata quando Lync è configurato per supportare l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="55f58-158">The **SavePassword** registry setting should be disabled when Lync is configured to support two-factor authentication.</span></span> <span data-ttu-id="55f58-159">Per impedire agli utenti di salvare le password, modificare la voce del registro di sistema seguente nella workstation locale o usare il modello amministrativo di Lync per applicare tutti gli utenti per un pool specifico tramite criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="55f58-159">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="55f58-160">HKEY\_software\_\\utente\\corrente Microsoft\\Office\\15,0\\Lync</span><span class="sxs-lookup"><span data-stu-id="55f58-160">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="55f58-161">DWORD\_reg: SavePassword</span><span class="sxs-lookup"><span data-stu-id="55f58-161">REG\_DWORD: SavePassword</span></span>

<span data-ttu-id="55f58-162">Valore: 0x0</span><span class="sxs-lookup"><span data-stu-id="55f58-162">Value: 0x0</span></span>

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="55f58-163">Riproduzione di token AD FS 2,0</span><span class="sxs-lookup"><span data-stu-id="55f58-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="55f58-164">ADFS 2,0 offre una caratteristica denominata rilevamento riproduzione token, in base alla quale più richieste di token che usano lo stesso token possono essere rilevate e quindi scartate.</span><span class="sxs-lookup"><span data-stu-id="55f58-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="55f58-165">Quando questa funzionalità è abilitata, il rilevamento della riproduzione del token protegge l'integrità delle richieste di autenticazione sia nel profilo passivo WS-Federation che nel profilo WebSSO SAML assicurando che lo stesso token non venga mai usato più di una volta.</span><span class="sxs-lookup"><span data-stu-id="55f58-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>

<span data-ttu-id="55f58-166">Questa caratteristica deve essere abilitata in situazioni in cui la sicurezza è un problema molto elevato, ad esempio quando si usano i chioschi.</span><span class="sxs-lookup"><span data-stu-id="55f58-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="55f58-167">Per altre informazioni sul rilevamento della riproduzione di token, vedere procedure consigliate per la pianificazione e la distribuzione sicure [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)di ADFS 2,0 at.</span><span class="sxs-lookup"><span data-stu-id="55f58-167">For more information about token replay detection, see Best Practices for Secure Planning and Deployment of AD FS 2.0 at [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215).</span></span>

</div>

<div>

## <a name="external-user-access"></a><span data-ttu-id="55f58-168">Accesso utenti esterni</span><span class="sxs-lookup"><span data-stu-id="55f58-168">External User Access</span></span>

<span data-ttu-id="55f58-169">La configurazione di un proxy ADFS o di un proxy inverso per supportare l'autenticazione a due fattori di Lync da reti esterne non è contemplata in questi argomenti.</span><span class="sxs-lookup"><span data-stu-id="55f58-169">Configuring an AD FS Proxy or Reverse Proxy to support Lync two-factor authentication from external networks is not covered in these topics.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

