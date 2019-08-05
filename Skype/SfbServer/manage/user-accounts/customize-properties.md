---
title: Personalizzare le proprietà degli account utente per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: È possibile usare le procedure descritte in questa sezione per modificare le singole proprietà degli account utente.
ms.openlocfilehash: fda11a1b52519f3653c841837af20392383cadd1
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "36195912"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="2df21-103">Personalizzare le proprietà degli account utente per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2df21-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="2df21-104">È possibile usare le procedure descritte in questa sezione per modificare le singole proprietà degli account utente.</span><span class="sxs-lookup"><span data-stu-id="2df21-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="2df21-105">Esistono due operazioni di base che è possibile eseguire a livello di singolo utente:</span><span class="sxs-lookup"><span data-stu-id="2df21-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="2df21-106">Configurare le opzioni di telefonia per un account utente specifico</span><span class="sxs-lookup"><span data-stu-id="2df21-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="2df21-107">Trasferire gli utenti in un altro pool</span><span class="sxs-lookup"><span data-stu-id="2df21-107">Move users to another pool</span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="2df21-108">Configurare le opzioni di telefonia per un account utente specifico</span><span class="sxs-lookup"><span data-stu-id="2df21-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="2df21-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="2df21-109"></span></span>

<span data-ttu-id="2df21-110">È possibile personalizzare le impostazioni di telefonia per un utente specifico, purché il singolo utente sia stato abilitato per Skype for Business Server e l'organizzazione supporti la telefonia.</span><span class="sxs-lookup"><span data-stu-id="2df21-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="2df21-111">Le opzioni di telefonia degli utenti di Skype for Business Server includono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="2df21-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="2df21-112">**Disattivato audio/video** L'utente non può effettuare chiamate con audio e video.</span><span class="sxs-lookup"><span data-stu-id="2df21-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="2df21-113">**Solo da PC a PC** L'utente può effettuare solo chiamate audio o video da PC a PC.</span><span class="sxs-lookup"><span data-stu-id="2df21-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="2df21-114">**Enterprise Voice** L'utente può usare l'infrastruttura di Skype for Business Server per instradare tutte le chiamate in entrata e in uscita.</span><span class="sxs-lookup"><span data-stu-id="2df21-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="2df21-115">L'utente può anche effettuare chiamate da PC a PC.</span><span class="sxs-lookup"><span data-stu-id="2df21-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="2df21-116">**Controllo delle chiamate remote** L'utente può usare Skype for Business Server per controllare il telefono desktop e può anche effettuare chiamate da PC a PC.</span><span class="sxs-lookup"><span data-stu-id="2df21-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="2df21-117">Per informazioni dettagliate sulla configurazione della telefonia per un'organizzazione, vedere [abilitare gli utenti di VoIP aziendale in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) e [distribuire VoIP aziendale in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2df21-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="2df21-118">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="2df21-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2df21-119">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2df21-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="2df21-120">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="2df21-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="2df21-121">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, il nome, il cognome, il nome dell'account SAM (Security Accounts Manager), l'indirizzo SIP o l'URI (Uniform Resource Identifier) della riga dell'account utente desiderato, quindi fare clic su \*\*trova. \*\*.</span><span class="sxs-lookup"><span data-stu-id="2df21-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="2df21-122">Nella tabella fare clic sull'account utente che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="2df21-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="2df21-123">Nel menu **modifica** fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="2df21-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="2df21-124">In **telefonia**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2df21-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="2df21-125">Per disabilitare le chiamate audio e video per l'utente, fare clic su **disabilitato audio/video**.</span><span class="sxs-lookup"><span data-stu-id="2df21-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="2df21-126">Per abilitare le comunicazioni audio da PC a PC per l'utente, ma non per controllo delle chiamate remote o VoIP aziendale, fare clic su **solo da PC a PC**.</span><span class="sxs-lookup"><span data-stu-id="2df21-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="2df21-127">Specificare un valore per l' **URI di linea** per il telefono usato dall'utente per le comunicazioni audio da PC a PC.</span><span class="sxs-lookup"><span data-stu-id="2df21-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="2df21-128">Per instradare le telefonate dell'utente usando l'infrastruttura Skype for business in conformità con la classe di criteri di servizio, incluse le comunicazioni audio da PC a PC, fai clic su **VoIP aziendale**.</span><span class="sxs-lookup"><span data-stu-id="2df21-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="2df21-129">In **URI linea**specificare il numero di telefono per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="2df21-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="2df21-130">In **criteri di dial plan** e **criteri vocali**specificare i criteri appropriati per l'utente.</span><span class="sxs-lookup"><span data-stu-id="2df21-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="2df21-131">Per specificare le regole di normalizzazione per la traduzione dei numeri di telefono comunicati dall'utente nel formato E. 164, selezionare il profilo di posizione appropriato in **criteri posizione**.</span><span class="sxs-lookup"><span data-stu-id="2df21-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="2df21-132">Per abilitare il controllo delle chiamate remote, che consente agli utenti di controllare la linea telefonica desktop da Skype for Business Server per effettuare chiamate da PC a PC e chiamate da PC a telefono, fare clic su **controllo chiamate remote**.</span><span class="sxs-lookup"><span data-stu-id="2df21-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="2df21-133">In **URI linea**specificare il numero di telefono per il controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="2df21-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="2df21-134">L'utente deve avere un telefono desktop e una connessione PBX (Private Branch Exchange) per il routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="2df21-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="2df21-135">Trasferire gli utenti in un altro pool</span><span class="sxs-lookup"><span data-stu-id="2df21-135">Move users to another pool</span></span>
<span data-ttu-id="2df21-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="2df21-136"></span></span>

<span data-ttu-id="2df21-137">Puoi usare il pannello di controllo di Skype for Business Server per assegnare gli utenti a un server o un pool specifico.</span><span class="sxs-lookup"><span data-stu-id="2df21-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="2df21-138">Lo spostamento di tutti gli utenti esistenti da un pool di origine che gestisce Lync Server 2010 o versioni precedenti a un pool di destinazione di Skype for Business Server in un ambiente di Active Directory complesso può causare una replica di Active Directory più lenta.</span><span class="sxs-lookup"><span data-stu-id="2df21-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="2df21-139">Per evitare questo problema, puoi usare i filtri di ricerca per trasferire gli utenti da pool che usano Lync Server 2010 o versioni precedenti separatamente oppure puoi usare Skype for Business Server Management Shell per trasferire gli utenti con i cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2df21-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="2df21-140">Inoltre, la funzionalità di filtro funziona con gli utenti di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2df21-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="2df21-141">Per trasferire gli utenti selezionati in un altro server o pool</span><span class="sxs-lookup"><span data-stu-id="2df21-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="2df21-142">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="2df21-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2df21-143">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2df21-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="2df21-144">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="2df21-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="2df21-145">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, il nome, il cognome, il nome dell'account SAM (Security Accounts Manager), l'indirizzo SIP o l'URI (Uniform Resource Identifier) della riga dell'account utente desiderato, quindi fare clic su \*\*trova. \*\*.</span><span class="sxs-lookup"><span data-stu-id="2df21-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="2df21-146">Nella tabella selezionare un utente o utenti specifici nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2df21-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="2df21-147">Nel menu **azione** fare clic su **Trasferisci utenti selezionati in pool**.</span><span class="sxs-lookup"><span data-stu-id="2df21-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="2df21-148">In **Move users**selezionare il pool in cui si vuole trasferire gli utenti nel pool di registrar di **destinazione**.</span><span class="sxs-lookup"><span data-stu-id="2df21-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="2df21-149">Opzionale Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **forza** .</span><span class="sxs-lookup"><span data-stu-id="2df21-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="2df21-150">Se si seleziona **forza**, l'account utente viene spostato, ma vengono eliminati tutti i dati dell'utente associato, ad esempio le conferenze che l'utente ha programmato.</span><span class="sxs-lookup"><span data-stu-id="2df21-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="2df21-151">Se non viene selezionato, sia l'account che i dati associati vengono spostati.</span><span class="sxs-lookup"><span data-stu-id="2df21-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="2df21-152">Per trasferire tutti gli utenti da un server o da un pool a un altro server o pool</span><span class="sxs-lookup"><span data-stu-id="2df21-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="2df21-153">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="2df21-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2df21-154">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2df21-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="2df21-155">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="2df21-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="2df21-156">Nel menu **azione** fare clic su **Trasferisci tutti gli utenti in pool**.</span><span class="sxs-lookup"><span data-stu-id="2df21-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="2df21-157">In **Move users**selezionare il pool che contiene gli account utente che si desidera trasferire nel **pool di registrazione di origine**.</span><span class="sxs-lookup"><span data-stu-id="2df21-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="2df21-158">Nel **pool**di registrar di destinazione selezionare il pool a cui si vuole trasferire gli utenti.</span><span class="sxs-lookup"><span data-stu-id="2df21-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="2df21-159">Opzionale Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **forza** .</span><span class="sxs-lookup"><span data-stu-id="2df21-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="2df21-160">Se si seleziona **forza**, l'account utente viene spostato, ma vengono eliminati tutti i dati dell'utente associato, ad esempio le conferenze che l'utente ha programmato.</span><span class="sxs-lookup"><span data-stu-id="2df21-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="2df21-161">Se non viene selezionato, sia l'account che i dati associati vengono spostati.</span><span class="sxs-lookup"><span data-stu-id="2df21-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="2df21-162">Per trasferire gli utenti da un pool a un altro tramite un filtro</span><span class="sxs-lookup"><span data-stu-id="2df21-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="2df21-163">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="2df21-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2df21-164">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2df21-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="2df21-165">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="2df21-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="2df21-166">In **ricerca utente**fare clic su **Cerca**e quindi su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="2df21-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="2df21-167">Nel criterio di ricerca selezionare **pool di registrazione**, selezionare **uguale a**, selezionare **FQDN corrente del pool**e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="2df21-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="2df21-168">Nel menu **azione** fare clic su **Trasferisci tutti gli utenti in pool**.</span><span class="sxs-lookup"><span data-stu-id="2df21-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2df21-169">Quando si applica un filtro a un set di utenti esistente, l'opzione **trasferisce tutti gli utenti al pool** si trova nel contesto del sottoinsieme filtrato degli utenti, non di **tutti** gli utenti possibili.</span><span class="sxs-lookup"><span data-stu-id="2df21-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="2df21-170">In **Move users**selezionare il pool che contiene gli account utente che si desidera trasferire nel **pool di registrazione di origine**.</span><span class="sxs-lookup"><span data-stu-id="2df21-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="2df21-171">Nel **pool**di registrar di destinazione selezionare il pool in cui si desidera trasferire gli utenti.</span><span class="sxs-lookup"><span data-stu-id="2df21-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="2df21-172">Opzionale Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **forza** .</span><span class="sxs-lookup"><span data-stu-id="2df21-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="2df21-173">Se si seleziona **forza**, l'account utente viene spostato, ma vengono eliminati tutti i dati degli utenti associati, ad esempio le conferenze che l'utente ha programmato e i contatti.</span><span class="sxs-lookup"><span data-stu-id="2df21-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="2df21-174">Se non viene selezionato, sia l'account che i dati associati vengono spostati.</span><span class="sxs-lookup"><span data-stu-id="2df21-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="2df21-175">Per trasferire gli utenti da un pool a un altro usando i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2df21-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="2df21-176">A seconda di come vengono eseguiti i comandi di Windows PowerShell, ovvero localmente o in remoto, è necessario accedere come membri dei ruoli amministrativi corretti di Skype for Business Server come segue:</span><span class="sxs-lookup"><span data-stu-id="2df21-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="2df21-177">un.</span><span class="sxs-lookup"><span data-stu-id="2df21-177">a.</span></span> <span data-ttu-id="2df21-178">Se si esegue il comando nel computer locale (ad esempio, si accede direttamente a un front end Server): accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con il necessario diritti utente come descritto in **autorizzazioni di configurazione**Delegate.</span><span class="sxs-lookup"><span data-stu-id="2df21-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="2df21-179">b.</span><span class="sxs-lookup"><span data-stu-id="2df21-179">b.</span></span> <span data-ttu-id="2df21-180">Se si eseguono i comandi in remoto in un altro computer, ad esempio si accede al computer e si eseguono i comandi in remoto in un server front-end Standard Edition: da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator ruolo, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="2df21-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2df21-181">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business**e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2df21-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="2df21-182">Per trasferire singoli utenti, usare il cmdlet Move-CsUser come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2df21-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="2df21-183">Dove l'utente deve spostarsi è l'utente Pilar Ackerman e l'utente verrà spostato dal proprio pool di Home attualmente assegnato al pool pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2df21-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="2df21-184">Per trasferire un numero elevato di utenti, usare i filtri con il cmdlet **Get-CsUser** e passare il set di utenti risultante a **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="2df21-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="2df21-185">I comandi combinati di **Get-CsUser** e **Move-CsUser** possono risultare in questo:</span><span class="sxs-lookup"><span data-stu-id="2df21-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


