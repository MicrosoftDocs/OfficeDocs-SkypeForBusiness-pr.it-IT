---
title: Configurare Connessione con operatore
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 09/30/2021
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
ms.openlocfilehash: 9abb37e195e602281c8fad0cdf052e35bf35cc67
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2022
ms.locfileid: "62181069"
---
# <a name="configure-operator-connect"></a>Configurare Connessione con operatore

Questo articolo descrive come configurare Connessione con operatore. Prima di configurare Connessione con operatore, leggere Pianificare [](operator-connect-plan.md) Connessione con operatore informazioni sui prerequisiti e sulle licenze.

## <a name="enable-an-operator"></a>Abilitare un operatore

È possibile abilitare, modificare e rimuovere operatori nell'Teams di amministrazione. Nel riquadro di spostamento sinistro passare a Operatori > **vocali**.

Per abilitare un operatore:

1. **Scegliere un operatore.** Nella scheda **Tutti gli operatori** filtrare gli operatori disponibili in base all'area geografica o al servizio per trovare l'operatore più giusto per le proprie esigenze vocali. Selezionare quindi l'operatore da abilitare.  

2. **Selezionare i paesi.** In **Impostazioni operatore** selezionare i paesi da abilitare con l'operatore selezionato.

3. **Fornisci informazioni di contatto** Le informazioni di contatto, inclusi il nome completo e l'indirizzo di posta elettronica, verranno condivise automaticamente con l'operatore. È possibile modificare queste informazioni in un secondo momento. Inoltre, dovrai fornire le dimensioni dell'azienda e avrai la possibilità di fornire il tuo numero di telefono. Gli operatori useranno queste informazioni per contattare l'utente con altri dettagli sulla Connessione con operatore.

4. Accettare l'avviso di trasferimento dei dati.

5. **Aggiungere l'operatore.** Selezionare **Aggiungi come operatore per** salvare.

## <a name="set-up-phone-numbers"></a>Configurare i numeri di telefono

La modalità di configurazione dei numeri di telefono dipende dalla configurazione dei numeri per i nuovi utenti o dallo spostamento dei numeri esistenti da Piani per chiamate Microsoft o Routing diretto.

