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
# <a name="skype-room-system-domain-joining-considerations"></a>Considerazioni sulla partecipazione del dominio del sistema Skype room
 
Leggere questo argomento per informazioni su come aggiungere un PC accessorio del sistema Skype room al proprio dominio.
  
## <a name="domain-joining-considerations"></a>Considerazioni sull'unione del dominio

È possibile aggiungere il PC del dispositivo del sistema Skype room al dominio di Active Directory o lasciarlo in un gruppo di lavoro. Prima di prendere questa decisione, prendere in considerazione i seguenti punti:
  
- Domain-partecipazione il PC di Skype room System Appliance aiuta ad importare automaticamente la catena di certificati radice privata dell'organizzazione.
    
- Domain-partecipazione il PC di Skype room System Appliance consente di concedere a utenti e gruppi di dominio diritti amministrativi. In questo modo, non è necessario ricordare la password dell'account amministratore a livello di computer locale.
    
- Quando si entra nel dominio in un PC appliance di Skype room System, è necessario creare un'unità organizzativa separata (OU), in modo che sia possibile fornire le esclusioni degli oggetti Criteri di gruppo all'unità organizzativa in cui risiedono tutte le strutture del computer del sistema di Skype room. Quando si esegue questa operazione, creare oggetti Machine nell'unità organizzativa prima di unire il PC del dispositivo di sistema Skype room al dominio.
    
- Molte organizzazioni dispongono degli oggetti Criteri di sistema seguenti, che influiscono sulle funzioni di Skype room System Appliance. Assicurarsi di ignorare o bloccare l'ereditarietà di tali oggetti Criteri di gruppo nell'unità organizzativa di sistema di Skype room: 
    
  - Timeout delle sessioni di accesso (blocco automatico)
    
  - Criteri correlati alla gestione dell'alimentazione
    
  - Richiedere ulteriori passaggi di autenticazione
    
  - Negare l'accesso alle unità locali
    
  - Suggerimento per gli utenti per le connessioni di rete lente
    
  - Avviare un determinato programma all'accesso
    
  - Creare un altro account utente di dominio in tutti i computer aggiunti a un dominio.
    
  - Push Windows Update to Skype room System
    
- In alternativa, è possibile decidere di lasciare il PC del dispositivo nel gruppo di lavoro. Come nel caso del client Skype for business desktop, è necessario importare manualmente la catena di certificati radice sul PC di Skype room System Appliance. Non è necessario importare la catena di certificati radice se la distribuzione di Skype for business utilizza un certificato pubblico (ad esempio, Entrust, VeriSign e così via). 
    
[! Nota] Se si prevede di aderire al dominio ai computer della chat room Skype, per evitare che l'Unione di Skype room System involontariamente in un'unità organizzativa indesiderata, che potrebbe non essere libera dagli oggetti Criteri di rete, assicurarsi di partecipare all'unità organizzativa corretta. È possibile utilizzare il cmdlet seguente dal computer del sistema di chat room Skype per partecipare all'unità organizzativa corretta e non ricevere gli oggetti Criteri di gruppo che potrebbero bloccare la funzionalità LRS. Contattare l'amministratore di sistema o il partner OEM per eseguire questi cmdlet:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Anche se si crea un'unità organizzativa separata e si blocca l'ereditarietà, esistono alcuni criteri che potrebbero causare problemi a un livello superiore. Un criterio di gruppo con nessuna impostazione di sostituzione batte un'unità organizzativa con un'impostazione di ereditarietà dei criteri di blocco. Per ulteriori informazioni, vedere l'articolo [Nessuna sostituzione rispetto all'ereditarietà dei criteri di blocco](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) nella documentazione relativa ai criteri di gruppo.
  
Per risolvere questi problemi, è possibile che si disponga di più approcci. Si consiglia di consultare gli esperti di Active Directory per assicurarsi di disporre di un'unità organizzativa con impostazioni di criteri di gruppo appropriate o almeno di un'unità organizzativa in cui non esistano i criteri descritti in precedenza. Si consiglia di abilitare la qualità del servizio (QoS) per i dispositivi Skype room System.

## <a name="see-also"></a>Vedere anche
  
[Configurazione dispositivo: crearne una nuova o modificarne una esistente](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gestione della qualità del servizio](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
