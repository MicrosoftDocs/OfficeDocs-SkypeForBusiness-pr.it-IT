---
title: Distribuzione dei telefoni per Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: Informazioni sui passaggi di distribuzione per ottenere il firmware corretto, aggiornarlo se necessario, assegnare licenze e configurare le impostazioni per Skype for Business telefoni online
ms.openlocfilehash: 1c607f0dd5c3a82c744f26432fe1c65f31263440
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237372"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="97761-103">Distribuzione dei telefoni per Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="97761-103">Deploying Skype for Business Online phones</span></span>

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="97761-104">[] Questa guida ti aiuta nella distribuzione dei telefoni IP per Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="97761-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="97761-105">In tutti i tipi di aziende, avere un numero di telefono consente agli utenti di effettuare e ricevere chiamate vocali ed è un requisito importante per le aziende.</span><span class="sxs-lookup"><span data-stu-id="97761-105">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business.</span></span> <span data-ttu-id="97761-106">Gli utenti che hanno numeri di telefono potranno effettuare chiamate vocali in tutti i Skype for Business, inclusi telefoni IP, PC e dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="97761-106">Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="97761-107">Per altre informazioni sui telefoni IP Skype for Business telefoni IP, vedere Ottenere telefoni [per Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="97761-107">You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="97761-108">Fasi della distribuzione di telefoni IP</span><span class="sxs-lookup"><span data-stu-id="97761-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="97761-109">Fase 1 - Scarica le guide per l'amministratore e i manuali del telefono del produttore</span><span class="sxs-lookup"><span data-stu-id="97761-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="97761-110">Prima di iniziare, è una buona idea quella di scaricare le guide per l'amministratore e i manuali d'uso del telefono del produttore.</span><span class="sxs-lookup"><span data-stu-id="97761-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="97761-111">Per i telefoni Polycom, vedere [la Libreria di documentazione Poly.](https://documents.polycom.com/category/voice)</span><span class="sxs-lookup"><span data-stu-id="97761-111">For Polycom phones, see the [Poly Documentation Library](https://documents.polycom.com/category/voice).</span></span>
    
