---
title: 'Lync Server 2013: creare gli oggetti contatto per la messaggistica unificata di Exchange ospitata'
description: 'Lync Server 2013: creare gli oggetti contatto per la messaggistica unificata di Exchange ospitata.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9760e2a39b5182f9b5194e364e059bddc6a63d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562302"
---
# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="01bb0-103">Creare oggetti contatto per la messaggistica unificata di Exchange ospitata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01bb0-103">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01bb0-104">_**Ultimo argomento modificato:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="01bb0-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="01bb0-105">Nella procedura riportata di seguito viene illustrato come creare oggetti contatto Operatore automatico o Accesso sottoscrittore per la messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="01bb0-105">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="01bb0-106">Per ulteriori informazioni, vedere [gestione degli oggetti contatto di Exchange ospitati in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="01bb0-106">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="01bb0-107">Per informazioni dettagliate sulla configurazione degli oggetti contatto, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="01bb0-107">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="01bb0-108">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="01bb0-108">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="01bb0-109">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="01bb0-109">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="01bb0-110">Prima di poter abilitare gli oggetti contatto di Lync Server 2013 per la messaggistica unificata di Exchange ospitata, è necessario distribuire un criterio di segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="01bb0-110">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="01bb0-111">Per ulteriori informazioni, vedere <A href="lync-server-2013-hosted-voice-mail-policies.md">criteri di segreteria telefonica ospitata in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="01bb0-111">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="01bb0-112">Per creare oggetti contatto Operatore automatico o Accesso sottoscrittore per la messaggistica unificata di Exchange ospitata</span><span class="sxs-lookup"><span data-stu-id="01bb0-112">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="01bb0-113">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="01bb0-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="01bb0-p102">Eseguire il cmdlet New-CsExUmContact per creare gli oggetti contatto necessari per la distribuzione. Ad esempio, per creare un oggetto contatto Operatore automatico e un oggetto contatto Accesso sottoscrittore:</span><span class="sxs-lookup"><span data-stu-id="01bb0-p102">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment. For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="01bb0-116">In questi esempi vengono impostati i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="01bb0-116">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="01bb0-117">**SipAddress** specifica l'indirizzo SIP dell'oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="01bb0-117">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="01bb0-118">Deve corrispondere a un indirizzo non ancora utilizzato per la configurazione di un utente o di un oggetto contatto in Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="01bb0-118">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="01bb0-119">Questo valore deve essere nel formato "SIP: \<*SIP address*\> " come illustrato negli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="01bb0-119">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="01bb0-120">**RegistrarPool** specifica il nome di dominio completo (FQDN) del pool su cui è in esecuzione il servizio di registrazione.</span><span class="sxs-lookup"><span data-stu-id="01bb0-120">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="01bb0-121">Gli oggetti contatto di messaggistica unificata di Exchange non possono essere spostati nei pool che fanno parte delle distribuzioni di Lync Server 2013 precedenti a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="01bb0-121">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="01bb0-122">**OU** specifica l'unità organizzativa Active Directory in cui sarà situato l'oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="01bb0-122">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="01bb0-p104">**DisplayNumber** specifica il numero di telefono dell'oggetto contatto. Il numero di telefono deve essere univoco per ogni oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="01bb0-p104">**DisplayNumber** specifies the telephone number of the contact object. The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="01bb0-p105">**AutoAttendant** specifica se l'oggetto contatto è un operatore automatico. La funzionalità Operatore automatico mette a disposizione una serie di istruzioni vocali che consentono ai chiamanti di navigare nel sistema telefonico fino a raggiungere l'interlocutore desiderato. Per questo parametro il valore **$False** (predefinito) indica un oggetto contatto Accesso sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="01bb0-p105">**AutoAttendant** specifies whether the Contact object is an Auto Attendant. Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact. A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

