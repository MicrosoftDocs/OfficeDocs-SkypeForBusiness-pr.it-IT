---
title: Gestire gli account utente per Skype for Business Server
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
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: Nelle sezioni di questo articolo viene descritto come abilitare, disabilitare temporaneamente o rimuovere gli utenti di Active Directory da Skype for Business Server.
ms.openlocfilehash: 0cf78b4ebe7023bc5a0f1b4af75c5d9e5a45db1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103122"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="beaec-103">Gestire gli account utente per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="beaec-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="beaec-104">Nelle sezioni di questo articolo viene descritto come abilitare, disabilitare temporaneamente o rimuovere gli utenti di Active Directory da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="beaec-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="beaec-105">Per informazioni su come abilitare un utente di Active Directory, vedere [Create a New User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="beaec-105">For information on how to enable an Active Directory user, see [Create a New User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)).</span></span> <span data-ttu-id="beaec-106">Per informazioni su come eliminare un utente di Active Directory, vedere [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="beaec-106">For information on how to delete an Active Directory user, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>

<span data-ttu-id="beaec-107">Queste procedure devono essere eseguite durante una finestra di manutenzione, quando l'utilizzo di Skype for Business è minimo.</span><span class="sxs-lookup"><span data-stu-id="beaec-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="beaec-108">L'eventuale esecuzione di questa operazione in base a una pianificazione giornaliera o settimanale dipende dalle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="beaec-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="beaec-109">In questo articolo sono contenute le procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="beaec-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="beaec-110">Per ricercare uno o più utenti</span><span class="sxs-lookup"><span data-stu-id="beaec-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="beaec-111">Aggiungere e abilitare un nuovo utente di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="beaec-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="beaec-112">Disabilitare o riattivare un account utente precedentemente abilitato per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="beaec-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="beaec-113">Disabilitare un utente per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="beaec-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="beaec-114">Rimuovere un account utente con Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="beaec-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="beaec-115">Per ricercare uno o più utenti</span><span class="sxs-lookup"><span data-stu-id="beaec-115">To search for one or more users</span></span>
<span data-ttu-id="beaec-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="beaec-116"><a name="Search"> </a></span></span>

<span data-ttu-id="beaec-117">È possibile utilizzare i risultati di una query di ricerca per configurare gli utenti di Active Directory per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="beaec-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="beaec-118">È possibile ricercare utenti in base al nome visualizzato, al nome, al cognome, al nome dell'account SAM (Security Accounts Manager), all'indirizzo SIP o all'URI (Uniform Resource Identifier) della linea.</span><span class="sxs-lookup"><span data-stu-id="beaec-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="beaec-119">È possibile cercare utenti utilizzando il Pannello di controllo di Skype for Business Server o lo snap-in Utenti e computer di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="beaec-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="beaec-120">La procedura seguente descrive come usare il Pannello di controllo di Skype for Business Server per cercare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="beaec-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="beaec-121">In un ambiente con una topologia a foresta centrale, i risultati della ricerca potrebbero non essere accurati quando si cerca un utente in base all'indirizzo di posta elettronica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="beaec-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="beaec-122">È invece possibile cercare utenti specificando un prefisso di indirizzo SIP, ad esempio sip:name, aggiungere un filtro di ricerca e selezionare un indirizzo SIP contenente un indirizzo di posta elettronica parziale oppure utilizzare il cmdlet **Get-CSUser.**</span><span class="sxs-lookup"><span data-stu-id="beaec-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="beaec-123">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="beaec-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="beaec-124">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="beaec-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="beaec-125">Nella barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="beaec-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="beaec-126">Nella casella **Ricerca utenti** digitare interamente o parzialmente il nome visualizzato, il nome, il cognome, il nome account SAM, l'indirizzo SIP o l'URI linea dell'account utente da ricercare e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="beaec-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="beaec-127">(Facoltativo) Specificare ulteriori criteri di ricerca per circoscrivere i risultati:</span><span class="sxs-lookup"><span data-stu-id="beaec-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="beaec-128">a.</span><span class="sxs-lookup"><span data-stu-id="beaec-128">a.</span></span> <span data-ttu-id="beaec-129">Fare clic sul pulsante freccia di espansione nell'angolo in alto a destra della schermata al di sopra di **Risultati della ricerca** e quindi fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="beaec-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="beaec-130">b.</span><span class="sxs-lookup"><span data-stu-id="beaec-130">b.</span></span> <span data-ttu-id="beaec-131">Digitare la proprietà utente oppure selezionarla facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="beaec-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="beaec-132">c.</span><span class="sxs-lookup"><span data-stu-id="beaec-132">c.</span></span> <span data-ttu-id="beaec-133">Nell'elenco **Uguale a** selezionare **Uguale a** o **Diverso da**.</span><span class="sxs-lookup"><span data-stu-id="beaec-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="beaec-134">d.</span><span class="sxs-lookup"><span data-stu-id="beaec-134">d.</span></span> <span data-ttu-id="beaec-135">Nella casella di testo digitare i criteri di ricerca che si desidera utilizzare per filtrare i risultati della ricerca e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="beaec-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="beaec-p110">I risultati della ricerca verranno visualizzati al di sotto di **Risultati della ricerca**. È possibile selezionare uno o tutti gli utenti dell'elenco ed eseguire attività di configurazione sugli utenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="beaec-p110">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="beaec-138">Aggiungere e abilitare un nuovo utente di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="beaec-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="beaec-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="beaec-139"><a name="Add"> </a></span></span>

