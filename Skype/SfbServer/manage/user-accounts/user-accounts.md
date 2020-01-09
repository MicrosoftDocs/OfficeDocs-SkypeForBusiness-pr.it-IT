---
title: Gestire gli account utente per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: Le sezioni di questo articolo descrivono come abilitare, disabilitare temporaneamente o rimuovere utenti di Active Directory da Skype for Business Server.
ms.openlocfilehash: 45217593dd010c4daf73d6b5edcbf6f5f4e681a5
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992403"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="e475c-103">Gestire gli account utente per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e475c-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="e475c-104">Le sezioni di questo articolo descrivono come abilitare, disabilitare temporaneamente o rimuovere utenti di Active Directory da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e475c-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="e475c-105">Per informazioni su come abilitare un utente di Active Directory, vedere [creare un nuovo account utente](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e475c-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="e475c-106">Per informazioni su come eliminare un utente di Active Directory, vedere [eliminare un account utente](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e475c-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="e475c-107">Queste procedure devono essere eseguite durante una finestra di manutenzione, quando l'utilizzo di Skype for business è più basso.</span><span class="sxs-lookup"><span data-stu-id="e475c-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="e475c-108">Il fatto che venga eseguito in una programmazione giornaliera o settimanale sarà determinato dalle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e475c-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="e475c-109">Questo articolo contiene le procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="e475c-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="e475c-110">Per cercare uno o più utenti</span><span class="sxs-lookup"><span data-stu-id="e475c-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="e475c-111">Aggiungere e abilitare un nuovo utente di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e475c-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="e475c-112">Disabilitare o riattivare un account utente abilitato in precedenza per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e475c-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="e475c-113">Disabilitare un utente per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="e475c-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="e475c-114">Rimuovere un account utente con Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="e475c-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="e475c-115">Per cercare uno o più utenti</span><span class="sxs-lookup"><span data-stu-id="e475c-115">To search for one or more users</span></span>
<span data-ttu-id="e475c-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="e475c-116"></span></span>

<span data-ttu-id="e475c-117">È possibile usare i risultati di una query di ricerca per configurare gli utenti di Active Directory per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e475c-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="e475c-118">È possibile cercare gli utenti per nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (SAM), indirizzo SIP o URI (Uniform Resource Identifier) linea.</span><span class="sxs-lookup"><span data-stu-id="e475c-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="e475c-119">Puoi cercare gli utenti usando il pannello di controllo di Skype for Business Server o lo snap-in utenti e computer di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e475c-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="e475c-120">La procedura seguente descrive come usare il pannello di controllo di Skype for Business Server per cercare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e475c-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="e475c-121">In un ambiente con una topologia di foresta centrale i risultati della ricerca potrebbero non essere precisi quando si cerca un utente tramite l'indirizzo di posta elettronica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e475c-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="e475c-122">È invece possibile cercare gli utenti specificando un prefisso di indirizzo SIP, ad esempio SIP: Name, aggiungere un filtro di ricerca e selezionare un indirizzo SIP che contiene un indirizzo di posta elettronica parziale oppure usare il cmdlet **Get-CSUser** .</span><span class="sxs-lookup"><span data-stu-id="e475c-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="e475c-123">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e475c-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="e475c-124">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e475c-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="e475c-125">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="e475c-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="e475c-126">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome dell'account SAM, indirizzo SIP o URI di linea dell'account utente che si desidera cercare e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="e475c-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="e475c-127">Opzionale Specificare altri criteri di ricerca per restringere i risultati:</span><span class="sxs-lookup"><span data-stu-id="e475c-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="e475c-128">un.</span><span class="sxs-lookup"><span data-stu-id="e475c-128">a.</span></span> <span data-ttu-id="e475c-129">Fare clic sul pulsante Espandi freccia nell'angolo in alto a destra dello schermo sopra i **Risultati della ricerca**e quindi fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="e475c-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="e475c-130">b.</span><span class="sxs-lookup"><span data-stu-id="e475c-130">b.</span></span> <span data-ttu-id="e475c-131">Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare una proprietà utente.</span><span class="sxs-lookup"><span data-stu-id="e475c-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="e475c-132">c.</span><span class="sxs-lookup"><span data-stu-id="e475c-132">c.</span></span> <span data-ttu-id="e475c-133">Nell'elenco **uguale a** fare clic su **uguale** a o **non uguale a**.</span><span class="sxs-lookup"><span data-stu-id="e475c-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="e475c-134">3D.</span><span class="sxs-lookup"><span data-stu-id="e475c-134">d.</span></span> <span data-ttu-id="e475c-135">Nella casella di testo digitare i criteri di ricerca che si desidera utilizzare per filtrare i risultati della ricerca e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="e475c-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="e475c-136">I risultati della ricerca vengono visualizzati nei **Risultati della ricerca**.</span><span class="sxs-lookup"><span data-stu-id="e475c-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="e475c-137">È possibile selezionare uno o tutti gli utenti nell'elenco ed eseguire attività di configurazione per gli utenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="e475c-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="e475c-138">Aggiungere e abilitare un nuovo utente di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e475c-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="e475c-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="e475c-139"></span></span>

