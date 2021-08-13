---
title: Configurare Connessione con operatore
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Altre informazioni su come configurare Connessione con operatore.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 886a9b87154555e75a8f3fbd76002efec86c394364f0301471e1c1ac9784086f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324835"
---
# <a name="configure-operator-connect"></a>Configurare Connessione con operatore

>[!NOTE]
>Connessione con operatore è attualmente disponibile solo **nell'anteprima pubblica.** L'anteprima pubblica consente di testare le funzionalità imminenti e fornire feedback. Le funzionalità incluse nell'anteprima pubblica potrebbero non essere complete, potrebbero subire modifiche e non sono supportate in Office 365 Government cloud.

Questo articolo descrive come configurare Connessione con operatore. Prima di configurare Connessione con operatore, leggere Pianificare [](operator-connect-plan.md) Connessione con operatore informazioni sui prerequisiti e sulle licenze.

## <a name="enable-an-operator"></a>Abilitare un operatore

È possibile abilitare, modificare e rimuovere operatori nell'Teams di amministrazione. Nel riquadro di spostamento sinistro passare a Operatori > **vocali.**

Per abilitare un operatore:

1. **Scegliere un operatore.** Nella scheda **Tutti gli operatori** filtrare gli operatori disponibili in base all'area geografica o al servizio per trovare l'operatore più giusto per le proprie esigenze vocali. Selezionare quindi l'operatore da abilitare.  

2. **Selezionare i paesi.** In **Impostazioni operatore** selezionare i paesi da abilitare con l'operatore selezionato.

3. **Fornisci le informazioni di contatto (facoltativo).** Se si vuole che gli operatori ti contattino con altre informazioni su Connessione con operatore, seleziona la casella e fornisci le informazioni di contatto.  

4. **Accettare l'avviso di trasferimento dei dati.**

5. **Aggiungere l'operatore.** Selezionare **Aggiungi come operatore per** salvare.

## <a name="set-up-phone-numbers"></a>Configurare i numeri di telefono

La modalità di configurazione dei numeri di telefono dipende dalla configurazione dei numeri per i nuovi utenti o dallo spostamento dei numeri esistenti da Piani per chiamate Microsoft o Routing diretto.

