---
title: Eliminare una raccolta esistente di impostazioni di configurazione di Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2be234fdbb2beb9d2f6f038acbdad03dd8d2048
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="56f26-102">Eliminare una raccolta esistente di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56f26-102">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56f26-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="56f26-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="56f26-104">Se non si vuole più usare una raccolta di impostazioni per i dispositivi che usano Lync Phone Edition, eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="56f26-104">If you no longer want to use a collection of settings for devices running Lync Phone Edition, delete it.</span></span> <span data-ttu-id="56f26-105">Se si elimina una raccolta per un sito, le impostazioni globali verranno applicate ai telefoni in tale sito.</span><span class="sxs-lookup"><span data-stu-id="56f26-105">If you delete a collection for a site, the global settings will apply to the phones in that site.</span></span> <span data-ttu-id="56f26-106">Non è possibile eliminare la raccolta globale.</span><span class="sxs-lookup"><span data-stu-id="56f26-106">You cannot delete the global collection.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="56f26-107">Invece di eliminare una raccolta, potresti voler solo modificare alcune delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="56f26-107">Instead of deleting a collection, you might just want to change some of the settings.</span></span> <span data-ttu-id="56f26-108">Per informazioni dettagliate su come eseguire questa operazione, vedere <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">creare o modificare una raccolta di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="56f26-108">For details about how to do so, see <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="56f26-109">Per eliminare una raccolta di impostazioni di configurazione di Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="56f26-109">To delete a collection of Lync Phone Edition configuration settings</span></span>

1.  <span data-ttu-id="56f26-110">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="56f26-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="56f26-111">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56f26-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="56f26-112">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="56f26-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="56f26-113">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento della **configurazione del dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="56f26-113">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="56f26-114">Nella pagina **Configurazione dispositivo** fare clic sulla raccolta che si vuole eliminare, fare clic sul menu **modifica** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="56f26-114">On the **Device Configuration** page, click the collection you want to delete, click the **Edit** menu, and then click **Delete**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="56f26-115">Se elimini la raccolta globale, le impostazioni vengono ripristinate solo alle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="56f26-115">If you delete the global collection, the settings just revert to the default settings.</span></span> <span data-ttu-id="56f26-116">La raccolta non scompare.</span><span class="sxs-lookup"><span data-stu-id="56f26-116">The collection does not go away.</span></span>

    
    </div>

5.  <span data-ttu-id="56f26-117">Nella casella di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="56f26-117">In the confirmation box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="56f26-118">Rimozione delle impostazioni di configurazione di Lync Phone Edition con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="56f26-118">Removing Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="56f26-119">Per eliminare le impostazioni di configurazione di Lync Phone Edition, è possibile usare Windows PowerShell e il cmdlet **Remove-CsUCConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="56f26-119">You can delete Lync Phone Edition configuration settings by using Windows PowerShell and the **Remove-CsUCConfiguration** cmdlet.</span></span> <span data-ttu-id="56f26-120">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56f26-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="56f26-121">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="56f26-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="56f26-122">Per rimuovere una raccolta specificata di impostazioni di configurazione di Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="56f26-122">To remove a specified collection of Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="56f26-123">Questo comando Elimina le impostazioni di configurazione del telefono UC applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="56f26-123">This command deletes the UC phone configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="56f26-124">Per rimuovere tutte le impostazioni di configurazione di Lync Phone Edition applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="56f26-124">To remove all of the Lync Phone Edition configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="56f26-125">Questo comando rimuove tutte le impostazioni di configurazione del telefono UC applicate all'ambito del servizio:</span><span class="sxs-lookup"><span data-stu-id="56f26-125">This command removes all the UC phone configuration settings applied to the service scope:</span></span>
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a><span data-ttu-id="56f26-126">Per rimuovere tutte le impostazioni di configurazione di Lync Phone Edition in cui il blocco del telefono è disabilitato</span><span class="sxs-lookup"><span data-stu-id="56f26-126">To remove all of the Lync Phone Edition configuration settings where phone locking is disabled</span></span>

  - <span data-ttu-id="56f26-127">Questo comando Elimina qualsiasi raccolta di impostazioni di configurazione del telefono UC in cui è stato disabilitato il blocco del telefono:</span><span class="sxs-lookup"><span data-stu-id="56f26-127">This command deletes any collection of UC phone configuration settings where phone locking has been disabled:</span></span>
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

<span data-ttu-id="56f26-128">Per informazioni dettagliate, vedere [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15)).</span><span class="sxs-lookup"><span data-stu-id="56f26-128">For details, see [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15)).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

