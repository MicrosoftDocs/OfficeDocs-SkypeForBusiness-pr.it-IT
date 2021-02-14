---
title: Considerazioni sulla partecipazione al dominio di Skype Room System
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
description: L'amministratore può scoprire come aggiungere un PC con appliance Skype Room System a un dominio Active Directory, oltre a considerazioni per farlo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfcee1421c25903a5ec8deb2f66871ed1d57ef1c
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905438"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Considerazioni sulla partecipazione al dominio di Skype Room System
 
Leggere questo argomento per informazioni su come aggiungere un PC con appliance Skype Room System al proprio dominio.
  
## <a name="domain-joining-considerations"></a>Considerazioni sulla partecipazione ai domini

È possibile aggiungere il PC dell'appliance Skype Room System al dominio Active Directory o lasciarlo in un gruppo di lavoro. Prima di prendere questa decisione, considerare i punti seguenti:
  
- L'aggiunta di un dominio all'appliance Skype Room System consente di importare automaticamente la catena di certificati radice privati dell'organizzazione.
- L'aggiunta di un dominio all'appliance Skype Room System consente di concedere diritti amministrativi agli utenti e ai gruppi di dominio. In questo modo non sarà necessario ricordare la password dell'account amministratore a livello di computer locale.
- Quando si aggiunge al dominio un PC con appliance Skype Room System, è necessario creare un'unità organizzativa (OU) distinta, in modo da poter fornire le esclusioni dell'oggetto Criteri di gruppo all'unità organizzativa in cui risiedono tutti gli oggetti computer di Skype Room System. Quando si esegue questa operazione, creare oggetti computer nell'unità organizzativa prima di aggiungere al dominio l'appliance PC Skype Room System.
- Molte organizzazioni dispongono dei seguenti oggetti Criteri di gruppo, che influiscono sulle funzioni dell'appliance Skype Room System. Assicurarsi di ignorare o bloccare l'ereditarietà di questi oggetti Criteri di gruppo nell'unità organizzativa Skype Room System:

  - Timeout delle sessioni di accesso (blocco automatico)
  - Criteri correlati alla gestione dell'alimentazione
  - Procedura di autenticazione aggiuntiva richiesta
  - Negazione dell'accesso alle unità locali
  - Richiesta agli utenti di connessioni di rete lente
  - Avviare un determinato programma all'accesso
  - Creare un altro account utente di dominio in tutti i computer aggiunti a un dominio.
  - Push Windows Update to Skype Room System
    
- In alternativa, è possibile decidere di lasciare il PC dell'appliance nel gruppo di lavoro. Come per il client desktop di Microsoft Teams o Skype for Business, questa operazione richiede l'importazione manuale della catena di certificati radice nel PC per appliance Skype Room System. Non è necessario importare la catena di certificati radice se la distribuzione usa un certificato pubblico, ad esempio Entrust, VeriSign e così via. 
    
Se pensi di aggiungere al dominio computer Skype Room System, per evitare di aggiungerti inavvertitamente a un'unità organizzativa involontaria, che potrebbe non essere esente da oggetti Criteri di gruppo, assicurati di aggiungerti all'unità organizzativa corretta. Puoi utilizzare il seguente cmdlet dal computer Skype Room System per partecipare all'unità organizzativa corretta e non riceve oggetti Criteri di gruppo che potrebbero bloccare la funzionalità LRS. Contattare l'amministratore di sistema o il partner OEM per eseguire questo cmdlet:
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Anche se si crea un'unità organizzativa distinta e si blocca l'ereditarietà, esistono alcuni criteri che potrebbero causare problemi a un livello superiore. Un criterio di gruppo con impostazione Nessun override supera un'unità organizzativa con un'impostazione Blocca ereditarietà dei criteri. Per altre informazioni, vedere l'articolo [Nessun override rispetto a](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) Blocca ereditarietà dei criteri nella documentazione di Criteri di gruppo.
  
Per risolvere questi problemi, è possibile che si abbia a che fare con diversi approcci. È opportuno consultare gli esperti di Active Directory per assicurarsi di avere a disposizione un'unità organizzativa con le impostazioni dell'oggetto Criteri di gruppo appropriate o almeno un'unità organizzativa in cui non esistono i criteri descritti in precedenza. Si consiglia di abilitare la qualità del servizio (QoS) per i dispositivi Skype Room System.

## <a name="related-topics"></a>Argomenti correlati
  
[Configurazione dispositivo: crearne una nuova o modificarne una esistente](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gestione della qualità del servizio](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
