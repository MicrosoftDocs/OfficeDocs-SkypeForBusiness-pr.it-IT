---
title: Considerazioni sull'aggiunta al dominio di Skype Room System
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: L'amministratore può scoprire come aggiungere un PC dell'appliance Skype Room System a un dominio Active Directory, insieme alle considerazioni per farlo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 806dcac8f73f555227c03f7612f30fe4a598812f
ms.sourcegitcommit: 2eaf80bca6dfad367283e57662d81a809c9437e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2021
ms.locfileid: "50997414"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="bbb0f-103">Considerazioni sull'aggiunta al dominio di Skype Room System</span><span class="sxs-lookup"><span data-stu-id="bbb0f-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="bbb0f-104">Leggi questo argomento per informazioni su come aggiungere un PC dell'appliance Skype Room System al tuo dominio.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="bbb0f-105">Considerazioni sull'aggiunta di domini</span><span class="sxs-lookup"><span data-stu-id="bbb0f-105">Domain joining considerations</span></span>

<span data-ttu-id="bbb0f-106">Puoi aggiungere il PC dell'appliance Skype Room System al dominio Active Directory o lasciarlo in un gruppo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="bbb0f-107">Prima di prendere questa decisione, considerare i punti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbb0f-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="bbb0f-108">L'aggiunta al PC dell'appliance Skype Room System consente di importare automaticamente la catena di certificati radice privata dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
- <span data-ttu-id="bbb0f-109">L'aggiunta a un dominio nel PC dell'appliance Skype Room System consente di concedere agli utenti e ai gruppi di dominio i diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="bbb0f-110">In questo modo, non sarà necessario ricordare la password dell'account di amministratore a livello di computer locale.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
- <span data-ttu-id="bbb0f-111">Quando si aggiunge un PC dell'appliance di Sistema sala Skype al dominio, è necessario creare un'unità organizzativa separata, in modo da poter fornire esclusioni di oggetti Criteri di gruppo all'unità organizzativa in cui si trovano tutti gli oggetti computer di Sistema sala Skype.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-111">When you join a Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="bbb0f-112">In questo caso, creare oggetti computer nell'unità organizzativa prima di aggiungere il PC dell'appliance Skype Room System al dominio.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
- <span data-ttu-id="bbb0f-113">Molte organizzazioni hanno i seguenti oggetti Criteri di gruppo, che influiscono sulle funzioni del PC dell'appliance Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="bbb0f-114">Assicurarsi di ignorare o bloccare l'ereditarietà di questi oggetti Criteri di gruppo nell'unità organizzativa Sistema sala Skype:</span><span class="sxs-lookup"><span data-stu-id="bbb0f-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span>

  - <span data-ttu-id="bbb0f-115">Timeout delle sessioni di accesso (blocco automatico)</span><span class="sxs-lookup"><span data-stu-id="bbb0f-115">Timeout of logon sessions (auto lockout)</span></span>
  - <span data-ttu-id="bbb0f-116">Criteri correlati alla gestione del risparmio energia</span><span class="sxs-lookup"><span data-stu-id="bbb0f-116">Policies related to power management</span></span>
  - <span data-ttu-id="bbb0f-117">Richiedere ulteriori passaggi di autenticazione</span><span class="sxs-lookup"><span data-stu-id="bbb0f-117">Requiring additional authentication steps</span></span>
  - <span data-ttu-id="bbb0f-118">Negazione dell'accesso alle unità locali</span><span class="sxs-lookup"><span data-stu-id="bbb0f-118">Denying access to local drives</span></span>
  - <span data-ttu-id="bbb0f-119">Richiesta di connessioni di rete lente agli utenti</span><span class="sxs-lookup"><span data-stu-id="bbb0f-119">Prompting users for slow network connections</span></span>
  - <span data-ttu-id="bbb0f-120">Avviare un determinato programma all'accesso</span><span class="sxs-lookup"><span data-stu-id="bbb0f-120">Start a certain program at logon</span></span>
  - <span data-ttu-id="bbb0f-121">Creare un altro account utente di dominio in tutti i computer aggiunti al dominio.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-121">Create another domain user account on all domain-joined machines.</span></span>
  - <span data-ttu-id="bbb0f-122">Push Windows Update to Skype Room System</span><span class="sxs-lookup"><span data-stu-id="bbb0f-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="bbb0f-123">In alternativa, è possibile decidere di lasciare il PC dell'appliance nel gruppo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="bbb0f-124">Come per il client desktop Microsoft Teams o Skype for Business, è necessario importare manualmente la catena di certificati radice nel PC dell'appliance Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="bbb0f-125">Non è necessario importare la catena di certificati radice se la distribuzione usa un certificato pubblico, ad esempio Entrust, VeriSign e così via.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="bbb0f-126">Se si prevede di aggiungere computer skype room system al dominio, per evitare di aggiungersi inavvertitamente a un'unità organizzativa non intenzionale, che potrebbe non essere esente da oggetti Criteri di gruppo, assicurarsi di partecipare all'unità organizzativa corretta.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="bbb0f-127">È possibile usare il cmdlet seguente dal computer Skype Room System per partecipare all'unità organizzativa corretta e non riceve oggetti Criteri di gruppo che potrebbero bloccare la funzionalità LRS.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="bbb0f-128">Contattare l'amministratore di sistema o il partner OEM per eseguire questi cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bbb0f-128">Contact your system administrator or OEM partner to run these cmdlets:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="bbb0f-129">Anche se si crea un'unità organizzativa separata e si blocca l'ereditarietà, esistono alcuni criteri che potrebbero causare problemi a un livello superiore.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-129">Even if you create a separate OU and block inheritance, there are some policies that could cause issues at a higher level.</span></span> <span data-ttu-id="bbb0f-130">Un'impostazione di Criteri di gruppo senza override supera un'unità organizzativa con un'impostazione Blocca ereditarietà dei criteri.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="bbb0f-131">Per altre informazioni, vedere [Nessun override rispetto](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) al blocco dell'ereditarietà dei criteri nella documentazione di Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-131">For more information, see [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="bbb0f-132">Potrebbero essere disponibili più approcci per risolvere questi problemi.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="bbb0f-133">Si consiglia di consultare gli esperti di Active Directory per assicurarsi di avere a disposizione un'unità organizzativa con le impostazioni appropriate dell'oggetto Criteri di gruppo o almeno un'unità organizzativa in cui i criteri descritti in precedenza non esistono.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-133">We advise you to consult with your Active Directory experts to ensure that you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="bbb0f-134">Consigliamo di abilitare la qualità del servizio (QoS) per i dispositivi Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-134">We advise to enabling Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bbb0f-135">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bbb0f-135">Related topics</span></span>
  
[<span data-ttu-id="bbb0f-136">Configurazione dispositivo: crearne una nuova o modificarne una esistente</span><span class="sxs-lookup"><span data-stu-id="bbb0f-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="bbb0f-137">Gestione della qualità del servizio</span><span class="sxs-lookup"><span data-stu-id="bbb0f-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)
