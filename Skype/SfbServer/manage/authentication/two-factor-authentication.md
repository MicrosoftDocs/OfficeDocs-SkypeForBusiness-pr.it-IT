---
title: Gestire l'autenticazione a due fattori in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: "Riepilogo: gestire l'autenticazione a due fattori in Skype for Business Server."
ms.openlocfilehash: 415eb23779450bc09cdaa25ea2e60b6cf3526e40
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806542"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="fc240-103">Gestire l'autenticazione a due fattori in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fc240-103">Manage two-factor authentication in Skype for Business Server</span></span>
 
<span data-ttu-id="fc240-104">**Riepilogo:** Gestire l'autenticazione a due fattori in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fc240-104">**Summary:** Manage two-factor authentication in Skype for Business Server.</span></span>
  
<span data-ttu-id="fc240-105">L'autenticazione a due fattori garantisce una maggiore sicurezza richiedendo agli utenti di fornire due forme di autenticazione o identificazione, ovvero una combinazione di nome utente/password e un token o un certificato.</span><span class="sxs-lookup"><span data-stu-id="fc240-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="fc240-106">Questo è conosciuto anche come "qualcosa che hai, qualcosa che conosci".</span><span class="sxs-lookup"><span data-stu-id="fc240-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="fc240-107">Un esempio tipico di autenticazione a due fattori con un certificato è l'utilizzo delle smart card.</span><span class="sxs-lookup"><span data-stu-id="fc240-107">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="fc240-108">Una smart card contiene un certificato associato all'account utente e può essere convalidato in base alle informazioni sugli utenti e sui certificati archiviati in un server.</span><span class="sxs-lookup"><span data-stu-id="fc240-108">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="fc240-109">Confrontando le informazioni utente (nome utente e password) per il certificato fornito, il server convalida le credenziali e autentica l'utente.</span><span class="sxs-lookup"><span data-stu-id="fc240-109">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="fc240-110">Si consideri gli argomenti seguenti quando si configura un ambiente di Skype for Business Server per supportare l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="fc240-110">Consider the following subjects when configuring a Skype for Business Server environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="fc240-111">Supporto client</span><span class="sxs-lookup"><span data-stu-id="fc240-111">Client Support</span></span>

<span data-ttu-id="fc240-112">Gli aggiornamenti cumulativi per Lync Server 2013: client desktop di luglio 2013 e il client Skype for business sono gli unici client che attualmente supportano l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="fc240-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="fc240-113">Requisiti della topologia</span><span class="sxs-lookup"><span data-stu-id="fc240-113">Topology Requirements</span></span>

