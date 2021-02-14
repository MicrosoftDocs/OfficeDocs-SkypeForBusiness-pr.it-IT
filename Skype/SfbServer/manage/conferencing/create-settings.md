---
title: Creare le impostazioni di configurazione delle riunioni in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Riepilogo: informazioni su come creare le impostazioni di configurazione delle riunioni in Skype for Business Server.'
ms.openlocfilehash: edc498ed3847618b17970fb2270c21fd3f4ec025
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828206"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="9d4ae-103">Creare le impostazioni di configurazione delle riunioni in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9d4ae-103">Create meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="9d4ae-104">**Riepilogo:** Informazioni su come creare le impostazioni di configurazione delle riunioni in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-104">**Summary:** Learn how to create meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="9d4ae-105">È possibile creare le impostazioni di configurazione delle riunioni utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-105">You can create meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9d4ae-106">Creare le impostazioni di configurazione delle riunioni utilizzando il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9d4ae-106">Create meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9d4ae-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="9d4ae-108">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9d4ae-109">Sulla barra di spostamento sinistra fare clic su Servizio **di** conferenza e quindi su **Configurazione riunione.**</span><span class="sxs-lookup"><span data-stu-id="9d4ae-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="9d4ae-110">Nella pagina **Configurazione riunione** fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d4ae-110">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
    - <span data-ttu-id="9d4ae-p101">Per creare un criterio a livello di sito, fare clic su **Configurazione sito**. Nel campo di ricerca **Seleziona un sito** digitare il nome del sito per cui si desidera definire le impostazioni di partecipazione alle riunioni, per intero o in parte. Fare clic sul sito desiderato nell'elenco dei siti e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-p101">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
    - <span data-ttu-id="9d4ae-p102">Per creare un criterio a livello di pool, fare clic su **Configurazione pool**. Nel campo di ricerca **Seleziona un servizio** digitare il nome del pool per cui si desidera definire le impostazioni di partecipazione alle riunioni, per intero o in parte. Fare clic su un pool desiderato nell'elenco di servizi e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-p102">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="9d4ae-p103">Per instradare i partecipanti che accedono dalla rete PSTN (Public Switched Telephone Network ) attraverso la sala di attesa, deselezionare la casella di controllo **I chiamanti PSTN ignorano la sala di attesa**. Per impostazione predefinita, i partecipanti che accedono dalla rete PSTN passano direttamente alla riunione.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-p103">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>
    
6. <span data-ttu-id="9d4ae-119">Per configurare l'utente che svolge la funzione di relatore nella riunione, in **Designa come relatore** effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d4ae-119">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
   - <span data-ttu-id="9d4ae-120">Per non consentire a persone diverse dall'organizzatore di svolgere la funzione di relatore, fare clic su **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-120">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
   - <span data-ttu-id="9d4ae-p104">Per consentire solo ai partecipanti membri dell'organizzazione di svolgere la funzione di relatore, fare clic su **Società**. Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-p104">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
   - <span data-ttu-id="9d4ae-123">Per consentire a qualsiasi partecipante di fungere da relatore, fare clic su **Tutti**.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-123">To allow any participants to be a presenter, click **Everyone**.</span></span>
    
7. <span data-ttu-id="9d4ae-p105">Per fare in modo che l'organizzatore selezioni il tipo di conferenza quando pianifica una riunione, deselezionare la casella di controllo **Tipo di conferenza assegnato per impostazione predefinita**. Per impostazione predefinita, il tipo di conferenza viene assegnato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-p105">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>
    
8. <span data-ttu-id="9d4ae-p106">Per impedire che gli utenti anonimi (non autenticati) vengano ammessi automaticamente, deselezionare la casella di controllo **Consenti utenti anonimi per impostazione predefinita**. Per impostazione predefinita, gli utenti anonimi vengono ammessi automaticamente alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-p106">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>
    
9. <span data-ttu-id="9d4ae-128">Per personalizzare l'invito alla riunione che viene inviato ai partecipanti, eseguire le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-128">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="9d4ae-129">Si noti che la dimensione massima degli URL e del testo del piè di pagina personalizzato è di 1 KB.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-129">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="9d4ae-130">Se non si specifica un valore per le personalizzazioni, queste non verranno incluse nella riunione, ad eccezione di **URL Guida**.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-130">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="9d4ae-131">Se non si include un URL della Guida personalizzato, l'URL della Guida predefinito per Skype for Business verrà visualizzato nell'invito.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-131">If you do not include a custom help URL, the default help URL for Skype for Business will be displayed in the invite.</span></span> 
    
   - <span data-ttu-id="9d4ae-132">Per personalizzare il logo che viene visualizzato nell'invito alla riunione, immettere il percorso del logo in **URL logo**.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-132">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span> <span data-ttu-id="9d4ae-133">Il logo deve essere un'immagine GIF o JPG con una dimensione di 188 per 30 pixel.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-133">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span> 
    
   - <span data-ttu-id="9d4ae-134">Per personalizzare il testo della Guida che viene visualizzato nell'invito alla riunione, immettere il percorso del testo della Guida in **URL Guida**.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-134">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
   - <span data-ttu-id="9d4ae-135">Per personalizzare il testo legale che viene visualizzato nell'invito alla riunione, immettere il percorso del testo legale in **URL testo legale**.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-135">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
   - <span data-ttu-id="9d4ae-136">Per personalizzare il testo del piè di pagina che viene visualizzato nell'invito alla riunione, immettere il testo in **Testo piè di pagina personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-136">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>
    
10. <span data-ttu-id="9d4ae-137">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-137">Click **Commit**.</span></span>
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="9d4ae-138">Creare le impostazioni di configurazione delle riunioni tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="9d4ae-138">Create meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="9d4ae-139">Per creare le impostazioni di configurazione delle riunioni, utilizzare il cmdlet **New-CsMeetingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="9d4ae-139">To create meeting configuration settings, use the **New-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="9d4ae-140">Il comando seguente crea un nuovo set di impostazioni di configurazione delle riunioni per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="9d4ae-140">The following command creates a new set of meeting configuration settings for the Redmond site:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="9d4ae-141">Poiché nel comando precedente non sono stati specificati parametri, eccetto il parametro obbligatorio Identity, le nuove impostazioni di configurazione di riunione utilizzeranno i valori predefiniti per le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-141">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>
  
<span data-ttu-id="9d4ae-p109">Per creare impostazioni basate su valori di proprietà diversi, è sufficiente includere il parametro appropriato e il valore corrispondente. Per creare ad esempio una raccolta di impostazioni di configurazione di riunione che per impostazione predefinita ammettono chiunque come relatore di una riunione, utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="9d4ae-p109">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="9d4ae-144">È possibile impostare più valori di proprietà includendo più parametri.</span><span class="sxs-lookup"><span data-stu-id="9d4ae-144">Multiple property values can be set by including multiple parameters.</span></span> <span data-ttu-id="9d4ae-145">Ad esempio, il comando seguente consente di ammettere tutti gli utenti a una riunione come relatori e di forzare anche gli utenti PSTN ad attendere nella sala di attesa fino a quando non vengono ammessi formalmente alla riunione:</span><span class="sxs-lookup"><span data-stu-id="9d4ae-145">For example, the following command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

<span data-ttu-id="9d4ae-146">Per ulteriori informazioni, incluso un elenco completo dei parametri, [vedere New-CsMeetingConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="9d4ae-146">For more information, including a complete list of parameters, see [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span></span>
  

