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
description: Leggi questo argomento per informazioni su come aggiungere un PC dell'appliance Skype Room System al dominio.
ms.openlocfilehash: 6d6decf689b1a38615851911b42676050a823e4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805916"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="181ea-103">Considerazioni sull'aggiunta al dominio di Skype Room System</span><span class="sxs-lookup"><span data-stu-id="181ea-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="181ea-104">Leggi questo argomento per informazioni su come aggiungere un PC dell'appliance Skype Room System al dominio.</span><span class="sxs-lookup"><span data-stu-id="181ea-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="181ea-105">Considerazioni sull'unione del dominio</span><span class="sxs-lookup"><span data-stu-id="181ea-105">Domain joining considerations</span></span>

<span data-ttu-id="181ea-106">È possibile aggiungere il PC dell'applicazione Skype Room System al dominio di Active Directory o lasciarlo in un gruppo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="181ea-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="181ea-107">Prima di prendere questa decisione, considerare i punti seguenti:</span><span class="sxs-lookup"><span data-stu-id="181ea-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="181ea-108">L'aggiunta al PC dell'appliance Skype Room System consente di importare automaticamente la catena di certificati radice privata dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="181ea-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="181ea-109">L'aggiunta al PC dell'appliance Skype Room System consente di concedere a utenti e gruppi di dominio diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="181ea-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="181ea-110">In questo modo, non sarà necessario ricordare la password dell'account amministratore a livello di computer locale.</span><span class="sxs-lookup"><span data-stu-id="181ea-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="181ea-111">Quando si aggiunge un PC dell'applicazione Skype Room System al dominio, è necessario creare un'unità organizzativa separata, in modo da poter fornire esclusioni di oggetti Criteri di gruppo all'unità organizzativa in cui risiedono tutti gli oggetti computer di Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="181ea-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="181ea-112">Quando si esegue questa operazione, creare oggetti computer nell'unità organizzativa prima di aggiungere il PC dell'appliance Skype Room System al dominio.</span><span class="sxs-lookup"><span data-stu-id="181ea-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="181ea-113">Molte organizzazioni hanno gli oggetti Criteri di gruppo seguenti, che influiscono sulle funzioni del PC dell'appliance Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="181ea-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="181ea-114">Assicurati di ignorare o bloccare l'ereditarietà di questi oggetti Criteri di gruppo nell'unità organizzativa Skype Room System:</span><span class="sxs-lookup"><span data-stu-id="181ea-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="181ea-115">Timeout delle sessioni di accesso (blocco automatico)</span><span class="sxs-lookup"><span data-stu-id="181ea-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="181ea-116">Criteri correlati alla gestione del risparmio energia</span><span class="sxs-lookup"><span data-stu-id="181ea-116">Power management related policies</span></span>
    
  - <span data-ttu-id="181ea-117">Richiesta di ulteriori passaggi di autenticazione</span><span class="sxs-lookup"><span data-stu-id="181ea-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="181ea-118">Negazione dell'accesso alle unità locali</span><span class="sxs-lookup"><span data-stu-id="181ea-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="181ea-119">Richiesta agli utenti di connessioni di rete lente</span><span class="sxs-lookup"><span data-stu-id="181ea-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="181ea-120">Avviare un determinato programma all'accesso</span><span class="sxs-lookup"><span data-stu-id="181ea-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="181ea-121">Creare un altro account utente di dominio in tutti i computer aggiunti al dominio.</span><span class="sxs-lookup"><span data-stu-id="181ea-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="181ea-122">Push di Windows Update nel sistema skype room</span><span class="sxs-lookup"><span data-stu-id="181ea-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="181ea-123">In alternativa, puoi decidere di lasciare il PC dell'applicazione nel gruppo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="181ea-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="181ea-124">Come per il client Desktop Skype for Business, è necessario importare manualmente la catena di certificati radice nel PC dell'appliance Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="181ea-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="181ea-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span><span class="sxs-lookup"><span data-stu-id="181ea-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="181ea-126">Se si prevede di aggiungere computer Skype Room System al dominio, per evitare di aggiungere inavvertitamente il computer Skype Room System a un'unità organizzativa non intenzionale, che potrebbe non essere libera dagli oggetti Criteri di gruppo, assicurarsi di aggiungere l'unità organizzativa corretta.</span><span class="sxs-lookup"><span data-stu-id="181ea-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="181ea-127">È possibile utilizzare il cmdlet seguente dal computer Skype Room System per partecipare all'unità organizzativa corretta e non riceve oggetti Criteri di gruppo che potrebbero bloccare la funzionalità LRS.</span><span class="sxs-lookup"><span data-stu-id="181ea-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="181ea-128">Contattare l'amministratore di sistema o il partner OEM per eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="181ea-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="181ea-129">Anche se si crea un'unità organizzativa separata e si blocca l'ereditarietà, esistono alcuni criteri che potrebbero causare problemi a un livello superiore.</span><span class="sxs-lookup"><span data-stu-id="181ea-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="181ea-130">Un'impostazione di Criteri di gruppo senza override supera un'unità organizzativa con un'impostazione Blocca ereditarietà dei criteri.</span><span class="sxs-lookup"><span data-stu-id="181ea-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="181ea-131">Per ulteriori informazioni, vedere l'articolo [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) nella documentazione relativa a Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="181ea-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="181ea-132">Potrebbero essere disponibili più approcci per risolvere questi problemi.</span><span class="sxs-lookup"><span data-stu-id="181ea-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="181ea-133">Ti consigliamo di consultare gli esperti di Active Directory per assicurarti di avere a disposizione un'unità organizzativa con le impostazioni appropriate dell'oggetto Criteri di gruppo o almeno un'unità organizzativa in cui non esistono i criteri descritti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="181ea-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="181ea-134">È consigliabile abilitare QoS (Quality of Service) per i dispositivi Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="181ea-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="181ea-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="181ea-135">See also</span></span>
  
[<span data-ttu-id="181ea-136">Configurazione dispositivo: crearne una nuova o modificarne una esistente</span><span class="sxs-lookup"><span data-stu-id="181ea-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="181ea-137">Gestione della qualità del servizio</span><span class="sxs-lookup"><span data-stu-id="181ea-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
