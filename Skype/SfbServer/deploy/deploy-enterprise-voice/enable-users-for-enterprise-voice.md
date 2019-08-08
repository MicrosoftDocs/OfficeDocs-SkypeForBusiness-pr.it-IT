---
title: Consentire agli utenti di VoIP aziendale in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Riepilogo: informazioni su come consentire agli utenti di effettuare e ricevere chiamate tramite VoIP aziendale in Skype for Business Server.'
ms.openlocfilehash: cf9aab0f104582c57e745c95ae5cf8f24f07b3a5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240611"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="8d757-103">Consentire agli utenti di VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8d757-103">Enable users for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="8d757-104">**Riepilogo:** Informazioni su come consentire agli utenti di effettuare e ricevere chiamate tramite VoIP aziendale in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8d757-104">**Summary:** Learn how to enable users to make and receive calls by using Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="8d757-105">Dopo aver distribuito VoIP aziendale o chiamata tramite lavoro, è possibile usare le procedure seguenti per consentire a un utente di effettuare chiamate tramite VoIP aziendale:</span><span class="sxs-lookup"><span data-stu-id="8d757-105">After you deploy Enterprise Voice or Call Via Work, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>
  
> [!NOTE]
> <span data-ttu-id="8d757-106">Delle procedure seguenti, solo il primo può essere eseguito usando il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8d757-106">Of the following procedures, only the first can be performed by using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="8d757-107">Per le procedure rimanenti, è possibile usare solo Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8d757-107">For the remaining procedures, you can use only Skype for Business Server Management Shell.</span></span> 
  
- <span data-ttu-id="8d757-108">Abilitare l'account utente per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="8d757-108">Enable the user account for Enterprise Voice.</span></span>
    
- <span data-ttu-id="8d757-109">Opzionale Assegnare l'account utente a un criterio vocale specifico per l'utente.</span><span class="sxs-lookup"><span data-stu-id="8d757-109">(Optional) Assign the user account a user-specific voice policy.</span></span>
    
- <span data-ttu-id="8d757-110">Opzionale Assegna l'account utente a un dial plan specifico per l'utente.</span><span class="sxs-lookup"><span data-stu-id="8d757-110">(Optional) Assign the user account a user-specific dial plan.</span></span>
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="8d757-111">Per abilitare un account utente per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="8d757-111">To enable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="8d757-112">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo di amministratore di **CsVoiceAdministrator**, **CsServerAdministrator**o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="8d757-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="8d757-113">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8d757-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8d757-114">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="8d757-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="8d757-115">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si vuole abilitare e quindi fare clic su **Trovare**.</span><span class="sxs-lookup"><span data-stu-id="8d757-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="8d757-116">Nella tabella fare clic sull'account utente che si desidera abilitare per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="8d757-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="8d757-117">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="8d757-117">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="8d757-118">Nella pagina **modifica utenti di Skype for Business Server** , in **telefonia**, fare clic su **VoIP aziendale**.</span><span class="sxs-lookup"><span data-stu-id="8d757-118">On the **Edit Skype for Business Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="8d757-119">Fare clic su **URI linea**e quindi digitare un numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="8d757-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
9. <span data-ttu-id="8d757-120">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8d757-120">Click **Commit**.</span></span>
    
<span data-ttu-id="8d757-121">Per completare l'abilitazione di un utente per VoIP aziendale, assicurati che all'utente sia assegnato un criterio vocale e un dial plan, sia globale (assegnato per impostazione predefinita) che specifico per l'utente. Per impostazione predefinita, a tutti gli utenti viene assegnato un criterio vocale globale e un dial plan.</span><span class="sxs-lookup"><span data-stu-id="8d757-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="8d757-122">Se un criterio vocale o un dial plan esiste a livello di sito per il sito in cui si trova l'account utente, i criteri del sito verranno applicati automaticamente all'utente.</span><span class="sxs-lookup"><span data-stu-id="8d757-122">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="8d757-123">Per applicare un criterio vocale per utente o un dial plan a un utente, è necessario eseguire i cmdlet **Grant-CsVoicePolicy** e **Grant-CsDialPlan** .</span><span class="sxs-lookup"><span data-stu-id="8d757-123">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="8d757-124">Per informazioni dettagliate, vedere le procedure seguenti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8d757-124">For details, see the following procedures in this topic.</span></span>
## <a name="voice-policy-assignment"></a><span data-ttu-id="8d757-125">Assegnazione dei criteri vocali</span><span class="sxs-lookup"><span data-stu-id="8d757-125">Voice Policy Assignment</span></span>