<span data-ttu-id="fc240-114">I clienti sono fortemente incoraggiati a distribuire l'autenticazione a due fattori utilizzando Skype for Business Server dedicato con pool di Edge, Director e User.</span><span class="sxs-lookup"><span data-stu-id="fc240-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server with Edge, Director, and User Pools.</span></span> <span data-ttu-id="fc240-115">Per abilitare l'autenticazione passiva per gli utenti, altri metodi di autenticazione devono essere disattivati per altri ruoli e servizi, tra cui i seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc240-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="fc240-116">**Tipo di configurazione**</span><span class="sxs-lookup"><span data-stu-id="fc240-116">**Configuration Type**</span></span>|<span data-ttu-id="fc240-117">**Tipo di servizio**</span><span class="sxs-lookup"><span data-stu-id="fc240-117">**Service Type**</span></span>|<span data-ttu-id="fc240-118">**Ruolo del server**</span><span class="sxs-lookup"><span data-stu-id="fc240-118">**Server Role**</span></span>|<span data-ttu-id="fc240-119">**Tipo di autenticazione da disabilitare**</span><span class="sxs-lookup"><span data-stu-id="fc240-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fc240-120">Web Service</span><span class="sxs-lookup"><span data-stu-id="fc240-120">Web Service</span></span>  <br/> |<span data-ttu-id="fc240-121">WebServer</span><span class="sxs-lookup"><span data-stu-id="fc240-121">WebServer</span></span>  <br/> |<span data-ttu-id="fc240-122">Direttore</span><span class="sxs-lookup"><span data-stu-id="fc240-122">Director</span></span>  <br/> |<span data-ttu-id="fc240-123">Kerberos, NTLM e certificato</span><span class="sxs-lookup"><span data-stu-id="fc240-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="fc240-124">Web Service</span><span class="sxs-lookup"><span data-stu-id="fc240-124">Web Service</span></span>  <br/> |<span data-ttu-id="fc240-125">WebServer</span><span class="sxs-lookup"><span data-stu-id="fc240-125">WebServer</span></span>  <br/> |<span data-ttu-id="fc240-126">Front End</span><span class="sxs-lookup"><span data-stu-id="fc240-126">Front End</span></span>  <br/> |<span data-ttu-id="fc240-127">Kerberos, NTLM e certificato</span><span class="sxs-lookup"><span data-stu-id="fc240-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="fc240-128">Proxy</span><span class="sxs-lookup"><span data-stu-id="fc240-128">Proxy</span></span>  <br/> |<span data-ttu-id="fc240-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="fc240-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="fc240-130">Edge</span><span class="sxs-lookup"><span data-stu-id="fc240-130">Edge</span></span>  <br/> |<span data-ttu-id="fc240-131">Kerberos e NTLM</span><span class="sxs-lookup"><span data-stu-id="fc240-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="fc240-132">Proxy</span><span class="sxs-lookup"><span data-stu-id="fc240-132">Proxy</span></span>  <br/> |<span data-ttu-id="fc240-133">Registrar</span><span class="sxs-lookup"><span data-stu-id="fc240-133">Registrar</span></span>  <br/> |<span data-ttu-id="fc240-134">Front End</span><span class="sxs-lookup"><span data-stu-id="fc240-134">Front End</span></span>  <br/> |<span data-ttu-id="fc240-135">Kerberos e NTLM</span><span class="sxs-lookup"><span data-stu-id="fc240-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="fc240-136">A meno che questi tipi di autenticazione non siano disabilitati a livello di servizio, tutte le altre versioni del client non saranno in grado di accedere correttamente dopo che è stata abilitata l'autenticazione a due fattori all'interno della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fc240-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="fc240-137">Individuazione del servizio Skype for business</span><span class="sxs-lookup"><span data-stu-id="fc240-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="fc240-138">I record DNS utilizzati dai client interni e/o esterni per individuare i servizi Skype for business devono essere configurati in modo da essere risolti in un server Skype for business non abilitato per l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="fc240-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="fc240-139">Con questa configurazione, gli utenti di pool Skype for business che non sono abilitati per l'autenticazione a due fattori non devono immettere un PIN da autenticare, mentre gli utenti dei pool Skype for business abilitati per l'autenticazione a due fattori saranno tenuti a immettere il proprio PIN da autenticare.</span><span class="sxs-lookup"><span data-stu-id="fc240-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="fc240-140">Autenticazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="fc240-140">Exchange Authentication</span></span>

<span data-ttu-id="fc240-141">I clienti che hanno distribuito l'autenticazione a due fattori per Microsoft Exchange possono rilevare che alcune caratteristiche nel client non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="fc240-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="fc240-142">Questo è attualmente in fase di progettazione, in quanto il client Skype for business non supporta l'autenticazione a due fattori per le caratteristiche che dipendono dall'integrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="fc240-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="fc240-143">Contatti</span><span class="sxs-lookup"><span data-stu-id="fc240-143">Contacts</span></span>

<span data-ttu-id="fc240-144">Gli utenti di Skype for business che sono configurati per sfruttare la caratteristica archivio contatti unificato troveranno che i loro contatti non sono più disponibili dopo aver eseguito l'accesso con l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="fc240-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="fc240-145">È consigliabile utilizzare il cmdlet **Invoke-CsUcsRollback** per rimuovere i contatti utente esistenti dall'archivio contatti unificato e archiviarli in Skype for Business Server prima di abilitare l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="fc240-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="fc240-146">Ricerca skill</span><span class="sxs-lookup"><span data-stu-id="fc240-146">Skill Search</span></span>

<span data-ttu-id="fc240-147">I clienti che hanno configurato la funzionalità di ricerca Skill nell'ambiente Skype for business troveranno che questa funzionalità non funziona quando Skype for business è abilitato per l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="fc240-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="fc240-148">Questo è in base alla progettazione, in quanto Microsoft SharePoint attualmente non supporta l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="fc240-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="fc240-149">Credentials</span><span class="sxs-lookup"><span data-stu-id="fc240-149">Credentials</span></span>

