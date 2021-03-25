---
title: Considerazioni sull'aggiunta al dominio di Skype Room System
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
description: L'amministratore può scoprire come aggiungere un PC dell'appliance Skype Room System a un dominio Active Directory, insieme alle considerazioni per farlo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c322819fb765e05cead793c95b5e3b6af2d2a180
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117554"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Considerazioni sull'aggiunta al dominio di Skype Room System
 
Leggi questo argomento per informazioni su come aggiungere un PC dell'appliance Skype Room System al tuo dominio.
  
## <a name="domain-joining-considerations"></a>Considerazioni sull'aggiunta di domini

Puoi aggiungere il PC dell'appliance Skype Room System al dominio Active Directory o lasciarlo in un gruppo di lavoro. Prima di prendere questa decisione, considerare i punti seguenti:
  
- L'aggiunta al PC dell'appliance Skype Room System consente di importare automaticamente la catena di certificati radice privata dell'organizzazione.
- L'aggiunta a un dominio nel PC dell'appliance Skype Room System consente di concedere agli utenti e ai gruppi di dominio i diritti amministrativi. In questo modo, non sarà necessario ricordare la password dell'account di amministratore a livello di computer locale.
- Quando si aggiunge un PC dell'appliance di Sistema sala Skype al dominio, è necessario creare un'unità organizzativa separata, in modo da poter fornire esclusioni di oggetti Criteri di gruppo all'unità organizzativa in cui si trovano tutti gli oggetti computer di Sistema sala Skype. In questo caso, creare oggetti computer nell'unità organizzativa prima di aggiungere il PC dell'appliance Skype Room System al dominio.
- Molte organizzazioni hanno i seguenti oggetti Criteri di gruppo, che influiscono sulle funzioni del PC dell'appliance Skype Room System. Assicurarsi di ignorare o bloccare l'ereditarietà di questi oggetti Criteri di gruppo nell'unità organizzativa Sistema sala Skype:

  - Timeout delle sessioni di accesso (blocco automatico)
  - Criteri correlati alla gestione del risparmio energia
  - Richiedere ulteriori passaggi di autenticazione
  - Negazione dell'accesso alle unità locali
  - Richiesta di connessioni di rete lente agli utenti
  - Avviare un determinato programma all'accesso
  - Creare un altro account utente di dominio in tutti i computer aggiunti al dominio.
  - Push Windows Update to Skype Room System
    
- In alternativa, è possibile decidere di lasciare il PC dell'appliance nel gruppo di lavoro. Come per il client desktop Microsoft Teams o Skype for Business, è necessario importare manualmente la catena di certificati radice nel PC dell'appliance Skype Room System. Non è necessario importare la catena di certificati radice se la distribuzione usa un certificato pubblico, ad esempio Entrust, VeriSign e così via. 
    
Se si prevede di aggiungere computer skype room system al dominio, per evitare di aggiungersi inavvertitamente a un'unità organizzativa non intenzionale, che potrebbe non essere esente da oggetti Criteri di gruppo, assicurarsi di partecipare all'unità organizzativa corretta. È possibile usare il cmdlet seguente dal computer Skype Room System per partecipare all'unità organizzativa corretta e non riceve oggetti Criteri di gruppo che potrebbero bloccare la funzionalità LRS. Contattare l'amministratore di sistema o il partner OEM per eseguire questi cmdlet:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Anche se si crea un'unità organizzativa separata e si blocca l'ereditarietà, esistono alcuni criteri che potrebbero causare problemi a un livello superiore. Un'impostazione di Criteri di gruppo senza override supera un'unità organizzativa con un'impostazione Blocca ereditarietà dei criteri. Per altre informazioni, vedere [Nessun override rispetto](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) al blocco dell'ereditarietà dei criteri nella documentazione di Criteri di gruppo.
  
Potrebbero essere disponibili più approcci per risolvere questi problemi. Si consiglia di consultare gli esperti di Active Directory per assicurarsi di avere a disposizione un'unità organizzativa con le impostazioni appropriate dell'oggetto Criteri di gruppo o almeno un'unità organizzativa in cui i criteri descritti in precedenza non esistono. Consigliamo di abilitare la qualità del servizio (QoS) per i dispositivi Skype Room System.

## <a name="related-topics"></a>Argomenti correlati
  
[Configurazione dispositivo: crearne una nuova o modificarne una esistente](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gestione della qualità del servizio](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)