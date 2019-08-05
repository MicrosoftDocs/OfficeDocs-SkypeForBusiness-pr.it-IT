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
# <a name="skype-room-system-domain-joining-considerations"></a>Considerazioni sull'Unione di domini di Skype room System
 
Leggere questo argomento per informazioni su come partecipare a un PC appliance di sistema Skype room al proprio dominio.
  
## <a name="domain-joining-considerations"></a>Considerazioni sull'Unione di domini

È possibile partecipare al PC di Skype room System Appliance al dominio Active Directory o lasciarlo in un gruppo di lavoro. Prima di prendere questa decisione, prendere in considerazione i punti seguenti:
  
- Domain-partecipare al PC di Skype room System Appliance aiuta ad importare automaticamente la catena di certificati radice privati dell'organizzazione.
    
- Domain-Joining Skype room System Appliance PC consente di concedere a utenti e gruppi di domini i diritti amministrativi. In questo modo, non è necessario ricordare la password dell'account di amministratore del livello di computer locale.
    
- Quando si partecipa a un PC Appliance Skype room System al dominio, è necessario creare un'unità organizzativa separata (OU), in modo da consentire l'esclusione degli oggetti Criteri di gruppo per l'unità organizzativa in cui risiedono tutte le applicazioni del computer room System Skype. Quando si esegue questa operazione, creare oggetti macchina nell'unità organizzativa prima di partecipare al PC di Skype room System Appliance al dominio.
    
- Molte organizzazioni hanno gli oggetti Criteri di rete seguenti, che influiscono sulle funzioni PC appliance di Skype room System. Assicurarsi di ignorare o bloccare l'ereditarietà di questi oggetti Criteri di gruppo nell'OU di sistema di chat room di Skype: 
    
  - Timeout delle sessioni di accesso (blocco automatico)
    
  - Criteri correlati a Power Management
    
  - Richiedere ulteriori passaggi di autenticazione
    
  - Negazione dell'accesso alle unità locali
    
  - Richiedere agli utenti le connessioni di rete lente
    
  - Avviare un determinato programma all'accesso
    
  - Creare un altro account utente di dominio in tutti i computer appartenenti a un dominio.
    
  - Push Windows Update per Skype room System
    
- In alternativa, è possibile che si decida di uscire dal PC Appliance nel gruppo di lavoro. Come per il client desktop Microsoft teams o Skype for business, è necessario importare manualmente la catena di certificati radice nel PC di Skype room System Appliance. Non è necessario importare la catena di certificati radice se la distribuzione usa un certificato pubblico, ad esempio Entrust, VeriSign e così via. 
    
Se si prevede di partecipare al dominio ai computer della sala sistemi Skype, per evitare che l'Unione di Skype room System non venga inavvertitamente in un'unità organizzativa non intenzionale, che potrebbe non essere priva di GPO, verificare di essere entrati nell'OU corretta. Puoi usare il cmdlet seguente dal computer per le chat room Skype per partecipare all'unità organizzativa corretta e non ricevere oggetti Criteri di gruppo che potrebbero bloccare la funzionalità LRS. Contattare l'amministratore di sistema o il partner OEM per eseguire questi cmdlet:
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Anche se si crea un'unità organizzativa separata e si blocca l'ereditarietà, esistono alcuni criteri che potrebbero causare problemi di livello superiore. Un criterio di gruppo senza l'impostazione di override batte un'unità organizzativa con un'impostazione di ereditarietà dei criteri di blocco. Per altre informazioni, vedere l'articolo [Nessun override rispetto a bloccare l'ereditarietà dei criteri](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) nella documentazione di criteri di gruppo.
  
Potresti avere più approcci per risolvere questi problemi. Ti consigliamo di consultarti con gli esperti di Active Directory per assicurarti di avere a disposizione un'unità organizzativa che disponga di impostazioni GPO appropriate o almeno un'unità organizzativa in cui i criteri descritti in precedenza non esistono. È consigliabile abilitare la qualità del servizio (QoS) per i dispositivi Skype room System.

## <a name="see-also"></a>Vedere anche
  
[Configurazione dispositivo: crearne una nuova o modificarne una esistente](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gestione della qualità del servizio](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