- Se è necessario acquisire numeri di telefono per i nuovi utenti, vedere Acquisire numeri per i nuovi utenti [Teams nuovi utenti](#acquire-numbers-for-new-teams-users).

- Per spostare i numeri esistenti da Piani per chiamate a Connessione con operatore, vedere Spostare i numeri da Piani per chiamate a [Connessione con operatore](#move-numbers-from-calling-plans-to-operator-connect).

- Per spostare i numeri esistenti da Instradamento diretto a Connessione con operatore, vedere Spostare i numeri da Instradamento diretto [a Connessione con operatore](#move-numbers-from-direct-routing-to-operator-connect).

### <a name="acquire-numbers-for-new-teams-users"></a>Acquisire numeri per i nuovi Teams utenti

Per acquisire numeri per i nuovi Teams utenti, seguire questa procedura:

1. **Assegnare una Sistema telefonico licenza.** È possibile assegnare una Sistema telefonico agli utenti dal interfaccia di amministrazione di Microsoft 365 o usando PowerShell. Per altre informazioni, vedere [Assegnare Teams licenze per i componenti aggiuntivi agli utenti.](teams-add-on-licensing/assign-teams-add-on-licenses.md)

2. Gli utenti a cui verranno assegnati numeri di telefono acquisiti con Connessione con operatore devono essere in modalità TeamsOnly. Se l'organizzazione è in modalità TeamsOnly, tutti gli utenti sono in modalità TeamsOnly. Per verificare questo problema, nell'interfaccia Teams di amministrazione passare a impostazioni Teams > Teams **di aggiornamento.** Se l'organizzazione è in modalità Isole, verificare se specifici utenti sono in modalità TeamsOnly. Passare a **Utenti** e selezionare un account utente. Nella scheda **Account,** in **Teams,** la modalità di coesistenza deve essere impostata su 'TeamsOnly'.

3. **Acquisire numeri.** Accedi al sito Web del tuo operatore per ordinare e acquisire numeri di telefono. Per un elenco dei siti Web degli operatori, passare alla [directory Microsoft 365 Connessione con operatore.](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) È necessario specificare l'ID tenant. Se non si conosce l'ID tenant, vedere Trovare [l'ID tenant Microsoft 365 per](/onedrive/find-your-office-365-tenant-id) altre informazioni.

4. **Assegnare numeri.** Una volta completato l'ordine, l'operatore carica i numeri nel tenant. Per visualizzare i numeri e il provider nell'interfaccia Teams di amministrazione, accedere a Numeri > Telefono **vocali**. Assegnare numeri agli utenti dall'Teams di amministrazione o usando PowerShell. Per altre informazioni, vedere [Assegnare numeri.](#assign-numbers)

> [!NOTE]
> Oltre a ottenere numeri di telefono per gli [utenti,](getting-phone-numbers-for-your-users.md)è possibile ottenere numeri a numero verde o a numero verde per servizi come audioconferenza (per bridge di conferenza), Operatori automatici e Code di chiamata (detti anche numeri di servizio). I numeri di servizio hanno una capacità di chiamate contemporanee superiore ai numeri di telefono per utenti o abbonati. Ad esempio, un numero di servizio può gestire centinaia di chiamate contemporaneamente, mentre il numero di telefono di un utente può gestire solo alcune chiamate contemporaneamente. Per ottenere i numeri di servizio, contattare l'operatore.

### <a name="emergency-addresses"></a>Indirizzi di emergenza

L'indirizzo di emergenza è una posizione statica associata a un numero. Dopo aver creato gli indirizzi di emergenza nell'Teams di amministrazione, la modalità di assegnazione o modifica degli indirizzi dipenderà dall'operatore.

Per assegnare numeri agli indirizzi di emergenza, l'operatore implementerà uno dei tre scenari seguenti:

- L'operatore assegna gli indirizzi di emergenza ai numeri di telefono e consente di modificarli in un secondo momento nell'Teams di amministrazione.

- L'operatore non assegna indirizzi e consente di assegnare indirizzi di emergenza ai numeri di telefono nell'interfaccia Teams di amministrazione.

- L'operatore assegna gli indirizzi di emergenza ai numeri di telefono e non consente di modificarli. In questo scenario, è necessario contattare l'operatore per apportare modifiche ai numeri di telefono e all'indirizzo di emergenza assegnato.

Per altre informazioni sulle chiamate di emergenza, vedere [Gestire le chiamate](what-are-emergency-locations-addresses-and-call-routing.md) di emergenza e Pianificare e configurare le chiamate di emergenza [dinamiche.](configure-dynamic-emergency-calling.md)

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Spostare i numeri da Piani per chiamate a Connessione con operatore

1. Contattare l'operatore per convertire i numeri in Connessione con operatore. Vedere [Microsoft 365 Connessione con operatore directory per](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) trovare il sito Web dell'operatore.

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
   Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <value of OnPremLineURI> -PhoneNumberType DirectRouting 
   ```

2. Rimuovere qualsiasi PSTNUsage associato agli utenti, altrimenti le chiamate verranno instradati al gateway specificato in Utilizzo PSTN. Per informazioni su come rimuovere l'utilizzo di PSTN, [vedere Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps).

3. Accedi al sito Web del tuo operatore per ordinare e acquisire numeri di telefono. Per trovare il sito Web degli operatori, vedere la [directory Microsoft 365 Connessione con operatore.](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) È necessario specificare l'ID tenant. Se non si conosce l'ID tenant, vedere Trovare [l'ID tenant Microsoft 365 per](/onedrive/find-your-office-365-tenant-id) altre informazioni.

4. Una volta completato l'ordine, l'operatore carica i numeri nel tenant. Per visualizzare i numeri e il provider nell'interfaccia Teams di amministrazione, accedere a Numeri > Telefono **vocali**. Assegnare Connessione con operatore numeri di telefono agli utenti usando l'interfaccia Teams di amministrazione o PowerShell. Per altre informazioni, vedere [Assegnare numeri.](#assign-numbers)

### <a name="assign-numbers"></a>Assegnare numeri

Per informazioni su come assegnare numeri di telefono agli utenti, vedere Assegnare, modificare o rimuovere un numero di telefono [per un utente.](assign-change-or-remove-a-phone-number-for-a-user.md)

## <a name="manage-your-operators"></a>Gestire gli operatori

Nella scheda **Operatori** personalizzati è possibile visualizzare gli operatori e il relativo stato e apportare le modifiche seguenti alle selezioni:  

- Gestire i servizi dell'operatore per paese
- Sospendere un operatore
- Rimuovere un operatore

> [!NOTE]
> Prima di rimuovere un operatore dall'organizzazione o da un paese, è necessario rimuovere tutti i numeri di telefono assegnati agli utenti dell'organizzazione o del paese e contattare l'operatore per rilasciare i numeri.

## <a name="release-numbers"></a>Numeri di rilascio

Per rilasciare i numeri di telefono dall'Teams di amministrazione, passare alla pagina **Telefono numeri** di telefono e selezionare un numero.

- Se il numero di telefono non è assegnato a un utente, selezionare **Rilascia**.

- Se il numero di telefono è assegnato a un utente, è necessario annullare l'assegnazione del numero. Selezionare **Modifica**, quindi **Rimuovi utente**. Dopo aver salvato le modifiche, selezionare **Rilascia**.

## <a name="related-topics"></a>Argomenti correlati

- [Pianificare Teams operatori automatici e code di chiamata](plan-auto-attendant-call-queue.md)
