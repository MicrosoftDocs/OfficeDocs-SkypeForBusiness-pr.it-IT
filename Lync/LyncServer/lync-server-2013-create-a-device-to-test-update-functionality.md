---
title: 'Lync Server 2013: creare un dispositivo per testare la funzionalità di aggiornamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad2fa5283561e1096cfe7e3053db59c3cd2e40e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a><span data-ttu-id="4e63a-102">Creare un dispositivo per testare la funzionalità di aggiornamento in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e63a-102">Create a device to test update functionality in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e63a-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4e63a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4e63a-104">È possibile aggiungere un dispositivo di test nella pagina **Dispositivo di test** e quindi usare il dispositivo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione.</span><span class="sxs-lookup"><span data-stu-id="4e63a-104">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="4e63a-105">È possibile testare un dispositivo a livello globale (nell'intero ambiente Lync Server) o all'interno di un singolo sito.</span><span class="sxs-lookup"><span data-stu-id="4e63a-105">You can test a device globally (throughout your entire Lync Server environment) or within a single site.</span></span> <span data-ttu-id="4e63a-106">Per identificare un dispositivo di test, usare il relativo indirizzo MAC (Media Access Control) o il numero di serie.</span><span class="sxs-lookup"><span data-stu-id="4e63a-106">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="4e63a-107">Quando si aggiunge un dispositivo, questo viene visualizzato nell'elenco nella pagina del **dispositivo di test** del pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4e63a-107">When you add a device, it appears in the list on the **Test Device** page of the Lync Server Control Panel.</span></span>

<div>

## <a name="to-add-a-test-device"></a><span data-ttu-id="4e63a-108">Per aggiungere un dispositivo di test</span><span class="sxs-lookup"><span data-stu-id="4e63a-108">To add a test device</span></span>

1.  <span data-ttu-id="4e63a-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4e63a-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4e63a-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4e63a-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="4e63a-111">Sulla barra di spostamento sinistra fare clic su **client**e quindi su **Test Device**.</span><span class="sxs-lookup"><span data-stu-id="4e63a-111">In the left navigation bar, click **Clients**, and then click **Test Device**.</span></span>

3.  <span data-ttu-id="4e63a-112">Fare clic su **nuovo**e quindi su dispositivo **test globale** o **dispositivo test sito**.</span><span class="sxs-lookup"><span data-stu-id="4e63a-112">Click **New**, and then click either **Global test device** or **Site test device**.</span></span>

4.  <span data-ttu-id="4e63a-113">Esegui una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e63a-113">Do one of the following:</span></span>
    
      - <span data-ttu-id="4e63a-114">Se si è selezionato **dispositivo test globale**, passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="4e63a-114">If you clicked **Global test device**, skip to the next step.</span></span>
    
      - <span data-ttu-id="4e63a-115">Se si è scelto il **dispositivo di test del sito**, selezionare un sito nell'elenco dei siti disponibili e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e63a-115">If you clicked **Site test device**, select a site from the list of available sites, and then click **OK**.</span></span>

5.  <span data-ttu-id="4e63a-116">In **nuovo dispositivo di test**Digitare un nome per il dispositivo in **nome dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="4e63a-116">In **New Test Device**, type a name for the device in **Device name**.</span></span>

6.  <span data-ttu-id="4e63a-117">In **tipo identificatore**fare clic su **indirizzo Mac** o **numero seriale**.</span><span class="sxs-lookup"><span data-stu-id="4e63a-117">Under **Identifier type**, click either **MAC address** or **Serial number**.</span></span>

7.  <span data-ttu-id="4e63a-118">Nella casella **identificatore univoco** Digitare l'indirizzo Mac o il numero di serie del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4e63a-118">In the **Unique identifier** box, type the MAC address or serial number of the device.</span></span>

8.  <span data-ttu-id="4e63a-119">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4e63a-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4e63a-120">Creazione di dispositivi di test con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e63a-120">Creating Test Devices by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4e63a-121">I dispositivi di test possono essere creati usando Windows PowerShell e il cmdlet New-CsTestDevice.</span><span class="sxs-lookup"><span data-stu-id="4e63a-121">Test devices can be created by using Windows PowerShell and the New-CsTestDevice cmdlet.</span></span> <span data-ttu-id="4e63a-122">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e63a-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4e63a-123">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="4e63a-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="4e63a-124">Quando si creano dispositivi di test con questo cmdlet, è necessario eseguire due operazioni:</span><span class="sxs-lookup"><span data-stu-id="4e63a-124">When creating test devices using this cmdlet, you must do two things:</span></span>

  - <span data-ttu-id="4e63a-125">Specifica MACAddress o NumeroSerie come IdentifierType.</span><span class="sxs-lookup"><span data-stu-id="4e63a-125">Specify either MACAddress or SerialNumber as the IdentifierType.</span></span>

  - <span data-ttu-id="4e63a-126">Includere l'ambito quando si specifica l'identità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4e63a-126">Include the scope when specifying the device Identity.</span></span> <span data-ttu-id="4e63a-127">Per creare un nuovo dispositivo in ambito globale, usare una sintassi simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="4e63a-127">To create a new device at the global scope use syntax similar to this:</span></span>
    
        -Identity "global/WindowsPhone"
    
    <span data-ttu-id="4e63a-128">Per creare un dispositivo di test nell'ambito del sito, usare una sintassi simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="4e63a-128">To create a test device at the site scope use syntax similar to this:</span></span>
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a><span data-ttu-id="4e63a-129">Per creare un dispositivo di test usando l'indirizzo MAC</span><span class="sxs-lookup"><span data-stu-id="4e63a-129">To create a test device by using the MAC address</span></span>

  - <span data-ttu-id="4e63a-130">Questo comando crea un dispositivo di test nell'ambito globale e usa l'indirizzo MAC come IdentifierType:</span><span class="sxs-lookup"><span data-stu-id="4e63a-130">This command creates a test device at the global scope, and using the MAC address as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a><span data-ttu-id="4e63a-131">Per creare un dispositivo di test usando il numero seriale</span><span class="sxs-lookup"><span data-stu-id="4e63a-131">To create a test device by using the serial number</span></span>

  - <span data-ttu-id="4e63a-132">Questo comando crea un nuovo dispositivo di test nell'ambito del sito (per il sito Redmond) e usa il numero seriale come IdentifierType:</span><span class="sxs-lookup"><span data-stu-id="4e63a-132">This command creates a new test device at the site scope (for the Redmond site) and uses the serial number as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

<span data-ttu-id="4e63a-133">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .</span><span class="sxs-lookup"><span data-stu-id="4e63a-133">For more information, see the help topic for the [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

