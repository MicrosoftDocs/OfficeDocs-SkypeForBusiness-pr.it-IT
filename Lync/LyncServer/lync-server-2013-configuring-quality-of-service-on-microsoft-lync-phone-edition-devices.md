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
ms.openlocfilehash: aa8068b69afa3e02a5634041c61be6f7711e8f30
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a><span data-ttu-id="7570e-102">Configurazione della qualità del servizio nei dispositivi Microsoft Lync Phone Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7570e-102">Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7570e-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7570e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7570e-104">Sebbene la qualità del servizio (QoS) non sia abilitata per impostazione predefinita per i dispositivi come gli iPhone, QoS è abilitata per impostazione predefinita per i dispositivi in cui è in uso Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="7570e-104">Although Quality of Service (QoS) is not enabled by default for devices such as iPhones, QoS is enabled by default for devices running Lync Phone Edition.</span></span> <span data-ttu-id="7570e-105">Questi dispositivi sono comunemente definiti telefoni UC o Unified Communication. Per verificare questo, eseguire il comando di Windows PowerShell seguente dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="7570e-105">(These devices are commonly referred to as UC or Unified Communication phones.) To verify this, run the following Windows PowerShell command from within the Lync Server Management Shell:</span></span>

    Get-CsUCPhoneConfiguration

<span data-ttu-id="7570e-106">Se non sono state apportate modifiche alle impostazioni di configurazione del telefono UC, verranno restituite le informazioni che hanno un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7570e-106">If you have not made any changes to your UC phone configuration settings then you will get back information that looks like this:</span></span>

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

<span data-ttu-id="7570e-107">Per la qualità dei servizi, è interessante solo una di queste proprietà: VoiceDiffServTag.</span><span class="sxs-lookup"><span data-stu-id="7570e-107">For Quality of Service purposes, only one of these properties is of interest: VoiceDiffServTag.</span></span> <span data-ttu-id="7570e-108">VoiceDiffServTag rappresenta il valore DSCP assegnato al traffico vocale proveniente da un dispositivo Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="7570e-108">The VoiceDiffServTag represents the DSCP value assigned to voice traffic emanating from a Lync Phone Edition device.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7570e-109">Il parametro Voice8021p non è più supportato in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7570e-109">The Voice8021p parameter is no longer supported in Lync Server 2013.</span></span> <span data-ttu-id="7570e-110">Il parametro è ancora valido per la compatibilità con le versioni precedenti di Microsoft Lync Server 2010; Tuttavia, non ha alcun effetto sui dispositivi usati con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7570e-110">The parameter is still valid for backward compatibility with Microsoft Lync Server 2010; however, it has no effect on devices used with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="7570e-111">Nella maggior parte delle reti, la marcatura dei pacchetti di Lync Phone Edition con una VoiceDiffServTag di 40 non deve causare problemi.</span><span class="sxs-lookup"><span data-stu-id="7570e-111">In most networks, marking Lync Phone Edition packets with a VoiceDiffServTag of 40 should not cause any problems.</span></span> <span data-ttu-id="7570e-112">Tuttavia 40 non è il valore normalmente usato per il traffico audio, che in genere è contrassegnato dal codice DSCP 46.</span><span class="sxs-lookup"><span data-stu-id="7570e-112">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="7570e-113">Per mantenere la coerenza in tutta la rete, è consigliabile modificare la proprietà VoiceDiffServTag dei telefoni UC in 46.</span><span class="sxs-lookup"><span data-stu-id="7570e-113">In order to maintain consistency throughout your network, you might want to change the VoiceDiffServTag property of your UC phones to 46.</span></span>

