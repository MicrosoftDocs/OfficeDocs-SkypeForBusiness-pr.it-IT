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
f1keywords: None
ms.custom:
- Phone System
description: Informazioni sui passaggi di distribuzione per ottenere il firmware corretto, aggiornarlo se necessario, assegnare licenze e configurare le impostazioni per i telefoni Skype for business online
ms.openlocfilehash: 1e83c240b5406fbb3e7a247200d2b38d74ba8ef5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298009"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="7bfed-103">Distribuzione dei telefoni per Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7bfed-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="7bfed-104">[] Questa guida ti aiuta nella distribuzione dei telefoni IP per Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="7bfed-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="7bfed-p101">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business. Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="7bfed-p101">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business. Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="7bfed-108">Fasi della distribuzione di telefoni IP</span><span class="sxs-lookup"><span data-stu-id="7bfed-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="7bfed-109">Fase 1 - Scarica le guide per l'amministratore e i manuali del telefono del produttore</span><span class="sxs-lookup"><span data-stu-id="7bfed-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="7bfed-110">Prima di iniziare, è una buona idea quella di scaricare le guide per l'amministratore e i manuali d'uso del telefono del produttore.</span><span class="sxs-lookup"><span data-stu-id="7bfed-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="7bfed-111">Per i telefoni Polycom, consulta la [Guida alla distribuzione di Polycom](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span><span class="sxs-lookup"><span data-stu-id="7bfed-111">For Polycom phones, see the [Polycom Deployment Guide](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span></span>
    
