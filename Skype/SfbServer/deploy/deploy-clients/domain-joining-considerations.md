---
title: Considerazioni sull'aggiunta al dominio di Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Leggere questo argomento per informazioni su come aggiungere un PC appliance skype room system al dominio.
ms.openlocfilehash: cf98f98a7294ead0920b3d6b07b00879cbfe15f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093570"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="0b027-103">Considerazioni sull'aggiunta al dominio di Skype Room System</span><span class="sxs-lookup"><span data-stu-id="0b027-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="0b027-104">Leggere questo argomento per informazioni su come aggiungere un PC appliance skype room system al dominio.</span><span class="sxs-lookup"><span data-stu-id="0b027-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="0b027-105">Considerazioni sull'unione del dominio</span><span class="sxs-lookup"><span data-stu-id="0b027-105">Domain joining considerations</span></span>

<span data-ttu-id="0b027-106">Puoi aggiungere il PC dell'appliance Skype Room System al dominio di Active Directory o lasciarlo in un gruppo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0b027-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="0b027-107">Prima di prendere questa decisione, considerare i punti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b027-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="0b027-108">L'aggiunta al PC dell'appliance Skype Room System consente di importare automaticamente la catena di certificati radice privata dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0b027-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="0b027-109">L'aggiunta al PC dell'appliance Skype Room System consente di concedere a utenti e gruppi di dominio diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="0b027-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="0b027-110">In questo modo, non sarà necessario ricordare la password dell'account amministratore a livello di computer locale.</span><span class="sxs-lookup"><span data-stu-id="0b027-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="0b027-111">Quando si aggiunge un PC dell'appliance di Sistema sala Skype al dominio, è necessario creare un'unità organizzativa separata, in modo da poter fornire esclusioni di oggetti Criteri di gruppo all'unità organizzativa in cui risiedono tutti gli oggetti computer del sistema Sala Skype.</span><span class="sxs-lookup"><span data-stu-id="0b027-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="0b027-112">Quando si esegue questa operazione, creare oggetti computer nell'unità organizzativa prima di aggiungere il PC dell'appliance Skype Room System al dominio.</span><span class="sxs-lookup"><span data-stu-id="0b027-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="0b027-113">Molte organizzazioni dispongono degli oggetti Criteri di gruppo seguenti, che influiscono sulle funzioni del PC dell'appliance Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="0b027-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="0b027-114">Assicurati di ignorare o bloccare l'ereditarietà di questi oggetti Criteri di gruppo nell'unità organizzativa Di sistema Sala Skype:</span><span class="sxs-lookup"><span data-stu-id="0b027-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="0b027-115">Timeout delle sessioni di accesso (blocco automatico)</span><span class="sxs-lookup"><span data-stu-id="0b027-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="0b027-116">Criteri correlati alla gestione del risparmio energia</span><span class="sxs-lookup"><span data-stu-id="0b027-116">Power management related policies</span></span>
    
  - <span data-ttu-id="0b027-117">Richiedere ulteriori passaggi di autenticazione</span><span class="sxs-lookup"><span data-stu-id="0b027-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="0b027-118">Negazione dell'accesso alle unità locali</span><span class="sxs-lookup"><span data-stu-id="0b027-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="0b027-119">Richiedere agli utenti connessioni di rete lente</span><span class="sxs-lookup"><span data-stu-id="0b027-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="0b027-120">Avviare un determinato programma all'accesso</span><span class="sxs-lookup"><span data-stu-id="0b027-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="0b027-121">Creare un altro account utente di dominio in tutti i computer aggiunti al dominio.</span><span class="sxs-lookup"><span data-stu-id="0b027-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="0b027-122">Push di Windows Update in Skype Room System</span><span class="sxs-lookup"><span data-stu-id="0b027-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="0b027-123">In alternativa, potresti decidere di lasciare il PC dell'appliance nel gruppo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0b027-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="0b027-124">Come per il client Desktop Skype for Business, è necessario importare manualmente la catena di certificati radice nel PC dell'appliance skype room system.</span><span class="sxs-lookup"><span data-stu-id="0b027-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="0b027-125">Non è necessario importare la catena di certificati radice se la distribuzione di Skype for Business usa un certificato pubblico (ad esempio, Entrust, VeriSign e così via).</span><span class="sxs-lookup"><span data-stu-id="0b027-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="0b027-126">Se si prevede di aggiungere i computer di Sistema sala Skype al dominio, per evitare di aggiungere inavvertitamente il computer di Sistema sala Skype a un'unità organizzativa non intenzionale, che potrebbe non essere libera dagli oggetti Criteri di gruppo, assicurarsi di aggiungere l'unità organizzativa corretta.</span><span class="sxs-lookup"><span data-stu-id="0b027-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="0b027-127">È possibile utilizzare il cmdlet seguente dal computer skype room system per partecipare all'unità organizzativa corretta e non riceve oggetti Criteri di gruppo che potrebbero bloccare la funzionalità LRS.</span><span class="sxs-lookup"><span data-stu-id="0b027-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="0b027-128">Contattare l'amministratore di sistema o il partner OEM per eseguire questo cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0b027-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="0b027-129">Anche se si crea un'unità organizzativa separata e si blocca l'ereditarietà, esistono alcuni criteri che potrebbero causare problemi a un livello superiore.</span><span class="sxs-lookup"><span data-stu-id="0b027-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="0b027-130">Un'impostazione di Criteri di gruppo con nessuna sostituzione supera un'unità organizzativa con un'impostazione Blocca ereditarietà dei criteri.</span><span class="sxs-lookup"><span data-stu-id="0b027-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="0b027-131">Per ulteriori informazioni, vedere l'articolo [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) nella documentazione relativa a Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="0b027-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="0b027-132">Potrebbero essere disponibili più approcci per risolvere questi problemi.</span><span class="sxs-lookup"><span data-stu-id="0b027-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="0b027-133">Si consiglia di consultare gli esperti di Active Directory per assicurarsi di avere a disposizione un'unità organizzativa con le impostazioni appropriate dell'oggetto Criteri di gruppo o almeno un'unità organizzativa in cui i criteri descritti in precedenza non esistono.</span><span class="sxs-lookup"><span data-stu-id="0b027-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="0b027-134">Si consiglia di abilitare la qualità del servizio (QoS) per i dispositivi Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="0b027-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b027-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b027-135">See also</span></span>
  
[<span data-ttu-id="0b027-136">Configurazione dispositivo: crearne una nuova o modificarne una esistente</span><span class="sxs-lookup"><span data-stu-id="0b027-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="0b027-137">Gestione della qualità del servizio</span><span class="sxs-lookup"><span data-stu-id="0b027-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)