---
title: Configurare la pagina di partecipazione alla riunione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva quale client è già installato nel computer dell'utente. Se un client è già installato, tale client si apre e si unisce alla riunione. Se un client non è installato, per impostazione predefinita viene aperto l'app Web.
ms.openlocfilehash: c5f6cd5b1d04b54f8db9f82080bc8dbabefdc11e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195018"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="eeff8-105">Configurare la pagina di partecipazione alla riunione</span><span class="sxs-lookup"><span data-stu-id="eeff8-105">Configure the meeting join page</span></span>

<span data-ttu-id="eeff8-106">Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva quale client è già installato nel computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="eeff8-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="eeff8-107">Se un client è già installato, tale client si apre e si unisce alla riunione.</span><span class="sxs-lookup"><span data-stu-id="eeff8-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="eeff8-108">Se un client non è installato, per impostazione predefinita viene aperto l'app Web.</span><span class="sxs-lookup"><span data-stu-id="eeff8-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="eeff8-109">È possibile modificare il comportamento della pagina di partecipazione alla riunione se si vuole consentire agli utenti di partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="eeff8-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="eeff8-110">Queste opzioni di configurazione sono state rimosse dal pannello di controllo, ma le configuri usando il cmdlet CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="eeff8-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="eeff8-111">**Parametri di CsWebServiceConfiguration pagina di join della riunione**</span><span class="sxs-lookup"><span data-stu-id="eeff8-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="eeff8-112">**Parametro CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="eeff8-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="eeff8-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="eeff8-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="eeff8-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="eeff8-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="eeff8-115">Se impostato su true, gli utenti che partecipano a una riunione usando un'applicazione client diversa da Lync avranno la possibilità di partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="eeff8-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="eeff8-116">Il valore predefinito è False.</span><span class="sxs-lookup"><span data-stu-id="eeff8-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="eeff8-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="eeff8-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="eeff8-118">Quando è impostato su true, le opzioni alternative per partecipare a una conferenza online verranno espanse e visualizzate automaticamente agli utenti.</span><span class="sxs-lookup"><span data-stu-id="eeff8-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="eeff8-119">Se impostato su false (il valore predefinito), queste opzioni saranno disponibili, ma l'utente dovrà visualizzare l'elenco di opzioni.</span><span class="sxs-lookup"><span data-stu-id="eeff8-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="eeff8-120">Per configurare la pagina di partecipazione alla riunione usando Skype for Business Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="eeff8-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="eeff8-121">Avviare Skype for Business Server 2019 Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft Skype for Business Server 2019**e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="eeff8-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="eeff8-122">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="eeff8-122">Run the following cmdlet:</span></span> 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="eeff8-123">Questo cmdlet restituisce le impostazioni di configurazione del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="eeff8-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="eeff8-124">Eseguire il comando seguente, con i parametri impostati su true o false, a seconda delle preferenze (per informazioni dettagliate sui parametri per questo cmdlet, vedere la documentazione di [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) ):</span><span class="sxs-lookup"><span data-stu-id="eeff8-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


