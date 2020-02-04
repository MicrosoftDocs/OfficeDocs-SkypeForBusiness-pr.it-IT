---
title: 'Lync Server 2013: configurazione della posta in uscita della segreteria telefonica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c32d3bbc39d8f18e30153193c1e722db1ec9d50e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a><span data-ttu-id="787ab-102">Configurazione della posta in uscita della segreteria telefonica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="787ab-102">Configuring voice mail escape in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="787ab-103">_**Argomento Ultima modifica:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="787ab-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="787ab-104">Quando un utente configura lo squillo simultaneo su un telefono cellulare, il chiamante viene in genere instradato alla segreteria telefonica personale dell'utente se il telefono cellulare è disattivato, non è più alimentato dalla batteria o fuori portata.</span><span class="sxs-lookup"><span data-stu-id="787ab-104">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user’s personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="787ab-105">Con Lync Server 2013, gli utenti possono scegliere di avere le chiamate correlate alle aziende instradate al sistema di segreteria telefonica aziendale.</span><span class="sxs-lookup"><span data-stu-id="787ab-105">With Lync Server 2013, users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="787ab-106">In particolare, è possibile configurare un timer e, se la chiamata viene risolta dalla segreteria telefonica del vettore entro l'intervallo di tempo definito, Lync Server si disconnette dal sistema di segreteria telefonica del gestore (e dalla segreteria telefonica personale dell'utente), mentre l'utente rimane gli endpoint nel sistema aziendale continuano a squillare.</span><span class="sxs-lookup"><span data-stu-id="787ab-106">Specifically, a timer can be configured, and if the call is answered by the carrier’s voice mail within the range of time defined, Lync Server will disconnect from the carrier’s voice mail system (and the user’s personal voice mail), while the user’s remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="787ab-107">In questo modo, il chiamante viene indirizzato automaticamente alla segreteria telefonica aziendale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="787ab-107">This way, the caller is automatically routed to the user’s corporate voice mail.</span></span>

<span data-ttu-id="787ab-108">Questa configurazione viene eseguita usando il cmdlet Lync Server Management Shell, **Set-CsVoicePolicy**, a livello di criteri vocali, con i parametri seguenti.</span><span class="sxs-lookup"><span data-stu-id="787ab-108">This configuration is performed using the Lync Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

<div>

## <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="787ab-109">Per configurare l'escape della segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="787ab-109">To configure voice mail escape</span></span>

1.  <span data-ttu-id="787ab-110">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="787ab-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="787ab-111">Specificare i parametri seguenti per **Set-CsVoicePolicy**:</span><span class="sxs-lookup"><span data-stu-id="787ab-111">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>
    
      - <span data-ttu-id="787ab-112">**EnableVoicemailEscapeTimer** -Abilita o Disabilita il timer di escape.</span><span class="sxs-lookup"><span data-stu-id="787ab-112">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>
    
      - <span data-ttu-id="787ab-113">**PSTNVoicemailEscapeTimer** -specifica il valore di timeout in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="787ab-113">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds.</span></span> <span data-ttu-id="787ab-114">Il valore predefinito è 1500 millisecondi e il valore può variare da 0 millisecondi a 8000 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="787ab-114">The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="787ab-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="787ab-115">Example</span></span>

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="787ab-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="787ab-116">See Also</span></span>


[<span data-ttu-id="787ab-117">Configurazione di criteri vocali e record utilizzo PSTN per autorizzare privilegi e funzionalità di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="787ab-117">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

