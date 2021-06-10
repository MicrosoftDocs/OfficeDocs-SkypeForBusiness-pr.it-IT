---
title: Preparare l'ambiente
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Informazioni su come preparare l'infrastruttura per la distribuzione di Microsoft Teams Rooms in modo da poter sfruttare tutte le funzionalità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 81aa41895f11b65c9406bd30311f2fcb974949a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117424"
---
# <a name="prepare-your-environment"></a><span data-ttu-id="74dbd-103">Predisporre l'ambiente</span><span class="sxs-lookup"><span data-stu-id="74dbd-103">Prepare your environment</span></span>

<span data-ttu-id="74dbd-104">Questa sezione contiene una panoramica dei passaggi necessari per preparare l'ambiente in modo da poter usare tutte le funzionalità di Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="74dbd-104">This section contains an overview of the steps required to prepare your environment so that you can use all of the features of Microsoft Teams Rooms.</span></span>
  
1. <span data-ttu-id="74dbd-105">Preparare un account del dispositivo per ogni Microsoft Teams Rooms console.</span><span class="sxs-lookup"><span data-stu-id="74dbd-105">Prepare a device account for each Microsoft Teams Rooms console.</span></span> <span data-ttu-id="74dbd-106">Vedere [Distribuire Microsoft Teams Rooms](rooms-deploy.md) per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="74dbd-106">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
    