<span data-ttu-id="fc240-150">Sono presenti diverse considerazioni sulla distribuzione che coinvolgono le credenziali salvate di Skype for business, che potrebbero influire sugli utenti configurati per l'utilizzo dell'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="fc240-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="fc240-151">Eliminazione delle credenziali salvate</span><span class="sxs-lookup"><span data-stu-id="fc240-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="fc240-152">Gli utenti devono utilizzare l'opzione **delete my Sign-in info** nel client Skype for business ed eliminare la cartella del profilo SIP da%LocalAppData%\Microsoft\Office\15.0\Skype for business prima di tentare di firmare per la prima volta utilizzando l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="fc240-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="fc240-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="fc240-153">DisableNTCredentials</span></span>

<span data-ttu-id="fc240-154">Con il metodo di autenticazione Kerberos o NTLM, le credenziali di Windows dell'utente vengono utilizzate automaticamente per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="fc240-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="fc240-155">In una tipica distribuzione di Skype for Business Server in cui Kerberos e/o NTLM è abilitato per l'autenticazione, gli utenti non devono immettere le proprie credenziali ogni volta che accedono.</span><span class="sxs-lookup"><span data-stu-id="fc240-155">In a typical Skype for Business Server deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="fc240-156">Se agli utenti vengono richieste involontariamente le credenziali prima che venga richiesto di immettere il proprio PIN, la chiave del registro di sistema **DisableNTCredentials** potrebbe essere involontariamente configurata nei computer client, possibilmente tramite criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="fc240-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="fc240-157">Per impedire la richiesta aggiuntiva di credenziali, creare la seguente voce del registro di sistema nella workstation locale o utilizzare il modello amministrativo Skype for business da applicare a tutti gli utenti di un determinato pool utilizzando criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="fc240-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="fc240-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="fc240-158">SavePassword</span></span>

<span data-ttu-id="fc240-159">Quando un utente accede a Skype for business per la prima volta, all'utente viene richiesto di salvare la propria password.</span><span class="sxs-lookup"><span data-stu-id="fc240-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="fc240-160">Se selezionata, questa opzione consente di archiviare il certificato client dell'utente nell'archivio certificati personale e le credenziali di Windows dell'utente da archiviare in Gestione credenziali del computer locale.</span><span class="sxs-lookup"><span data-stu-id="fc240-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="fc240-161">L'impostazione del registro di sistema **SavePassword** dovrebbe essere disattivata quando Skype for business è configurato per supportare l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="fc240-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="fc240-162">Per impedire agli utenti di salvare le password, modificare la seguente voce del registro di sistema nella workstation locale o utilizzare il modello amministrativo Skype for business da applicare a tutti gli utenti di un determinato pool utilizzando criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="fc240-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="fc240-163">Riproduzione di token AD FS 2,0</span><span class="sxs-lookup"><span data-stu-id="fc240-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="fc240-164">AD FS 2,0 fornisce una funzionalità denominata rilevamento della riproduzione di token, in base al quale è possibile rilevare più richieste di token utilizzando lo stesso token e quindi eliminarle.</span><span class="sxs-lookup"><span data-stu-id="fc240-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="fc240-165">Quando questa funzionalità è abilitata, il rilevamento della riproduzione di token protegge l'integrità delle richieste di autenticazione sia nel WS-Federation profilo passivo che nel profilo WebSSO SAML assicurandosi che lo stesso token non venga mai utilizzato più di una volta.</span><span class="sxs-lookup"><span data-stu-id="fc240-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="fc240-166">Questa funzionalità deve essere abilitata in situazioni in cui la sicurezza è un problema molto elevato, ad esempio quando si utilizzano i chioschi.</span><span class="sxs-lookup"><span data-stu-id="fc240-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="fc240-167">Per ulteriori informazioni sul rilevamento della riproduzione di token, vedere [procedure consigliate per la pianificazione e la distribuzione sicure di ad FS 2,0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span><span class="sxs-lookup"><span data-stu-id="fc240-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="fc240-168">Accesso utente esterno</span><span class="sxs-lookup"><span data-stu-id="fc240-168">External User Access</span></span>

<span data-ttu-id="fc240-169">La configurazione di un proxy ADFS o di un proxy inverso per il supporto dell'autenticazione a due fattori di Skype for business da reti esterne non è illustrata in questi argomenti.</span><span class="sxs-lookup"><span data-stu-id="fc240-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fc240-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc240-170">See also</span></span>

[<span data-ttu-id="fc240-171">Configurare l'autenticazione a due fattori in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fc240-171">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
  