<span data-ttu-id="8d757-126">I criteri vocali globali e a livello di sito vengono assegnati automaticamente a tutti gli account utente abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="8d757-126">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="8d757-127">È anche possibile creare criteri vocali applicabili a utenti o gruppi specifici.</span><span class="sxs-lookup"><span data-stu-id="8d757-127">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="8d757-128">Questi criteri per utente devono essere assegnati in modo esplicito agli utenti o ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="8d757-128">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="8d757-129">Se si vuole usare il criterio vocale globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione e continuare la sezione [assegnazione di dial plan](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8d757-129">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to [Dial Plan Assignment](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) section later in this topic.</span></span>
  
### <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="8d757-130">Per assegnare un criterio vocale specifico per l'utente</span><span class="sxs-lookup"><span data-stu-id="8d757-130">To assign a user-specific voice policy</span></span>

1. <span data-ttu-id="8d757-131">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8d757-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8d757-132">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8d757-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8d757-133">Per assegnare un criterio vocale utente esistente a un utente, eseguire le operazioni seguenti al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="8d757-133">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="8d757-134">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8d757-134">For example:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    <span data-ttu-id="8d757-135">In questo esempio l'utente con il nome visualizzato Bob Kelly viene assegnato il criterio vocale con il nome **VoicePolicyJapan**.</span><span class="sxs-lookup"><span data-stu-id="8d757-135">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>
    
## <a name="dial-plan-assignment"></a><span data-ttu-id="8d757-136">Assegnazione di dial plan</span><span class="sxs-lookup"><span data-stu-id="8d757-136">Dial Plan Assignment</span></span>
<span data-ttu-id="8d757-137"><a name="BKMK_DialPlanAssignment"> </a></span><span class="sxs-lookup"><span data-stu-id="8d757-137"></span></span>

<span data-ttu-id="8d757-138">Per completare la configurazione dell'account utente per gli utenti di VoIP aziendale o per gli utenti di servizi di conferenza telefonica con accesso esterno, l'utente deve essere assegnato a un dial plan.</span><span class="sxs-lookup"><span data-stu-id="8d757-138">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="8d757-139">Gli account utente useranno automaticamente il dial plan globale o, se disponibile, il dial plan a livello di sito, quando non si assegna esplicitamente un dial plan per utente esistente.</span><span class="sxs-lookup"><span data-stu-id="8d757-139">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="8d757-140">Se si vuole usare il dial plan globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione.</span><span class="sxs-lookup"><span data-stu-id="8d757-140">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>
  
### <a name="to-assign-a-user-specific-dial-plan"></a><span data-ttu-id="8d757-141">Per assegnare un dial plan specifico dell'utente</span><span class="sxs-lookup"><span data-stu-id="8d757-141">To assign a user-specific dial plan</span></span>

1. <span data-ttu-id="8d757-142">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8d757-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8d757-143">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8d757-143">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8d757-144">Per assegnare un dial plan specifico per l'utente, eseguire la procedura seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="8d757-144">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="8d757-145">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8d757-145">For example:</span></span>
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    <span data-ttu-id="8d757-146">In questo esempio l'utente con il nome visualizzato Bob Kelly viene assegnato al dial plan utente con il nome **DialPlanJapan**.</span><span class="sxs-lookup"><span data-stu-id="8d757-146">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>
    