- <span data-ttu-id="7bfed-112">Per i telefoni Yealink, vedi la [soluzione Yealink Skype for Business HD SIP Phones](http://www.yealink.com/products_top_2.html).</span><span class="sxs-lookup"><span data-stu-id="7bfed-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="7bfed-113">Per i telefoni AudioCodes, consulta la [Guida alla gestione del provisioning Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span><span class="sxs-lookup"><span data-stu-id="7bfed-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="7bfed-114">Fase 2 - Assicurati di stare acquistando o migrando un telefono IP e firmware supportati da Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="7bfed-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="7bfed-p102">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="7bfed-p102">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="7bfed-117">Fase 3 - Verifica che sia installato il firmware giusto e aggiorna il firmware, se necessario</span><span class="sxs-lookup"><span data-stu-id="7bfed-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="7bfed-p103">Check the firmware version on your phones. For:</span><span class="sxs-lookup"><span data-stu-id="7bfed-p103">Check the firmware version on your phones. For:</span></span>
  
- <span data-ttu-id="7bfed-120">**Telefoni VVX Polycom**, vai a **Impostazioni** > **Stato** > **Piattaforma** > **Applicazione** > **Principale**.</span><span class="sxs-lookup"><span data-stu-id="7bfed-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="7bfed-121">i **telefoni Yealink**, accedi a **Status** (Stato) sulla schermata principale del telefono.</span><span class="sxs-lookup"><span data-stu-id="7bfed-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="7bfed-122">**Telefoni AudioCodes**, vai a **Menu** > **Stato dispositivo** > **Versione firmware** dalla schermata di avvio.</span><span class="sxs-lookup"><span data-stu-id="7bfed-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7bfed-p104">For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals.</span><span class="sxs-lookup"><span data-stu-id="7bfed-p104">For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="7bfed-125">I **telefoni Lync Phone Edition (LPE)**, accedi a **Menu** > **System Information** (Informazioni sul sistema) dalla schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="7bfed-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="7bfed-126">Fase 4 - Considerazioni sull'aggiornamento del dispositivo</span><span class="sxs-lookup"><span data-stu-id="7bfed-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="7bfed-p105">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock." Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured. Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span><span class="sxs-lookup"><span data-stu-id="7bfed-p105">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock." Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured. Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="7bfed-p106">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span><span class="sxs-lookup"><span data-stu-id="7bfed-p106">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![Distribuzione di telefoni.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="7bfed-p107">When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span><span class="sxs-lookup"><span data-stu-id="7bfed-p107">When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![Distribuzione di telefoni.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="7bfed-138">Per un telefono Polycom, è possibile aggiornare il firmware del telefono selezionando **SwUpdate**.</span><span class="sxs-lookup"><span data-stu-id="7bfed-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![Distribuzione di telefoni.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="7bfed-p108">Puoi anche scegliere di gestire gli aggiornamenti del firmware utilizzando un sistema di provisioning partner. Per la gestione del sistema di provisioning partner, compresa la personalizzazione avanzata del telefono, consulta le guide per l'amministratore del produttore.</span><span class="sxs-lookup"><span data-stu-id="7bfed-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="7bfed-142">Assicurati di avere un'unica autorità di aggiornamento dispositivi (aggiornamento del dispositivo in banda o server di provisioning di terze parti) per evitare loop di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="7bfed-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="7bfed-143">Passaggio 5-impostazioni del telefono per la configurazione e l'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="7bfed-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="7bfed-p109">Puoi impostare le opzioni e i criteri del telefono più comunemente utilizzati che utilizzano i cmdlet di Windows PowerShell per la gestione in banda di Skype for Business. Consulta [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) per i dettagli di questi parametri e impostazioni.</span><span class="sxs-lookup"><span data-stu-id="7bfed-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="7bfed-146">Per la pianificazione dell'infrastruttura di rete, Vedi [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span><span class="sxs-lookup"><span data-stu-id="7bfed-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="7bfed-147">Passaggio 6-preparazione per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="7bfed-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="7bfed-p110">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum, you will need to assign a Phone System license and a Calling Plan. For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="7bfed-p110">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum, you will need to assign a Phone System license and a Calling Plan. For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="7bfed-151">Per altre informazioni sui piani di chiamata, è possibile leggere i [piani di telefono e chiamate](/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="7bfed-151">You can find out more about Calling Plans by reading [Phone System and Calling Plans](/microsoftteams/calling-plan-landing-page)</span></span>
  
- <span data-ttu-id="7bfed-152">Le **opzioni di accesso** disponibili per gli utenti online son le seguenti.</span><span class="sxs-lookup"><span data-stu-id="7bfed-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="7bfed-153">Gli utenti con **Polycom VVX 5xx/6xx** Phones vedranno:</span><span class="sxs-lookup"><span data-stu-id="7bfed-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Distribuzione di telefoni.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="7bfed-155">Gli utenti con **YEALINK T48G/T46G** Phones vedranno:</span><span class="sxs-lookup"><span data-stu-id="7bfed-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Accesso telefoni Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="7bfed-157">Per informazioni dettagliate sulle opzioni di accesso supportate dal produttore, vedere [ottenere telefoni per Skype for business online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="7bfed-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="7bfed-p111">**ID utente** Utilizzando la tastiera del telefono o la tastiera a schermo (se disponibile), gli utenti possono utilizzare il nome utente e la password della propria organizzazione per accedere al telefono. Ad esempio, possono utilizzare il formato UPN come <em>amosm@contoso.com</em>  per il nome utente.</span><span class="sxs-lookup"><span data-stu-id="7bfed-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like <em>amosm@contoso.com</em>  for their user name.</span></span>
    
     ![Distribuzione di telefoni.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="7bfed-161">L'autenticazione PIN non è supportata per Skype for Business online per i telefoni IP LPE e Partner.</span><span class="sxs-lookup"><span data-stu-id="7bfed-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="7bfed-p112">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App. See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span><span class="sxs-lookup"><span data-stu-id="7bfed-p112">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App. See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="7bfed-p113">Gli utenti devono utilizzare il nome utente e la password della propria organizzazione per accedere al telefono. Ad esempio, possono utilizzare il formato UPN come  <em>amosm@contoso.com</em>  per il nome utente.</span><span class="sxs-lookup"><span data-stu-id="7bfed-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  <em>amosm@contoso.com</em>  for their user name.</span></span>
  
     ![Distribuzione di telefoni.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="7bfed-p114">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign in.</span><span class="sxs-lookup"><span data-stu-id="7bfed-p114">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="7bfed-169">Gli utenti con **Polycom VVX 5xx/6xx** Phones vedranno:</span><span class="sxs-lookup"><span data-stu-id="7bfed-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Distribuzione di telefoni.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="7bfed-171">Gli utenti con **YEALINK T48G/T46G** Phones vedranno:</span><span class="sxs-lookup"><span data-stu-id="7bfed-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Accesso telefoni Yealink.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="7bfed-p115">The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span><span class="sxs-lookup"><span data-stu-id="7bfed-p115">The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="7bfed-175">Gli utenti con **Polycom VVX 5xx/6xx** Phones vedranno:</span><span class="sxs-lookup"><span data-stu-id="7bfed-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Codice PIN scaduto.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="7bfed-177">Gli utenti con **YEALINK T48G/T46G** Phones vedranno:</span><span class="sxs-lookup"><span data-stu-id="7bfed-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Accesso telefoni Yealink.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="7bfed-179">Utilizzando un browser, accedi all'indirizzo visualizzato sul telefono e inserisci il tuo nome utente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="7bfed-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![Distribuzione di telefoni.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="7bfed-181">Immetti il codice mostrato sul telefono.</span><span class="sxs-lookup"><span data-stu-id="7bfed-181">Enter the code shown on the phone.</span></span>
    
     ![Distribuzione di telefoni.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="7bfed-183">Verificare che il sito visualizzi "[nome produttore telefono] **telefono certificato Skype for business**", quindi fare clic su **continua**.</span><span class="sxs-lookup"><span data-stu-id="7bfed-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![Distribuzione di telefoni.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="7bfed-185">Fai clic sulle credenziali dell'utente o fai clic su **Usa un altro account**:</span><span class="sxs-lookup"><span data-stu-id="7bfed-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![Distribuzione di telefoni.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="7bfed-187">Quando viene visualizzata la pagina seguente, è sicuro chiudere il browser.</span><span class="sxs-lookup"><span data-stu-id="7bfed-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![Distribuzione di telefoni.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="7bfed-189">I telefoni LPE per Skype for Business online supportano l'accesso solo attraverso tethering USB.</span><span class="sxs-lookup"><span data-stu-id="7bfed-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="7bfed-190">**Distribuzioni supportate** La tabella seguente mostra i tipi di autenticazione supportati per i modelli di distribuzione attualmente supportati tra cui integrazione Exchange, autenticazione moderna con autenticazione a più fattori (MFA) e Skype for Business online e locale.</span><span class="sxs-lookup"><span data-stu-id="7bfed-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7bfed-191">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="7bfed-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="7bfed-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="7bfed-192">**Exchange**</span></span> <br/> |<span data-ttu-id="7bfed-193">**Metodo di accesso telefono**</span><span class="sxs-lookup"><span data-stu-id="7bfed-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="7bfed-194">**Accesso di Skype for business**</span><span class="sxs-lookup"><span data-stu-id="7bfed-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="7bfed-195">**Accesso Exchange con autorizzazione moderna e MFA disattivate**</span><span class="sxs-lookup"><span data-stu-id="7bfed-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="7bfed-196">**Accesso Exchange con autorizzazione moderna e MFA attivate**</span><span class="sxs-lookup"><span data-stu-id="7bfed-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="7bfed-197">Online</span><span class="sxs-lookup"><span data-stu-id="7bfed-197">Online</span></span>  <br/> |<span data-ttu-id="7bfed-198">Online</span><span class="sxs-lookup"><span data-stu-id="7bfed-198">Online</span></span>  <br/> |<span data-ttu-id="7bfed-199">Accesso Web</span><span class="sxs-lookup"><span data-stu-id="7bfed-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="7bfed-200">Sì</span><span class="sxs-lookup"><span data-stu-id="7bfed-200">Yes</span></span>  <br/> |<span data-ttu-id="7bfed-201">Sì</span><span class="sxs-lookup"><span data-stu-id="7bfed-201">Yes</span></span>  <br/> |<span data-ttu-id="7bfed-202">Sì</span><span class="sxs-lookup"><span data-stu-id="7bfed-202">Yes</span></span>  <br/> |
|<span data-ttu-id="7bfed-203">Online</span><span class="sxs-lookup"><span data-stu-id="7bfed-203">Online</span></span>  <br/> |<span data-ttu-id="7bfed-204">Online</span><span class="sxs-lookup"><span data-stu-id="7bfed-204">Online</span></span>  <br/> |<span data-ttu-id="7bfed-205">Nome utente/password</span><span class="sxs-lookup"><span data-stu-id="7bfed-205">Username/Password</span></span>  <br/> |<span data-ttu-id="7bfed-206">Sì</span><span class="sxs-lookup"><span data-stu-id="7bfed-206">Yes</span></span>  <br/> |<span data-ttu-id="7bfed-207">Sì</span><span class="sxs-lookup"><span data-stu-id="7bfed-207">Yes</span></span>  <br/> |<span data-ttu-id="7bfed-208">No</span><span class="sxs-lookup"><span data-stu-id="7bfed-208">No</span></span>  <br/> |
|<span data-ttu-id="7bfed-209">Online</span><span class="sxs-lookup"><span data-stu-id="7bfed-209">Online</span></span>  <br/> |<span data-ttu-id="7bfed-210">Locale</span><span class="sxs-lookup"><span data-stu-id="7bfed-210">On-premises</span></span>  <br/> |<span data-ttu-id="7bfed-211">Accesso Web</span><span class="sxs-lookup"><span data-stu-id="7bfed-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="7bfed-212">Sì</span><span class="sxs-lookup"><span data-stu-id="7bfed-212">Yes</span></span>  <br/> |<span data-ttu-id="7bfed-213">No</span><span class="sxs-lookup"><span data-stu-id="7bfed-213">No</span></span>  <br/> |<span data-ttu-id="7bfed-214">No</span><span class="sxs-lookup"><span data-stu-id="7bfed-214">No</span></span>  <br/> |
|<span data-ttu-id="7bfed-215">Online</span><span class="sxs-lookup"><span data-stu-id="7bfed-215">Online</span></span>  <br/> |<span data-ttu-id="7bfed-216">Locale</span><span class="sxs-lookup"><span data-stu-id="7bfed-216">On-Premises</span></span>  <br/> |<span data-ttu-id="7bfed-217">Nome utente/password</span><span class="sxs-lookup"><span data-stu-id="7bfed-217">Username/Password</span></span>  <br/> |<span data-ttu-id="7bfed-218">Sì</span><span class="sxs-lookup"><span data-stu-id="7bfed-218">Yes</span></span>  <br/> |<span data-ttu-id="7bfed-219">Sì</span><span class="sxs-lookup"><span data-stu-id="7bfed-219">Yes</span></span>  <br/> |<span data-ttu-id="7bfed-220">No</span><span class="sxs-lookup"><span data-stu-id="7bfed-220">No</span></span>  <br/> |
|<span data-ttu-id="7bfed-221">Locale</span><span class="sxs-lookup"><span data-stu-id="7bfed-221">On-premises</span></span>  <br/> |<span data-ttu-id="7bfed-222">Online/locale</span><span class="sxs-lookup"><span data-stu-id="7bfed-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="7bfed-223">Autenticazione PIN</span><span class="sxs-lookup"><span data-stu-id="7bfed-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="7bfed-224">Sì</span><span class="sxs-lookup"><span data-stu-id="7bfed-224">Yes</span></span>  <br/> |<span data-ttu-id="7bfed-225">No</span><span class="sxs-lookup"><span data-stu-id="7bfed-225">No</span></span>  <br/> |<span data-ttu-id="7bfed-226">No</span><span class="sxs-lookup"><span data-stu-id="7bfed-226">No</span></span>  <br/> |
|<span data-ttu-id="7bfed-227">Locale</span><span class="sxs-lookup"><span data-stu-id="7bfed-227">On-premises</span></span>  <br/> |<span data-ttu-id="7bfed-228">Online/locale</span><span class="sxs-lookup"><span data-stu-id="7bfed-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="7bfed-229">Nome utente/password</span><span class="sxs-lookup"><span data-stu-id="7bfed-229">Username/Password</span></span>  <br/> |<span data-ttu-id="7bfed-230">Sì</span><span class="sxs-lookup"><span data-stu-id="7bfed-230">Yes</span></span>  <br/> |<span data-ttu-id="7bfed-231">Sì</span><span class="sxs-lookup"><span data-stu-id="7bfed-231">Yes</span></span>  <br/> |<span data-ttu-id="7bfed-232">N/D</span><span class="sxs-lookup"><span data-stu-id="7bfed-232">N/A</span></span>  <br/> |
|<span data-ttu-id="7bfed-233">Locale</span><span class="sxs-lookup"><span data-stu-id="7bfed-233">On-premises</span></span>  <br/> |<span data-ttu-id="7bfed-234">Online/locale</span><span class="sxs-lookup"><span data-stu-id="7bfed-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="7bfed-235">Accesso via PC (BTOE)</span><span class="sxs-lookup"><span data-stu-id="7bfed-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="7bfed-236">Sì</span><span class="sxs-lookup"><span data-stu-id="7bfed-236">Yes</span></span>  <br/> |<span data-ttu-id="7bfed-237">Sì</span><span class="sxs-lookup"><span data-stu-id="7bfed-237">Yes</span></span>  <br/> |<span data-ttu-id="7bfed-238">N/D</span><span class="sxs-lookup"><span data-stu-id="7bfed-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="7bfed-p116">**Phone features** The feature set may vary slightly based on the IP phone partner. For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="7bfed-p116">**Phone features** The feature set may vary slightly based on the IP phone partner. For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="7bfed-p117">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successful authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner. The user's PIN should be between 6 and 15 digits.</span><span class="sxs-lookup"><span data-stu-id="7bfed-p117">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successful authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner. The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="7bfed-246">È possibile disabilitare il blocco telefonico per l'organizzazione (che è abilitato per impostazione predefinita), cambiare il timeout di inattività e scegliere se gli utenti possono effettuare telefonate mentre sono bloccati o non usano le impostazioni di inbando.</span><span class="sxs-lookup"><span data-stu-id="7bfed-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span></span> <span data-ttu-id="7bfed-247">Per altre informazioni su queste impostazioni, vedere [Set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/mt629497.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7bfed-247">See [Set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="7bfed-248">Fase 7 (opzionale) - Con accoppiamento dispositivo e Better Together over Ethernet (BToE)</span><span class="sxs-lookup"><span data-stu-id="7bfed-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="7bfed-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="7bfed-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="7bfed-p119">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app. BToE enables users to:</span><span class="sxs-lookup"><span data-stu-id="7bfed-p119">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app. BToE enables users to:</span></span>
  
- <span data-ttu-id="7bfed-252">Accedere al proprio telefono IP usando l'app desktop Skype for business (usando un PC)</span><span class="sxs-lookup"><span data-stu-id="7bfed-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="7bfed-253">Sincronizza telefono con blocco PC</span><span class="sxs-lookup"><span data-stu-id="7bfed-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="7bfed-254">Fare clic per chiamare</span><span class="sxs-lookup"><span data-stu-id="7bfed-254">Click to call</span></span>
    
<span data-ttu-id="7bfed-p120">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span><span class="sxs-lookup"><span data-stu-id="7bfed-p120">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="7bfed-258">**Per distribuire BToE agli utenti**</span><span class="sxs-lookup"><span data-stu-id="7bfed-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="7bfed-259">Collegare il PC al telefono utilizzando la porta del PC.</span><span class="sxs-lookup"><span data-stu-id="7bfed-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![Distribuzione di telefoni.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="7bfed-p121">Scaricare e installare l'ultima versione del software BToE dal sito web del produttore dai link qui sotto. Per una migliore esperienza utente, è possibile distribuire e installare il software BToE utilizzando una soluzione di distribuzione di amministrazione come System Center Configuration Manager (SCCM). Per informazioni sull'utilizzo di SCCM, consulta [Pacchetti e programmi in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="7bfed-p121">Download and install the latest BToE software from the manufacturer website from the links below. For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as System Center Configuration Manager (SCCM). For help using SCCM, See [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>
    
   - [<span data-ttu-id="7bfed-264">Sito di download del software Polycom BToE</span><span class="sxs-lookup"><span data-stu-id="7bfed-264">Polycom BToE Software Download site</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [<span data-ttu-id="7bfed-265">Download software BToE Yealink</span><span class="sxs-lookup"><span data-stu-id="7bfed-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
   - [<span data-ttu-id="7bfed-266">Download software BToE AudioCodes</span><span class="sxs-lookup"><span data-stu-id="7bfed-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="7bfed-p122">The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="7bfed-p122">The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="7bfed-269">BToE non è attualmente supportato su piattaforme Mac e VDI.</span><span class="sxs-lookup"><span data-stu-id="7bfed-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="7bfed-270">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7bfed-270">Related topics</span></span>
[<span data-ttu-id="7bfed-271">Ottenere numeri di servizio per Skype for Business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7bfed-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="7bfed-272">Ecco cosa offre il Sistema telefonico in Office 365</span><span class="sxs-lookup"><span data-stu-id="7bfed-272">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="7bfed-273">Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica</span><span class="sxs-lookup"><span data-stu-id="7bfed-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