<span data-ttu-id="7570e-114">A questo scopo, puoi usare Windows PowerShell o il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7570e-114">To do that, you can use either Windows PowerShell or the Lync Server Control Panel.</span></span> <span data-ttu-id="7570e-115">Per modificare il valore di VoiceDiffServTag con Windows PowerShell, eseguire il comando seguente da Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="7570e-115">To modify the VoiceDiffServTag value by using Windows PowerShell, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="7570e-116">Il comando precedente modifica la raccolta globale delle impostazioni di configurazione del telefono UC.</span><span class="sxs-lookup"><span data-stu-id="7570e-116">The preceding command modifies the global collection of UC phone configuration settings.</span></span> <span data-ttu-id="7570e-117">Tieni presente, tuttavia, che le impostazioni del telefono UC possono essere assegnate anche all'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="7570e-117">Note, however, that UC phone settings can also be assigned to the site scope.</span></span> <span data-ttu-id="7570e-118">Per modificare le impostazioni di configurazione del telefono UC nell'ambito del sito, è necessario specificare l'identità del sito.</span><span class="sxs-lookup"><span data-stu-id="7570e-118">To modify UC phone configuration settings at the site scope, you must specify the site Identity.</span></span> <span data-ttu-id="7570e-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7570e-119">For example:</span></span>

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

<span data-ttu-id="7570e-120">È anche possibile usare il comando seguente per modificare contemporaneamente tutte le impostazioni di configurazione del telefono UC:</span><span class="sxs-lookup"><span data-stu-id="7570e-120">You can also use the following command to simultaneously modify all your UC phone configuration settings:</span></span>

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="7570e-121">Se si preferisce apportare questa modifica usando il pannello di controllo di Lync Server, avviare il pannello di controllo e quindi completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="7570e-121">If you prefer to make this change using Lync Server Control Panel, then start the Control Panel and then complete the following procedure:</span></span>

1.  <span data-ttu-id="7570e-122">Fare clic su **client** e quindi su **Configurazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="7570e-122">Click **Clients** and then click **Device Configuration**.</span></span>

2.  <span data-ttu-id="7570e-123">Nella scheda **Configurazione dispositivo** fare doppio clic sulla raccolta di impostazioni che si desidera modificare, ad esempio **globale**.</span><span class="sxs-lookup"><span data-stu-id="7570e-123">On the **Device Configuration** tab, double-click the collection of settings you want to modify (for example, **Global**).</span></span>

3.  <span data-ttu-id="7570e-124">Nella finestra di dialogo **modifica configurazione dispositivo** impostare il valore della casella **qualità vocale del servizio (QoS)** su **46** e quindi fare clic su **commit**.</span><span class="sxs-lookup"><span data-stu-id="7570e-124">In the **Edit Device Configuration** dialog box, set the value of the **Voice Quality of Service (QoS)** box to **46** and then click **Commit**.</span></span>

<span data-ttu-id="7570e-125">Se si hanno più raccolte, sarà necessario ripetere questa procedura per ogni raccolta di impostazioni del telefono UC.</span><span class="sxs-lookup"><span data-stu-id="7570e-125">If you have multiple collections you will need to repeat this process for each collection of UC phone settings.</span></span> <span data-ttu-id="7570e-126">Il pannello di controllo di Lync Server non consente di modificare contemporaneamente più insiemi di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="7570e-126">Lync Server Control Panel will not allow you to simultaneously modify multiple setting collections.</span></span>

<span data-ttu-id="7570e-127">Se si hanno dispositivi che non sono basati sul sistema operativo Windows (ad esempio iPhone) nell'organizzazione, questi dispositivi non saranno interessati modificando l'impostazione VoiceDiffServTag.</span><span class="sxs-lookup"><span data-stu-id="7570e-127">If you have devices that are not based on the Windows operating system (such as iPhones) in your organization these devices will not be affected by changing the VoiceDiffServTag setting.</span></span> <span data-ttu-id="7570e-128">Se si vogliono modificare i valori di DSCP in questi dispositivi, è necessario fare riferimento al manuale di amministrazione per ogni tipo di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7570e-128">If you want to change DSCP values on those devices you will need to refer to the administration manual for each of your device types.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

