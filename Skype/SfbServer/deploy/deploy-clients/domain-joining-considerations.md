---
title: Considerazioni sulla partecipazione del dominio del sistema Skype room
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
description: Leggere questo argomento per informazioni su come aggiungere un PC accessorio del sistema Skype room al proprio dominio.
ms.openlocfilehash: 6d6decf689b1a38615851911b42676050a823e4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805916"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="43135-103">Considerazioni sulla partecipazione del dominio del sistema Skype room</span><span class="sxs-lookup"><span data-stu-id="43135-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="43135-104">Leggere questo argomento per informazioni su come aggiungere un PC accessorio del sistema Skype room al proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="43135-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="43135-105">Considerazioni sull'unione del dominio</span><span class="sxs-lookup"><span data-stu-id="43135-105">Domain joining considerations</span></span>

<span data-ttu-id="43135-106">È possibile aggiungere il PC del dispositivo del sistema Skype room al dominio di Active Directory o lasciarlo in un gruppo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="43135-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="43135-107">Prima di prendere questa decisione, prendere in considerazione i seguenti punti:</span><span class="sxs-lookup"><span data-stu-id="43135-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="43135-108">Domain-partecipazione il PC di Skype room System Appliance aiuta ad importare automaticamente la catena di certificati radice privata dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="43135-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="43135-109">Domain-partecipazione il PC di Skype room System Appliance consente di concedere a utenti e gruppi di dominio diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="43135-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="43135-110">In questo modo, non è necessario ricordare la password dell'account amministratore a livello di computer locale.</span><span class="sxs-lookup"><span data-stu-id="43135-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="43135-111">Quando si entra nel dominio in un PC appliance di Skype room System, è necessario creare un'unità organizzativa separata (OU), in modo che sia possibile fornire le esclusioni degli oggetti Criteri di gruppo all'unità organizzativa in cui risiedono tutte le strutture del computer del sistema di Skype room.</span><span class="sxs-lookup"><span data-stu-id="43135-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="43135-112">Quando si esegue questa operazione, creare oggetti Machine nell'unità organizzativa prima di unire il PC del dispositivo di sistema Skype room al dominio.</span><span class="sxs-lookup"><span data-stu-id="43135-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="43135-113">Molte organizzazioni dispongono degli oggetti Criteri di sistema seguenti, che influiscono sulle funzioni di Skype room System Appliance.</span><span class="sxs-lookup"><span data-stu-id="43135-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="43135-114">Assicurarsi di ignorare o bloccare l'ereditarietà di tali oggetti Criteri di gruppo nell'unità organizzativa di sistema di Skype room:</span><span class="sxs-lookup"><span data-stu-id="43135-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="43135-115">Timeout delle sessioni di accesso (blocco automatico)</span><span class="sxs-lookup"><span data-stu-id="43135-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="43135-116">Criteri correlati alla gestione dell'alimentazione</span><span class="sxs-lookup"><span data-stu-id="43135-116">Power management related policies</span></span>
    
  - <span data-ttu-id="43135-117">Richiedere ulteriori passaggi di autenticazione</span><span class="sxs-lookup"><span data-stu-id="43135-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="43135-118">Negare l'accesso alle unità locali</span><span class="sxs-lookup"><span data-stu-id="43135-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="43135-119">Suggerimento per gli utenti per le connessioni di rete lente</span><span class="sxs-lookup"><span data-stu-id="43135-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="43135-120">Avviare un determinato programma all'accesso</span><span class="sxs-lookup"><span data-stu-id="43135-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="43135-121">Creare un altro account utente di dominio in tutti i computer aggiunti a un dominio.</span><span class="sxs-lookup"><span data-stu-id="43135-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="43135-122">Push Windows Update to Skype room System</span><span class="sxs-lookup"><span data-stu-id="43135-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="43135-123">In alternativa, è possibile decidere di lasciare il PC del dispositivo nel gruppo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="43135-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="43135-124">Come nel caso del client Skype for business desktop, è necessario importare manualmente la catena di certificati radice sul PC di Skype room System Appliance.</span><span class="sxs-lookup"><span data-stu-id="43135-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="43135-125">Non è necessario importare la catena di certificati radice se la distribuzione di Skype for business utilizza un certificato pubblico (ad esempio, Entrust, VeriSign e così via).</span><span class="sxs-lookup"><span data-stu-id="43135-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="43135-126">[! Nota] Se si prevede di aderire al dominio ai computer della chat room Skype, per evitare che l'Unione di Skype room System involontariamente in un'unità organizzativa indesiderata, che potrebbe non essere libera dagli oggetti Criteri di rete, assicurarsi di partecipare all'unità organizzativa corretta.</span><span class="sxs-lookup"><span data-stu-id="43135-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="43135-127">È possibile utilizzare il cmdlet seguente dal computer del sistema di chat room Skype per partecipare all'unità organizzativa corretta e non ricevere gli oggetti Criteri di gruppo che potrebbero bloccare la funzionalità LRS.</span><span class="sxs-lookup"><span data-stu-id="43135-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="43135-128">Contattare l'amministratore di sistema o il partner OEM per eseguire questi cmdlet:</span><span class="sxs-lookup"><span data-stu-id="43135-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="43135-129">Anche se si crea un'unità organizzativa separata e si blocca l'ereditarietà, esistono alcuni criteri che potrebbero causare problemi a un livello superiore.</span><span class="sxs-lookup"><span data-stu-id="43135-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="43135-130">Un criterio di gruppo con nessuna impostazione di sostituzione batte un'unità organizzativa con un'impostazione di ereditarietà dei criteri di blocco.</span><span class="sxs-lookup"><span data-stu-id="43135-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="43135-131">Per ulteriori informazioni, vedere l'articolo [Nessuna sostituzione rispetto all'ereditarietà dei criteri di blocco](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) nella documentazione relativa ai criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="43135-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="43135-132">Per risolvere questi problemi, è possibile che si disponga di più approcci.</span><span class="sxs-lookup"><span data-stu-id="43135-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="43135-133">Si consiglia di consultare gli esperti di Active Directory per assicurarsi di disporre di un'unità organizzativa con impostazioni di criteri di gruppo appropriate o almeno di un'unità organizzativa in cui non esistano i criteri descritti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="43135-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="43135-134">Si consiglia di abilitare la qualità del servizio (QoS) per i dispositivi Skype room System.</span><span class="sxs-lookup"><span data-stu-id="43135-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="43135-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43135-135">See also</span></span>
  
[<span data-ttu-id="43135-136">Configurazione dispositivo: crearne una nuova o modificarne una esistente</span><span class="sxs-lookup"><span data-stu-id="43135-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="43135-137">Gestione della qualità del servizio</span><span class="sxs-lookup"><span data-stu-id="43135-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
