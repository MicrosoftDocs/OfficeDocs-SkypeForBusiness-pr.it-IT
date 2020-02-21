---
title: 'Lync Server 2013: rimuovere un account utente da Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db45682fd130aba378cab0f9894537ff4c23c28b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a><span data-ttu-id="be117-102">Rimuovere un account utente da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be117-102">Remove a user account from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be117-103">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="be117-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="be117-104">È possibile utilizzare la procedura seguente per rimuovere un account utente aggiunto in precedenza in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="be117-104">You can use the following procedure to remove a previously added user account in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be117-105">La rimozione di un utente comporterà la perdita delle impostazioni configurate per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="be117-105">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="be117-106">Se invece si desidera disabilitare temporaneamente un account utente, vedere l'argomento <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">disabilitare o riabilitare l'account utente per Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="be117-106">If you would like to temporarily disable a user account instead, see the topic <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a><span data-ttu-id="be117-107">Per rimuovere un account utente utilizzando Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="be117-107">To remove a user account by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="be117-108">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="be117-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="be117-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="be117-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="be117-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="be117-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="be117-111">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="be117-111">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="be117-112">Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, nome, cognome, nome dell'account Gestione account di protezione, indirizzo SIP o URI (Uniform Resource Identifier) di linea dell'account utente da disabilitare o riabilitare e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="be117-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="be117-113">Nella tabella fare clic sull'account utente da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="be117-113">In the table, click the user account that you want to remove.</span></span>

6.  <span data-ttu-id="be117-114">Nel menu **Azione** selezionare **Rimuovi da Lync Server**. Verrà visualizzata una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="be117-114">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7.  <span data-ttu-id="be117-115">Dalla finestra di dialogo selezionare **OK** per rimuovere l'utente.</span><span class="sxs-lookup"><span data-stu-id="be117-115">From the dialog box, select **OK** to remove the user.</span></span>

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="be117-116">Rimozione degli account utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="be117-116">Removing User Accounts by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="be117-117">È possibile rimuovere gli account utente utilizzando il cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="be117-117">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="be117-118">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be117-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="be117-119">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="be117-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-user-account"></a><span data-ttu-id="be117-120">Per rimuovere un account utente</span><span class="sxs-lookup"><span data-stu-id="be117-120">To remove a user account</span></span>

  - <span data-ttu-id="be117-p104">Per rimuovere un account utente, usare il cmdlet Disable-CsUser. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="be117-p104">To remove a user account, use the Disable-CsUser cmdlet. For example:</span></span>
    
        Disable-CsUser -Identity "Ken Myer"
    
    <span data-ttu-id="be117-p105">Dopo aver eseguito questo comando, non sarà più possibile riabilitare l'account e le relative impostazioni precedenti. Sarà invece necessario usare il cmdlet Enable-CsUser per creare un account completamente nuovo per Davide Garghentini.</span><span class="sxs-lookup"><span data-stu-id="be117-p105">After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.</span></span>

</div>

<span data-ttu-id="be117-125">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="be117-125">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="be117-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be117-126">See Also</span></span>


[<span data-ttu-id="be117-127">Disabilitare o riabilitare l'account utente per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be117-127">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="be117-128">Abilitazione e disabilitazione degli utenti per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be117-128">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

