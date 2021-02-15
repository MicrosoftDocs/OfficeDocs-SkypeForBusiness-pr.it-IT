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
description: Le sezioni di questo articolo descrivono come abilitare, disabilitare temporaneamente o rimuovere gli utenti di Active Directory da Skype for Business Server.
ms.openlocfilehash: aa1b1b21ba089815af20b61da3360179fb10935e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832776"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="32d93-103">Gestire gli account utente per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="32d93-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="32d93-104">Le sezioni di questo articolo descrivono come abilitare, disabilitare temporaneamente o rimuovere gli utenti di Active Directory da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="32d93-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="32d93-105">Per informazioni su come abilitare un utente di Active Directory, vedere [Creare un nuovo account utente.](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="32d93-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="32d93-106">Per informazioni su come eliminare un utente di Active Directory, vedere [Eliminare un account utente.](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="32d93-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="32d93-107">Queste procedure devono essere eseguite durante una finestra di manutenzione, quando l'utilizzo di Skype for Business è minimo.</span><span class="sxs-lookup"><span data-stu-id="32d93-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="32d93-108">L'esecuzione di questa operazione in base a una pianificazione giornaliera o settimanale dipenderà dalle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="32d93-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="32d93-109">In questo articolo sono contenute le procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="32d93-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="32d93-110">Per ricercare uno o più utenti</span><span class="sxs-lookup"><span data-stu-id="32d93-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="32d93-111">Aggiungere e abilitare un nuovo utente di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="32d93-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="32d93-112">Disabilitare o riattivare un account utente precedentemente abilitato per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="32d93-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="32d93-113">Disabilitare un utente per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="32d93-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="32d93-114">Rimuovere un account utente con Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="32d93-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="32d93-115">Per ricercare uno o più utenti</span><span class="sxs-lookup"><span data-stu-id="32d93-115">To search for one or more users</span></span>
<span data-ttu-id="32d93-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="32d93-116"><a name="Search"> </a></span></span>

<span data-ttu-id="32d93-117">È possibile utilizzare i risultati di una query di ricerca per configurare gli utenti di Active Directory per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="32d93-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="32d93-118">È possibile ricercare utenti in base al nome visualizzato, al nome, al cognome, al nome dell'account SAM (Security Accounts Manager), all'indirizzo SIP o all'URI (Uniform Resource Identifier) della linea.</span><span class="sxs-lookup"><span data-stu-id="32d93-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="32d93-119">È possibile cercare utenti utilizzando il Pannello di controllo di Skype for Business Server o lo snap-in Utenti e computer di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="32d93-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="32d93-120">La procedura seguente descrive come usare il Pannello di controllo di Skype for Business Server per cercare utenti.</span><span class="sxs-lookup"><span data-stu-id="32d93-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="32d93-121">In un ambiente con una topologia a foresta centrale, i risultati della ricerca potrebbero non essere accurati quando si cerca un utente in base all'indirizzo di posta elettronica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="32d93-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="32d93-122">È invece possibile cercare utenti specificando un prefisso di indirizzo SIP, ad esempio sip:name, aggiungere un filtro di ricerca e selezionare un indirizzo SIP contenente un indirizzo di posta elettronica parziale oppure utilizzare il cmdlet **Get-CSUser.**</span><span class="sxs-lookup"><span data-stu-id="32d93-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="32d93-123">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="32d93-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="32d93-124">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="32d93-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="32d93-125">Nella barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="32d93-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="32d93-126">Nella casella **Ricerca utenti** digitare interamente o parzialmente il nome visualizzato, il nome, il cognome, il nome account SAM, l'indirizzo SIP o l'URI linea dell'account utente da ricercare e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="32d93-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="32d93-127">(Facoltativo) Specificare ulteriori criteri di ricerca per circoscrivere i risultati:</span><span class="sxs-lookup"><span data-stu-id="32d93-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="32d93-128">a.</span><span class="sxs-lookup"><span data-stu-id="32d93-128">a.</span></span> <span data-ttu-id="32d93-129">Fare clic sul pulsante freccia di espansione nell'angolo in alto a destra della schermata al di sopra di **Risultati della ricerca** e quindi fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="32d93-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="32d93-130">b.</span><span class="sxs-lookup"><span data-stu-id="32d93-130">b.</span></span> <span data-ttu-id="32d93-131">Digitare la proprietà utente oppure selezionarla facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="32d93-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="32d93-132">c.</span><span class="sxs-lookup"><span data-stu-id="32d93-132">c.</span></span> <span data-ttu-id="32d93-133">Nell'elenco **Uguale a** selezionare **Uguale a** o **Diverso da**.</span><span class="sxs-lookup"><span data-stu-id="32d93-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="32d93-134">d.</span><span class="sxs-lookup"><span data-stu-id="32d93-134">d.</span></span> <span data-ttu-id="32d93-135">Nella casella di testo digitare i criteri di ricerca che si desidera utilizzare per filtrare i risultati della ricerca e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="32d93-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="32d93-p110">I risultati della ricerca verranno visualizzati al di sotto di **Risultati della ricerca**. È possibile selezionare uno o tutti gli utenti dell'elenco ed eseguire attività di configurazione sugli utenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="32d93-p110">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="32d93-138">Aggiungere e abilitare un nuovo utente di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="32d93-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="32d93-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="32d93-139"><a name="Add"> </a></span></span>

<span data-ttu-id="32d93-140">Dopo aver abilitato un account utente in Utenti e computer di Active Directory, è possibile utilizzare il Pannello di controllo di Skype for Business Server per creare e abilitare nuovi account utente di Skype for Business Server aggiungendo un utente di Active Directory a Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="32d93-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="32d93-141">È inoltre possibile utilizzare un cmdlet, in [particolare Enable-CsUser.](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="32d93-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="32d93-142">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="32d93-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="32d93-143">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="32d93-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="32d93-144">Nella barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="32d93-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="32d93-145">Fare clic su **Abilita utenti**.</span><span class="sxs-lookup"><span data-stu-id="32d93-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="32d93-146">Nella finestra di dialogo **Nuovo utente di Lync Server** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="32d93-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="32d93-147">Nella casella **Ricerca utenti** digitare il nome intero o parziale, il nome visualizzato, il nome, il cognome, il nome account del sistema degli account di sicurezza (SAM), l'indirizzo di posta elettronica, il nome dell'entità utente o il numero di telefono dell'account utente di Active Directory desiderato e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="32d93-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="32d93-148">Nella tabella, selezionare l'account che si desidera aggiungere a Skype for Business Server, quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="32d93-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="32d93-149">Assegnare l'utente a un pool, specificare eventuali dettagli aggiuntivi, assegnare i criteri all'utente desiderato e quindi fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="32d93-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="32d93-150">Disabilitare o riattivare un account utente precedentemente abilitato per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="32d93-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="32d93-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="32d93-151"><a name="Disable"> </a></span></span>

<span data-ttu-id="32d93-152">È possibile utilizzare la procedura seguente per disabilitare un account utente abilitato in precedenza in Skype for Business Server senza perdere le impostazioni di Skype for Business Server configurate per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="32d93-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="32d93-153">Poiché non si perdono le impostazioni dell'account utente di Skype for Business Server, è possibile ri abilitare nuovamente un account utente abilitato in precedenza senza dover riconfigurare l'account utente.</span><span class="sxs-lookup"><span data-stu-id="32d93-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="32d93-154">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="32d93-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="32d93-155">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="32d93-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="32d93-156">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="32d93-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="32d93-157">Nella casella **Cerca utenti** digitare tutto o solo la prima parte del nome visualizzato, del nome, del cognome, del nome di account SAM (Security Accounts Manager), dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) linea dell'account utente che si desidera disabilitare o abilitare di nuovo e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="32d93-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="32d93-158">Nella tabella fare clic sull'account utente che si desidera disabilitare o abilitare di nuovo.</span><span class="sxs-lookup"><span data-stu-id="32d93-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="32d93-159">Dal menu **Azione** scegliere uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="32d93-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="32d93-160">Per disabilitare temporaneamente l'account utente per Skype for Business Server, fare clic su **Disabilita temporaneamente per Lync Server.**</span><span class="sxs-lookup"><span data-stu-id="32d93-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="32d93-161">Per abilitare l'account utente per Skype for Business Server, fare clic **su Ri-abilita per Lync Server.**</span><span class="sxs-lookup"><span data-stu-id="32d93-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="32d93-162">Utilizzare Windows PowerShell per disabilitare o riattivare gli account utente</span><span class="sxs-lookup"><span data-stu-id="32d93-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="32d93-163">Gli account utente possono essere temporaneamente disabilitati e quindi ri-abilitati successivamente utilizzando il cmdlet **Set-CsUser.**</span><span class="sxs-lookup"><span data-stu-id="32d93-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="32d93-164">È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="32d93-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="32d93-165">Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="32d93-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="32d93-166">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="32d93-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="32d93-167">Per disabilitare un account utente</span><span class="sxs-lookup"><span data-stu-id="32d93-167">To disable a user account</span></span>

- <span data-ttu-id="32d93-168">Per disabilitare temporaneamente un account utente, impostare il valore della proprietà Enabled su False ($False).</span><span class="sxs-lookup"><span data-stu-id="32d93-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="32d93-169">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="32d93-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="32d93-170">Per abilitare di nuovo un account utente</span><span class="sxs-lookup"><span data-stu-id="32d93-170">To re-enable a user account</span></span>

- <span data-ttu-id="32d93-171">Per abilitare nuovamente un account utente disabilitato, impostare il valore della proprietà Enabled su True ($True).</span><span class="sxs-lookup"><span data-stu-id="32d93-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="32d93-172">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="32d93-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="32d93-173">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsUser.](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="32d93-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="32d93-174">Disabilitare un utente per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="32d93-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="32d93-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="32d93-175"><a name="Disable_EV"> </a></span></span>

<span data-ttu-id="32d93-176">Utilizzare la procedura seguente per disabilitare VoIP aziendale per un account utente abilitato per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="32d93-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="32d93-177">Per disabilitare un account utente per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="32d93-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="32d93-178">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="32d93-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="32d93-179">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="32d93-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="32d93-180">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="32d93-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="32d93-181">Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account di Gestione account di protezione, dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente da abilitare e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="32d93-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="32d93-182">Nella tabella fare clic sull'account utente che si desidera abilitare per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="32d93-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="32d93-183">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="32d93-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="32d93-184">Nella pagina **Modifica utente Lync Server**, in **Telefonia** fare clic su qualsiasi opzione, ad eccezione di **VoIP aziendale**.</span><span class="sxs-lookup"><span data-stu-id="32d93-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="32d93-185">Per impedire a un utente di effettuare chiamate audio o video tramite Lync, in **Telefonia** fare clic **su Audio/video disabilitato.**</span><span class="sxs-lookup"><span data-stu-id="32d93-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="32d93-186">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="32d93-186">Click **Commit**.</span></span>

<span data-ttu-id="32d93-187">L'utente non è più in grado di usare la VoIP aziendale utente.</span><span class="sxs-lookup"><span data-stu-id="32d93-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="32d93-188">Informazioni correlate:</span><span class="sxs-lookup"><span data-stu-id="32d93-188">Related information:</span></span> <br/>[<span data-ttu-id="32d93-189">VoIP aziendale e dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="32d93-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="32d93-190">Abilitare gli utenti per VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="32d93-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="32d93-191">Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="32d93-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="32d93-192">Rimuovere un account utente con Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="32d93-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="32d93-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="32d93-193"><a name="Remove"> </a></span></span>

<span data-ttu-id="32d93-194">È possibile utilizzare la procedura seguente per rimuovere un account utente aggiunto in precedenza in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="32d93-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="32d93-195">La rimozione di un utente comporterà la perdita delle impostazioni configurate per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="32d93-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="32d93-196">Se invece si desidera disabilitare temporaneamente un account utente, vedere Disabilitare o riattivare un account utente precedentemente abilitato [per Skype for Business Server.](user-accounts.md#Disable)</span><span class="sxs-lookup"><span data-stu-id="32d93-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="32d93-197">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="32d93-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="32d93-198">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="32d93-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="32d93-199">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="32d93-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="32d93-200">Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, nome, cognome, nome dell'account Gestione account di protezione, indirizzo SIP o URI (Uniform Resource Identifier) di linea dell'account utente da disabilitare o riabilitare e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="32d93-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="32d93-201">Nella tabella fare clic sull'account utente da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="32d93-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="32d93-202">Nel menu **Azione** selezionare **Rimuovi da Lync Server**. Verrà visualizzata una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="32d93-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="32d93-203">Dalla finestra di dialogo selezionare **OK** per rimuovere l'utente.</span><span class="sxs-lookup"><span data-stu-id="32d93-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="32d93-204">Rimuovere gli account utente con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="32d93-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="32d93-205">È possibile rimuovere gli account utente utilizzando il cmdlet Disable-CsUser seguente.</span><span class="sxs-lookup"><span data-stu-id="32d93-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="32d93-206">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="32d93-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="32d93-207">Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="32d93-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="32d93-208">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="32d93-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="32d93-209">Per rimuovere un account utente</span><span class="sxs-lookup"><span data-stu-id="32d93-209">To remove a user account</span></span>
<span data-ttu-id="32d93-210">Per rimuovere un account utente, usare il cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="32d93-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="32d93-211">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="32d93-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="32d93-212">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Disable-CsUser.](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="32d93-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="32d93-213">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32d93-213">See also</span></span>
<span data-ttu-id="32d93-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="32d93-214"><a name="Remove"> </a></span></span>

[<span data-ttu-id="32d93-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="32d93-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="32d93-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="32d93-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