- Se è necessario acquisire numeri di telefono per i nuovi utenti, vedere Acquisire numeri per i nuovi utenti [Teams nuovi utenti](#acquire-numbers-for-new-teams-users).

- Per spostare i numeri esistenti da Piani per chiamate a Connessione con operatore, vedere Spostare i numeri da Piani per chiamate a [Connessione con operatore](#move-numbers-from-calling-plans-to-operator-connect).

- Per spostare i numeri esistenti da Instradamento diretto a Connessione con operatore, vedere Spostare i numeri da Instradamento diretto a [Connessione con operatore](#move-numbers-from-direct-routing-to-operator-connect).

>[!IMPORTANT]
>**Indirizzi di emergenza: Telefono** numeri associati agli indirizzi di emergenza sono gestiti dall'operatore. Dopo aver creato gli indirizzi di emergenza nell'Teams di amministrazione, l'operatore assegnerà i numeri di telefono a tali indirizzi di emergenza. Per apportare modifiche agli indirizzi di emergenza e ai numeri di telefono assegnati, contattare l'operatore.

### <a name="acquire-numbers-for-new-teams-users"></a>Acquisire numeri per i nuovi Teams utenti

Per acquisire numeri per i nuovi Teams utenti, seguire questa procedura:

1. **Assegnare una Sistema telefonico licenza.** È possibile assegnare una Sistema telefonico agli utenti dal interfaccia di amministrazione di Microsoft 365 o usando PowerShell. Per altre informazioni, vedere [Assegnare Teams licenze per i componenti aggiuntivi agli utenti.](teams-add-on-licensing/assign-teams-add-on-licenses.md)

2. **Assicurati di essere in modalità Teams attiva.** Per verificare se l'organizzazione è in modalità Teams, nell'interfaccia di amministrazione di Teams passare a Impostazioni a livello di **organizzazione > Teams aggiornamento**. Per verificare se un utente è in Teams modalità Solo utenti, passare a **Utenti** e selezionare un account utente. Nella scheda **Account,** in **Teams,** verificare che la modalità di coesistenza sia impostata su "solo Teams lavoro".

3. **Creare e convalidare gli indirizzi di emergenza.** Nell'Teams di amministrazione passare a Posizioni **> indirizzi di emergenza** per configurare gli indirizzi di emergenza. Per altre informazioni, vedere Aggiungere, modificare o rimuovere una posizione per gli interventi di [emergenza per l'organizzazione.](add-change-remove-emergency-location-organization.md)

4. **Acquisire numeri.** Accedi al sito Web del tuo operatore per ordinare e acquisire numeri di telefono. Per un elenco dei siti Web degli operatori, vedere [Operatori](#operators). È necessario specificare l'ID tenant. Se non si conosce l'ID tenant, vedere Trovare [l'ID tenant](/onedrive/find-your-office-365-tenant-id) Microsoft 365 per altre informazioni.

5. **Assegnare numeri.** Una volta completato l'ordine, l'operatore carica i numeri nel tenant. Per visualizzare i numeri e il provider nell'interfaccia Teams di amministrazione, accedere a **Numeri > Telefono vocali**. Assegnare numeri agli utenti usando l'interfaccia Teams di amministrazione o PowerShell. Per altre informazioni, vedere [Assegnare numeri.](#assign-numbers)
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Spostare i numeri da Piani per chiamate a Connessione con operatore

1. Contattare l'operatore per convertire i numeri Connessione con operatore. Vedere [Operatori per](#operators) trovare il sito Web dell'operatore.

2. Dopo che l'operatore ha completato l'ordine di trasferimento, è possibile annullare l'assegnazione dei numeri di telefono del piano di chiamata degli utenti e rimuovere la licenza per il piano di chiamata. Quindi, l'operatore può caricare i numeri nel tenant.

3. Assegnare Connessione con operatore numeri di telefono agli utenti usando l'interfaccia Teams di amministrazione o PowerShell. Per altre informazioni, vedere [Assegnare numeri.](#assign-numbers)

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Spostare i numeri da Instradamento diretto a Connessione con operatore

1. Rimuovere il numero di telefono esistente dall'utente nel modo seguente:  

   Ottenere l'URI di riga on-prem esistente eseguendo il comando di PowerShell seguente:

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   Rimuovere l'URI di riga predefinito eseguendo il comando di PowerShell seguente:  

   ```
   Set-CsUser -identity <user> - OnPremLineURI $null 
   ```

2. Rimuovere qualsiasi PSTNUsage associato agli utenti, altrimenti le chiamate verranno instradati al gateway specificato in Utilizzo PSTN. Per informazioni su come rimuovere l'utilizzo di PSTN, [vedere Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps).

3. Accedi al sito Web del tuo operatore per ordinare e acquisire numeri di telefono. Per un elenco dei siti Web degli operatori, vedere [Operatori](#operators). È necessario specificare l'ID tenant. Se non si conosce l'ID tenant, vedere Trovare [l'ID tenant](/onedrive/find-your-office-365-tenant-id) Microsoft 365 per altre informazioni.

4. Una volta completato l'ordine, l'operatore carica i numeri nel tenant. Per visualizzare i numeri e il provider nell'interfaccia Teams di amministrazione, accedere a **Numeri > Telefono vocali**. Assegnare Connessione con operatore numeri di telefono agli utenti usando l'interfaccia Teams di amministrazione o PowerShell. Per altre informazioni, vedere [Assegnare numeri.](#assign-numbers)

   

### <a name="assign-numbers"></a>Assegnare numeri

Se si aggiungono nuovi utenti Teams o si spostano utenti esistenti in Connessione con operatore, la procedura per l'assegnazione dei numeri è la seguente:

Per assegnare numeri usando l'interfaccia Teams di amministrazione, passare a Telefono **numeri**. I passaggi sono gli stessi dell'assegnazione di numeri per i Piani per chiamate. Per altre informazioni, vedere [Assegnare un numero di telefono a un utente.](assign-change-or-remove-a-phone-number-for-a-user.md)

Per assegnare numeri usando PowerShell, usare il cmdlet Set-CsOnlineVoiceUser seguente:

```
Set-CsOnlineVoiceUser -Identity <user>  -TelephoneNumber <phone number> 
```

Ad esempio:

```
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

Per altre informazioni su come assegnare numeri di telefono agli utenti, vedere Assegnare, modificare o rimuovere un numero di telefono [per un utente.](assign-change-or-remove-a-phone-number-for-a-user.md)



## <a name="manage-your-operators"></a>Gestire gli operatori

Nella scheda Operatori personalizzati è possibile visualizzare gli operatori e il relativo stato e apportare le modifiche seguenti alle selezioni:  

- Gestire i servizi dell'operatore per paese
- Sospendere un operatore
- Rimuovere un operatore

> [!NOTE]
> Prima di rimuovere un operatore dall'organizzazione o da un paese, è necessario rimuovere tutti i numeri di telefono assegnati agli utenti dell'organizzazione o del paese e contattare l'operatore per rilasciare i numeri.

## <a name="operators"></a>Operatori

È possibile acquisire numeri di telefono dai seguenti operatori visitando i siti Web collegati qui:


|Operatore  |Sito Web operatore  |
|---------|---------|
|`BT`     |     https://www.globalservices.bt.com/en/aboutus/operator-connect        |
|`Deutsche Telekom`     |   https://cloud.telekom.de/de/blog/cloud-software/microsoft-teams-operator-connect      |
|`Intrado`     | https://insight.intrado.com/operator-connect       |
|`NTT`     |  https://www.hello.global.ntt/operator-connect       |
|`NuWave`     |   https://ipilot.io/microsoft-operator-connect/   |
|`Orange Business Services`     | https://www.orange-business.com/en/blogs/operator-connect-orange-and-microsoft-streamline-calling-for-teams-users        |
|`Pure IP`    | https://info.pure-ip.com/operator-connect        |
|`Rogers`    | https://www.rogers.com/business/products-and-solutions/microsoft-365-business-voice        |
|`TATA Communications`     |  https://www.tatacommunications.com/solutions/unified-communications/unified-communications-as-a-service/microsoft-teams-solutions/       |
|`Telenor`     | https://www.telenor.no/bedrift/telefoni/teams/operator-connect        |
|`Verizon`     |  https://www.verizon.com/business/resources/lp/operator-connect       |
