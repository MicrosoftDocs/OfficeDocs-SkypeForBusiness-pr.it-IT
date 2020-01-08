---
title: 'Lync Server 2013: Creare oggetti contatto per la messaggistica unificata di Exchange ospitata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53d5bdfe3b341f534a3e8066fe85be5e93b0a7f7
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40976606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="daeb6-102">Creare oggetti contatto per la messaggistica unificata di Exchange ospitata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="daeb6-102">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="daeb6-103">_**Argomento Ultima modifica:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="daeb6-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="daeb6-104">La procedura seguente illustra come creare oggetti contatto di operatore automatico (AA) o di accesso sottoscrittore per la messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="daeb6-104">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="daeb6-105">Per informazioni dettagliate, vedere [gestione degli oggetti contatto di Exchange ospitati in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="daeb6-105">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="daeb6-106">Per informazioni dettagliate sulla configurazione degli oggetti contatto, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="daeb6-106">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="daeb6-107">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="daeb6-107">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="daeb6-108">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="daeb6-108">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="daeb6-109">Prima che gli oggetti contatto di Lync Server 2013 possano essere abilitati per la messaggistica unificata di Exchange ospitata, è necessario distribuire un criterio di segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="daeb6-109">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="daeb6-110">Per informazioni dettagliate, vedere Criteri per la segreteria <A href="lync-server-2013-hosted-voice-mail-policies.md">telefonica ospitati in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="daeb6-110">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="daeb6-111">Per creare oggetti contatto AA o SA per la messaggistica unificata di Exchange ospitata</span><span class="sxs-lookup"><span data-stu-id="daeb6-111">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="daeb6-112">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="daeb6-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="daeb6-113">Eseguire il cmdlet New-CsExUmContact per creare qualsiasi oggetto contatto necessario per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="daeb6-113">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment.</span></span> <span data-ttu-id="daeb6-114">Ad esempio, Esegui le operazioni seguenti per creare un oggetto contatto AA e SA:</span><span class="sxs-lookup"><span data-stu-id="daeb6-114">For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="daeb6-115">In questi esempi vengono impostati i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="daeb6-115">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="daeb6-116">**SipAddress** specifica l'indirizzo SIP dell'oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="daeb6-116">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="daeb6-117">Deve essere un indirizzo che non è già stato usato per configurare un utente o un oggetto contatto in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="daeb6-117">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="daeb6-118">Questo valore deve essere nel formato "SIP:\<*SIP Address*\>", come illustrato negli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="daeb6-118">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="daeb6-119">**RegistrarPool** specifica il nome di dominio completo (FQDN) del pool in cui è in uso il servizio registrar.</span><span class="sxs-lookup"><span data-stu-id="daeb6-119">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="daeb6-120">Gli oggetti contatto di messaggistica unificata di Exchange non possono essere spostati nei pool che fanno parte delle distribuzioni di Lync Server 2013 prima di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="daeb6-120">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="daeb6-121">**Ou** specifica l'unità organizzativa Active Directory in cui verrà individuato l'oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="daeb6-121">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="daeb6-122">**DisplayNumber** specifica il numero di telefono dell'oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="daeb6-122">**DisplayNumber** specifies the telephone number of the contact object.</span></span> <span data-ttu-id="daeb6-123">Il numero di telefono per ogni oggetto contatto deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="daeb6-123">The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="daeb6-124">**AutoAttendant specifica se** l'oggetto contatto è un operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="daeb6-124">**AutoAttendant** specifies whether the Contact object is an Auto Attendant.</span></span> <span data-ttu-id="daeb6-125">Operatore automatico fornisce un set di richieste vocali che consentono ai chiamanti di spostarsi nel sistema telefonico e di raggiungere l'interlocutore che vuole contattare.</span><span class="sxs-lookup"><span data-stu-id="daeb6-125">Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact.</span></span> <span data-ttu-id="daeb6-126">Il valore **false** (impostazione predefinita) per questo parametro indica un oggetto contatto di accesso del Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="daeb6-126">A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

