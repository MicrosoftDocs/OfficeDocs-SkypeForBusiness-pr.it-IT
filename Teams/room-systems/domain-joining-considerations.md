---
title: Considerazioni sull'Unione di domini di Skype room System
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Leggere questo argomento per informazioni su come partecipare a un PC appliance di sistema Skype room al proprio dominio.
ms.openlocfilehash: 8419ccc2234ec0c549dcd001dc95c3a4374f3720
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182479"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="df059-103">Considerazioni sull'Unione di domini di Skype room System</span><span class="sxs-lookup"><span data-stu-id="df059-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="df059-104">Leggere questo argomento per informazioni su come partecipare a un PC appliance di sistema Skype room al proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="df059-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="df059-105">Considerazioni sull'Unione di domini</span><span class="sxs-lookup"><span data-stu-id="df059-105">Domain joining considerations</span></span>

<span data-ttu-id="df059-106">È possibile partecipare al PC di Skype room System Appliance al dominio Active Directory o lasciarlo in un gruppo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="df059-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="df059-107">Prima di prendere questa decisione, prendere in considerazione i punti seguenti:</span><span class="sxs-lookup"><span data-stu-id="df059-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="df059-108">Domain-partecipare al PC di Skype room System Appliance aiuta ad importare automaticamente la catena di certificati radice privati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="df059-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="df059-109">Domain-Joining Skype room System Appliance PC consente di concedere a utenti e gruppi di domini i diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="df059-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="df059-110">In questo modo, non è necessario ricordare la password dell'account di amministratore del livello di computer locale.</span><span class="sxs-lookup"><span data-stu-id="df059-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="df059-111">Quando si partecipa a un PC Appliance Skype room System al dominio, è necessario creare un'unità organizzativa separata (OU), in modo da consentire l'esclusione degli oggetti Criteri di gruppo per l'unità organizzativa in cui risiedono tutte le applicazioni del computer room System Skype.</span><span class="sxs-lookup"><span data-stu-id="df059-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="df059-112">Quando si esegue questa operazione, creare oggetti macchina nell'unità organizzativa prima di partecipare al PC di Skype room System Appliance al dominio.</span><span class="sxs-lookup"><span data-stu-id="df059-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="df059-113">Molte organizzazioni hanno gli oggetti Criteri di rete seguenti, che influiscono sulle funzioni PC appliance di Skype room System.</span><span class="sxs-lookup"><span data-stu-id="df059-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="df059-114">Assicurarsi di ignorare o bloccare l'ereditarietà di questi oggetti Criteri di gruppo nell'OU di sistema di chat room di Skype:</span><span class="sxs-lookup"><span data-stu-id="df059-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="df059-115">Timeout delle sessioni di accesso (blocco automatico)</span><span class="sxs-lookup"><span data-stu-id="df059-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="df059-116">Criteri correlati a Power Management</span><span class="sxs-lookup"><span data-stu-id="df059-116">Power management related policies</span></span>
    
  - <span data-ttu-id="df059-117">Richiedere ulteriori passaggi di autenticazione</span><span class="sxs-lookup"><span data-stu-id="df059-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="df059-118">Negazione dell'accesso alle unità locali</span><span class="sxs-lookup"><span data-stu-id="df059-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="df059-119">Richiedere agli utenti le connessioni di rete lente</span><span class="sxs-lookup"><span data-stu-id="df059-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="df059-120">Avviare un determinato programma all'accesso</span><span class="sxs-lookup"><span data-stu-id="df059-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="df059-121">Creare un altro account utente di dominio in tutti i computer appartenenti a un dominio.</span><span class="sxs-lookup"><span data-stu-id="df059-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="df059-122">Push Windows Update per Skype room System</span><span class="sxs-lookup"><span data-stu-id="df059-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="df059-123">In alternativa, è possibile che si decida di uscire dal PC Appliance nel gruppo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="df059-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="df059-124">Come per il client desktop Microsoft teams o Skype for business, è necessario importare manualmente la catena di certificati radice nel PC di Skype room System Appliance.</span><span class="sxs-lookup"><span data-stu-id="df059-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="df059-125">Non è necessario importare la catena di certificati radice se la distribuzione usa un certificato pubblico, ad esempio Entrust, VeriSign e così via.</span><span class="sxs-lookup"><span data-stu-id="df059-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="df059-126">Se si prevede di partecipare al dominio ai computer della sala sistemi Skype, per evitare che l'Unione di Skype room System non venga inavvertitamente in un'unità organizzativa non intenzionale, che potrebbe non essere priva di GPO, verificare di essere entrati nell'OU corretta.</span><span class="sxs-lookup"><span data-stu-id="df059-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="df059-127">Puoi usare il cmdlet seguente dal computer per le chat room Skype per partecipare all'unità organizzativa corretta e non ricevere oggetti Criteri di gruppo che potrebbero bloccare la funzionalità LRS.</span><span class="sxs-lookup"><span data-stu-id="df059-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="df059-128">Contattare l'amministratore di sistema o il partner OEM per eseguire questi cmdlet:</span><span class="sxs-lookup"><span data-stu-id="df059-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="df059-129">Anche se si crea un'unità organizzativa separata e si blocca l'ereditarietà, esistono alcuni criteri che potrebbero causare problemi di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="df059-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="df059-130">Un criterio di gruppo senza l'impostazione di override batte un'unità organizzativa con un'impostazione di ereditarietà dei criteri di blocco.</span><span class="sxs-lookup"><span data-stu-id="df059-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="df059-131">Per altre informazioni, vedere l'articolo [Nessun override rispetto a bloccare l'ereditarietà dei criteri](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) nella documentazione di criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="df059-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="df059-132">Potresti avere più approcci per risolvere questi problemi.</span><span class="sxs-lookup"><span data-stu-id="df059-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="df059-133">Ti consigliamo di consultarti con gli esperti di Active Directory per assicurarti di avere a disposizione un'unità organizzativa che disponga di impostazioni GPO appropriate o almeno un'unità organizzativa in cui i criteri descritti in precedenza non esistono.</span><span class="sxs-lookup"><span data-stu-id="df059-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="df059-134">È consigliabile abilitare la qualità del servizio (QoS) per i dispositivi Skype room System.</span><span class="sxs-lookup"><span data-stu-id="df059-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="df059-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df059-135">See also</span></span>
  
[<span data-ttu-id="df059-136">Configurazione dispositivo: crearne una nuova o modificarne una esistente</span><span class="sxs-lookup"><span data-stu-id="df059-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="df059-137">Gestione della qualità del servizio</span><span class="sxs-lookup"><span data-stu-id="df059-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
