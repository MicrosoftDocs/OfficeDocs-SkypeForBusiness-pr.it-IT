---
title: Creare impostazioni di configurazione delle riunioni in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Riepilogo: informazioni su come creare le impostazioni di configurazione delle riunioni in Skype for Business Server.'
ms.openlocfilehash: 3d4f986b850b309d50967da9126b8b4eea08a166
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194481"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="768dc-103">Creare impostazioni di configurazione delle riunioni in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="768dc-103">Create meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="768dc-104">**Riepilogo:** Informazioni su come creare le impostazioni di configurazione delle riunioni in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="768dc-104">**Summary:** Learn how to create meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="768dc-105">Puoi creare le impostazioni di configurazione delle riunioni usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="768dc-105">You can create meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="768dc-106">Creare impostazioni di configurazione delle riunioni tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="768dc-106">Create meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="768dc-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="768dc-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="768dc-108">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="768dc-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="768dc-109">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **Configurazione riunione**.</span><span class="sxs-lookup"><span data-stu-id="768dc-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="768dc-110">Nella pagina **Configurazione riunione** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="768dc-110">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
    - <span data-ttu-id="768dc-111">Per creare un criterio a livello di sito, fare clic su **configurazione sito**.</span><span class="sxs-lookup"><span data-stu-id="768dc-111">To create a site-level policy, click **Site configuration**.</span></span> <span data-ttu-id="768dc-112">Nel campo **Seleziona ricerca sito** digitare tutto o parte del nome del sito per il quale si desidera definire le impostazioni di partecipazione alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="768dc-112">In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings.</span></span> <span data-ttu-id="768dc-113">Nell'elenco dei siti risultante fare clic sul sito desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="768dc-113">In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
    - <span data-ttu-id="768dc-114">Per creare criteri a livello di pool, fare clic su **Configurazione pool**.</span><span class="sxs-lookup"><span data-stu-id="768dc-114">To create a pool-level policy, click **Pool configuration**.</span></span> <span data-ttu-id="768dc-115">Nel campo **selezionare un servizio** di ricerca digitare tutto o parte del nome del servizio pool per cui si desidera definire le impostazioni di partecipazione alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="768dc-115">In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings.</span></span> <span data-ttu-id="768dc-116">Nell'elenco dei servizi risultante fare clic sul pool desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="768dc-116">In the resulting list of services, click the pool you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="768dc-117">Per instradare i partecipanti che effettuano la chiamata tramite la rete PSTN (Public Switched Telephone Network) nella sala di attesa, deselezionare la casella di controllo **Ignora chiamate PSTN** .</span><span class="sxs-lookup"><span data-stu-id="768dc-117">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box.</span></span> <span data-ttu-id="768dc-118">Per impostazione predefinita, i partecipanti che effettuano la chiamata dalla rete PSTN accedono direttamente alla riunione.</span><span class="sxs-lookup"><span data-stu-id="768dc-118">By default, participants dialing in from the PSTN go directly to the meeting.</span></span>
    
6. <span data-ttu-id="768dc-119">Per configurare chi può essere un relatore nella riunione, in **designa come**relatore eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="768dc-119">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
   - <span data-ttu-id="768dc-120">Per non consentire a utenti diversi dall'organizzatore di essere relatori, fare clic su **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="768dc-120">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
   - <span data-ttu-id="768dc-121">Per consentire solo ai partecipanti membri dell'organizzazione di essere relatori, fare clic su **società**.</span><span class="sxs-lookup"><span data-stu-id="768dc-121">To allow only participants who are members of your organization to be a presenter, click **Company**.</span></span> <span data-ttu-id="768dc-122">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="768dc-122">This is the default setting.</span></span>
    
   - <span data-ttu-id="768dc-123">Per consentire a tutti i partecipanti di essere un relatore, fare clic su **tutti**.</span><span class="sxs-lookup"><span data-stu-id="768dc-123">To allow any participants to be a presenter, click **Everyone**.</span></span>
    
7. <span data-ttu-id="768dc-124">Per fare in modo che l'organizzatore selezioni un tipo di conferenza durante la programmazione di una riunione, deselezionare la casella **di controllo tipo di conferenza assegnata per impostazione predefinita** .</span><span class="sxs-lookup"><span data-stu-id="768dc-124">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box.</span></span> <span data-ttu-id="768dc-125">Per impostazione predefinita, il tipo di conferenza viene assegnato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="768dc-125">By default, the conference type is automatically assigned.</span></span>
    
