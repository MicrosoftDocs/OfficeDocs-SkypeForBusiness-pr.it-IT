---
title: 'Lync Server 2013: impostare il PIN di conferenza telefonica con accesso esterno di un utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 258c6e5da1dc5b78d53bbc3779d50890935d7b58
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a><span data-ttu-id="aaf06-102">Impostare il PIN di conferenza telefonica con accesso esterno di un utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aaf06-102">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aaf06-103">_**Argomento Ultima modifica:** 2014-06-10_</span><span class="sxs-lookup"><span data-stu-id="aaf06-103">_**Topic Last Modified:** 2014-06-10_</span></span>

<span data-ttu-id="aaf06-104">Per partecipare a una conferenza telefonica con accesso esterno come utente autenticato, un utente di Lync Server 2013 con le credenziali di Active Directory Domain Services (AD DS) richiede un PIN (Personal Identification Number).</span><span class="sxs-lookup"><span data-stu-id="aaf06-104">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="aaf06-105">Se un utente dimentica il PIN per i servizi di conferenza telefonica con accesso esterno o non ha impostato il PIN tramite Lync Server, è possibile impostare il PIN dell'utente dal pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aaf06-105">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Lync Server, you can set the user’s PIN from Lync Server Control Panel.</span></span> <span data-ttu-id="aaf06-106">È possibile generare automaticamente il PIN o crearne uno manualmente.</span><span class="sxs-lookup"><span data-stu-id="aaf06-106">You can automatically generate the PIN or create one manually.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aaf06-107">Le caratteristiche specifiche del PIN, ad esempio la lunghezza minima, possono essere configurate come criteri.</span><span class="sxs-lookup"><span data-stu-id="aaf06-107">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="aaf06-108">Oltre al criterio globale, è possibile configurare un criterio PIN per singoli siti o utenti.</span><span class="sxs-lookup"><span data-stu-id="aaf06-108">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> <span data-ttu-id="aaf06-109">Per informazioni dettagliate sulla configurazione di un criterio PIN, vedere <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">configurare le regole pin (Personal Identification Number) di conferenza telefonica con accesso esterno in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="aaf06-109">For details about configuring a PIN policy, see <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-set-a-users-pin"></a><span data-ttu-id="aaf06-110">Per impostare il PIN di un utente</span><span class="sxs-lookup"><span data-stu-id="aaf06-110">To set a user’s PIN</span></span>

1.  <span data-ttu-id="aaf06-111">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="aaf06-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aaf06-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aaf06-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aaf06-113">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="aaf06-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aaf06-114">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="aaf06-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="aaf06-115">Usare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="aaf06-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="aaf06-116">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="aaf06-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="aaf06-117">Se si ha una query salvata, fare clic sull'icona **Apri query** , usare la finestra di dialogo **Apri** per recuperare la query (un file con estensione USF) e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="aaf06-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="aaf06-118">Opzionale Specificare altri criteri di ricerca per restringere i risultati:</span><span class="sxs-lookup"><span data-stu-id="aaf06-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="aaf06-119">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="aaf06-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="aaf06-120">Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="aaf06-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="aaf06-121">Nell'elenco **a discesa uguale a** fare clic sull'operatore, ad esempio **uguale** a o diverso **da**.</span><span class="sxs-lookup"><span data-stu-id="aaf06-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="aaf06-122">A seconda della proprietà utente selezionata, immettere i criteri da usare per filtrare i risultati della ricerca digitando o facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="aaf06-122">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="aaf06-123">Per aggiungere altre clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="aaf06-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="aaf06-124">Fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="aaf06-124">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aaf06-125">Se il PIN è bloccato, è necessario sbloccare il PIN prima di poterlo impostare.</span><span class="sxs-lookup"><span data-stu-id="aaf06-125">If the PIN is locked, you must unlock the PIN before you can set it.</span></span> <span data-ttu-id="aaf06-126">Per sbloccare il PIN, fare clic sull'utente, fare clic su <STRONG>azione</STRONG>e quindi su <STRONG>Sblocca PIN</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="aaf06-126">To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="aaf06-127">Fare clic su un utente nei risultati della ricerca, fare clic su **azione**e quindi su **Imposta PIN**.</span><span class="sxs-lookup"><span data-stu-id="aaf06-127">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>