<span data-ttu-id="e475c-140">Dopo l'abilitazione di un account utente in utenti e computer di Active Directory, è possibile usare il pannello di controllo di Skype for Business Server per creare e abilitare nuovi account utente di Skype for Business Server aggiungendo un utente di Active Directory a Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e475c-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="e475c-141">Puoi anche usare un cmdlet, in particolare [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e475c-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="e475c-142">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e475c-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="e475c-143">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e475c-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="e475c-144">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="e475c-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="e475c-145">Fare clic su **Abilita utenti**.</span><span class="sxs-lookup"><span data-stu-id="e475c-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="e475c-146">Nella finestra di dialogo **nuovo utente di Lync Server** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e475c-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="e475c-147">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome, il nome visualizzato, il nome, il cognome, il nome dell'account SAM (Security Accounts Manager), l'indirizzo di posta elettronica, il nome dell'entità utente (UPN) o il numero di telefono dell'account utente di Active Directory desiderato e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="e475c-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="e475c-148">Nella tabella selezionare l'account che si vuole aggiungere a Skype for Business Server e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e475c-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="e475c-149">Assegnare l'utente a un pool, specificare eventuali dettagli aggiuntivi e assegnare i criteri all'utente desiderato e quindi fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="e475c-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="e475c-150">Disabilitare o riattivare un account utente abilitato in precedenza per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e475c-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="e475c-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="e475c-151"></span></span>

<span data-ttu-id="e475c-152">È possibile usare la procedura seguente per disabilitare un account utente abilitato in precedenza in Skype for Business Server senza perdere le impostazioni di Skype for Business Server configurate per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="e475c-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="e475c-153">Dato che le impostazioni dell'account utente di Skype for Business Server non vengono perse, è possibile riattivare nuovamente un account utente abilitato in precedenza senza dover riconfigurare l'account utente.</span><span class="sxs-lookup"><span data-stu-id="e475c-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="e475c-154">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e475c-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="e475c-155">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e475c-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="e475c-156">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="e475c-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="e475c-157">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si desidera disabilitare o riabilitare e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="e475c-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="e475c-158">Nella tabella fare clic sull'account utente che si vuole disabilitare o riattivare.</span><span class="sxs-lookup"><span data-stu-id="e475c-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="e475c-159">Nel menu **azione** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e475c-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="e475c-160">Per disabilitare temporaneamente l'account utente per Skype for Business Server, fare clic su **Disabilita temporaneamente per Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e475c-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="e475c-161">Per abilitare l'account utente per Skype for Business Server, fare clic su **riattiva per Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e475c-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="e475c-162">Usare Windows PowerShell per disabilitare o riattivare gli account utente</span><span class="sxs-lookup"><span data-stu-id="e475c-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="e475c-163">Gli account utente possono essere temporaneamente disabilitati e quindi riattivati in seguito usando il cmdlet **Set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="e475c-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="e475c-164">Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e475c-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e475c-165">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="e475c-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="e475c-166">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e475c-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="e475c-167">Per disabilitare un account utente</span><span class="sxs-lookup"><span data-stu-id="e475c-167">To disable a user account</span></span>

