---
title: 'Lync Server 2013: configurare le impostazioni di sicurezza per Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7bd44b5d3f466728ac1dbe928c08b1f4786f8fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="a690b-102">Configurare le impostazioni di sicurezza per Lync Phone Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a690b-102">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a690b-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a690b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a690b-104">Migliorare la sicurezza dei dispositivi in cui è in uso Lync Phone Edition tramite l'impostazione di sicurezza SIP e le impostazioni di blocco del telefono.</span><span class="sxs-lookup"><span data-stu-id="a690b-104">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="a690b-105">Per configurare le impostazioni di sicurezza per Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="a690b-105">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="a690b-106">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="a690b-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a690b-107">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a690b-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a690b-108">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a690b-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a690b-109">Sulla barra di spostamento sinistra fare clic su **client**e quindi su **Configurazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="a690b-109">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="a690b-110">Nell'elenco delle configurazioni dei dispositivi della pagina **Configurazione dispositivo** fare doppio clic sulla configurazione per la quale si desidera modificare le impostazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a690b-110">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="a690b-111">In **modifica configurazione dispositivo**, in **sicurezza SIP**, specificare il livello di sicurezza SIP.</span><span class="sxs-lookup"><span data-stu-id="a690b-111">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level.</span></span> <span data-ttu-id="a690b-112">Il livello predefinito è **High**, che consigliamo di usare.</span><span class="sxs-lookup"><span data-stu-id="a690b-112">The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="a690b-113">In **modifica configurazione dispositivo**, in **blocco telefono**Selezionare o deselezionare la casella di controllo **applica blocco dispositivo** (selezionata per impostazione predefinita) e specificare la lunghezza minima del PIN (6 caratteri per impostazione predefinita) e il periodo di timeout (10 minuti per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="a690b-113">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default).</span></span> <span data-ttu-id="a690b-114">È consigliabile usare questi valori predefiniti o aumentare la lunghezza del PIN e/o diminuire il periodo di timeout.</span><span class="sxs-lookup"><span data-stu-id="a690b-114">We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a690b-115">Per informazioni dettagliate, vedere <A href="lync-server-2013-enforce-phone-locking.md">applicare il blocco telefonico in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a690b-115">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a690b-116">Configurazione delle impostazioni di sicurezza per i telefoni Lync Phone Edition tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a690b-116">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a690b-117">Le impostazioni di sicurezza possono essere gestite tramite Lync Server Management Shell e il cmdlet **Get-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a690b-117">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="a690b-118">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a690b-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a690b-119">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="a690b-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="a690b-120">Per modificare la modalità di sicurezza SIP</span><span class="sxs-lookup"><span data-stu-id="a690b-120">To modify the SIP security mode</span></span>

  - <span data-ttu-id="a690b-121">Questo comando imposta il SIPSecurityMode per la raccolta globale delle impostazioni del telefono UC su media.</span><span class="sxs-lookup"><span data-stu-id="a690b-121">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium.</span></span> <span data-ttu-id="a690b-122">La sicurezza SIP può anche essere impostata su basso o alto (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="a690b-122">SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="a690b-123">Per modificare la lunghezza minima del PIN</span><span class="sxs-lookup"><span data-stu-id="a690b-123">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="a690b-124">In questo esempio tutte le impostazioni del telefono UC vengono modificate per richiedere una lunghezza minima di PIN di 7 cifre.</span><span class="sxs-lookup"><span data-stu-id="a690b-124">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="a690b-125">Per informazioni dettagliate, vedere [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="a690b-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a690b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a690b-126">See Also</span></span>


[<span data-ttu-id="a690b-127">Gestione dell'autenticazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a690b-127">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="a690b-128">Gestione di dispositivi, telefoni e applicazioni client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a690b-128">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