- <span data-ttu-id="97761-112">Per i telefoni Yealink, vedere [Yealink Skype for Business hd SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span><span class="sxs-lookup"><span data-stu-id="97761-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="97761-113">Per i telefoni AudioCodes, consulta la [Guida alla gestione del provisioning Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span><span class="sxs-lookup"><span data-stu-id="97761-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="97761-114">Fase 2 - Assicurati di stare acquistando o migrando un telefono IP e firmware supportati da Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="97761-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="97761-115">Un telefono e firmware supportati da Skype for Business Online sono compatibili anche con Skype for Business Server, ma non è sempre vero il contrario.</span><span class="sxs-lookup"><span data-stu-id="97761-115">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true.</span></span> <span data-ttu-id="97761-116">Per assicurarsi di acquistare o eseguire il provisioning di un telefono e firmware supportati, vedere Ottenere telefoni per Skype for Business [Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="97761-116">To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="97761-117">Fase 3 - Verifica che sia installato il firmware giusto e aggiorna il firmware, se necessario</span><span class="sxs-lookup"><span data-stu-id="97761-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="97761-118">Controllare la versione del firmware nei telefoni.</span><span class="sxs-lookup"><span data-stu-id="97761-118">Check the firmware version on your phones.</span></span> <span data-ttu-id="97761-119">Per:</span><span class="sxs-lookup"><span data-stu-id="97761-119">For:</span></span>
  
- <span data-ttu-id="97761-120">**Telefoni VVX Polycom**, vai a **Impostazioni** > **Stato** > **Piattaforma** > **Applicazione** > **Principale**.</span><span class="sxs-lookup"><span data-stu-id="97761-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="97761-121">i **telefoni Yealink**, accedi a **Status** (Stato) sulla schermata principale del telefono.</span><span class="sxs-lookup"><span data-stu-id="97761-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="97761-122">**Telefoni AudioCodes**, vai a **Menu** > **Stato dispositivo** > **Versione firmware** dalla schermata di avvio.</span><span class="sxs-lookup"><span data-stu-id="97761-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="97761-123">Per l'accesso remoto ai dettagli del telefono, vedere le guide per l'amministrazione del produttore.</span><span class="sxs-lookup"><span data-stu-id="97761-123">For remote access to phone details, refer to manufacturer administration guides.</span></span> <span data-ttu-id="97761-124">Vedi i link qui sopra per i manuali d'uso e i manuali del telefono.</span><span class="sxs-lookup"><span data-stu-id="97761-124">See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="97761-125">I **telefoni Lync Phone Edition (LPE)**, accedi a **Menu** > **System Information** (Informazioni sul sistema) dalla schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="97761-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="97761-126">Fase 4 - Considerazioni sull'aggiornamento del dispositivo</span><span class="sxs-lookup"><span data-stu-id="97761-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="97761-127">Il firmware Polycom precedente alla 5.5.1.X aveva un meccanismo di blocco del dispositivo specifico del produttore che viene sostituito con un'implementazione Skype for Business "Telefono-Lock".</span><span class="sxs-lookup"><span data-stu-id="97761-127">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock."</span></span> <span data-ttu-id="97761-128">L'aggiornamento di un telefono da 5.4.X.X protetto con "Device-Lock" a 5.5.1.X con "Telefono-Lock" non erediterà il codice PIN da "Device-Lock", che può lasciare il telefono non protetto.</span><span class="sxs-lookup"><span data-stu-id="97761-128">Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured.</span></span> <span data-ttu-id="97761-129">Gli utenti che hanno attivato "Device-Lock" devono abilitare il parametro Profilo dispositivo Polycom seguente per concedere agli utenti il controllo del tempo di aggiornamento (lync.deviceUpdate.popUpSK.enabled=1).</span><span class="sxs-lookup"><span data-stu-id="97761-129">Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="97761-130">Gli upgrade del firmware sono gestiti dal servizio Skype for Business Service.</span><span class="sxs-lookup"><span data-stu-id="97761-130">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="97761-131">Ogni firmware del telefono certificato Skype for Business viene caricato sul server Skype for Business Update e gli aggiornamenti dispositivo sono attivati su tutti i telefoni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="97761-131">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> <span data-ttu-id="97761-132">A seconda del tempo di inattività sul telefono e degli intervalli di polling, i telefoni scaricano e installano automaticamente l'ultima build certificata.</span><span class="sxs-lookup"><span data-stu-id="97761-132">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="97761-133">È possibile disabilitare le impostazioni di aggiornamento del dispositivo usando il cmdlet [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) e impostando il _parametro EnableDeviceUpdate_ su `false` .</span><span class="sxs-lookup"><span data-stu-id="97761-133">You can disable the device update settings by using the [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![Schermata che mostra la distribuzione di telefoni](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="97761-135">Quando un nuovo firmware è disponibile e pronto per il download e l'installazione, il telefono avviserà l'utente.</span><span class="sxs-lookup"><span data-stu-id="97761-135">When a new firmware is available and ready for download and install, the phone will notify the user.</span></span> <span data-ttu-id="97761-136">I telefoni Polycom invieranno una notifica all'utente e gli forniranno un'opzione **per l'aggiornamento o** il **posticipo.**</span><span class="sxs-lookup"><span data-stu-id="97761-136">Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![Schermata che mostra le opzioni aggiorna e posticipa.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="97761-138">Per un telefono Polycom, è possibile aggiornare il firmware del telefono selezionando **SwUpdate**.</span><span class="sxs-lookup"><span data-stu-id="97761-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![Schermata che mostra l'opzione SwUpdate](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="97761-p108">Puoi anche scegliere di gestire gli aggiornamenti del firmware utilizzando un sistema di provisioning partner. Per la gestione del sistema di provisioning partner, compresa la personalizzazione avanzata del telefono, consulta le guide per l'amministratore del produttore.</span><span class="sxs-lookup"><span data-stu-id="97761-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="97761-142">Assicurati di avere un'unica autorità di aggiornamento dispositivi (aggiornamento del dispositivo in banda o server di provisioning di terze parti) per evitare loop di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="97761-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="97761-143">Passaggio 5 - Configurazione e impostazioni telefoniche dell'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="97761-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="97761-p109">Puoi impostare le opzioni e i criteri del telefono più comunemente utilizzati che utilizzano i cmdlet di Windows PowerShell per la gestione in banda di Skype for Business. Consulta [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) per i dettagli di questi parametri e impostazioni.</span><span class="sxs-lookup"><span data-stu-id="97761-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="97761-146">Per la pianificazione dell'infrastruttura di rete, [vedere Skype Operations Framework.](https://www.skypeoperationsframework.com/)</span><span class="sxs-lookup"><span data-stu-id="97761-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="97761-147">Passaggio 6 - Preparazione per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="97761-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="97761-148">Per consentire agli utenti di accedere correttamente a un telefono Skype for Business Online ed effettuare chiamate, è necessario assicurarsi che agli utenti siano assegnate le licenze corrette.</span><span class="sxs-lookup"><span data-stu-id="97761-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span></span> <span data-ttu-id="97761-149">Come minimo, dovrai assegnare una licenza Sistema telefonico e un piano per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="97761-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="97761-150">Per altre informazioni, è possibile vedere Skype for Business e [Microsoft Teams licenze](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) per i componenti aggiuntivi e [Assegnare](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)Skype for Business e Microsoft Teams licenze .</span><span class="sxs-lookup"><span data-stu-id="97761-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="97761-151">Per saperne di più sui Piani per chiamate, leggere Sistema telefonico [e Piani per chiamate](/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="97761-151">You can find out more about Calling Plans by reading [Phone System and Calling Plans](/microsoftteams/calling-plan-landing-page)</span></span>
  
- <span data-ttu-id="97761-152">Le **opzioni di accesso** disponibili per gli utenti online son le seguenti.</span><span class="sxs-lookup"><span data-stu-id="97761-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="97761-153">Gli utenti **con telefoni Polycom VVX 5XX/6XX** visualizzano:</span><span class="sxs-lookup"><span data-stu-id="97761-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Schermata che mostra l'accesso ai telefoni Polycom](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="97761-155">Gli utenti **con telefoni Yealink T48G/T46G** potranno vedere:</span><span class="sxs-lookup"><span data-stu-id="97761-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Schermata che mostra l'accesso ai telefoni Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="97761-157">Per informazioni dettagliate sulle opzioni di accesso supportate dal produttore, vedere Ottenere telefoni [per Skype for Business Online.](getting-phones-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="97761-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="97761-p111">**ID utente** Utilizzando la tastiera del telefono o la tastiera a schermo (se disponibile), gli utenti possono utilizzare il nome utente e la password della propria organizzazione per accedere al telefono. Ad esempio, possono utilizzare il formato UPN come <em>amosm@contoso.com</em>  per il nome utente.</span><span class="sxs-lookup"><span data-stu-id="97761-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like <em>amosm@contoso.com</em>  for their user name.</span></span>
    
     ![Schermata che mostra la schermata di accesso](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="97761-161">L'autenticazione PIN non è supportata per Skype for Business online per i telefoni IP LPE e Partner.</span><span class="sxs-lookup"><span data-stu-id="97761-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="97761-162">**Uso di un PC** Quando il software Better Together over Ethernet (BToE) è installato nel PC dell'utente e abilitato, gli utenti possono accedere ai loro telefoni usando la finestra di autenticazione nell'app Windows Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="97761-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span></span> <span data-ttu-id="97761-163">Per altre informazioni, vedere Passaggio 7 (facoltativo) - Se si ha l'associazione di dispositivi e [Better Together over Ethernet (BToE).](deploying-skype-for-business-online-phones.md#BK_BTOE)</span><span class="sxs-lookup"><span data-stu-id="97761-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="97761-p113">Gli utenti devono utilizzare il nome utente e la password della propria organizzazione per accedere al telefono. Ad esempio, possono utilizzare il formato UPN come  <em>amosm@contoso.com</em>  per il nome utente.</span><span class="sxs-lookup"><span data-stu-id="97761-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  <em>amosm@contoso.com</em>  for their user name.</span></span>
  
     ![Schermata che mostra la schermata di accesso](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="97761-167">**Uso dell'accesso Web:** si tratta di un nuovo modo per gli utenti online di eseguire l'autenticazione con un Web browser standard.</span><span class="sxs-lookup"><span data-stu-id="97761-167">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser.</span></span> <span data-ttu-id="97761-168">Agli utenti verrà fornito un set di istruzioni da seguire quando usano un browser per accedere.</span><span class="sxs-lookup"><span data-stu-id="97761-168">Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="97761-169">Gli utenti **con telefoni Polycom VVX 5XX/6XX** visualizzano:</span><span class="sxs-lookup"><span data-stu-id="97761-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Schermata che mostra le istruzioni Polycom](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="97761-171">Gli utenti **con telefoni Yealink T48G/T46G** potranno vedere:</span><span class="sxs-lookup"><span data-stu-id="97761-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Schermata che mostra le istruzioni yealink](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="97761-173">Il codice che viene generato scadrà in 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="97761-173">The code that is generated will expire in 15 minutes.</span></span> <span data-ttu-id="97761-174">Alla scadenza, l'utente dovrà fare clic **su** Riprova o **su OK** per generare un nuovo codice, a seconda del telefono.</span><span class="sxs-lookup"><span data-stu-id="97761-174">When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="97761-175">Gli utenti **con telefoni Polycom VVX 5XX/6XX** visualizzano:</span><span class="sxs-lookup"><span data-stu-id="97761-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Schermata che mostra il codice Polycom scaduto](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="97761-177">Gli utenti **con telefoni Yealink T48G/T46G** potranno vedere:</span><span class="sxs-lookup"><span data-stu-id="97761-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Schermata che mostra il codice Yealink scaduto](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="97761-179">Utilizzando un browser, accedi all'indirizzo visualizzato sul telefono e inserisci il tuo nome utente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="97761-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![Schermata che mostra la verifica della posta elettronica](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="97761-181">Immetti il codice mostrato sul telefono.</span><span class="sxs-lookup"><span data-stu-id="97761-181">Enter the code shown on the phone.</span></span>
    
     ![Schermata che mostra l'immissione di codice nella schermata di accesso](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="97761-183">Verificare che nel sito sia visualizzato "[Telefono Nome produttore] **Skype for Business certificato Telefono**", quindi fare clic su **Continua**.</span><span class="sxs-lookup"><span data-stu-id="97761-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![Schermata che mostra la verifica del nome](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="97761-185">Fai clic sulle credenziali dell'utente o fai clic su **Usa un altro account**:</span><span class="sxs-lookup"><span data-stu-id="97761-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![Schermata che mostra le opzioni delle credenziali](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="97761-187">Quando viene visualizzata la pagina seguente, è possibile chiudere il browser.</span><span class="sxs-lookup"><span data-stu-id="97761-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![Schermata che mostra il messaggio di conferma](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="97761-189">I telefoni LPE per Skype for Business online supportano l'accesso solo attraverso tethering USB.</span><span class="sxs-lookup"><span data-stu-id="97761-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="97761-190">**Distribuzioni supportate** La tabella seguente mostra i tipi di autenticazione supportati per i modelli di distribuzione attualmente supportati tra cui integrazione Exchange, autenticazione moderna con autenticazione a più fattori (MFA) e Skype for Business online e locale.</span><span class="sxs-lookup"><span data-stu-id="97761-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="97761-191">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="97761-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="97761-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="97761-192">**Exchange**</span></span> <br/> |<span data-ttu-id="97761-193">**Metodo di accesso telefono**</span><span class="sxs-lookup"><span data-stu-id="97761-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="97761-194">**Skype for Business accesso**</span><span class="sxs-lookup"><span data-stu-id="97761-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="97761-195">**Accesso Exchange con autorizzazione moderna e MFA disattivate**</span><span class="sxs-lookup"><span data-stu-id="97761-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="97761-196">**Accesso Exchange con autorizzazione moderna e MFA attivate**</span><span class="sxs-lookup"><span data-stu-id="97761-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="97761-197">Online</span><span class="sxs-lookup"><span data-stu-id="97761-197">Online</span></span>  <br/> |<span data-ttu-id="97761-198">Online</span><span class="sxs-lookup"><span data-stu-id="97761-198">Online</span></span>  <br/> |<span data-ttu-id="97761-199">Accesso Web</span><span class="sxs-lookup"><span data-stu-id="97761-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="97761-200">Sì</span><span class="sxs-lookup"><span data-stu-id="97761-200">Yes</span></span>  <br/> |<span data-ttu-id="97761-201">Sì</span><span class="sxs-lookup"><span data-stu-id="97761-201">Yes</span></span>  <br/> |<span data-ttu-id="97761-202">Sì</span><span class="sxs-lookup"><span data-stu-id="97761-202">Yes</span></span>  <br/> |
|<span data-ttu-id="97761-203">Online</span><span class="sxs-lookup"><span data-stu-id="97761-203">Online</span></span>  <br/> |<span data-ttu-id="97761-204">Online</span><span class="sxs-lookup"><span data-stu-id="97761-204">Online</span></span>  <br/> |<span data-ttu-id="97761-205">Nome utente/password</span><span class="sxs-lookup"><span data-stu-id="97761-205">Username/Password</span></span>  <br/> |<span data-ttu-id="97761-206">Sì</span><span class="sxs-lookup"><span data-stu-id="97761-206">Yes</span></span>  <br/> |<span data-ttu-id="97761-207">Sì</span><span class="sxs-lookup"><span data-stu-id="97761-207">Yes</span></span>  <br/> |<span data-ttu-id="97761-208">No</span><span class="sxs-lookup"><span data-stu-id="97761-208">No</span></span>  <br/> |
|<span data-ttu-id="97761-209">Online</span><span class="sxs-lookup"><span data-stu-id="97761-209">Online</span></span>  <br/> |<span data-ttu-id="97761-210">Locale</span><span class="sxs-lookup"><span data-stu-id="97761-210">On-premises</span></span>  <br/> |<span data-ttu-id="97761-211">Accesso Web</span><span class="sxs-lookup"><span data-stu-id="97761-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="97761-212">Sì</span><span class="sxs-lookup"><span data-stu-id="97761-212">Yes</span></span>  <br/> |<span data-ttu-id="97761-213">No</span><span class="sxs-lookup"><span data-stu-id="97761-213">No</span></span>  <br/> |<span data-ttu-id="97761-214">No</span><span class="sxs-lookup"><span data-stu-id="97761-214">No</span></span>  <br/> |
|<span data-ttu-id="97761-215">Online</span><span class="sxs-lookup"><span data-stu-id="97761-215">Online</span></span>  <br/> |<span data-ttu-id="97761-216">Locale</span><span class="sxs-lookup"><span data-stu-id="97761-216">On-Premises</span></span>  <br/> |<span data-ttu-id="97761-217">Nome utente/password</span><span class="sxs-lookup"><span data-stu-id="97761-217">Username/Password</span></span>  <br/> |<span data-ttu-id="97761-218">Sì</span><span class="sxs-lookup"><span data-stu-id="97761-218">Yes</span></span>  <br/> |<span data-ttu-id="97761-219">Sì</span><span class="sxs-lookup"><span data-stu-id="97761-219">Yes</span></span>  <br/> |<span data-ttu-id="97761-220">No</span><span class="sxs-lookup"><span data-stu-id="97761-220">No</span></span>  <br/> |
|<span data-ttu-id="97761-221">Locale</span><span class="sxs-lookup"><span data-stu-id="97761-221">On-premises</span></span>  <br/> |<span data-ttu-id="97761-222">Online/locale</span><span class="sxs-lookup"><span data-stu-id="97761-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="97761-223">Autenticazione PIN</span><span class="sxs-lookup"><span data-stu-id="97761-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="97761-224">Sì</span><span class="sxs-lookup"><span data-stu-id="97761-224">Yes</span></span>  <br/> |<span data-ttu-id="97761-225">No</span><span class="sxs-lookup"><span data-stu-id="97761-225">No</span></span>  <br/> |<span data-ttu-id="97761-226">No</span><span class="sxs-lookup"><span data-stu-id="97761-226">No</span></span>  <br/> |
|<span data-ttu-id="97761-227">Locale</span><span class="sxs-lookup"><span data-stu-id="97761-227">On-premises</span></span>  <br/> |<span data-ttu-id="97761-228">Online/locale</span><span class="sxs-lookup"><span data-stu-id="97761-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="97761-229">Nome utente/password</span><span class="sxs-lookup"><span data-stu-id="97761-229">Username/Password</span></span>  <br/> |<span data-ttu-id="97761-230">Sì</span><span class="sxs-lookup"><span data-stu-id="97761-230">Yes</span></span>  <br/> |<span data-ttu-id="97761-231">Sì</span><span class="sxs-lookup"><span data-stu-id="97761-231">Yes</span></span>  <br/> |<span data-ttu-id="97761-232">N/D</span><span class="sxs-lookup"><span data-stu-id="97761-232">N/A</span></span>  <br/> |
|<span data-ttu-id="97761-233">Locale</span><span class="sxs-lookup"><span data-stu-id="97761-233">On-premises</span></span>  <br/> |<span data-ttu-id="97761-234">Online/locale</span><span class="sxs-lookup"><span data-stu-id="97761-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="97761-235">Accesso via PC (BTOE)</span><span class="sxs-lookup"><span data-stu-id="97761-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="97761-236">Sì</span><span class="sxs-lookup"><span data-stu-id="97761-236">Yes</span></span>  <br/> |<span data-ttu-id="97761-237">Sì</span><span class="sxs-lookup"><span data-stu-id="97761-237">Yes</span></span>  <br/> |<span data-ttu-id="97761-238">N/D</span><span class="sxs-lookup"><span data-stu-id="97761-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="97761-239">**Telefono caratteristiche** Il set di funzionalità può variare leggermente in base al partner del telefono IP.</span><span class="sxs-lookup"><span data-stu-id="97761-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span></span> <span data-ttu-id="97761-240">Per la serie di funzionalità completa e per ulteriori informazioni sulle funzionalità per ogni produttore di telefono, consulta [Ottenere telefoni per Skype for Business online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="97761-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="97761-241">**Phone-Lock** è una funzionalità di recente introduzione nei telefoni certificati Skype for Business che permette di proteggere un telefono.</span><span class="sxs-lookup"><span data-stu-id="97761-241">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone.</span></span> <span data-ttu-id="97761-242">Se abilitata, agli utenti verrà chiesto di creare un PIN al completamento dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="97761-242">If enabled, users will be asked to create a PIN upon successful authentication.</span></span> <span data-ttu-id="97761-243">Una volta creato il PIN, il telefono si blocca quando scade un periodo di inattività definito, quando l'utente blocca manualmente il telefono o quando sincronizza il proprio Phone-Lock con il blocco su PC utilizzando l'accoppiamento del telefono.</span><span class="sxs-lookup"><span data-stu-id="97761-243">Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing.</span></span> <span data-ttu-id="97761-244">Se il PIN di blocco del telefono viene immesso più volte in modo errato, il telefono disconnette l'utente o richiede il codice di un amministratore per sbloccare il telefono, ma questo varia a seconda del partner telefonico.</span><span class="sxs-lookup"><span data-stu-id="97761-244">If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner.</span></span> <span data-ttu-id="97761-245">Il PIN dell'utente deve essere composto di un numero di cifre compreso tra 6 e 15.</span><span class="sxs-lookup"><span data-stu-id="97761-245">The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="97761-246">È possibile disabilitare Phone-Lock per l'organizzazione (abilitata per impostazione predefinita), modificare il timeout di inattività e scegliere se gli utenti possono effettuare chiamate mentre sono bloccati o non usano le impostazioni in banda.</span><span class="sxs-lookup"><span data-stu-id="97761-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span></span> <span data-ttu-id="97761-247">Per altre informazioni su queste impostazioni, vedere [Set-CsUCPhoneConfiguration.](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="97761-247">See [Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="97761-248">Fase 7 (opzionale) - Con accoppiamento dispositivo e Better Together over Ethernet (BToE)</span><span class="sxs-lookup"><span data-stu-id="97761-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="97761-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="97761-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="97761-250">BToE è un meccanismo di connessione telefonica per i telefoni IP partner che abbina il telefono di un utente con l'app Windows Skype for Business telefono.</span><span class="sxs-lookup"><span data-stu-id="97761-250">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app.</span></span> <span data-ttu-id="97761-251">BToE consente agli utenti di:</span><span class="sxs-lookup"><span data-stu-id="97761-251">BToE enables users to:</span></span>
  
- <span data-ttu-id="97761-252">Accedere al telefono IP usando l'app desktop Skype for Business (con un PC)</span><span class="sxs-lookup"><span data-stu-id="97761-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="97761-253">Sincronizzare Phone-Lock con BLOCCO PC</span><span class="sxs-lookup"><span data-stu-id="97761-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="97761-254">Fare clic per chiamare</span><span class="sxs-lookup"><span data-stu-id="97761-254">Click to call</span></span>
    
<span data-ttu-id="97761-255">BToE può essere configurato per funzionare in due modalità:  *Automatico*  (impostazione predefinita) e *Manuale*  .</span><span class="sxs-lookup"><span data-stu-id="97761-255">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  .</span></span> <span data-ttu-id="97761-256">Può anche essere abilitato (impostazione predefinita)/disabilitato per gli utenti che utilizzano le impostazioni in banda di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="97761-256">It can also be enabled (default)/disabled for users using Skype for Business in-band settings.</span></span> <span data-ttu-id="97761-257">In modalità *Manuale*  , gli utenti dovranno eseguire un ulteriore passaggio per accoppiare il telefono alla app su Windows.</span><span class="sxs-lookup"><span data-stu-id="97761-257">When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="97761-258">**Per distribuire BToE agli utenti**</span><span class="sxs-lookup"><span data-stu-id="97761-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="97761-259">Collegare il PC al telefono utilizzando la porta del PC.</span><span class="sxs-lookup"><span data-stu-id="97761-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![Schermata che mostra la connessione a un PC](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="97761-261">Scaricare e installare l'ultima versione del software BToE dal sito web del produttore dai link qui sotto.</span><span class="sxs-lookup"><span data-stu-id="97761-261">Download and install the latest BToE software from the manufacturer website from the links below.</span></span> <span data-ttu-id="97761-262">Per una migliore esperienza utente, è possibile distribuire e installare il software BToE usando una soluzione di distribuzione di amministrazione come Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="97761-262">For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="97761-263">Per informazioni sull'uso di Configuration Manager, vedere [Pacchetti e programmi in Configuration Manager.](/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="97761-263">For help using Configuration Manager, See [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span></span>
    
   - [<span data-ttu-id="97761-264">Sito di download del software Polycom BToE</span><span class="sxs-lookup"><span data-stu-id="97761-264">Polycom BToE Software Download site</span></span>](https://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [<span data-ttu-id="97761-265">Download software BToE Yealink</span><span class="sxs-lookup"><span data-stu-id="97761-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
   - [<span data-ttu-id="97761-266">Download software BToE AudioCodes</span><span class="sxs-lookup"><span data-stu-id="97761-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="97761-267">L'impostazione del server per BToE è impostata **su Abilitato** e la **modalità automatica** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="97761-267">The server setting for BToE is set to **Enabled** and **Auto mode** by default.</span></span> <span data-ttu-id="97761-268">Per modificare le impostazioni, consulta [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy).</span><span class="sxs-lookup"><span data-stu-id="97761-268">To change those settings, see [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy).</span></span>
    
> [!NOTE]
> <span data-ttu-id="97761-269">BToE non è attualmente supportato su piattaforme Mac e VDI.</span><span class="sxs-lookup"><span data-stu-id="97761-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="97761-270">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="97761-270">Related topics</span></span>
[<span data-ttu-id="97761-271">Ottenere numeri di servizio per Skype for Business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="97761-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="97761-272">Vantaggi offerti dal Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="97761-272">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="97761-273">Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica</span><span class="sxs-lookup"><span data-stu-id="97761-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
