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
# <a name="skype-room-system-domain-joining-considerations"></a>Considerazioni sull'aggiunta al dominio di Skype Room System
 
Leggi questo argomento per informazioni su come aggiungere un PC dell'appliance Skype Room System al dominio.
  
## <a name="domain-joining-considerations"></a>Considerazioni sull'unione del dominio

È possibile aggiungere il PC dell'applicazione Skype Room System al dominio di Active Directory o lasciarlo in un gruppo di lavoro. Prima di prendere questa decisione, considerare i punti seguenti:
  
- L'aggiunta al PC dell'appliance Skype Room System consente di importare automaticamente la catena di certificati radice privata dell'organizzazione.
    
- L'aggiunta al PC dell'appliance Skype Room System consente di concedere a utenti e gruppi di dominio diritti amministrativi. In questo modo, non sarà necessario ricordare la password dell'account amministratore a livello di computer locale.
    
- Quando si aggiunge un PC dell'applicazione Skype Room System al dominio, è necessario creare un'unità organizzativa separata, in modo da poter fornire esclusioni di oggetti Criteri di gruppo all'unità organizzativa in cui risiedono tutti gli oggetti computer di Skype Room System. Quando si esegue questa operazione, creare oggetti computer nell'unità organizzativa prima di aggiungere il PC dell'appliance Skype Room System al dominio.
    
- Molte organizzazioni hanno gli oggetti Criteri di gruppo seguenti, che influiscono sulle funzioni del PC dell'appliance Skype Room System. Assicurati di ignorare o bloccare l'ereditarietà di questi oggetti Criteri di gruppo nell'unità organizzativa Skype Room System: 
    
  - Timeout delle sessioni di accesso (blocco automatico)
    
  - Criteri correlati alla gestione del risparmio energia
    
  - Richiesta di ulteriori passaggi di autenticazione
    
  - Negazione dell'accesso alle unità locali
    
  - Richiesta agli utenti di connessioni di rete lente
    
  - Avviare un determinato programma all'accesso
    
  - Creare un altro account utente di dominio in tutti i computer aggiunti al dominio.
    
  - Push di Windows Update nel sistema skype room
    
- In alternativa, puoi decidere di lasciare il PC dell'applicazione nel gruppo di lavoro. Come per il client Desktop Skype for Business, è necessario importare manualmente la catena di certificati radice nel PC dell'appliance Skype Room System. You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on). 
    
Se si prevede di aggiungere computer Skype Room System al dominio, per evitare di aggiungere inavvertitamente il computer Skype Room System a un'unità organizzativa non intenzionale, che potrebbe non essere libera dagli oggetti Criteri di gruppo, assicurarsi di aggiungere l'unità organizzativa corretta. È possibile utilizzare il cmdlet seguente dal computer Skype Room System per partecipare all'unità organizzativa corretta e non riceve oggetti Criteri di gruppo che potrebbero bloccare la funzionalità LRS. Contattare l'amministratore di sistema o il partner OEM per eseguire il cmdlet seguente:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Anche se si crea un'unità organizzativa separata e si blocca l'ereditarietà, esistono alcuni criteri che potrebbero causare problemi a un livello superiore. Un'impostazione di Criteri di gruppo senza override supera un'unità organizzativa con un'impostazione Blocca ereditarietà dei criteri. Per ulteriori informazioni, vedere l'articolo [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) nella documentazione relativa a Criteri di gruppo.
  
Potrebbero essere disponibili più approcci per risolvere questi problemi. Ti consigliamo di consultare gli esperti di Active Directory per assicurarti di avere a disposizione un'unità organizzativa con le impostazioni appropriate dell'oggetto Criteri di gruppo o almeno un'unità organizzativa in cui non esistono i criteri descritti in precedenza. È consigliabile abilitare QoS (Quality of Service) per i dispositivi Skype Room System.

## <a name="see-also"></a>Vedere anche
  
[Configurazione dispositivo: crearne una nuova o modificarne una esistente](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gestione della qualità del servizio](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
