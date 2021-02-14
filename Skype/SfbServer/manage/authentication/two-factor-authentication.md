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
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="f5cb9-103">Gestire l'autenticazione a due fattori in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f5cb9-103">Manage two-factor authentication in Skype for Business Server</span></span>
 
<span data-ttu-id="f5cb9-104">**Riepilogo:** Gestire l'autenticazione a due fattori in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-104">**Summary:** Manage two-factor authentication in Skype for Business Server.</span></span>
  
<span data-ttu-id="f5cb9-105">L'autenticazione a due fattori offre una maggiore sicurezza richiedendo agli utenti di fornire due forme di autenticazione o identificazione, una combinazione nome utente/password e token o certificato.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="f5cb9-106">Questa operazione è nota anche come "qualcosa di cui si dispone, qualcosa che si conosce".</span><span class="sxs-lookup"><span data-stu-id="f5cb9-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="f5cb9-107">Un esempio tipico di autenticazione a due fattori con un certificato è l'uso di smart card.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-107">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="f5cb9-108">Una smart card contiene un certificato associato all'account utente e può essere convalidata in base alle informazioni sull'utente e sul certificato archiviate in un server.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-108">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="f5cb9-109">Confrontando le informazioni utente (nome utente e password) con il certificato fornito, il server convalida le credenziali e autentica l'utente.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-109">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="f5cb9-110">Quando si configura un ambiente Skype for Business Server per supportare l'autenticazione a due fattori, considerare gli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-110">Consider the following subjects when configuring a Skype for Business Server environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="f5cb9-111">Supporto client</span><span class="sxs-lookup"><span data-stu-id="f5cb9-111">Client Support</span></span>

<span data-ttu-id="f5cb9-112">Gli aggiornamenti cumulativi per lync Server 2013: client desktop di luglio 2013 e il client Skype for Business sono gli unici client che attualmente supportano l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="f5cb9-113">Requisiti della topologia</span><span class="sxs-lookup"><span data-stu-id="f5cb9-113">Topology Requirements</span></span>