8. <span data-ttu-id="768dc-126">Per impedire l'ammissione automatica degli utenti anonimi (non autenticati), deselezionare la casella **di controllo Ammetti gli utenti anonimi per impostazione predefinita** .</span><span class="sxs-lookup"><span data-stu-id="768dc-126">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box.</span></span> <span data-ttu-id="768dc-127">Per impostazione predefinita, gli utenti anonimi vengono ammessi automaticamente alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="768dc-127">By default, anonymous users are automatically admitted to meetings.</span></span>
    
9. <span data-ttu-id="768dc-128">Per personalizzare l'invito alla riunione inviato ai partecipanti, eseguire le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="768dc-128">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="768dc-129">Tieni presente che la lunghezza massima per gli URL e il testo del piè di pagina personalizzato è 1KB.</span><span class="sxs-lookup"><span data-stu-id="768dc-129">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="768dc-130">Ad eccezione dell' **URL della Guida**, se non si specifica un valore per le personalizzazioni, questi non verranno inclusi nella riunione.</span><span class="sxs-lookup"><span data-stu-id="768dc-130">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="768dc-131">Se non si include un URL della Guida personalizzato, l'URL della Guida predefinito per Skype for business verrà visualizzato nell'invito.</span><span class="sxs-lookup"><span data-stu-id="768dc-131">If you do not include a custom help URL, the default help URL for Skype for Business will be displayed in the invite.</span></span> 
    
   - <span data-ttu-id="768dc-132">Per personalizzare il logo visualizzato nell'invito alla riunione, in **URL logo**immettere la posizione del logo.</span><span class="sxs-lookup"><span data-stu-id="768dc-132">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span> <span data-ttu-id="768dc-133">Il logo deve essere un'immagine GIF o JPG con una dimensione di 188 di 30 pixel.</span><span class="sxs-lookup"><span data-stu-id="768dc-133">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span> 
    
   - <span data-ttu-id="768dc-134">Per personalizzare il testo della Guida visualizzato nell'invito alla riunione, in **URL della Guida**immettere la posizione del testo della guida.</span><span class="sxs-lookup"><span data-stu-id="768dc-134">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
   - <span data-ttu-id="768dc-135">Per personalizzare il testo legale visualizzato nell'invito alla riunione, in **URL di testo legale**immettere la posizione del testo legale.</span><span class="sxs-lookup"><span data-stu-id="768dc-135">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
   - <span data-ttu-id="768dc-136">Per personalizzare il testo del piè di pagina visualizzato nell'invito alla riunione, nel **testo del piè**di pagina personalizzato immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="768dc-136">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>
    
10. <span data-ttu-id="768dc-137">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="768dc-137">Click **Commit**.</span></span>
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="768dc-138">Creare impostazioni di configurazione delle riunioni con Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="768dc-138">Create meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="768dc-139">Per creare le impostazioni di configurazione della riunione, usare il cmdlet **New-CsMeetingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="768dc-139">To create meeting configuration settings, use the **New-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="768dc-140">Il comando seguente crea un nuovo set di impostazioni di configurazione delle riunioni per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="768dc-140">The following command creates a new set of meeting configuration settings for the Redmond site:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="768dc-141">Poiché non sono stati specificati parametri (ad eccezione del parametro di identità obbligatorio) nel comando precedente, le nuove impostazioni di configurazione della riunione utilizzeranno i valori predefiniti per tutte le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="768dc-141">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>
  
<span data-ttu-id="768dc-142">Per creare impostazioni che usano valori di proprietà diversi, includere semplicemente il parametro e il valore del parametro appropriati.</span><span class="sxs-lookup"><span data-stu-id="768dc-142">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="768dc-143">Ad esempio, per creare una raccolta di impostazioni di configurazione della riunione che, per impostazione predefinita, ammettono tutti a una riunione come relatore usare un comando come questo:</span><span class="sxs-lookup"><span data-stu-id="768dc-143">For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="768dc-144">Più valori di proprietà possono essere impostati includendo più parametri.</span><span class="sxs-lookup"><span data-stu-id="768dc-144">Multiple property values can be set by including multiple parameters.</span></span> <span data-ttu-id="768dc-145">Ad esempio, il comando seguente ammette tutti i partecipanti a una riunione come relatore e costringe anche gli utenti PSTN ad attendere nella sala di attesa finché non vengono formalmente ammessi alla riunione:</span><span class="sxs-lookup"><span data-stu-id="768dc-145">For example, the following command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

<span data-ttu-id="768dc-146">Per altre informazioni, incluso un elenco completo dei parametri, vedere [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="768dc-146">For more information, including a complete list of parameters, see [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span></span>
  

