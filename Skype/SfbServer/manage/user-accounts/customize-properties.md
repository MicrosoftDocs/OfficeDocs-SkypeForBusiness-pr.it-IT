---
title: Personalizzare le proprietà dell'account utente per Skype for Business Server
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
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: È possibile utilizzare le procedure descritte in questa sezione per modificare le proprietà dei singoli account utente.
ms.openlocfilehash: 6f2c3a76f9047da0a5d78695518cfb8355ab82e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826266"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="8f5c9-103">Personalizzare le proprietà dell'account utente per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8f5c9-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="8f5c9-104">È possibile utilizzare le procedure descritte in questa sezione per modificare le proprietà dei singoli account utente.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="8f5c9-105">A livello di singolo utente è possibile eseguire due operazioni di base:</span><span class="sxs-lookup"><span data-stu-id="8f5c9-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="8f5c9-106">Configurare le opzioni di telefonia per un account utente specifico</span><span class="sxs-lookup"><span data-stu-id="8f5c9-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="8f5c9-107">Spostare gli utenti in un altro pool</span><span class="sxs-lookup"><span data-stu-id="8f5c9-107">Move users to another pool</span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="8f5c9-108">Configurare le opzioni di telefonia per un account utente specifico</span><span class="sxs-lookup"><span data-stu-id="8f5c9-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="8f5c9-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="8f5c9-109"><a name="Tel_Op"> </a></span></span>

