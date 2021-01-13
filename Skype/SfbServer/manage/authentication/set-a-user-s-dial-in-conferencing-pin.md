---
title: Impostare il PIN di conferenza telefonica con accesso esterno di un utente in Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Riepilogo: impostare il PIN per le conferenze telefoniche con accesso esterno di un utente per Skype for Business Server.'
ms.openlocfilehash: cd7375519fa9fc161c6414dcf1b9d0fbf6de6ef0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828301"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a><span data-ttu-id="4528c-103">Impostare il PIN di conferenza telefonica con accesso esterno di un utente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4528c-103">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="4528c-104">**Riepilogo:** Impostare il PIN di conferenza telefonica con accesso esterno di un utente per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4528c-104">**Summary:** Set a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="4528c-105">Per partecipare a una conferenza telefonica con accesso esterno come utente autenticato, un utente di Skype for Business Server con le credenziali di servizi di dominio Active Directory richiede un codice PIN (Personal Identification Number).</span><span class="sxs-lookup"><span data-stu-id="4528c-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="4528c-106">Se un utente dimentica il PIN per le conferenze telefoniche con accesso esterno o non ha impostato il PIN utilizzando Skype for Business Server, è possibile impostare il PIN dell'utente dal pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4528c-106">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Skype for Business Server, you can set the user's PIN from Skype for Business Server Control Panel.</span></span> <span data-ttu-id="4528c-107">È possibile generare automaticamente il PIN o crearne uno manualmente.</span><span class="sxs-lookup"><span data-stu-id="4528c-107">You can automatically generate the PIN or create one manually.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4528c-108">Le caratteristiche specifiche del PIN, ad esempio la lunghezza minima, possono essere configurate come criterio.</span><span class="sxs-lookup"><span data-stu-id="4528c-108">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="4528c-109">Oltre al criterio globale, è possibile configurare un criterio PIN per singoli siti o utenti.</span><span class="sxs-lookup"><span data-stu-id="4528c-109">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> 
  
### <a name="to-set-a-users-pin"></a><span data-ttu-id="4528c-110">Per impostare il PIN di un utente</span><span class="sxs-lookup"><span data-stu-id="4528c-110">To set a user's PIN</span></span>

1. <span data-ttu-id="4528c-111">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4528c-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4528c-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4528c-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="4528c-113">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="4528c-113">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4528c-114">Utilizzare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="4528c-114">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="4528c-115">Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="4528c-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="4528c-116">Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="4528c-116">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="4528c-117">(Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:</span><span class="sxs-lookup"><span data-stu-id="4528c-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="4528c-118">a.</span><span class="sxs-lookup"><span data-stu-id="4528c-118">a.</span></span> <span data-ttu-id="4528c-119">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="4528c-119">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="4528c-120">b.</span><span class="sxs-lookup"><span data-stu-id="4528c-120">b.</span></span> <span data-ttu-id="4528c-121">Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.</span><span class="sxs-lookup"><span data-stu-id="4528c-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="4528c-122">c.</span><span class="sxs-lookup"><span data-stu-id="4528c-122">c.</span></span> <span data-ttu-id="4528c-123">Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Non uguale a**).</span><span class="sxs-lookup"><span data-stu-id="4528c-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="4528c-124">d.</span><span class="sxs-lookup"><span data-stu-id="4528c-124">d.</span></span> <span data-ttu-id="4528c-125">A seconda della proprietà utente selezionata, immettere i criteri che si desidera utilizzare per filtrare i risultati della ricerca digitandoli oppure facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="4528c-125">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="4528c-126">Per aggiungere ulteriori clausole di ricerca alla query, fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="4528c-126">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="4528c-127">e.</span><span class="sxs-lookup"><span data-stu-id="4528c-127">e.</span></span> <span data-ttu-id="4528c-128">Fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="4528c-128">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4528c-p108">Se il PIN è bloccato, è necessario sbloccarlo per poterlo impostare. Per sbloccare il PIN, fare clic sull'utente, su **Azione** e quindi su **Sblocca PIN**.</span><span class="sxs-lookup"><span data-stu-id="4528c-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="4528c-131">Fare clic su un utente nei risultati della ricerca, su **Azione** e quindi su **Imposta PIN**.</span><span class="sxs-lookup"><span data-stu-id="4528c-131">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>
    
7. <span data-ttu-id="4528c-132">Nella finestra di dialogo **Imposta PIN** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4528c-132">In the **Set PIN** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="4528c-133">Per consentire a Skype for Business Server di generare il PIN dell'utente, selezionare **genera automaticamente un PIN valido** (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="4528c-133">To allow Skype for Business Server to generate the user's PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
   - <span data-ttu-id="4528c-134">Per creare un PIN personalizzato, fare clic su **Immetti manualmente un PIN specifico**, fare clic sulla casella di testo e quindi digitare un PIN che soddisfi i requisiti PIN specificati nelle impostazioni del criterio PIN.</span><span class="sxs-lookup"><span data-stu-id="4528c-134">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>
    
8. <span data-ttu-id="4528c-135">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4528c-135">Click **OK**.</span></span>
    
9. <span data-ttu-id="4528c-136">In **Imposta PIN** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4528c-136">In **Set PIN**, do one of the following:</span></span> 
    
   - <span data-ttu-id="4528c-137">Selezionare la casella di controllo **Mostra PIN** per visualizzare il PIN e quindi copiare il PIN e comunicarlo all'utente utilizzando il metodo preferito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4528c-137">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
   - <span data-ttu-id="4528c-p109">Fare clic su **Apri applicazione di posta elettronica per inviare il nuovo PIN all'utente** per inviare il PIN per posta elettronica. Se si utilizza Microsoft Office Outlook come client di posta elettronica, il PIN verrà copiato automaticamente in un nuovo messaggio di posta elettronica. Se invece si utilizza un altro client di posta elettronica, selezionare la casella di controllo **Mostra PIN** per visualizzare il PIN e quindi copiarlo nel messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4528c-p109">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>
    
10. <span data-ttu-id="4528c-141">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="4528c-141">Click **Close**.</span></span>
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4528c-142">Assegnazione di un PIN utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4528c-142">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4528c-143">È possibile assegnare i numeri di PIN anche utilizzando il cmdlet Set-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="4528c-143">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="4528c-144">È possibile eseguire questo cmdlet sia da Skype for Business Server Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4528c-144">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4528c-145">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo del Blog ["Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="4528c-145">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="4528c-146">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4528c-146">The process is the same in Skype for Business Server.</span></span> 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="4528c-147">Per assegnare automaticamente un numero di PIN a un utente</span><span class="sxs-lookup"><span data-stu-id="4528c-147">To auto-assign a PIN number to a user</span></span>

<span data-ttu-id="4528c-148">Il comando seguente assegna un numero PIN all'utente Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="4528c-148">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="4528c-149">Poiché il parametro PIN non è incluso, Skype for Business Server genererà e assegnerà automaticamente il numero di PIN.</span><span class="sxs-lookup"><span data-stu-id="4528c-149">Because the Pin parameter is not included, Skype for Business Server will automatically generate and assign the PIN number.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="4528c-150">Per assegnare un numero di PIN specifico a un utente</span><span class="sxs-lookup"><span data-stu-id="4528c-150">To assign a specific PIN number to a user</span></span>

<span data-ttu-id="4528c-151">Questo comando usa il parametro Pin per assegnare il numero PIN 121989 all'utente Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="4528c-151">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

<span data-ttu-id="4528c-152">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="4528c-152">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet.</span></span>
  