<span data-ttu-id="beaec-140">Dopo aver abilitato un account utente in Utenti e computer di Active Directory, è possibile utilizzare il Pannello di controllo di Skype for Business Server per creare e abilitare nuovi account utente di Skype for Business Server aggiungendo un utente di Active Directory a Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="beaec-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="beaec-141">È inoltre possibile utilizzare un cmdlet, in particolare [Enable-CsUser.](/powershell/module/skype/enable-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="beaec-141">You can also use a cmdlet, specifically [Enable-CsUser](/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="beaec-142">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="beaec-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="beaec-143">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="beaec-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="beaec-144">Nella barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="beaec-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="beaec-145">Fare clic su **Abilita utenti**.</span><span class="sxs-lookup"><span data-stu-id="beaec-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="beaec-146">Nella finestra di dialogo **Nuovo utente di Lync Server** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="beaec-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="beaec-147">Nella casella **Ricerca utenti** digitare il nome intero o parziale, il nome visualizzato, il nome, il cognome, il nome account del sistema degli account di sicurezza (SAM), l'indirizzo di posta elettronica, il nome dell'entità utente o il numero di telefono dell'account utente di Active Directory desiderato e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="beaec-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="beaec-148">Nella tabella selezionare l'account che si desidera aggiungere a Skype for Business Server e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="beaec-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="beaec-149">Assegnare l'utente a un pool, specificare eventuali dettagli aggiuntivi, assegnare i criteri all'utente desiderato e quindi fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="beaec-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="beaec-150">Disabilitare o riattivare un account utente precedentemente abilitato per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="beaec-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="beaec-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="beaec-151"><a name="Disable"> </a></span></span>

<span data-ttu-id="beaec-152">È possibile utilizzare la procedura seguente per disabilitare un account utente abilitato in precedenza in Skype for Business Server senza perdere le impostazioni di Skype for Business Server configurate per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="beaec-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="beaec-153">Poiché non si perdono le impostazioni dell'account utente di Skype for Business Server, è possibile riconfigurare un account utente abilitato in precedenza senza dover riconfigurare l'account utente.</span><span class="sxs-lookup"><span data-stu-id="beaec-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="beaec-154">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="beaec-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="beaec-155">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="beaec-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="beaec-156">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="beaec-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="beaec-157">Nella casella **Cerca utenti** digitare tutto o solo la prima parte del nome visualizzato, del nome, del cognome, del nome di account SAM (Security Accounts Manager), dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) linea dell'account utente che si desidera disabilitare o abilitare di nuovo e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="beaec-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="beaec-158">Nella tabella fare clic sull'account utente che si desidera disabilitare o abilitare di nuovo.</span><span class="sxs-lookup"><span data-stu-id="beaec-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="beaec-159">Dal menu **Azione** scegliere uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="beaec-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="beaec-160">Per disabilitare temporaneamente l'account utente per Skype for Business Server, fare clic su **Disabilita temporaneamente per Lync Server.**</span><span class="sxs-lookup"><span data-stu-id="beaec-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="beaec-161">Per abilitare l'account utente per Skype for Business Server, fare clic **su Ri-abilita per Lync Server.**</span><span class="sxs-lookup"><span data-stu-id="beaec-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="beaec-162">Disabilitazione o riattivazione degli account utente tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="beaec-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="beaec-163">Gli account utente possono essere temporaneamente disabilitati e quindi ri abilitati in un secondo momento utilizzando il cmdlet **Set-CsUser.**</span><span class="sxs-lookup"><span data-stu-id="beaec-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="beaec-164">È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="beaec-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="beaec-165">Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo di blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="beaec-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="beaec-166">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="beaec-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="beaec-167">Per disabilitare un account utente</span><span class="sxs-lookup"><span data-stu-id="beaec-167">To disable a user account</span></span>

- <span data-ttu-id="beaec-168">Per disabilitare temporaneamente un account utente, impostare il valore della proprietà Enabled su False ($False).</span><span class="sxs-lookup"><span data-stu-id="beaec-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="beaec-169">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="beaec-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="beaec-170">Per abilitare di nuovo un account utente</span><span class="sxs-lookup"><span data-stu-id="beaec-170">To re-enable a user account</span></span>

