---
title: Restrizioni per i caratteri speciali nei criteri di Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Informazioni sui problemi relativi ai caratteri speciali nei nomi dei criteri e sulle operazioni che è possibile eseguire per risolvere il problema.
ms.openlocfilehash: 899cffa45bc5ec7a36339e89e3cb97e35e6e4507
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814715"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="26c91-103">Quali sono le restrizioni dei caratteri speciali nei criteri di Teams?</span><span class="sxs-lookup"><span data-stu-id="26c91-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="26c91-104">**Non è possibile creare o modificare criteri (per la messaggistica, le riunioni e così via) che hanno un carattere speciale nel nome nell'interfaccia di amministrazione di Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="26c91-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="26c91-105">Se il nome di un criterio contiene caratteri speciali, sarà limitato a gestire questi criteri nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="26c91-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="26c91-106">**Di conseguenza, consigliamo vivamente che i nomi dei criteri non includano caratteri speciali**.</span><span class="sxs-lookup"><span data-stu-id="26c91-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="26c91-107">I nomi dei criteri creati con PowerShell per le riunioni e la messaggistica in team possono avere caratteri speciali, ad esempio @, #, $.</span><span class="sxs-lookup"><span data-stu-id="26c91-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="26c91-108">Tuttavia, se si vuole apportare modifiche ai criteri nell'interfaccia di amministrazione di Microsoft teams, non sarà possibile.</span><span class="sxs-lookup"><span data-stu-id="26c91-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="26c91-109">Se si dispone di un criterio con caratteri speciali, sarà necessario modificare i criteri usando Windows PowerShell (per sempre) o creare un nuovo criterio nell'interfaccia di amministrazione di Microsoft teams con le stesse impostazioni dei vecchi criteri e assegnarlo allo stesso gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="26c91-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="26c91-110">Per rimuovere caratteri speciali</span><span class="sxs-lookup"><span data-stu-id="26c91-110">To remove special characters</span></span>

<span data-ttu-id="26c91-111">**Passaggio 1: creare una connessione remota con PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="26c91-111">**Step 1 - Make a remote connection with PowerShell.**</span></span>
> [!NOTE]
> <span data-ttu-id="26c91-112">Skype for Business Online Connector fa attualmente parte del modulo di PowerShell più recente di teams.</span><span class="sxs-lookup"><span data-stu-id="26c91-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell Module.</span></span>
>
> <span data-ttu-id="26c91-113">Se si usa l'ultima [versione pubblica di PowerShell per Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/), non è necessario installare il connettore Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="26c91-113">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```PowerShell
 Import-Module -Name MicrosoftTeams
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="26c91-114">**Passaggio 2: ottenere le impostazioni per i vecchi criteri e acquisire l'output.**</span><span class="sxs-lookup"><span data-stu-id="26c91-114">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="26c91-115">Questo esempio è per i criteri di [messaggistica](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="26c91-115">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="26c91-116">La procedura è la stessa per altri tipi di criteri, ma è necessario usare il cmdlet corretto.</span><span class="sxs-lookup"><span data-stu-id="26c91-116">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="26c91-117">**Passaggio 3: creare un nuovo criterio.**</span><span class="sxs-lookup"><span data-stu-id="26c91-117">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="26c91-118">Puoi creare il nuovo criterio con la stessa impostazione usando l'interfaccia di amministrazione di Microsoft teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26c91-118">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="26c91-119">In questo modo verrà creato un nuovo criterio, ma sarà necessario aggiungere le impostazioni corrette visualizzando [set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) e quindi eseguendolo:</span><span class="sxs-lookup"><span data-stu-id="26c91-119">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="26c91-120">**Passaggio 4: assegnare il criterio.**</span><span class="sxs-lookup"><span data-stu-id="26c91-120">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="26c91-121">Per altre informazioni su questo cmdlet, vedere [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="26c91-121">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="26c91-122">**Passaggio 5-eliminare i vecchi criteri.**</span><span class="sxs-lookup"><span data-stu-id="26c91-122">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="26c91-123">Questo eliminerà il vecchio criterio con i caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="26c91-123">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="26c91-124">Per altre informazioni su questo cmdlet, vedere [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="26c91-124">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="26c91-125">Se il comando ha esito positivo, l'operazione è completata.</span><span class="sxs-lookup"><span data-stu-id="26c91-125">If this command succeeds, you're done.</span></span> <span data-ttu-id="26c91-126">Se il comando precedente restituisce un errore, è perché il criterio precedente viene assegnato agli utenti, quindi è necessario eseguire per rimuovere tutti gli utenti assegnati dal criterio:</span><span class="sxs-lookup"><span data-stu-id="26c91-126">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="26c91-127">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="26c91-127">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="26c91-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="26c91-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="26c91-129">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione in grado di semplificare il lavoro quotidiano quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="26c91-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="26c91-130">Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="26c91-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="26c91-131">Perché è necessario usare Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="26c91-131">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="26c91-132">Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="26c91-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="26c91-133">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo con l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="26c91-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="26c91-134">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="26c91-134">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="26c91-135">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="26c91-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="26c91-136">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="26c91-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="26c91-137">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="26c91-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="26c91-138">Il modulo di Windows PowerShell per Skype for business online consente di creare una sessione remota di Windows PowerShell che si connette a Skype for business online e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="26c91-138">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="26c91-139">Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="26c91-139">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