2. <span data-ttu-id="74dbd-107">Verificare che sia disponibile una connessione di rete/Internet funzionante per il dispositivo da usare.</span><span class="sxs-lookup"><span data-stu-id="74dbd-107">Ensure that there is a working network/Internet connection for the device to use.</span></span> 
    
   <span data-ttu-id="74dbd-108">Deve essere in grado di ricevere un indirizzo IP usando il protocollo DHCP.</span><span class="sxs-lookup"><span data-stu-id="74dbd-108">It must be able to receive an IP address by using DHCP.</span></span> <span data-ttu-id="74dbd-109">(Microsoft Teams Rooms non può essere configurato con un indirizzo IP statico all'avvio della prima unità, ma successivamente è possibile configurare un indirizzo IP statico per il dispositivo nel dispositivo o nello switch o router upstream.</span><span class="sxs-lookup"><span data-stu-id="74dbd-109">(Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup, but afterwards, a static IP address for the device could be configured on the device or on the upstream switch or router.)</span></span>

   <span data-ttu-id="74dbd-110">Deve avere queste porte aperte (oltre ad aprire le porte normali per i supporti):</span><span class="sxs-lookup"><span data-stu-id="74dbd-110">It must have these ports open (in addition to opening the normal ports for media):</span></span>
   - <span data-ttu-id="74dbd-111">HTTPS: 443</span><span class="sxs-lookup"><span data-stu-id="74dbd-111">HTTPS: 443</span></span>
   - <span data-ttu-id="74dbd-112">HTTP: 80</span><span class="sxs-lookup"><span data-stu-id="74dbd-112">HTTP: 80</span></span>

   <span data-ttu-id="74dbd-113">Se la rete viene eseguita tramite un proxy, sono necessarie anche le informazioni sull'indirizzo proxy o sullo script.</span><span class="sxs-lookup"><span data-stu-id="74dbd-113">If your network runs through a proxy, you'll need the proxy address or script information as well.</span></span>
    
   > [!IMPORTANT]
   > <span data-ttu-id="74dbd-114">Microsoft Teams Rooms non supporta l'autenticazione proxy perché può interferire con le normali operazioni della chat room.</span><span class="sxs-lookup"><span data-stu-id="74dbd-114">Microsoft Teams Rooms does not support proxy authentication as it may interfere with regular operations of the room.</span></span> <span data-ttu-id="74dbd-115">Assicurarsi che Microsoft Teams Rooms siano state esentate dall'autenticazione proxy prima di entrare in produzione.</span><span class="sxs-lookup"><span data-stu-id="74dbd-115">Ensure that Microsoft Teams Rooms have been exempted from proxy authentication before going into production.</span></span>
  
3. <span data-ttu-id="74dbd-116">Per migliorare l'esperienza utente, Microsoft raccoglie i dati.</span><span class="sxs-lookup"><span data-stu-id="74dbd-116">In order to improve your experience, Microsoft collects data.</span></span> <span data-ttu-id="74dbd-117">Per consentire a Microsoft di raccogliere dati, consentire questi siti:</span><span class="sxs-lookup"><span data-stu-id="74dbd-117">To allow Microsoft to collect data, allow these sites:</span></span>

   - <span data-ttu-id="74dbd-118">Endpoint client di telemetria: https://vortex.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="74dbd-118">Telemetry client endpoint: https://vortex.data.microsoft.com/</span></span>
   - <span data-ttu-id="74dbd-119">Endpoint delle impostazioni di telemetria: https://settings.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="74dbd-119">Telemetry settings endpoint: https://settings.data.microsoft.com/</span></span>
    
### <a name="create-and-test-a-device-account"></a><span data-ttu-id="74dbd-120">Creare e testare un account del dispositivo</span><span class="sxs-lookup"><span data-stu-id="74dbd-120">Create and test a device account</span></span>

<span data-ttu-id="74dbd-121">Un *account del dispositivo* è un account che il client di Microsoft Teams Rooms usa per accedere alle funzionalità da Exchange, ad esempio il calendario, e per abilitare Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="74dbd-121">A  *device account*  is an account that the Microsoft Teams Rooms client uses to access features from Exchange, like calendar, and to enable Skype for Business.</span></span> <span data-ttu-id="74dbd-122">Vedere [Distribuire Microsoft Teams Rooms](rooms-deploy.md) per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="74dbd-122">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
  
### <a name="check-network-availability"></a><span data-ttu-id="74dbd-123">Verificare la disponibilità della rete</span><span class="sxs-lookup"><span data-stu-id="74dbd-123">Check network availability</span></span>

<span data-ttu-id="74dbd-124">Per funzionare correttamente, il dispositivo Microsoft Teams Rooms deve avere accesso a una rete cablata che soddisfi questi requisiti:</span><span class="sxs-lookup"><span data-stu-id="74dbd-124">In order to function properly, the Microsoft Teams Rooms device must have access to a wired network that meets these requirements:</span></span>
  
- <span data-ttu-id="74dbd-125">Accesso all'istanza di Active Directory o Azure Active Directory (Azure AD), nonché ai server microsoft Exchange e Skype for Business server.</span><span class="sxs-lookup"><span data-stu-id="74dbd-125">Access to your Active Directory or Azure Active Directory (Azure AD) instance, as well as your Microsoft Exchange and Skype for Business servers.</span></span>

- <span data-ttu-id="74dbd-126">Accesso a un server in grado di fornire un indirizzo IP tramite DHCP.</span><span class="sxs-lookup"><span data-stu-id="74dbd-126">Access to a server that can provide an IP address using DHCP.</span></span> <span data-ttu-id="74dbd-127">Microsoft Teams Rooms non può essere configurato con un indirizzo IP statico al primo avvio dell'unità.</span><span class="sxs-lookup"><span data-stu-id="74dbd-127">Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup.</span></span>

- <span data-ttu-id="74dbd-128">Accesso alle porte HTTP 80 e 443.</span><span class="sxs-lookup"><span data-stu-id="74dbd-128">Access to HTTP ports 80 and 443.</span></span>

- <span data-ttu-id="74dbd-129">Le porte TCP e UDP configurate come descritto [in](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) Requisiti di porta e protocollo per i server per le implementazioni Skype for Business Server locali o URL e intervalli di indirizzi IP di Microsoft 365 e Office 365 per le implementazioni online di [Microsoft Teams](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="74dbd-129">TCP and UDP ports configured as described in [Port and protocol requirements for servers](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) for on-premise Skype for Business Server implementations, or [Microsoft 365 and Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) for Microsoft Teams or Skype for Business online implementations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74dbd-130">Assicurarsi di usare una connessione di rete cablata da 1 Gbps per assicurarsi di avere la larghezza di banda necessaria.</span><span class="sxs-lookup"><span data-stu-id="74dbd-130">Be sure to use a wired 1 Gbps network connection to assure you will have the needed bandwidth.</span></span>

> [!NOTE]
> <span data-ttu-id="74dbd-131">Gli aggiornamenti software per Microsoft Teams Rooms vengono scaricati automaticamente dal Microsoft Store per le aziende.</span><span class="sxs-lookup"><span data-stu-id="74dbd-131">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="74dbd-132">Vedere [Prerequisiti per Microsoft Store per le aziende e Education](/microsoft-store/prerequisites-microsoft-store-for-business) per verificare che la console della sala sia in grado di accedere al negozio e di eseguire l'aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="74dbd-132">See [Prerequisites for Microsoft Store for Business and Education](/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>
  
### <a name="certificates"></a><span data-ttu-id="74dbd-133">Certificati</span><span class="sxs-lookup"><span data-stu-id="74dbd-133">Certificates</span></span>

<span data-ttu-id="74dbd-134">Il dispositivo Microsoft Teams Rooms usa certificati per Exchange web services, Microsoft Teams o Skype for Business, l'utilizzo della rete e l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="74dbd-134">Your Microsoft Teams Rooms device uses certificates for Exchange Web Services, Microsoft Teams or Skype for Business, network usage, and authentication.</span></span> <span data-ttu-id="74dbd-135">Se i server correlati usano certificati pubblici, come nel caso di Online e di alcune distribuzioni locali, non dovrebbero essere necessarie altre azioni da parte dell'amministratore per installare i certificati.</span><span class="sxs-lookup"><span data-stu-id="74dbd-135">If the related servers use public certificates, which is the case for Online and some On-Premises deployments, there should be no further action required on the part of the admin to install certificates.</span></span> <span data-ttu-id="74dbd-136">Se, d'altra parte, l'autorità di certificazione è una CA privata (tipica per le distribuzioni locali), il dispositivo deve considerare attendibile tale CA, ovvero avere i certificati della catena CA +CA installati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="74dbd-136">If, on the other hand, the certificate authority is a private CA (typical for On-Premises deployments) then the device needs to trust that CA which means having the CA + CA chain certificates installed on the device.</span></span> <span data-ttu-id="74dbd-137">L'aggiunta del dispositivo al dominio può eseguire questa attività automaticamente.</span><span class="sxs-lookup"><span data-stu-id="74dbd-137">Adding the device to the domain may perform this task automatically.</span></span>
  
<span data-ttu-id="74dbd-138">I certificati verranno installati nello stesso modo per qualsiasi altro client Windows client.</span><span class="sxs-lookup"><span data-stu-id="74dbd-138">You will install certificates the same way you would for any other Windows client.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="74dbd-139">I certificati potrebbero essere necessari per Microsoft Teams Rooms usare Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="74dbd-139">Certificates may be required in order to have Microsoft Teams Rooms use Skype for Business Server.</span></span>
  
### <a name="proxy"></a><span data-ttu-id="74dbd-140">Proxy</span><span class="sxs-lookup"><span data-stu-id="74dbd-140">Proxy</span></span>

<span data-ttu-id="74dbd-141">Microsoft Teams Rooms è progettato per ereditare le impostazioni del proxy dal Windows sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="74dbd-141">Microsoft Teams Rooms is designed to inherit Proxy settings from the Windows OS.</span></span> <span data-ttu-id="74dbd-142">Accedere al Windows sistema operativo nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="74dbd-142">Access the Windows OS in the following manner:</span></span>
  
1. <span data-ttu-id="74dbd-143">Nell'Microsoft Teams Rooms utente fare clic sull'icona Impostazioni a forma di ingranaggio nel punto in cui verrà richiesta la password di amministratore locale nel dispositivo (la password predefinita è **sfb).**</span><span class="sxs-lookup"><span data-stu-id="74dbd-143">In the Microsoft Teams Rooms UI, click on the Settings gear icon where you'll be prompted for the local Administrator password on the device (the default password is **sfb**).</span></span>
2. <span data-ttu-id="74dbd-144">Toccare **Impostazioni** seguito dal pulsante Vai **a Windows** e quindi toccare  il pulsante Accedi amministratore e  quindi fare clic sul pulsante Amministratore (se il computer fa parte del dominio scegliere **Altro utente,** quindi usare .\admin come nome utente).</span><span class="sxs-lookup"><span data-stu-id="74dbd-144">Tap on **Settings** followed by tapping on the **Go to Windows** button and then tapping on the **go to Admin Sign In** button and then clicking the **Administrator** button (if the computer is domain joined choose **Other User,** then use .\admin as the user name).</span></span>
3. <span data-ttu-id="74dbd-145">Nella casella **Cerca Windows** in basso a sinistra digitare regedit (premere a lungo lo schermo o fare clic con il pulsante destro del mouse e scegliere Esegui **come amministratore).**</span><span class="sxs-lookup"><span data-stu-id="74dbd-145">In the **Search Windows** box bottom left type in regedit (either long press the screen or right click and choose **Run as administrator**).</span></span>
4. <span data-ttu-id="74dbd-146">Fare clic sulla cartella HKEY_USERS (verrà visualizzato un elenco di SID degli utenti del computer) verificare che la cartella radice HKEY_USERS selezionata.</span><span class="sxs-lookup"><span data-stu-id="74dbd-146">Click on the HKEY_USERS folder (you'll see a list of machine user SIDs) ensure the root folder HKEY_USERS is selected.</span></span>
       
5. <span data-ttu-id="74dbd-147">Fare clic su File e quindi **scegliere Carica hive.**</span><span class="sxs-lookup"><span data-stu-id="74dbd-147">Click on File and then choose **Load Hive.**</span></span>
6. <span data-ttu-id="74dbd-148">Passare alla **cartella C:\Users\Skype** e digitare nella casella Nome file NTUSER.dat e premere il pulsante Apri</span><span class="sxs-lookup"><span data-stu-id="74dbd-148">Browse to the **C:\Users\Skype** folder and type in the File name box NTUSER.dat and press the open button</span></span>

7. <span data-ttu-id="74dbd-149">Verrà richiesto di specificare un nome di chiave per l'hive appena caricato. digitare Skype (ora dovrebbero essere presenti le impostazioni del Registro di sistema per l'Skype utente).</span><span class="sxs-lookup"><span data-stu-id="74dbd-149">You'll be prompted for a Key Name for your newly loaded Hive; type in Skype (you should now see the registry settings for the Skype User).</span></span>
 
8. <span data-ttu-id="74dbd-150">Aprire il Skype chiave e passare a HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings quindi verificare che le impostazioni siano immesse:</span><span class="sxs-lookup"><span data-stu-id="74dbd-150">Open the Skype key and browse to HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings then ensure these settings are entered:</span></span> 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    <span data-ttu-id="74dbd-151">Se ProxyServer non esiste, potrebbe essere necessario aggiungere questa chiave come stringa, modificare xx.xx.xx.xx:8080 nell'ip/host e nella porta del server proxy.</span><span class="sxs-lookup"><span data-stu-id="74dbd-151">If ProxyServer doesn't exist you may have to add this key as a string, change the xx.xx.xx.xx:8080 to the ip/host and port of your Proxy server.</span></span>
 
    <span data-ttu-id="74dbd-152">Se il cliente usa un file PAC, la configurazione sarà simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="74dbd-152">If the customer is using a PAC file the configuration would look like the example below:</span></span>

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. <span data-ttu-id="74dbd-153">Dopo aver apportato le modifiche, evidenziare la chiave utente Skype (cartella radice per Skype) e scegliere scarica Hive dal menu File del Registro di sistema (verrà chiesto di confermare - selezionare **Sì**).</span><span class="sxs-lookup"><span data-stu-id="74dbd-153">Once you are finished making your changes highlight the Skype User key (root folder for Skype) and choose unload Hive from the Registry file menu (you'll be prompted for confirmation - select **Yes**).</span></span>
    
10. <span data-ttu-id="74dbd-154">È ora possibile chiudere l'editor del Registro di sistema e digitare la disconnessione nella Windows di ricerca.</span><span class="sxs-lookup"><span data-stu-id="74dbd-154">You can now close the registry editor and type logoff into the Windows search box.</span></span>
    
11. <span data-ttu-id="74dbd-155">Tornare alla schermata di accesso, scegliere l'Skype **utente.**</span><span class="sxs-lookup"><span data-stu-id="74dbd-155">Back at the sign-in screen, choose the **Skype** user.</span></span> <span data-ttu-id="74dbd-156">Se tutti i passaggi precedenti hanno avuto esito positivo, Microsoft Teams Rooms l'accesso verrà eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="74dbd-156">If all the previous steps were successful, the Microsoft Teams Rooms device will sign-in successfully.</span></span>
    
<span data-ttu-id="74dbd-157">Vedere [l'articolo Sicurezza](./security.md#network-security) di rete per informazioni dettagliate su FQDN, porte e intervalli di indirizzi IP necessari per Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="74dbd-157">See the [Network Security](./security.md#network-security) article for full details on FQDNs, ports, and IP address ranges required for Microsoft Teams Rooms.</span></span>
  
  
### <a name="create-provisioning-packages"></a><span data-ttu-id="74dbd-158">Creare pacchetti di provisioning</span><span class="sxs-lookup"><span data-stu-id="74dbd-158">Create provisioning packages</span></span>

<span data-ttu-id="74dbd-159">I pacchetti di provisioning verranno utilizzati per eseguire l'autenticazione Exchange Server, Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="74dbd-159">You will use provisioning packages to authenticate to Exchange Server, Microsoft 365, or Office 365.</span></span>
  
### <a name="admin-group-management"></a><span data-ttu-id="74dbd-160">Gestione dei gruppi di amministratori</span><span class="sxs-lookup"><span data-stu-id="74dbd-160">Admin group management</span></span>

<span data-ttu-id="74dbd-161">Dopo l'aggiunta al dominio, è possibile usare Criteri di gruppo o Gestione computer locale per impostare un gruppo di sicurezza come amministratore locale come per un PC Windows nel dominio.</span><span class="sxs-lookup"><span data-stu-id="74dbd-161">After domain joining, you can use Group Policy or the Local Computer Management to set a Security Group as local administrator just like you would for a Windows PC in your domain.</span></span> <span data-ttu-id="74dbd-162">Chiunque sia membro di quel gruppo di sicurezza può immettere le proprie credenziali e sbloccare Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="74dbd-162">Anyone who is a member of that security group can enter their credentials and unlock Settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="74dbd-163">Se il dispositivo Microsoft Teams Rooms perde la relazione di trust con il dominio, ad esempio se si rimuove il Microsoft Teams Rooms dal dominio dopo che è stato aggiunto al dominio, non sarà possibile eseguire l'autenticazione nel dispositivo e aprire Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="74dbd-163">If your Microsoft Teams Rooms device loses trust with the domain (for example, if you remove the Microsoft Teams Rooms from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="74dbd-164">La soluzione alternativa consiste nell'accedere con l'account di amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="74dbd-164">The workaround is to log in with the local Admin account.</span></span> 
  
## <a name="local-accounts"></a><span data-ttu-id="74dbd-165">Account locali</span><span class="sxs-lookup"><span data-stu-id="74dbd-165">Local accounts</span></span>

### <a name="microsoft-teams-rooms-local-user-account"></a><span data-ttu-id="74dbd-166">Microsoft Teams Rooms Account utente locale</span><span class="sxs-lookup"><span data-stu-id="74dbd-166">Microsoft Teams Rooms Local User Account</span></span>

<span data-ttu-id="74dbd-167">L'account del dispositivo in genere non usa una password.</span><span class="sxs-lookup"><span data-stu-id="74dbd-167">The Device Account does not typically use a password.</span></span> <span data-ttu-id="74dbd-168">È possibile assegnare una password, ma ci sono conseguenze, tra cui la possibilità che gli utenti siano bloccati dall'applicazione console alla scadenza della password.</span><span class="sxs-lookup"><span data-stu-id="74dbd-168">It is possible to give it a password, but there are consequences, including a possibility that users might get locked out of the console application when that password expires.</span></span> <span data-ttu-id="74dbd-169">Di conseguenza, l'amministratore deve assicurarsi che la password non scada.</span><span class="sxs-lookup"><span data-stu-id="74dbd-169">Consequently, the administrator should take are to ensure that the password is not allowed to expire.</span></span>
  
### <a name="admin---local-administrator-account"></a><span data-ttu-id="74dbd-170">"Amministratore" - Account di amministratore locale</span><span class="sxs-lookup"><span data-stu-id="74dbd-170">"Admin" - Local Administrator Account</span></span>

<span data-ttu-id="74dbd-171">Microsoft Teams Rooms password predefinita è impostata su "sfb".</span><span class="sxs-lookup"><span data-stu-id="74dbd-171">Microsoft Teams Rooms default password is set to "sfb".</span></span> <span data-ttu-id="74dbd-172">La password può essere modificata in locale selezionando Windows Impostazioni Vai a Windows o nel file AutoUnattend.xml (usare Windows System Image Manager da ADK per apportare la modifica al \> file XML).</span><span class="sxs-lookup"><span data-stu-id="74dbd-172">The Password can be changed locally by going to Windows Settings \> Go to Windows or in the AutoUnattend.xml file (use the Windows System Image manager from ADK to make the change to the xml file).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="74dbd-173">Assicurarsi di cambiare la password Microsoft Teams Rooms non appena possibile.</span><span class="sxs-lookup"><span data-stu-id="74dbd-173">Be sure to change the Microsoft Teams Rooms password as soon as possible.</span></span> 
  
<span data-ttu-id="74dbd-174">È anche possibile gestire la password dell'amministratore locale configurando un criterio di gruppo in cui gli amministratori di dominio sono amministratori locali.</span><span class="sxs-lookup"><span data-stu-id="74dbd-174">You can also manage the Local Administrator password by setting up a group policy where domain admins are made local admins.</span></span>
  
<span data-ttu-id="74dbd-175">La password di amministratore locale non è inclusa come scelta durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="74dbd-175">The Local admin password is not included as a choice during Setup.</span></span>
  
### <a name="machine-account"></a><span data-ttu-id="74dbd-176">Account computer</span><span class="sxs-lookup"><span data-stu-id="74dbd-176">Machine Account</span></span>

<span data-ttu-id="74dbd-177">Come qualsiasi dispositivo Windows, il nome del computer può essere rinominato facendo clic con il pulsante destro del mouse **Impostazioni** \> **su** \> **Rinomina PC.**</span><span class="sxs-lookup"><span data-stu-id="74dbd-177">Much like any Windows device, the Machine Name can be renamed by right-clicking in **Settings** \> **About** \> **Rename PC**.</span></span>
  
<span data-ttu-id="74dbd-178">Se si vuole rinominare il computer dopo l'aggiunta a un dominio, usare **Rename-Computer**, un comando di PowerShell seguito dal nuovo nome del computer.</span><span class="sxs-lookup"><span data-stu-id="74dbd-178">If you would like to rename the computer after joining it to a domain, use **Rename-Computer**, a PowerShell command, followed by the computer's new name.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="74dbd-179">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="74dbd-179">Related topics</span></span>

[<span data-ttu-id="74dbd-180">Pianificare Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="74dbd-180">Plan Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="74dbd-181">Requisiti per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="74dbd-181">Microsoft Teams Rooms requirements</span></span>](requirements.md)
  
[<span data-ttu-id="74dbd-182">Distribuire Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="74dbd-182">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="74dbd-183">Configurare una console per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="74dbd-183">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
<span data-ttu-id="74dbd-184">[Gestire Microsoft Teams Rooms](rooms-manage.md).</span><span class="sxs-lookup"><span data-stu-id="74dbd-184">[Manage Microsoft Teams Rooms](rooms-manage.md)</span></span>

[<span data-ttu-id="74dbd-185">Prerequisiti per l'Microsoft Store per le aziende e l'istruzione</span><span class="sxs-lookup"><span data-stu-id="74dbd-185">Prerequisites for Microsoft Store for Business and Education</span></span>](/microsoft-store/prerequisites-microsoft-store-for-business)