<span data-ttu-id="f5cb9-114">I clienti sono invitati a distribuire l'autenticazione a due fattori usando Skype for Business Server dedicato con pool di server perimetrali, director e utenti.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server with Edge, Director, and User Pools.</span></span> <span data-ttu-id="f5cb9-115">Per abilitare l'autenticazione passiva per gli utenti, è necessario disabilitare altri metodi di autenticazione per altri ruoli e servizi, tra cui:</span><span class="sxs-lookup"><span data-stu-id="f5cb9-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="f5cb9-116">**Tipo di configurazione**</span><span class="sxs-lookup"><span data-stu-id="f5cb9-116">**Configuration Type**</span></span>|<span data-ttu-id="f5cb9-117">**Tipo di servizio**</span><span class="sxs-lookup"><span data-stu-id="f5cb9-117">**Service Type**</span></span>|<span data-ttu-id="f5cb9-118">**Ruolo del server**</span><span class="sxs-lookup"><span data-stu-id="f5cb9-118">**Server Role**</span></span>|<span data-ttu-id="f5cb9-119">**Tipo di autenticazione da disabilitare**</span><span class="sxs-lookup"><span data-stu-id="f5cb9-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f5cb9-120">Web Service</span><span class="sxs-lookup"><span data-stu-id="f5cb9-120">Web Service</span></span>  <br/> |<span data-ttu-id="f5cb9-121">WebServer</span><span class="sxs-lookup"><span data-stu-id="f5cb9-121">WebServer</span></span>  <br/> |<span data-ttu-id="f5cb9-122">Direttore</span><span class="sxs-lookup"><span data-stu-id="f5cb9-122">Director</span></span>  <br/> |<span data-ttu-id="f5cb9-123">Kerberos, NTLM e certificato</span><span class="sxs-lookup"><span data-stu-id="f5cb9-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="f5cb9-124">Web Service</span><span class="sxs-lookup"><span data-stu-id="f5cb9-124">Web Service</span></span>  <br/> |<span data-ttu-id="f5cb9-125">WebServer</span><span class="sxs-lookup"><span data-stu-id="f5cb9-125">WebServer</span></span>  <br/> |<span data-ttu-id="f5cb9-126">Front End</span><span class="sxs-lookup"><span data-stu-id="f5cb9-126">Front End</span></span>  <br/> |<span data-ttu-id="f5cb9-127">Kerberos, NTLM e certificato</span><span class="sxs-lookup"><span data-stu-id="f5cb9-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="f5cb9-128">Proxy</span><span class="sxs-lookup"><span data-stu-id="f5cb9-128">Proxy</span></span>  <br/> |<span data-ttu-id="f5cb9-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="f5cb9-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="f5cb9-130">Edge</span><span class="sxs-lookup"><span data-stu-id="f5cb9-130">Edge</span></span>  <br/> |<span data-ttu-id="f5cb9-131">Kerberos e NTLM</span><span class="sxs-lookup"><span data-stu-id="f5cb9-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="f5cb9-132">Proxy</span><span class="sxs-lookup"><span data-stu-id="f5cb9-132">Proxy</span></span>  <br/> |<span data-ttu-id="f5cb9-133">Registrar</span><span class="sxs-lookup"><span data-stu-id="f5cb9-133">Registrar</span></span>  <br/> |<span data-ttu-id="f5cb9-134">Front End</span><span class="sxs-lookup"><span data-stu-id="f5cb9-134">Front End</span></span>  <br/> |<span data-ttu-id="f5cb9-135">Kerberos e NTLM</span><span class="sxs-lookup"><span data-stu-id="f5cb9-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="f5cb9-136">A meno che questi tipi di autenticazione non siano disabilitati a livello di servizio, tutte le altre versioni del client non saranno in grado di accedere correttamente una volta abilitata l'autenticazione a due fattori all'interno della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="f5cb9-137">Individuazione dei servizi di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f5cb9-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="f5cb9-138">I record DNS utilizzati dai client interni ed/o esterni per individuare i servizi Skype for Business devono essere configurati per la risoluzione in un server Skype for Business non abilitato per l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="f5cb9-139">Con questa configurazione, gli utenti dei pool Skype for Business non abilitati per l'autenticazione a due fattori non saranno tenuti a immettere un PIN per l'autenticazione, mentre gli utenti dei pool Skype for Business abilitati per l'autenticazione a due fattori saranno necessari per immettere il PIN per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="f5cb9-140">Autenticazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="f5cb9-140">Exchange Authentication</span></span>

<span data-ttu-id="f5cb9-141">I clienti che hanno distribuito l'autenticazione a due fattori per Microsoft Exchange potrebbero scoprire che alcune funzionalità nel client non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="f5cb9-142">Questo è attualmente da progettazione, poiché il client Skype for Business non supporta l'autenticazione a due fattori per le funzionalità che dipendono dall'integrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="f5cb9-143">Contatti</span><span class="sxs-lookup"><span data-stu-id="f5cb9-143">Contacts</span></span>

<span data-ttu-id="f5cb9-144">Gli utenti di Skype for Business configurati per sfruttare la funzionalità Archivio contatti unificato scopriranno che i loro contatti non sono più disponibili dopo l'accesso con l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="f5cb9-145">È consigliabile utilizzare il cmdlet **Invoke-CsUcsRollback** per rimuovere i contatti utente esistenti dall'archivio contatti unificato e archiviarli in Skype for Business Server prima di abilitare l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="f5cb9-146">Ricerca competenze</span><span class="sxs-lookup"><span data-stu-id="f5cb9-146">Skill Search</span></span>

<span data-ttu-id="f5cb9-147">I clienti che hanno configurato la funzionalità Di ricerca per competenza nell'ambiente Skype for Business scopriranno che questa funzionalità non funziona quando Skype for Business è abilitato per l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="f5cb9-148">Questo è da progettazione, poiché Microsoft SharePoint attualmente non supporta l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="f5cb9-149">Credentials</span><span class="sxs-lookup"><span data-stu-id="f5cb9-149">Credentials</span></span>