7.  <span data-ttu-id="aaf06-128">Nella finestra di dialogo **Imposta PIN** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aaf06-128">In the **Set PIN** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="aaf06-129">Per consentire a Lync Server 2013 di generare il PIN dell'utente, selezionare **genera automaticamente un PIN valido** (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="aaf06-129">To allow Lync Server 2013 to generate the user’s PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
      - <span data-ttu-id="aaf06-130">Per creare un PIN personalizzato, fare clic su **immettere manualmente un PIN specifico**, fare clic sulla casella di testo e quindi digitare un pin che soddisfi i requisiti del PIN specificati nelle impostazioni dei criteri PIN.</span><span class="sxs-lookup"><span data-stu-id="aaf06-130">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>

8.  <span data-ttu-id="aaf06-131">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="aaf06-131">Click **OK**.</span></span>

9.  <span data-ttu-id="aaf06-132">In **Imposta PIN**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aaf06-132">In **Set PIN**, do one of the following:</span></span>
    
      - <span data-ttu-id="aaf06-133">Selezionare la casella di controllo **Mostra PIN** per visualizzare il PIN e quindi copiare il PIN e comunicarlo all'utente usando il metodo preferito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="aaf06-133">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
      - <span data-ttu-id="aaf06-134">Fare clic su **Apri l'applicazione di posta elettronica per inviare il nuovo PIN all'utente** per inviare il PIN tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="aaf06-134">Click **Open my email application to send the new PIN to the user** to send the PIN by email.</span></span> <span data-ttu-id="aaf06-135">Se Microsoft Office Outlook è il client di posta elettronica, il PIN viene copiato automaticamente in un nuovo messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="aaf06-135">If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message.</span></span> <span data-ttu-id="aaf06-136">Se si usa un altro client di posta elettronica, selezionare la casella di controllo **Mostra PIN** per visualizzare il PIN e quindi copiarlo nel messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="aaf06-136">If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>

10. <span data-ttu-id="aaf06-137">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="aaf06-137">Click **Close**.</span></span>

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="aaf06-138">Assegnazione di un PIN utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aaf06-138">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="aaf06-139">Puoi assegnare i numeri di PIN anche usando il cmdlet Set-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="aaf06-139">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="aaf06-140">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aaf06-140">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="aaf06-141">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="aaf06-141">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="aaf06-142">Per assegnare automaticamente un numero PIN a un utente</span><span class="sxs-lookup"><span data-stu-id="aaf06-142">To auto-assign a PIN number to a user</span></span>

  - <span data-ttu-id="aaf06-143">Con il comando seguente viene assegnato un numero PIN all'utente Ken.</span><span class="sxs-lookup"><span data-stu-id="aaf06-143">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="aaf06-144">Dato che il parametro PIN non è incluso, Lync Server genera automaticamente e assegna il numero di PIN.</span><span class="sxs-lookup"><span data-stu-id="aaf06-144">Because the Pin parameter is not included, Lync Server will automatically generate and assign the PIN number.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="aaf06-145">Per assegnare un numero PIN specifico a un utente</span><span class="sxs-lookup"><span data-stu-id="aaf06-145">To assign a specific PIN number to a user</span></span>

  - <span data-ttu-id="aaf06-146">Questo comando usa il parametro PIN per assegnare il PIN numero 121989 all'utente Ken.</span><span class="sxs-lookup"><span data-stu-id="aaf06-146">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

<span data-ttu-id="aaf06-147">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) .</span><span class="sxs-lookup"><span data-stu-id="aaf06-147">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aaf06-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aaf06-148">See Also</span></span>


<span data-ttu-id="aaf06-149">[Numero di accesso esterno](https://technet.microsoft.com/en-us/library/gg133674\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="aaf06-149">[Dial-in Access Number](https://technet.microsoft.com/en-us/library/gg133674\(v=ocs.15\))</span></span>  


[<span data-ttu-id="aaf06-150">Configurare le regole PIN (Personal Identification Number) per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aaf06-150">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

