---
title: Gestire le voci DNS durante la rimozione dell'ambiente locale
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Istruzioni su come gestire le voci DNS durante la rimozione dell'ambiente Skype for Business locale.
ms.openlocfilehash: c21a736c19ecec41ddc0458931675ca8ede34ed2
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671882"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>Aggiornare le voci DNS per consentire all'organizzazione di essere solo Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Le organizzazioni che in precedenza avevano distribuzioni locali di Skype for Business Server o Lync Server potrebbero avere ancora voci DNS che puntano a una distribuzione Skype for Business locale. Questi record sono necessari se l'organizzazione include utenti Skype for Business locali. Tuttavia, dopo che l'organizzazione non ha più utenti locali Skype for Business o Lync Server, questi record originali non sono più necessari per la distribuzione locale e **queste voci DNS devono essere aggiornate in modo che puntino a Microsoft 365 (o in alcuni casi rimossi)** come parte della migrazione da locale a solo Teams. *Microsoft non può aggiornare questi record DNS per conto dell'utente.*

Quando si tenta di concedere TeamsOnly all'intero tenant, Teams controllerà DNS per determinare se uno di questi record DNS elencati di seguito esiste in ognuno dei domini verificati Microsoft 365 nell'organizzazione. Se vengono trovati record e puntano a qualcosa di diverso da Microsoft 365, il tentativo di modificare la modalità di coesistenza del tenant in TeamsOnly avrà esito negativo in base alla progettazione. Ciò impedisce alle organizzazioni ibride con utenti locali di applicare erroneamente la modalità TeamsOnly al tenant, perché in questo modo si interromperebbe la federazione per tutti gli utenti Skype for Business locali nell'organizzazione (sia che si usi Teams che Skype for Business).

## <a name="how-to-identify-stale-dns-records"></a>Come identificare i record DNS non aggiornati

Per identificare eventuali record DNS che impediscono all'organizzazione di diventare solo Teams, è possibile usare l'interfaccia di amministrazione Teams per modificare la modalità di coesistenza in TeamsOnly. Passare alle **impostazioni** di aggiornamento Teams  > **Teams**. Nel messaggio di errore verranno inclusi tutti i record DNS che impediscono all'organizzazione di diventare Teams Solo.  Nel caso in cui non vengano trovati record DNS, la modalità di coesistenza per l'organizzazione verrà modificata in TeamsOnly.

In alternativa, è possibile usare Teams PowerShell per eseguire la stessa operazione, come illustrato di seguito:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
   ```

## <a name="dns-records-to-be-updated"></a>Record DNS da aggiornare

Se l'organizzazione non ha più utenti ospitati in Skype for Business Server locali o Lync Server, è necessario eseguire le operazioni seguenti:

- Aggiornare l'elenco di record DNS Skype for Business riportato di seguito in modo che punti a Microsoft 365 (anziché alla distribuzione locale). Se si dispone di più di un dominio SIP, è necessario eseguire questa operazione per ogni dominio SIP che è un dominio verificato Microsoft 365.

- Rimuovere Skype for Business record DNS se il dominio SIP non viene più usato.

In ogni dominio in cui si trova uno dei record seguenti, aggiornarli come segue:

|Tipo di record|Nome|TTL|Priorità|Peso|Porta|Value|
|---|---|---|---|---|---|---|
|SRV|_sipfederationtls._tcp|3600|100|1|5061|sipfed.online.lync.com|
|SRV|_sip._tls|3600|100|1|443|sipdir.online.lync.com|
|CNAME|lyncdiscover|3600|N/D|N/D|N/D|webdir.online.lync.com|
|CNAME|sip|3600|N/D|N/D|N/D|sipdir.online.lync.com|

Inoltre, i record CNAME per meet o dialin (se presenti) possono essere eliminati. Infine, tutti i record DNS per Skype for Business nella rete interna devono essere rimossi.

> [!NOTE]
> In rari casi, la modifica del DNS da locale a Microsoft 365 per l'organizzazione può causare la federazione con altre organizzazioni a smettere di funzionare fino a quando l'altra organizzazione non aggiorna la configurazione della federazione:
>
> - Tutte le organizzazioni federate che usano il modello di federazione diretta meno recente (noto anche come Server partner consentito) dovranno aggiornare le voci di dominio consentite affinché l'organizzazione rimuova il nome di dominio completo del proxy. Questo modello federativo legacy non è basato sui record SRV DNS, quindi una configurazione di questo tipo non sarà più aggiornata dopo che l'organizzazione si sposta nel cloud.
>
> - Qualsiasi organizzazione federata che non dispone di un provider di hosting abilitato per sipfed.online.lync.<span> com dovrà aggiornare la configurazione per abilitarla. Questa situazione è possibile solo se l'organizzazione federata è esclusivamente locale e non è mai stata federata con un tenant ibrido o online. In tal caso, la federazione con queste organizzazioni non funzionerà finché non abilita il provider di hosting.
>
> Se si sospetta che uno dei partner federati stia usando la federazione diretta o non sia federato con un'organizzazione online o ibrida, è consigliabile inviare loro una comunicazione su questo argomento durante la preparazione per completare la migrazione al cloud.