<span data-ttu-id="8f5c9-110">È possibile personalizzare le impostazioni di telefonia per un utente specifico (purché il singolo utente sia stato abilitato per Skype for Business Server e l'organizzazione supporti la telefonia).</span><span class="sxs-lookup"><span data-stu-id="8f5c9-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="8f5c9-111">Le opzioni di telefonia degli utenti di Skype for Business Server includono:</span><span class="sxs-lookup"><span data-stu-id="8f5c9-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="8f5c9-112">**Audio/video disabilitato** L'utente non può effettuare chiamate con audio e video.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="8f5c9-113">**Solo da PC a PC** L'utente può effettuare solo chiamate audio o video da PC a PC.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="8f5c9-114">**VoIP aziendale** L'utente può utilizzare l'infrastruttura di Skype for Business Server per instradare tutte le chiamate in arrivo e in uscita.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="8f5c9-115">Può inoltre effettuare chiamate da PC a PC.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="8f5c9-116">**Controllo delle chiamate remote** L'utente può usare Skype for Business Server per controllare il telefono desktop e può anche effettuare chiamate da PC a PC.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="8f5c9-117">Per informazioni dettagliate sulla configurazione della telefonia per un'organizzazione, vedere [Enable users for VoIP aziendale in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and Deploy VoIP aziendale in Skype for Business [Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="8f5c9-118">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8f5c9-119">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="8f5c9-120">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="8f5c9-121">Nella casella **Ricerca utenti** digitare interamente o parzialmente il nome visualizzato, il nome, il cognome, il nome account del sistema degli account di sicurezza (SAM), l'indirizzo SIP o l'URI (Uniform Resource Identifier) linea dell'account utente desiderato e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="8f5c9-122">Nella tabella fare clic sull'account utente che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="8f5c9-123">Scegliere **Modifica** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="8f5c9-124">In **Telefonia** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f5c9-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="8f5c9-125">Per disabilitare le chiamate audio e le videochiamate per l'utente, fare clic su **Audio/video disabilitati**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="8f5c9-p102">Per abilitare le comunicazioni audio da PC a PC per l'utente, ma non il controllo delle chiamate remote o VoIP aziendale, fare clic su **Solo da PC a PC**. Specificare un valore per **URI linea** per il telefono utilizzato dall'utente per le comunicazioni audio da PC a PC.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-p102">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="8f5c9-128">Per instradare le chiamate telefoniche dell'utente utilizzando l'infrastruttura di Skype for Business in conformità ai criteri di classe del servizio, incluse le comunicazioni audio da PC a PC, fare clic su **VoIP aziendale**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="8f5c9-129">In **URI linea** specificare il numero di telefono per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="8f5c9-130">In **Criteri dial plan** e **Criteri vocali** specificare i criteri appropriati per l'utente.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="8f5c9-131">Per specificare le regole di normalizzazione per la conversione dei numeri di telefono composti dall'utente nel formato E.164, selezionare il profilo località appropriato in **Criteri percorso**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="8f5c9-132">Per abilitare il controllo delle chiamate remote, che consente agli utenti di controllare la linea telefonica desktop da Skype for Business Server per effettuare chiamate da PC a PC e da PC a telefono, fare clic su Controllo **chiamate remote.**</span><span class="sxs-lookup"><span data-stu-id="8f5c9-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="8f5c9-133">In **URI linea** specificare il numero di telefono per il controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="8f5c9-134">L'utente deve disporre di un telefono da scrivania e di una connessione PBX per il routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="8f5c9-135">Spostare gli utenti in un altro pool</span><span class="sxs-lookup"><span data-stu-id="8f5c9-135">Move users to another pool</span></span>
<span data-ttu-id="8f5c9-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="8f5c9-136"><a name="Move_Users"> </a></span></span>

<span data-ttu-id="8f5c9-137">È possibile utilizzare il Pannello di controllo di Skype for Business Server per assegnare gli utenti a un server o a un pool specifico.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="8f5c9-138">Lo spostamento di tutti gli utenti esistenti da un pool di origine che esegue Lync Server 2010 o versioni precedenti a un pool di destinazione di Skype for Business Server in un ambiente Active Directory complesso potrebbe rallentare la replica di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="8f5c9-139">Per evitare questo problema, è possibile utilizzare i filtri di ricerca per spostare gli utenti dai pool che eseguono Lync Server 2010 o versioni precedenti separatamente oppure è possibile utilizzare Skype for Business Server Management Shell per spostare gli utenti con i cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="8f5c9-140">Inoltre, la funzionalità di filtro funziona con gli utenti di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="8f5c9-141">Per spostare un gruppo selezionato di utenti in un server o un pool diverso</span><span class="sxs-lookup"><span data-stu-id="8f5c9-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="8f5c9-142">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8f5c9-143">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="8f5c9-144">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="8f5c9-145">Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, nome, cognome, nome dell'account Gestione account di protezione, indirizzo SIP o URI (Uniform Resource Identifier (URI) di linea dell'account utente desiderato e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="8f5c9-146">Nell'elenco della tabella selezionare uno o più utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="8f5c9-147">Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="8f5c9-148">In **Sposta utenti** selezionare il pool in cui spostare gli utenti in **Pool di registrazione di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="8f5c9-149">(Facoltativo) Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **Forza**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="8f5c9-p106">Se si seleziona **Forza**, l'account utente viene spostato, ma i dati utente associati vengono eliminati, ad esempio le conferenze pianificate dall'utente. Se non si seleziona questa casella di controllo, vengono spostati sia l'account sia i dati associati.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-p106">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="8f5c9-152">Per spostare tutti gli utenti da un server o un pool a un server o un pool diverso</span><span class="sxs-lookup"><span data-stu-id="8f5c9-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="8f5c9-153">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8f5c9-154">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="8f5c9-155">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="8f5c9-156">Scegliere **Sposta tutti gli utenti nel pool** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="8f5c9-157">In **Sposta utenti** selezionare il pool contenente gli account utente da spostare in **Pool di registrazione di origine**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="8f5c9-158">In **Pool di registrazione di destinazione** selezionare il pool in cui spostare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="8f5c9-159">(Facoltativo) Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **Forza**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="8f5c9-p107">Se si seleziona **Forza**, l'account utente viene spostato, ma i dati utente associati vengono eliminati, ad esempio le conferenze pianificate dall'utente. Se non si seleziona questa casella di controllo, vengono spostati sia l'account sia i dati associati.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-p107">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="8f5c9-162">Per spostare gli utenti da un pool a un altro mediante un filtro</span><span class="sxs-lookup"><span data-stu-id="8f5c9-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="8f5c9-163">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8f5c9-164">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="8f5c9-165">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="8f5c9-166">In **Ricerca utente** fare clic su **Ricerca** e quindi su **Aggiungi filtro.**</span><span class="sxs-lookup"><span data-stu-id="8f5c9-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="8f5c9-167">Nei criteri di ricerca selezionare **Pool di registrazione**, **Uguale a**, **FQDN pool** e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="8f5c9-168">Scegliere **Sposta tutti gli utenti nel pool** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8f5c9-169">Quando a un set esistente di utenti viene applicato un filtro, l'opzione **Sposta tutti gli utenti nel pool** si trova nel contesto di un subset filtrato di utenti, non di **tutti** i possibili utenti.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="8f5c9-170">In **Sposta utenti** selezionare il pool contenente gli account utente da spostare in **Pool di registrazione di origine**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="8f5c9-171">In **Pool di registrazione di destinazione** selezionare il pool in cui spostare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="8f5c9-172">(Facoltativo) Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **Forza**.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="8f5c9-p108">Se si seleziona **Forza**, l'account utente viene spostato, ma i dati utente associati vengono eliminati, ad esempio le conferenze pianificate dall'utente e i contatti. Se non si seleziona questa casella di controllo, vengono spostati sia l'account sia i dati associati.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-p108">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="8f5c9-175">Per spostare gli utenti da un pool a un altro utilizzando i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f5c9-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="8f5c9-176">A seconda di come si eseguono i comandi di Windows PowerShell (ovvero in locale o in remoto), è necessario accedere come membro dei ruoli amministrativi di Skype for Business Server corretti come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8f5c9-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="8f5c9-177">a.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-177">a.</span></span> <span data-ttu-id="8f5c9-178">Se si eseguono i comandi nel computer locale (ad esempio, si accede direttamente a un Front End Server): accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in **Delegare** le autorizzazioni di installazione.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="8f5c9-179">b.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-179">b.</span></span> <span data-ttu-id="8f5c9-180">Se si eseguono i comandi in remoto in un altro computer (ad esempio, si accede al computer ed eseguono i comandi in remoto in un Front End Server Standard Edition): da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8f5c9-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8f5c9-181">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business** e quindi Skype for Business Server Management **Shell.**</span><span class="sxs-lookup"><span data-stu-id="8f5c9-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8f5c9-182">Per spostare singoli utenti, utilizzare il cmdlet Move-CsUser come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8f5c9-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="8f5c9-183">Dove l'utente da spostare si chiama Luisa Cazzaniga e verrà spostato dal pool principale assegnato al pool pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8f5c9-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="8f5c9-184">Per spostare un numero elevato di utenti, utilizzare i filtri con il cmdlet **Get-CsUser** e passare il set di utenti risultanti a **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="8f5c9-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="8f5c9-185">I comandi **Get-CsUser** e **Move-CsUser** combinati potrebbero risultare come segue:</span><span class="sxs-lookup"><span data-stu-id="8f5c9-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