<span data-ttu-id="f5cb9-150">Esistono alcune considerazioni sulla distribuzione che riguardano le credenziali di Skype for Business salvate che possono influire sugli utenti configurati per l'utilizzo dell'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="f5cb9-151">Eliminazione delle credenziali salvate</span><span class="sxs-lookup"><span data-stu-id="f5cb9-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="f5cb9-152">Gli utenti  devono usare l'opzione Elimina le informazioni di accesso nel client Skype for Business ed eliminare la cartella del profilo SIP da %localappdata%\Microsoft\Office\15.0\Skype for Business prima di tentare di accedere per la prima volta utilizzando l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="f5cb9-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="f5cb9-153">DisableNTCredentials</span></span>

<span data-ttu-id="f5cb9-154">Con il metodo di autenticazione Kerberos o NTLM, le credenziali di Windows dell'utente vengono utilizzate automaticamente per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="f5cb9-155">In una distribuzione tipica di Skype for Business Server in cui Kerberos e/o NTLM è abilitato per l'autenticazione, gli utenti non devono immettere le proprie credenziali ogni volta che eseguono l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-155">In a typical Skype for Business Server deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="f5cb9-156">Se agli utenti vengono involontariamente richieste le credenziali prima che venga richiesto di immettere il PIN, la chiave del Registro di sistema **DisableNTCredentials** potrebbe essere configurata involontariamente nei computer client, probabilmente tramite Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="f5cb9-157">Per impedire la richiesta aggiuntiva di credenziali, creare la seguente voce del Registro di sistema nella workstation locale o utilizzare il modello amministrativo di Skype for Business da applicare a tutti gli utenti per un determinato pool tramite Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="f5cb9-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="f5cb9-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="f5cb9-158">SavePassword</span></span>

<span data-ttu-id="f5cb9-159">Quando un utente accede a Skype for Business per la prima volta, all'utente viene richiesto di salvare la password.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="f5cb9-160">Se selezionata, questa opzione consente di archiviare il certificato client dell'utente nell'archivio certificati personali e le credenziali di Windows dell'utente in Gestione credenziali del computer locale.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="f5cb9-161">L'impostazione del Registro di sistema **SavePassword** deve essere disabilitata quando Skype for Business è configurato per supportare l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="f5cb9-162">Per impedire agli utenti di salvare le password, modificare la seguente voce del Registro di sistema nella workstation locale o utilizzare il modello amministrativo di Skype for Business da applicare a tutti gli utenti di un determinato pool tramite Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="f5cb9-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="f5cb9-163">Riesecuzione token AD FS 2.0</span><span class="sxs-lookup"><span data-stu-id="f5cb9-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="f5cb9-164">ADFS 2.0 offre una funzionalità denominata rilevamento della riproduzione di token, in base alla quale è possibile rilevare e quindi eliminare più richieste di token che usano lo stesso token.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="f5cb9-165">Quando questa funzionalità è abilitata, il rilevamento della riproduzione dei token protegge l'integrità delle richieste di autenticazione sia nel profilo passivo di WS-Federation che nel profilo WebSSO SAML assicurando che lo stesso token non sia mai utilizzato più di una volta.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="f5cb9-166">Questa funzionalità deve essere abilitata in situazioni in cui la sicurezza è molto importante, ad esempio quando si usano chioschi.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="f5cb9-167">Per ulteriori informazioni sul rilevamento della riproduzione di token, vedere Procedure consigliate per la pianificazione e [la distribuzione sicure di ADFS 2.0.](https://go.microsoft.com/fwlink/p/?LinkId=309215)</span><span class="sxs-lookup"><span data-stu-id="f5cb9-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="f5cb9-168">Accesso utente esterno</span><span class="sxs-lookup"><span data-stu-id="f5cb9-168">External User Access</span></span>

<span data-ttu-id="f5cb9-169">La configurazione di un proxy ADFS o di un proxy inverso per supportare l'autenticazione a due fattori di Skype for Business da reti esterne non è trattata in questi argomenti.</span><span class="sxs-lookup"><span data-stu-id="f5cb9-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f5cb9-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5cb9-170">See also</span></span>

[<span data-ttu-id="f5cb9-171">Configurare l'autenticazione a due fattori in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f5cb9-171">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
  
