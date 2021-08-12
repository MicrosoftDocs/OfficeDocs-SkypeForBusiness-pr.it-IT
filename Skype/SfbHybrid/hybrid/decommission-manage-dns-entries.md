---
title: Gestire le voci DNS durante la rimozione delle autorizzazioni dell'ambiente locale
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Istruzioni su come gestire le voci DNS durante la rimozione delle autorizzazioni dell'ambiente Skype for Business locale.
ms.openlocfilehash: 0dabf9790b1e579d136fef459308af450e879b110474b2877513855c8e78cf29
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315172"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>Aggiornare le voci DNS per consentire all'organizzazione di essere Teams solo

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Le organizzazioni che in precedenza avevano distribuzioni locali di Skype for Business Server o Lync Server potrebbero avere ancora voci DNS che puntano a una distribuzione Skype for Business locale. Questi record sono necessari se l'organizzazione include utenti Skype for Business locali. Tuttavia, una volta che l'organizzazione non ha più utenti di Skype for Business o Lync Server locali, questi record originali non sono più necessari per la distribuzione locale e queste voci DNS devono essere aggiornate in modo che puntino **a Microsoft 365 (o in** alcuni casi rimosse) come parte della migrazione da locale a solo Teams. *Microsoft non può aggiornare questi record DNS per conto dell'utente.*

Quando si tenta di concedere TeamsOnly all'intero tenant, Teams verificherà DNS per determinare se uno di questi record DNS elencati di seguito esiste in ognuno dei domini verificati Microsoft 365 nell'organizzazione. Se vengono trovati record e puntano a un valore diverso da Microsoft 365, il tentativo di modificare la modalità di coesistenza del tenant in TeamsOnly avrà esito negativo in base alla progettazione. In questo modo le organizzazioni ibride con utenti locali non applicherebbero erroneamente la modalità TeamsOnly al tenant, perché in questo modo si interromperebbe la federazione per tutti gli utenti di Skype for Business locali nell'organizzazione (se si usa Teams o Skype for Business).


## <a name="how-to-identify-stale-dns-records"></a>Come identificare i record DNS non aggiornati

Per identificare i record DNS che impediscono all'organizzazione di diventare solo Teams, è possibile utilizzare l'interfaccia di amministrazione di Teams per modificare la modalità di coesistenza in TeamsOnly. Passare a **Impostazioni a livello di** organizzazione Teams  ->  **Aggiorna**. Tutti i record DNS che impediscono all'organizzazione di diventare Teams verranno inclusi nel messaggio di errore.  Nel caso in cui non vengono trovati record DNS, la modalità di coesistenza per l'organizzazione verrà modificata in TeamsOnly.   

In alternativa, è possibile usare Teams PowerShell per eseguire la stessa operazione, come illustrato di seguito:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
   ```

## <a name="dns-records-to-be-updated"></a>Record DNS da aggiornare

Se nell'organizzazione non sono più presenti utenti ospitati in Skype for Business Server locale o Lync Server, è necessario eseguire le operazioni seguenti:

- Aggiornare l'Skype for Business di record DNS seguente in modo che punti a Microsoft 365 (anziché alla distribuzione locale). Se si dispone di più di un dominio SIP, è necessario eseguire questa operazione per ogni dominio SIP che è un Microsoft 365 verificato.

- Rimuovere Skype for Business record DNS se il dominio SIP non è più utilizzato. 

In ogni dominio in cui si trova uno dei record seguenti, aggiornarli come segue:

| Tipo di record | Nome | TTL | Priorità | Peso | Porta | Value |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| SRV | _sipfederationtls.tcp | 3600 |  100 | 1 | 5061  | sipfed.online.lync.com |
| SRV | _sip.tls | 3600  | 100 |    1   | 443   | sipdir.online.lync.com |
| CNAME | lyncdiscover |    3600 |  N/D |   N/D |   N/D |   webdir.online.lync.com |
| CNAME |   sip | 3600 |    N/D |   N/D  | N/D |    sipdir.online.lync.com |
|||||||

Inoltre, i record CNAME per meet o dialin (se presente) possono essere eliminati. Infine, tutti i record DNS Skype for Business nella rete interna devono essere rimossi.

> [!Note] 
> In rari casi, la modifica del DNS da locale a Microsoft 365 per l'organizzazione può causare la federazione con altre organizzazioni smettere di funzionare finché l'altra organizzazione non aggiorna la configurazione della federazione:
>
> - Tutte le organizzazioni federate che utilizzano il modello di federazione diretta precedente (noto anche come Server partner consentito) dovranno aggiornare le voci di dominio consentite per l'organizzazione per rimuovere il nome di dominio completo del proxy. Questo modello di federazione legacy non è basato sui record DNS SRV, quindi una configurazione di questo tipo diventerà non aggiornata dopo che l'organizzazione si sposta nel cloud.
> 
> - Qualsiasi organizzazione federata che non dispone di un provider di hosting abilitato per sipfed.online.lync. <span> com dovrà aggiornare la configurazione per abilitarla. Questa situazione è possibile solo se l'organizzazione federata è puramente locale e non ha mai federato con un tenant ibrido o online. In tal caso, la federazione con queste organizzazioni non funzionerà finché non abilita il provider di hosting.
>
> Se si sospetta che uno dei partner federati utilizzi la federazione diretta o che non sia federato con un'organizzazione online o ibrida, è consigliabile inviare loro una comunicazione in proposito mentre si prepara a completare la migrazione al cloud.
  




