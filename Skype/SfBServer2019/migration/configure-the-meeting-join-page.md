---
title: Configurare la pagina di partecipazione alle riunioni
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva quale client è già installato nel computer dell'utente. In caso affermativo, il client viene aperto e accede alla riunione. Se non è installato un client, per impostazione predefinita viene aperta l'app Web.
ms.openlocfilehash: a7bb0983438708bbc0d30cd527eb494491c3cbf2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754026"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="f860f-105">Configurare la pagina di partecipazione alle riunioni</span><span class="sxs-lookup"><span data-stu-id="f860f-105">Configure the meeting join page</span></span>

<span data-ttu-id="f860f-106">Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva quale client è già installato nel computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f860f-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="f860f-107">In caso affermativo, il client viene aperto e accede alla riunione.</span><span class="sxs-lookup"><span data-stu-id="f860f-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="f860f-108">Se non è installato un client, per impostazione predefinita viene aperta l'app Web.</span><span class="sxs-lookup"><span data-stu-id="f860f-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="f860f-109">È possibile modificare il comportamento della pagina di partecipazione alle riunioni se si desidera consentire agli utenti di partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="f860f-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="f860f-110">Queste opzioni di configurazione sono state rimosse dal Pannello di controllo, ma è possibile configurarle utilizzando il cmdlet CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f860f-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="f860f-111">**Parametri di CsWebServiceConfiguration per la pagina di partecipazione alla riunione**</span><span class="sxs-lookup"><span data-stu-id="f860f-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="f860f-112">**Parametro di CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="f860f-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="f860f-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f860f-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f860f-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="f860f-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="f860f-115">Se impostato su True, gli utenti che aderiscono a una riunione utilizzando un'applicazione client diversa da Lync avranno la possibilità di partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="f860f-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="f860f-116">Il valore predefinito è False.</span><span class="sxs-lookup"><span data-stu-id="f860f-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="f860f-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="f860f-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="f860f-118">Se impostato su True, le opzioni alternative per partecipare a una conferenza online verranno automaticamente espanse e visualizzate agli utenti.</span><span class="sxs-lookup"><span data-stu-id="f860f-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="f860f-119">Se impostato su False (valore predefinito), queste opzioni saranno disponibili, ma l'utente dovrà visualizzare automaticamente l'elenco delle opzioni.</span><span class="sxs-lookup"><span data-stu-id="f860f-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="f860f-120">Per configurare la pagina di partecipazione alle riunioni tramite Skype for Business Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="f860f-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="f860f-121">Avviare Skype for Business Server 2019 Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Microsoft Skype for Business Server 2019** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="f860f-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f860f-122">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="f860f-122">Run the following cmdlet:</span></span> 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="f860f-123">Questo cmdlet restituisce le impostazioni di configurazione del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="f860f-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="f860f-124">Eseguire il comando seguente, con i parametri impostati su True o False, a seconda delle proprie preferenze (per informazioni dettagliate sui parametri per questo cmdlet, vedere la documentazione di [Skype for Business Server Management Shell):](../../SfbServer/manage/management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="f860f-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


