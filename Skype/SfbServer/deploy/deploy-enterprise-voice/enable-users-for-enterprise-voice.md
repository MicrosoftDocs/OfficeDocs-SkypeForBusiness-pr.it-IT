---
title: Abilitare gli utenti per VoIP aziendale in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Riepilogo: informazioni su come consentire agli utenti di effettuare e ricevere chiamate tramite VoIP aziendale in Skype for Business Server.'
ms.openlocfilehash: 3c18836f1c2b03d2c6d50712f33d9e3a900b43b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830876"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="96663-103">Abilitare gli utenti per VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="96663-103">Enable users for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="96663-104">**Riepilogo:** Informazioni su come consentire agli utenti di effettuare e ricevere chiamate tramite VoIP aziendale in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="96663-104">**Summary:** Learn how to enable users to make and receive calls by using Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="96663-105">Dopo la distribuzione di VoIP aziendale o chiamata tramite lavoro, è possibile utilizzare le procedure seguenti per consentire a un utente di effettuare chiamate tramite VoIP aziendale:</span><span class="sxs-lookup"><span data-stu-id="96663-105">After you deploy Enterprise Voice or Call Via Work, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>
  
> [!NOTE]
> <span data-ttu-id="96663-106">Nelle procedure riportate di seguito, solo il primo può essere eseguito utilizzando il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="96663-106">Of the following procedures, only the first can be performed by using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="96663-107">Per le procedure rimanenti, è possibile utilizzare solo Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="96663-107">For the remaining procedures, you can use only Skype for Business Server Management Shell.</span></span> 
  
- <span data-ttu-id="96663-108">Abilitare l'account utente per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="96663-108">Enable the user account for Enterprise Voice.</span></span>
    
- <span data-ttu-id="96663-109">(Facoltativo) Assegnare all'account utente criteri vocali specifici dell'utente.</span><span class="sxs-lookup"><span data-stu-id="96663-109">(Optional) Assign the user account a user-specific voice policy.</span></span>
    
- <span data-ttu-id="96663-110">(Facoltativo) Assegnare all'account utente un dial plan specifico dell'utente.</span><span class="sxs-lookup"><span data-stu-id="96663-110">(Optional) Assign the user account a user-specific dial plan.</span></span>
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="96663-111">Per abilitare un account utente per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="96663-111">To enable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="96663-112">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo amministrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="96663-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="96663-113">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="96663-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="96663-114">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="96663-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="96663-115">Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account di Gestione account di protezione, dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente da abilitare e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="96663-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="96663-116">Nella tabella fare clic sull'account utente che si desidera abilitare per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="96663-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="96663-117">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="96663-117">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="96663-118">Nella pagina **modifica utente di Skype for Business Server** , in **telefonia**, fare clic su **VoIP aziendale**.</span><span class="sxs-lookup"><span data-stu-id="96663-118">On the **Edit Skype for Business Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="96663-119">Fare clic su **URI linea** e quindi digitare un numero di telefono normalizzato univoco, ad esempio tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="96663-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
9. <span data-ttu-id="96663-120">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="96663-120">Click **Commit**.</span></span>
    
<span data-ttu-id="96663-121">Per completare l'abilitazione di un utente per VoIP aziendale, assicurarsi che all'utente sia assegnato un criterio vocale e un dial plan, indipendentemente dal fatto che sia globale (assegnato per impostazione predefinita) o specifico dell'utente. Per impostazione predefinita, a tutti gli utenti viene assegnato un criterio vocale globale e un dial plan.</span><span class="sxs-lookup"><span data-stu-id="96663-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="96663-122">Se nel sito principale dell'utente esistono criteri vocali o un dial plan a livello di sito, i criteri del sito verranno applicati automaticamente all'utente.</span><span class="sxs-lookup"><span data-stu-id="96663-122">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="96663-123">Per applicare criteri vocali o un dial plan per utente, è necessario eseguire i cmdlet **Grant-CsVoicePolicy** e **Grant-CsDialPlan**.</span><span class="sxs-lookup"><span data-stu-id="96663-123">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="96663-124">Per informazioni dettagliate, vedere le procedure seguenti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="96663-124">For details, see the following procedures in this topic.</span></span>
## <a name="voice-policy-assignment"></a><span data-ttu-id="96663-125">Assegnazione di criteri vocali</span><span class="sxs-lookup"><span data-stu-id="96663-125">Voice Policy Assignment</span></span>

<span data-ttu-id="96663-126">I criteri vocali globali e a livello di sito vengono assegnati automaticamente a tutti gli account utente abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="96663-126">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="96663-127">È inoltre possibile creare criteri vocali applicabili a utenti o gruppi specifici.</span><span class="sxs-lookup"><span data-stu-id="96663-127">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="96663-128">Questi criteri per utente devono essere assegnati esplicitamente agli utenti o ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="96663-128">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="96663-129">Se si desidera utilizzare il criterio vocale globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione e continuare con la sezione [assegnazione dial plan](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="96663-129">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to [Dial Plan Assignment](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) section later in this topic.</span></span>
  
### <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="96663-130">Per assegnare criteri vocali specifici dell'utente</span><span class="sxs-lookup"><span data-stu-id="96663-130">To assign a user-specific voice policy</span></span>

1. <span data-ttu-id="96663-131">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="96663-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="96663-132">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="96663-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="96663-133">Per assegnare un criterio vocale esistente a un utente, eseguire quanto segue al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="96663-133">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="96663-134">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="96663-134">For example:</span></span>
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    <span data-ttu-id="96663-135">In questo esempio, all'utente con il nome visualizzato Bob Kelly viene assegnato il criterio vocale con il nome **VoicePolicyJapan**.</span><span class="sxs-lookup"><span data-stu-id="96663-135">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>
    
## <a name="dial-plan-assignment"></a><span data-ttu-id="96663-136">Assegnazione di dial plan</span><span class="sxs-lookup"><span data-stu-id="96663-136">Dial Plan Assignment</span></span>
<span data-ttu-id="96663-137"><a name="BKMK_DialPlanAssignment"> </a></span><span class="sxs-lookup"><span data-stu-id="96663-137"><a name="BKMK_DialPlanAssignment"> </a></span></span>

<span data-ttu-id="96663-138">Per completare la configurazione degli account per gli utenti di VoIP aziendale o per gli utenti delle conferenze telefoniche con accesso esterno, è necessario che all'utente sia assegnato un dial plan.</span><span class="sxs-lookup"><span data-stu-id="96663-138">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="96663-139">Gli account utente utilizzeranno automaticamente il dial plan globale oppure, se disponibile, il dial plan a livello di sito se non si assegna esplicitamente un dial plan per utente.</span><span class="sxs-lookup"><span data-stu-id="96663-139">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="96663-140">Se si desidera utilizzare il dial plan globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione.</span><span class="sxs-lookup"><span data-stu-id="96663-140">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>
  
### <a name="to-assign-a-user-specific-dial-plan"></a><span data-ttu-id="96663-141">Per assegnare un dial plan specifico dell'utente</span><span class="sxs-lookup"><span data-stu-id="96663-141">To assign a user-specific dial plan</span></span>

1. <span data-ttu-id="96663-142">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="96663-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="96663-143">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="96663-143">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="96663-144">Per assegnare un dial plan specifico dell'utente, al prompt dei comandi eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="96663-144">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="96663-145">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="96663-145">For example:</span></span>
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    <span data-ttu-id="96663-146">In questo esempio, all'utente con il nome visualizzato Bob Kelly viene assegnato il dial plan utente con il nome **DialPlanJapan**.</span><span class="sxs-lookup"><span data-stu-id="96663-146">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>
    

