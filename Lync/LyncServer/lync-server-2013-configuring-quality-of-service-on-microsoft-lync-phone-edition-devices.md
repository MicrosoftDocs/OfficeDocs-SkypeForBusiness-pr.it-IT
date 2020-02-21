---
title: Configurazione della qualità del servizio nei dispositivi Microsoft Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e154df7c71b32e9f5f1c1440707511bc91c3117
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a><span data-ttu-id="483f9-102">Configurazione della qualità del servizio nei dispositivi Microsoft Lync Phone Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="483f9-102">Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="483f9-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="483f9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="483f9-104">Anche se la qualità del servizio (QoS) non è abilitata per impostazione predefinita per i dispositivi come iPhone, QoS è abilitata per impostazione predefinita per i dispositivi che eseguono Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="483f9-104">Although Quality of Service (QoS) is not enabled by default for devices such as iPhones, QoS is enabled by default for devices running Lync Phone Edition.</span></span> <span data-ttu-id="483f9-105">Questi dispositivi sono comunemente denominati telefoni di comunicazione unificati o UC. Per verificarlo, eseguire il comando di Windows PowerShell seguente dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="483f9-105">(These devices are commonly referred to as UC or Unified Communication phones.) To verify this, run the following Windows PowerShell command from within the Lync Server Management Shell:</span></span>

    Get-CsUCPhoneConfiguration

<span data-ttu-id="483f9-106">Se non sono state apportate modifiche alle impostazioni di configurazione dei telefoni UC, verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="483f9-106">If you have not made any changes to your UC phone configuration settings then you will get back information that looks like this:</span></span>

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

<span data-ttu-id="483f9-107">Per motivi di qualità del servizio, è interessante solo una delle proprietà seguenti: VoiceDiffServTag.</span><span class="sxs-lookup"><span data-stu-id="483f9-107">For Quality of Service purposes, only one of these properties is of interest: VoiceDiffServTag.</span></span> <span data-ttu-id="483f9-108">VoiceDiffServTag rappresenta il valore DSCP assegnato al traffico vocale proveniente da un dispositivo Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="483f9-108">The VoiceDiffServTag represents the DSCP value assigned to voice traffic emanating from a Lync Phone Edition device.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="483f9-109">Il parametro Voice8021p non è più supportato in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="483f9-109">The Voice8021p parameter is no longer supported in Lync Server 2013.</span></span> <span data-ttu-id="483f9-110">Il parametro è ancora valido per la compatibilità con le versioni precedenti di Microsoft Lync Server 2010; Tuttavia, non ha alcun effetto sui dispositivi utilizzati con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="483f9-110">The parameter is still valid for backward compatibility with Microsoft Lync Server 2010; however, it has no effect on devices used with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="483f9-111">Nella maggior parte delle reti, la marcatura dei pacchetti di Lync Phone Edition con una VoiceDiffServTag di 40 non deve causare problemi.</span><span class="sxs-lookup"><span data-stu-id="483f9-111">In most networks, marking Lync Phone Edition packets with a VoiceDiffServTag of 40 should not cause any problems.</span></span> <span data-ttu-id="483f9-112">40 non è tuttavia il valore utilizzato comunemente per il traffico audio, che invece è quasi sempre contrassegnato con il codice DSCP 46.</span><span class="sxs-lookup"><span data-stu-id="483f9-112">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="483f9-113">Per mantenere la coerenza all'interno della rete, è possibile modificare la proprietà VoiceDiffServTag dei telefoni UC impostandola su 46.</span><span class="sxs-lookup"><span data-stu-id="483f9-113">In order to maintain consistency throughout your network, you might want to change the VoiceDiffServTag property of your UC phones to 46.</span></span>

<span data-ttu-id="483f9-114">A tale scopo, è possibile utilizzare Windows PowerShell o il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="483f9-114">To do that, you can use either Windows PowerShell or the Lync Server Control Panel.</span></span> <span data-ttu-id="483f9-115">Per modificare il valore VoiceDiffServTag tramite Windows PowerShell, eseguire il comando riportato di seguito dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="483f9-115">To modify the VoiceDiffServTag value by using Windows PowerShell, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="483f9-p106">Il comando precedente modifica la raccolta globale delle impostazioni di configurazione dei telefoni UC. Tali impostazioni possono tuttavia essere assegnate anche all'ambito del sito. Per modificare le impostazioni di configurazione dei telefoni UC nell'ambito del sito, è necessario specificare l'identità (Identity) del sito. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="483f9-p106">The preceding command modifies the global collection of UC phone configuration settings. Note, however, that UC phone settings can also be assigned to the site scope. To modify UC phone configuration settings at the site scope, you must specify the site Identity. For example:</span></span>

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

<span data-ttu-id="483f9-120">È inoltre possibile utilizzare il comando seguente per modificare contemporaneamente tutte le impostazioni di configurazione dei telefoni UC:</span><span class="sxs-lookup"><span data-stu-id="483f9-120">You can also use the following command to simultaneously modify all your UC phone configuration settings:</span></span>

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="483f9-121">Se si preferisce apportare questa modifica utilizzando il pannello di controllo di Lync Server, avviare il pannello di controllo e quindi completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="483f9-121">If you prefer to make this change using Lync Server Control Panel, then start the Control Panel and then complete the following procedure:</span></span>

1.  <span data-ttu-id="483f9-122">Fare clic su **Client** e quindi su **Configurazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="483f9-122">Click **Clients** and then click **Device Configuration**.</span></span>

2.  <span data-ttu-id="483f9-123">Nella scheda **Configurazione dispositivo** fare doppio clic sulla raccolta di impostazioni che si desidera modificare, ad esempio **Globale**.</span><span class="sxs-lookup"><span data-stu-id="483f9-123">On the **Device Configuration** tab, double-click the collection of settings you want to modify (for example, **Global**).</span></span>

3.  <span data-ttu-id="483f9-124">Nella finestra di dialogo **Modifica configurazione dispositivo** impostare il valore della casella **Qualità vocale servizio (QoS)** su **46** e quindi fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="483f9-124">In the **Edit Device Configuration** dialog box, set the value of the **Voice Quality of Service (QoS)** box to **46** and then click **Commit**.</span></span>

<span data-ttu-id="483f9-125">Se si dispone di più raccolte, sarà necessario ripetere questo processo per ogni raccolta di impostazioni per i telefoni UC.</span><span class="sxs-lookup"><span data-stu-id="483f9-125">If you have multiple collections you will need to repeat this process for each collection of UC phone settings.</span></span> <span data-ttu-id="483f9-126">Il pannello di controllo di Lync Server non consentirà di modificare contemporaneamente più insiemi di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="483f9-126">Lync Server Control Panel will not allow you to simultaneously modify multiple setting collections.</span></span>

<span data-ttu-id="483f9-p108">Se si dispone di dispositivi non basati sul sistema operativo Windows, come nel caso di iPhone, nell'organizzazione la modifica dell'impostazione VoiceDiffServTag non inciderà su questi dispositivi. Se si desidera modificare i valori DSCP su tali dispositivi, sarà necessario fare riferimento al manuale dell'amministratore per ogni tipo di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="483f9-p108">If you have devices that are not based on the Windows operating system (such as iPhones) in your organization these devices will not be affected by changing the VoiceDiffServTag setting. If you want to change DSCP values on those devices you will need to refer to the administration manual for each of your device types.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