- <span data-ttu-id="e475c-168">Per disabilitare temporaneamente un account utente, imposta il valore della proprietà Enabled su false ($False).</span><span class="sxs-lookup"><span data-stu-id="e475c-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="e475c-169">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e475c-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="e475c-170">Per riattivare un account utente</span><span class="sxs-lookup"><span data-stu-id="e475c-170">To re-enable a user account</span></span>

- <span data-ttu-id="e475c-171">Per riattivare un account utente disabilitato, imposta il valore della proprietà Enabled su true ($True).</span><span class="sxs-lookup"><span data-stu-id="e475c-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="e475c-172">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e475c-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="e475c-173">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e475c-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="e475c-174">Disabilitare un utente per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="e475c-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="e475c-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="e475c-175"></span></span>

<span data-ttu-id="e475c-176">Usare la procedura seguente per disabilitare VoIP aziendale per un account utente abilitato per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e475c-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="e475c-177">Per disabilitare un account utente per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="e475c-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="e475c-178">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e475c-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="e475c-179">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e475c-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="e475c-180">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="e475c-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="e475c-181">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si vuole abilitare e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="e475c-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="e475c-182">Nella tabella fare clic sull'account utente che si desidera abilitare per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="e475c-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="e475c-183">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="e475c-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="e475c-184">Nella pagina **modifica utente di Lync Server** , in **telefonia**, fare clic su qualsiasi opzione eccetto **VoIP aziendale**.</span><span class="sxs-lookup"><span data-stu-id="e475c-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e475c-185">Per impedire a un utente di effettuare chiamate audio o video tramite Lync, in **telefonia**fare clic su **disabilitato audio/video**.</span><span class="sxs-lookup"><span data-stu-id="e475c-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="e475c-186">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="e475c-186">Click **Commit**.</span></span>

<span data-ttu-id="e475c-187">Ora l'utente non è in grado di usare la caratteristica VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="e475c-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="e475c-188">Informazioni correlate:</span><span class="sxs-lookup"><span data-stu-id="e475c-188">Related information:</span></span> <br/>[<span data-ttu-id="e475c-189">VoIP aziendale e mobilità</span><span class="sxs-lookup"><span data-stu-id="e475c-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="e475c-190">Consentire agli utenti di VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e475c-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="e475c-191">Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="e475c-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="e475c-192">Rimuovere un account utente con Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="e475c-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="e475c-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="e475c-193"></span></span>

<span data-ttu-id="e475c-194">È possibile usare la procedura seguente per rimuovere un account utente aggiunto in precedenza in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e475c-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="e475c-195">La rimozione di un utente causerà la perdita di tutte le impostazioni configurate per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="e475c-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="e475c-196">Se invece si vuole disabilitare temporaneamente un account utente, vedere [disabilitare o riabilitare un account utente abilitato in precedenza per Skype for Business Server](user-accounts.md#Disable).</span><span class="sxs-lookup"><span data-stu-id="e475c-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="e475c-197">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e475c-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="e475c-198">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e475c-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="e475c-199">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="e475c-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="e475c-200">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si desidera disabilitare o riabilitare e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="e475c-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="e475c-201">Nella tabella fare clic sull'account utente che si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="e475c-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="e475c-202">Nel menu **azione** selezionare **Rimuovi da Lync Server**e viene visualizzata una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="e475c-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="e475c-203">Nella finestra di dialogo selezionare **OK** per rimuovere l'utente.</span><span class="sxs-lookup"><span data-stu-id="e475c-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="e475c-204">Rimuovere gli account utente con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e475c-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="e475c-205">Puoi rimuovere gli account utente usando il cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="e475c-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="e475c-206">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e475c-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="e475c-207">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="e475c-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="e475c-208">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e475c-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="e475c-209">Per rimuovere un account utente</span><span class="sxs-lookup"><span data-stu-id="e475c-209">To remove a user account</span></span>
<span data-ttu-id="e475c-210">Per rimuovere un account utente, usare il cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="e475c-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="e475c-211">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e475c-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="e475c-212">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e475c-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="e475c-213">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e475c-213">See also</span></span>
<span data-ttu-id="e475c-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="e475c-214"></span></span>

[<span data-ttu-id="e475c-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="e475c-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="e475c-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="e475c-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
