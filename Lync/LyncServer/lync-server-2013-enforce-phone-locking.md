---
title: 'Lync Server 2013: applicare il blocco del telefono'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8473809982a58ccc966482cd72223e0b234dd9ec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a><span data-ttu-id="4d030-102">Applicare il blocco del telefono in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d030-102">Enforce phone locking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d030-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4d030-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4d030-104">I dispositivi Lync Phone Edition possono essere bloccati per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4d030-104">Lync Phone Edition devices can be locked for security purposes.</span></span> <span data-ttu-id="4d030-105">Se si applica il blocco del telefono, il dispositivo che esegue Lync Phone Edition si blocca dopo un periodo di tempo configurabile.</span><span class="sxs-lookup"><span data-stu-id="4d030-105">If you enforce phone lock, the device running Lync Phone Edition locks after a period of time that you configure.</span></span> <span data-ttu-id="4d030-106">Quando un telefono è bloccato, un utente può effettuare chiamate ma non può accedere alle informazioni su calendario e contatti, alla segreteria telefonica o ai registri di chiamata oppure utilizza la funzionalità di ricerca.</span><span class="sxs-lookup"><span data-stu-id="4d030-106">When a phone is locked, a user can make calls but cannot access calendar and contact information, voice mail, or call logs or use search.</span></span> <span data-ttu-id="4d030-107">Per sbloccare il telefono, l'utente immette un PIN.</span><span class="sxs-lookup"><span data-stu-id="4d030-107">To unlock the phone, the user enters a PIN.</span></span>

<span data-ttu-id="4d030-108">Per applicare il blocco del telefono, abilitarlo e configurarlo utilizzando il pannello di controllo di Lync Server o i cmdlet di PowerShell di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d030-108">To enforce phone lock, enable and configure it by using Lync Server Control Panel or Lync Server PowerShell cmdlets.</span></span> <span data-ttu-id="4d030-109">È possibile applicare il blocco del telefono a livello globale o solo all'interno del sito per il quale è configurato.</span><span class="sxs-lookup"><span data-stu-id="4d030-109">You can enforce phone lock globally or only within the site for which it is configured.</span></span>

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a><span data-ttu-id="4d030-110">Per configurare e applicare il blocco del telefono</span><span class="sxs-lookup"><span data-stu-id="4d030-110">To configure and enforce the phone lock</span></span>

1.  <span data-ttu-id="4d030-111">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4d030-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d030-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d030-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4d030-113">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4d030-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4d030-114">Fare clic su **Client** e quindi su **Configurazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="4d030-114">Click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="4d030-115">Nell'elenco delle configurazioni dei dispositivi nella scheda **Configurazione dispositivo** fare doppio clic sulla configurazione per cui si desidera modificare le impostazioni di blocco del telefono.</span><span class="sxs-lookup"><span data-stu-id="4d030-115">On the **Device Configuration** tab, in the list of device configurations, double-click the configuration for which you want to change the phone lock settings.</span></span>

5.  <span data-ttu-id="4d030-116">Nella finestra di dialogo **Modifica configurazione dispositivo** verificare che la casella di controllo **Applica blocco dispositivo** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="4d030-116">In the **Edit Device Configuration** dialog box, verify that the **Enforce device locking** check box is selected.</span></span>

6.  <span data-ttu-id="4d030-117">Nella **lunghezza minima del pin**, accettare il valore predefinito per il numero minimo di cifre che il pin di sblocco deve contenere oppure specificare un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="4d030-117">In **Minimum PIN length**, accept the default value for the minimum number of digits that the unlock PIN must contain or specify a new value.</span></span> <span data-ttu-id="4d030-118">L'intervallo per la lunghezza del PIN è compreso tra quattro e 15 cifre e il valore predefinito è sei.</span><span class="sxs-lookup"><span data-stu-id="4d030-118">The range for the PIN length is four to 15 digits, and the default is six.</span></span>

7.  <span data-ttu-id="4d030-119">Nel **timeout di blocco del telefono**, accettare il valore predefinito per il periodo di tempo minimo prima che il telefono si blocchi o specifichi un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="4d030-119">In **Phone lock time-out**, accept the default value for the minimum length of time before the phone locks itself or specify a new value.</span></span> <span data-ttu-id="4d030-120">L'intervallo per il timeout è compreso tra 0 e 60 minuti e il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="4d030-120">The range for the timeout is 0 to 60 minutes, and the default is 10.</span></span> <span data-ttu-id="4d030-121">Immettere il valore nel formato HH: MM: SS.</span><span class="sxs-lookup"><span data-stu-id="4d030-121">Enter the value in the format HH:MM:SS.</span></span>

8.  <span data-ttu-id="4d030-122">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4d030-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4d030-123">Applicazione del blocco del telefono tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d030-123">Enforcing Phone Locking by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4d030-124">È possibile applicare il blocco del telefono utilizzando il cmdlet Set-CsUCPhoneConfiguration.</span><span class="sxs-lookup"><span data-stu-id="4d030-124">Phone locking can be enforced by using the Set-CsUCPhoneConfiguration cmdlet.</span></span> <span data-ttu-id="4d030-125">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d030-125">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4d030-126">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="4d030-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-phone-locking"></a><span data-ttu-id="4d030-127">Per abilitare il blocco del telefono</span><span class="sxs-lookup"><span data-stu-id="4d030-127">To enable phone locking</span></span>

  - <span data-ttu-id="4d030-128">Il comando seguente attiva il blocco telefono per il sito di Redmond.</span><span class="sxs-lookup"><span data-stu-id="4d030-128">The following command enables phone locking for the Redmond site.</span></span> <span data-ttu-id="4d030-129">Per disattivare il blocco telefono, impostare la proprietà EnforcePhoneLock su False ($False).</span><span class="sxs-lookup"><span data-stu-id="4d030-129">To disable phone locking, set the EnforcePhoneLock property to False ($False).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a><span data-ttu-id="4d030-130">Per abilitare il blocco del telefono e modificare il timeout di blocco del telefono</span><span class="sxs-lookup"><span data-stu-id="4d030-130">To enable phone locking and modify the phone lock timeout</span></span>

  - <span data-ttu-id="4d030-131">Questo comando attiva il blocco telefono e imposta il relativo timeout su 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="4d030-131">This command enables phone locking and also sets the phone lock timeout to 30 minutes.</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a><span data-ttu-id="4d030-132">Per abilitare il blocco del telefono all'interno dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="4d030-132">To enable phone locking throughout the organization</span></span>

  - <span data-ttu-id="4d030-133">In questo esempio il blocco telefono viene attivato su tutte le impostazioni di configurazione dei telefoni UC in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d030-133">In this example, phone locking is enabled on all the UC phone configuration settings in use in the organization.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

<span data-ttu-id="4d030-134">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="4d030-134">For more information, see the help topic for the [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d030-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d030-135">See Also</span></span>


[<span data-ttu-id="4d030-136">Gestione dell'autenticazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d030-136">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="4d030-137">Gestione di dispositivi, telefoni e applicazioni client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d030-137">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

