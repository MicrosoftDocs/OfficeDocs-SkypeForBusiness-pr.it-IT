---
title: Skype considerazioni sull'aggiunta a un dominio room system
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: L'amministratore può scoprire come aggiungere un PC Skype Appliance room System a un dominio active directory, insieme alle considerazioni per farlo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c64f6df46a8fec7364c63227e3c0a620758038f1
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503973"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Skype considerazioni sull'aggiunta a un dominio room system
 
Leggere questo argomento per informazioni su come aggiungere un PC Skype pc dell'appliance Room System al dominio.
  
## <a name="domain-joining-considerations"></a>Considerazioni sull'aggiunta di domini

È possibile aggiungere il PC dell Skype Room System appliance al dominio Active Directory o lasciarlo in un gruppo di lavoro. Prima di prendere questa decisione, considerare i punti seguenti:
  
- L'aggiunta a un dominio Skype pc dell'appliance Room System consente di importare automaticamente la catena di certificati radice privata dell'organizzazione.
- L'aggiunta a un dominio Skype pc dell'appliance Room System consente di concedere a utenti e gruppi di dominio i diritti amministrativi. In questo modo, non sarà necessario ricordare la password dell'account di amministratore a livello di computer locale.
- Quando si aggiunge un PC dell'appliance Skype Room System al dominio, è necessario creare un'unità organizzativa separata, in modo da poter fornire esclusioni di oggetti Criteri di gruppo all'unità organizzativa in cui si trovano tutti gli oggetti computer del sistema room Skype. In questo caso, creare oggetti computer nell'unità organizzativa prima di aggiungere il PC dell'appliance Skype Room System al dominio.
- Molte organizzazioni hanno gli oggetti Criteri di gruppo seguenti, che influiscono sulle Skype pc dell'appliance Room System. Assicurarsi di ignorare o bloccare l'ereditarietà di questi oggetti Criteri di gruppo nell'Skype di sistema room:

  - Timeout delle sessioni di accesso (blocco automatico)
  - Criteri correlati alla gestione del risparmio energia
  - Richiedere ulteriori passaggi di autenticazione
  - Negazione dell'accesso alle unità locali
  - Richiesta di connessioni di rete lente agli utenti
  - Avviare un determinato programma all'accesso
  - Creare un altro account utente di dominio in tutti i computer aggiunti al dominio.
  - Push Windows Update to Skype Room System
    
- In alternativa, è possibile decidere di lasciare il PC dell'appliance nel gruppo di lavoro. Come per il client Microsoft Teams o Skype for Business desktop, è necessario importare manualmente la catena di certificati radice nel PC dell'appliance Skype Room System. Non è necessario importare la catena di certificati radice se la distribuzione usa un certificato pubblico, ad esempio Entrust, VeriSign e così via. 
    
Se si prevede di aggiungere computer Skype Room System al dominio, per evitare di aggiungere inavvertitamente un computer Skype Room System a un'unità organizzativa non intenzionale, che potrebbe non essere esente da oggetti Criteri di gruppo, assicurarsi di aggiungere l'unità organizzativa corretta. È possibile usare il cmdlet seguente dal computer Skype Room System per partecipare all'unità organizzativa corretta e non riceve oggetti Criteri di gruppo che potrebbero bloccare la funzionalità LRS. Contattare l'amministratore di sistema o il partner OEM per eseguire questi cmdlet:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Anche se si crea un'unità organizzativa separata e si blocca l'ereditarietà, esistono alcuni criteri che potrebbero causare problemi a un livello superiore. Un'impostazione di Criteri di gruppo senza override supera un'unità organizzativa con un'impostazione Blocca ereditarietà dei criteri. Per altre informazioni, vedere [Nessun override rispetto](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) al blocco dell'ereditarietà dei criteri nella documentazione di Criteri di gruppo.
  
Potrebbero essere disponibili più approcci per risolvere questi problemi. Si consiglia di consultare gli esperti di Active Directory per assicurarsi di avere a disposizione un'unità organizzativa con le impostazioni appropriate dell'oggetto Criteri di gruppo o almeno un'unità organizzativa in cui i criteri descritti in precedenza non esistono. Consigliamo di abilitare la qualità del servizio (QoS) per i Skype room system.

## <a name="related-topics"></a>Argomenti correlati
  
[Configurazione dispositivo: crearne una nuova o modificarne una esistente](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gestione della qualità del servizio](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)