---
title: Skype Considerazioni sull'aggiunta al dominio del sistema sala
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Leggere questo argomento per informazioni su come aggiungere un PC Skype Appliance room al dominio.
ms.openlocfilehash: b7590f17e8572d4379324f13924a5b4d7d339753
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623038"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Skype Considerazioni sull'aggiunta al dominio del sistema sala
 
Leggere questo argomento per informazioni su come aggiungere un PC Skype Appliance room al dominio.
  
## <a name="domain-joining-considerations"></a>Considerazioni sull'unione del dominio

Puoi aggiungere il PC Skype Appliance room system al dominio di Active Directory o lasciarlo in un gruppo di lavoro. Prima di prendere questa decisione, considerare i punti seguenti:
  
- L'aggiunta al PC Skype appliance room consente di importare automaticamente la catena di certificati radice privata dell'organizzazione.
    
- L'aggiunta al PC Skype room system consente di concedere a utenti e gruppi di dominio diritti amministrativi. In questo modo, non sarà necessario ricordare la password dell'account amministratore a livello di computer locale.
    
- Quando si aggiunge un PC dell'appliance Skype Room System al dominio, è necessario creare un'unità organizzativa separata, in modo da poter fornire esclusioni di oggetti Criteri di gruppo all'unità organizzativa in cui risiedono tutti gli oggetti computer di Skype Room System. Quando si esegue questa operazione, creare oggetti computer nell'unità organizzativa prima di aggiungere il PC dell'appliance Skype Room System al dominio.
    
- Molte organizzazioni dispongono degli oggetti Criteri di gruppo seguenti, che influiscono sulle Skype pc dell'appliance Room System. Assicurarsi di ignorare o bloccare l'ereditarietà di questi oggetti Criteri di gruppo nell'Skype di sistema room: 
    
  - Timeout delle sessioni di accesso (blocco automatico)
    
  - Criteri correlati alla gestione del risparmio energia
    
  - Richiedere ulteriori passaggi di autenticazione
    
  - Negazione dell'accesso alle unità locali
    
  - Richiedere agli utenti connessioni di rete lente
    
  - Avviare un determinato programma all'accesso
    
  - Creare un altro account utente di dominio in tutti i computer aggiunti al dominio.
    
  - Push Windows Update to Skype Room System
    
- In alternativa, potresti decidere di lasciare il PC dell'appliance nel gruppo di lavoro. Come per il client Skype for Business desktop, è necessario importare manualmente la catena di certificati radice nel PC dell'appliance Skype Room System. Non è necessario importare la catena di certificati radice se la distribuzione di Skype for Business usa un certificato pubblico (ad esempio, Entrust, VeriSign e così via). 
    
Se si prevede di aggiungere computer Skype Room System al dominio, per evitare di aggiungere il computer Skype Room System inavvertitamente a un'unità organizzativa non intenzionale, che potrebbe non essere libera dagli oggetti Criteri di gruppo, assicurarsi di aggiungere l'unità organizzativa corretta. È possibile utilizzare il cmdlet seguente dal computer Skype Room System per partecipare all'unità organizzativa corretta e non ricevere oggetti Criteri di gruppo che potrebbero bloccare la funzionalità LRS. Contattare l'amministratore di sistema o il partner OEM per eseguire questo cmdlet:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Anche se si crea un'unità organizzativa separata e si blocca l'ereditarietà, esistono alcuni criteri che potrebbero causare problemi a un livello superiore. Un'impostazione di Criteri di gruppo con nessuna sostituzione supera un'unità organizzativa con un'impostazione Blocca ereditarietà dei criteri. Per ulteriori informazioni, vedere l'articolo [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) nella documentazione relativa a Criteri di gruppo.
  
Potrebbero essere disponibili più approcci per risolvere questi problemi. Si consiglia di consultare gli esperti di Active Directory per assicurarsi di avere a disposizione un'unità organizzativa con le impostazioni appropriate dell'oggetto Criteri di gruppo o almeno un'unità organizzativa in cui i criteri descritti in precedenza non esistono. È consigliabile abilitare la qualità del servizio (QoS) per Skype di sistema room.

## <a name="see-also"></a>Vedere anche
  
[Configurazione dispositivo: crearne una nuova o modificarne una esistente](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gestione della qualità del servizio](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)