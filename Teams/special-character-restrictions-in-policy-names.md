---
title: Quali sono le restrizioni dei caratteri speciali nei criteri di Teams?
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
description: Informazioni sui problemi relativi ai caratteri speciali nei nomi dei criteri e sulle operazioni che è possibile eseguire per risolvere il problema.
ms.openlocfilehash: 4116f34c06667a3bd4e75f9a5541b23c8ea79dcb
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837926"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="034a6-103">Quali sono le restrizioni dei caratteri speciali nei criteri di Teams?</span><span class="sxs-lookup"><span data-stu-id="034a6-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="034a6-104">**Non è possibile creare o modificare criteri (per la messaggistica, le riunioni e così via) che hanno un carattere speciale nel nome nell'interfaccia di amministrazione di Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="034a6-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="034a6-105">Se il nome di un criterio contiene caratteri speciali, sarà limitato a gestire questi criteri nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="034a6-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="034a6-106">**Di conseguenza, consigliamo vivamente che i nomi dei criteri non includano caratteri speciali**.</span><span class="sxs-lookup"><span data-stu-id="034a6-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="034a6-107">I nomi dei criteri creati con PowerShell per le riunioni e la messaggistica in team possono avere caratteri speciali, ad esempio @, #, $.</span><span class="sxs-lookup"><span data-stu-id="034a6-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="034a6-108">Tuttavia, se si vuole apportare modifiche ai criteri nell'interfaccia di amministrazione di Microsoft teams, non sarà possibile.</span><span class="sxs-lookup"><span data-stu-id="034a6-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="034a6-109">Se si dispone di un criterio con caratteri speciali, sarà necessario modificare i criteri usando Windows PowerShell (per sempre) o creare un nuovo criterio nell'interfaccia di amministrazione di Microsoft teams con le stesse impostazioni dei vecchi criteri e assegnarlo allo stesso gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="034a6-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="034a6-110">Per rimuovere caratteri speciali</span><span class="sxs-lookup"><span data-stu-id="034a6-110">To remove special characters</span></span>

<span data-ttu-id="034a6-111">**Passaggio 1: creare una connessione remota con PowerShell.** 
Se non è ancora stato [configurato, configurare il computer per Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) .</span><span class="sxs-lookup"><span data-stu-id="034a6-111">**Step 1 - Make a remote connection with PowerShell.**
[Set up your computer for Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) if you haven't yet.</span></span>
```PowerShell
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="034a6-112">**Passaggio 2: ottenere le impostazioni per i vecchi criteri e acquisire l'output.**</span><span class="sxs-lookup"><span data-stu-id="034a6-112">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="034a6-113">Questo esempio è per i criteri di [messaggistica](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="034a6-113">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="034a6-114">La procedura è la stessa per altri tipi di criteri, ma è necessario usare il cmdlet corretto.</span><span class="sxs-lookup"><span data-stu-id="034a6-114">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="034a6-115">**Passaggio 3: creare un nuovo criterio.**</span><span class="sxs-lookup"><span data-stu-id="034a6-115">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="034a6-116">Puoi creare il nuovo criterio con la stessa impostazione usando l'interfaccia di amministrazione di Microsoft teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="034a6-116">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="034a6-117">In questo modo verrà creato un nuovo criterio, ma sarà necessario aggiungere le impostazioni corrette visualizzando [set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) e quindi eseguendolo:</span><span class="sxs-lookup"><span data-stu-id="034a6-117">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="034a6-118">**Passaggio 4: assegnare il criterio.**</span><span class="sxs-lookup"><span data-stu-id="034a6-118">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="034a6-119">Per altre informazioni su questo cmdlet, vedere [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="034a6-119">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="034a6-120">**Passaggio 5-eliminare i vecchi criteri.**</span><span class="sxs-lookup"><span data-stu-id="034a6-120">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="034a6-121">Questo eliminerà il vecchio criterio con i caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="034a6-121">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="034a6-122">Per altre informazioni su questo cmdlet, vedere [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="034a6-122">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="034a6-123">Se il comando ha esito positivo, l'operazione è completata.</span><span class="sxs-lookup"><span data-stu-id="034a6-123">If this command succeeds, you're done.</span></span> <span data-ttu-id="034a6-124">Se il comando precedente restituisce un errore, è perché il criterio precedente viene assegnato agli utenti, quindi è necessario eseguire per rimuovere tutti gli utenti assegnati dal criterio:</span><span class="sxs-lookup"><span data-stu-id="034a6-124">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="034a6-125">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="034a6-125">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="034a6-p105">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="034a6-p105">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="034a6-129">Perché è necessario usare Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="034a6-129">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="034a6-130">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="034a6-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="034a6-131">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo con l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="034a6-131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="034a6-132">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="034a6-132">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="034a6-133">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="034a6-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="034a6-134">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="034a6-134">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="034a6-135">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="034a6-135">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="034a6-136">Il modulo di Windows PowerShell per Skype for business online consente di creare una sessione remota di Windows PowerShell che si connette a Skype for business online e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="034a6-136">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="034a6-137">Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="034a6-137">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