- <span data-ttu-id="beaec-171">Per abilitare nuovamente un account utente disabilitato, impostare il valore della proprietà Enabled su True ($True).</span><span class="sxs-lookup"><span data-stu-id="beaec-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="beaec-172">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="beaec-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="beaec-173">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsUser.](/powershell/module/skype/set-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="beaec-173">For more information, see the help topic for the [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="beaec-174">Disabilitare un utente per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="beaec-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="beaec-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="beaec-175"><a name="Disable_EV"> </a></span></span>

<span data-ttu-id="beaec-176">Utilizzare la procedura seguente per disabilitare VoIP aziendale per un account utente abilitato per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="beaec-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="beaec-177">Per disabilitare un account utente per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="beaec-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="beaec-178">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="beaec-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="beaec-179">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="beaec-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="beaec-180">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="beaec-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="beaec-181">Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account di Gestione account di protezione, dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente da abilitare e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="beaec-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="beaec-182">Nella tabella fare clic sull'account utente che si desidera abilitare per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="beaec-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="beaec-183">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="beaec-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="beaec-184">Nella pagina **Modifica utente Lync Server**, in **Telefonia** fare clic su qualsiasi opzione, ad eccezione di **VoIP aziendale**.</span><span class="sxs-lookup"><span data-stu-id="beaec-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="beaec-185">Per impedire a un utente di effettuare chiamate audio o video tramite Lync, in **Telefonia** fare clic **su Audio/video disabilitato.**</span><span class="sxs-lookup"><span data-stu-id="beaec-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="beaec-186">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="beaec-186">Click **Commit**.</span></span>

<span data-ttu-id="beaec-187">L'utente non è ora in grado di usare la VoIP aziendale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="beaec-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="beaec-188">Informazioni correlate:</span><span class="sxs-lookup"><span data-stu-id="beaec-188">Related information:</span></span> <br/>[<span data-ttu-id="beaec-189">VoIP aziendale mobilità</span><span class="sxs-lookup"><span data-stu-id="beaec-189">Enterprise Voice and mobility</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [<span data-ttu-id="beaec-190">Abilitare gli utenti per VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="beaec-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="beaec-191">Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="beaec-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="beaec-192">Rimuovere un account utente con Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="beaec-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="beaec-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="beaec-193"><a name="Remove"> </a></span></span>

<span data-ttu-id="beaec-194">È possibile utilizzare la procedura seguente per rimuovere un account utente aggiunto in precedenza in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="beaec-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="beaec-195">La rimozione di un utente comporterà la perdita delle impostazioni configurate per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="beaec-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="beaec-196">Se invece si desidera disabilitare temporaneamente un account utente, vedere Disabilitare o riattivare un account utente abilitato in precedenza [per Skype for Business Server.](user-accounts.md#Disable)</span><span class="sxs-lookup"><span data-stu-id="beaec-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="beaec-197">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="beaec-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="beaec-198">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="beaec-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="beaec-199">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="beaec-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="beaec-200">Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, nome, cognome, nome dell'account Gestione account di protezione, indirizzo SIP o URI (Uniform Resource Identifier) di linea dell'account utente da disabilitare o riabilitare e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="beaec-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="beaec-201">Nella tabella fare clic sull'account utente da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="beaec-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="beaec-202">Nel menu **Azione** selezionare **Rimuovi da Lync Server**. Verrà visualizzata una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="beaec-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="beaec-203">Dalla finestra di dialogo selezionare **OK** per rimuovere l'utente.</span><span class="sxs-lookup"><span data-stu-id="beaec-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="beaec-204">Rimuovere gli account utente con i cmdlet di Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="beaec-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="beaec-205">È possibile rimuovere gli account utente utilizzando il cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="beaec-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="beaec-206">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="beaec-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="beaec-207">Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo di blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="beaec-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="beaec-208">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="beaec-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="beaec-209">Per rimuovere un account utente</span><span class="sxs-lookup"><span data-stu-id="beaec-209">To remove a user account</span></span>
<span data-ttu-id="beaec-210">Per rimuovere un account utente, usare il cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="beaec-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="beaec-211">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="beaec-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="beaec-212">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Disable-CsUser.](/powershell/module/skype/disable-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="beaec-212">For more information, see the help topic for the [Disable-CsUser](/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="beaec-213">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="beaec-213">See also</span></span>
<span data-ttu-id="beaec-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="beaec-214"><a name="Remove"> </a></span></span>

[<span data-ttu-id="beaec-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="beaec-215">Enable-CsUser</span></span>](/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="beaec-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="beaec-216">Disable-CsUser</span></span>](/powershell/module/skype/disable-csuser?view=skype-ps)