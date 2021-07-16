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
ms.openlocfilehash: bd8f3873ab28ef8e0b7ade86ffc95b4d5bb4e4cb
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458997"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>Aggiornare le voci DNS per consentire all'organizzazione di essere Teams solo

Le organizzazioni che in precedenza avevano distribuzioni locali di Skype for Business Server o Lync Server potrebbero avere ancora voci DNS che puntano a una distribuzione Skype for Business locale. Questi record sono necessari se l'organizzazione include utenti Skype for Business locali. Tuttavia, una volta che l'organizzazione non ha più utenti locali Skype for Business o Lync Server, questi record non sono più necessari. Infatti, come parte del completamento della migrazione da locale a Teams, questi record devono essere aggiornati in modo che puntino a Microsoft 365 o rimossi. Microsoft non può eseguire questo passaggio.

Quando si tenta di concedere TeamsOnly all'intero tenant, Teams dns per determinare se esiste uno di questi record DNS per l'organizzazione. Se vengono trovati record e puntano a un valore diverso da Microsoft 365, il tentativo di modificare la modalità di coesistenza del tenant in TeamsOnly avrà esito negativo in base alla progettazione. Questa progettazione consente di impedire alle organizzazioni ibride con utenti locali di applicare erroneamente la modalità TeamsOnly al tenant, perché in questo modo si interromperebbe la federazione per tutti gli utenti di Skype for Business locali (se si usa Teams o Skype for Business).

Inoltre, questi record devono essere aggiornati in modo da poter concedere TeamsOnly all'intero tenant.

> [!Note] 
> In rari casi, la modifica del DNS da locale a Microsoft 365 per l'organizzazione può causare la federazione con altre organizzazioni smettere di funzionare finché l'altra organizzazione non aggiorna la configurazione della federazione:
>
> - Tutte le organizzazioni federate che utilizzano il modello di federazione diretta precedente (noto anche come Server partner consentito) dovranno aggiornare le voci di dominio consentite per l'organizzazione per rimuovere il nome di dominio completo del proxy. Questo modello di federazione legacy non è basato sui record DNS SRV, quindi una configurazione di questo tipo diventerà non aggiornata dopo che l'organizzazione si sposta nel cloud.
> 
> - Qualsiasi organizzazione federata che non dispone di un provider di hosting abilitato per sipfed.online.lync. <span> com dovrà aggiornare la configurazione per abilitarla. Questa situazione è possibile solo se l'organizzazione federata è puramente locale e non ha mai federato con un tenant ibrido o online. In tal caso, la federazione con queste organizzazioni non funzionerà finché non abilita il provider di hosting.
>
> Se si sospetta che uno dei partner federati utilizzi la federazione diretta o che non sia federato con un'organizzazione online o ibrida, è consigliabile inviare loro una comunicazione in proposito mentre si prepara a completare la migrazione al cloud.

## <a name="how-to-identify-stale-dns-records"></a>Come identificare i record DNS non aggiornati

Per identificare i record DNS che impediscono all'organizzazione di diventare solo Teams, è possibile utilizzare l'interfaccia di amministrazione di Teams per modificare la modalità di coesistenza in TeamsOnly. Passare a **Impostazioni a livello di** organizzazione Teams  ->  **Aggiorna**. Tutti i record DNS che impediscono all'organizzazione di diventare Teams verranno inclusi nel messaggio di errore.  Nel caso in cui non vengono trovati record DNS, la modalità di coesistenza per l'organizzazione verrà modificata in TeamsOnly. 

## <a name="how-to-remove-stale-dns-records"></a>Come rimuovere record DNS non aggiornati

Se l'organizzazione non dispone più di utenti locali Skype for Business Server o Lync Server, è necessario eseguire le operazioni seguenti:

- Aggiornare Skype for Business record DNS in modo che puntino a Microsoft 365 (anziché alla distribuzione locale).

- Rimuovere Skype for Business record DNS se il dominio SIP non è più utilizzato. 

In ogni dominio in cui si trova uno dei record seguenti, aggiornarli come segue:

| Tipo di record | Nome | TTL | Priorità | Peso | Porta | Value |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| SRV | _sipfederationtls.tcp | 3600 |  100 | 1  | 5061  | sipfed.online.lync.com |
| SRV | _sip.tls | 3600  | 100 |    1    | 443   | sipdir.online.lync.com |
| CNAME | lyncdiscover |    3600 |  N/D |   N/D |   N/D |   webdir.online.lync.com |
| CNAME |   sip | 3600 |    N/D |   N/D  | N/D |    sipdir.online.lync.com |
|||||||




