---
title: Configurare Teams Phone Mobile
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
ms.reviewer: crowe
search.appverid: MET150
description: Altre informazioni su come configurare Teams Phone Mobile.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f05eeb70808d39b721d1b33ba252c8257433c4a
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584178"
---
# <a name="configure-teams-phone-mobile"></a>Configurare Teams Phone Mobile

Per un elenco degli operatori che partecipano al programma di Operatore di telefonia mobile di Microsoft Teams e dei paesi o delle aree geografiche in cui il loro servizio è disponibile, vedi [Microsoft 365 Teams Phone Mobile](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/teams-phone-mobile).

Questo articolo descrive come configurare Teams Phone Mobile. Prima di configurare Teams Phone Mobile, assicurati di leggere [Plan for Teams Phone Mobile](operator-connect-mobile-plan.md) per informazioni su vantaggi, prerequisiti e licenze.

## <a name="enable-an-operator"></a>Abilitare un operatore

È possibile abilitare, modificare e rimuovere operatori nell'interfaccia di amministrazione di Teams. Nel riquadro di spostamento sinistro passare a **Operatori > vocali**.

Per abilitare un operatore:

1. Scegliere un operatore che supporti Teams Phone Mobile. Nella scheda **Tutti gli operatori** , filtrare gli operatori disponibili per area geografica o servizio per trovare l'operatore giusto che supporta Teams Phone Mobile. Seleziona quindi l'operatore che vuoi abilitare.

2. In **Impostazioni operatore** seleziona i paesi che vuoi abilitare con l'operatore selezionato.

3. **Fornisci le informazioni di contatto.** Le informazioni di contatto, inclusi il nome completo e l'indirizzo di posta elettronica, verranno condivise automaticamente con l'operatore. È possibile modificare queste informazioni in un secondo momento. Inoltre, dovrai fornire le dimensioni dell'azienda e avrai la possibilità di fornire il tuo numero di telefono. Gli operatori useranno queste informazioni per contattarti con altri dettagli su Teams Phone Mobile.

4. Accetta la notifica di trasferimento dati.

5. Seleziona **Aggiungi come operatore** per salvare.

## <a name="set-up-phone-numbers"></a>Configurare i numeri di telefono

Se vuoi aggiungere i numeri di telefono abilitati per la SIM a pagamento della tua azienda esistente a Teams, contatta il tuo operatore per assicurarti di avere l'abbonamento a Teams Phone Mobile idoneo e loro possono caricare i tuoi numeri su Teams. Dopo che l'operatore ha completato l'ordine, è possibile assegnarli agli utenti. 

Per trovare il sito Web del tuo operatore, consulta [l'elenco Microsoft 365 Teams Phone Mobile](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory).

Dovrai fornire il tuo ID tenant. Se non si conosce l'ID tenant, vedere [Trovare l'ID tenant di Microsoft 365](/onedrive/find-your-office-365-tenant-id.md). Potresti trasferire un numero di telefono fisso o un numero di linea in un abbonamento wireless vocale se è supportato nella tua area geografica e dal tuo operatore. 

La modalità di configurazione dei numeri di telefono varia a seconda che tu stia configurando i numeri per i nuovi utenti o spostando i numeri esistenti da Piani per chiamate Microsoft, Connessione operatore o Routing diretto.

- [Acquisire numeri per i nuovi utenti di Teams](#acquire-numbers-for-new-teams-users).  

- [Spostare i numeri da Piani per chiamate a Teams Phone Mobile](#move-numbers-from-calling-plans-to-teams-phone-mobile).  

- [Spostare i numeri da Operator Connect a Teams Phone Mobile](#move-numbers-from-operator-connect-to-teams-phone-mobile).  

- [Spostare i numeri dal routing diretto a Teams Phone Mobile](#move-numbers-from-direct-routing-to-teams-phone-mobile).  


### <a name="assign-numbers-to-emergency-addresses"></a>Assegnare numeri agli indirizzi per gli interventi di emergenza

L'indirizzo per gli interventi di emergenza è una posizione statica associata a un numero quando è accessibile tramite gli endpoint/client di Microsoft Teams. Dopo aver creato gli indirizzi di emergenza nell'interfaccia di amministrazione di Teams, la modalità di assegnazione o modifica degli indirizzi dipenderà dall'operatore.

Per assegnare numeri agli indirizzi di emergenza utilizzati dagli endpoint di Microsoft Teams, l'operatore implementerà uno dei tre scenari seguenti:

- L'operatore assegna gli indirizzi di emergenza ai numeri di telefono e consente di modificarli in un secondo momento nell'interfaccia di amministrazione di Teams.

- L'operatore non assegna indirizzi e consente di assegnare indirizzi di emergenza ai numeri di telefono nell'interfaccia di amministrazione di Teams.

- L'operatore assegna gli indirizzi per gli interventi di emergenza ai numeri di telefono e non consente di modificarli. In questo scenario dovrai contattare l'operatore per apportare modifiche ai numeri di telefono e all'indirizzo di emergenza assegnato.

Quando le chiamate vengono effettuate tramite il dialer nativo dello smartphone abilitato per la SIM, l'operatore può utilizzare le coordinate geografiche o la torre cellulare che gestisce la chiamata per approssimare la posizione di emergenza per ricevere assistenza.

Per ulteriori informazioni sulle chiamate di emergenza, vedi [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md) e [Pianificare e configurare le chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md).

### <a name="acquire-numbers-for-new-teams-users"></a>Acquisire numeri per i nuovi utenti di Teams

Per acquisire numeri per i nuovi utenti di Teams, seguire questa procedura:

1. **Assegnare una licenza Sistema telefonico e una licenza per il componente aggiuntivo Teams Phone Mobile.** È possibile assegnare una licenza Sistema telefonico e una licenza per il componente aggiuntivo Teams Phone Mobile agli utenti dal interfaccia di amministrazione di Microsoft 365 o tramite PowerShell. Per altre informazioni, vedere [Assegnare licenze per i componenti aggiuntivi di Teams agli utenti](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. **Gli utenti a cui verranno assegnati numeri di telefono acquisiti con Teams Phone Mobile devono essere in modalità TeamsOnly.** Se l'organizzazione è in modalità TeamsOnly, tutti gli utenti sono in modalità TeamsOnly. 

   Per verificarlo, nell'interfaccia di amministrazione di Teams passare alle **impostazioni di aggiornamento di Teams > Teams**. Se la tua organizzazione è in modalità Isole, controlla se specifici utenti sono in modalità TeamsOnly. Passare a **Utenti** e selezionare un account utente. Nella scheda **Account** , in **Aggiornamento di Teams,** la modalità di coesistenza deve essere impostata su TeamsOnly.

3. **Acquisisci numeri.** Vai al sito Web del tuo operatore o contatta il tuo operatore per ordinare e acquisire numeri di telefono abilitati per la SIM mobile con il servizio Teams Phone Mobile abilitato. 

   Dopo aver completato l'ordine, l'operatore caricherà i numeri di cellulare abilitati per la SIM nel tenant. Puoi visualizzare i numeri e il provider nell'interfaccia di amministrazione di Teams accedendo a **Numeri di telefono > vocali**. 

4. **Assegna numeri.** È possibile assegnare numeri agli utenti dall'interfaccia di amministrazione di Teams o tramite PowerShell. Per altre informazioni, vedere [Assegnare numeri](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-calling-plans-to-teams-phone-mobile"></a>Spostare numeri da Piani per chiamate a Teams Phone Mobile

1. Assicurarsi di avere abbonamenti Microsoft 365 idonei per Teams Phone Mobile e la licenza per il componente aggiuntivo Teams Phone Mobile. Devi [rimuovere il numero di telefono da spostare per i rispettivi utenti](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user). 

2. Contatta il tuo operatore per trasferire i tuoi numeri in Teams Phone Mobile con un piano vocale wireless idoneo abilitato per la SIM. 

3. Dopo che l'operatore avrà completato l'ordine di trasferimento, l'operatore caricherà i numeri nel tenant.  Puoi visualizzare i numeri e il provider nell'interfaccia di amministrazione di Teams accedendo a **Numeri di telefono > vocali**. 

4. È possibile assegnare numeri agli utenti usando l'interfaccia di amministrazione di Teams o PowerShell. Per altre informazioni, vedere [Assegnare numeri](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-operator-connect-to-teams-phone-mobile"></a>Spostare numeri da Operator Connect a Teams Phone Mobile

1. Assicurarsi di avere abbonamenti Microsoft 365 idonei per Teams Phone Mobile e la licenza per il componente aggiuntivo Teams Phone Mobile. Devi [rimuovere il numero di telefono da spostare per i rispettivi utenti](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user). Contatta il provider operator connect esistente per rimuovere i numeri di telefono dal tenant.

2. Contatta il tuo operatore per trasferire i tuoi numeri in Teams Phone Mobile con un piano vocale wireless idoneo abilitato per la SIM. 

3. Dopo che l'operatore avrà completato l'ordine di trasferimento, l'operatore caricherà i numeri nel tenant. Puoi visualizzare i numeri e il provider nell'interfaccia di amministrazione di Teams accedendo a **Numeri di telefono > vocali**. 

4. È possibile assegnare numeri agli utenti usando l'interfaccia di amministrazione di Teams o PowerShell. Per altre informazioni, vedere [Assegnare numeri](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-direct-routing-to-teams-phone-mobile"></a>Spostare i numeri dal routing diretto a Teams Phone Mobile   

Per spostare i numeri dal routing diretto a Teams Phone Mobile, è necessario completare i passaggi seguenti:

1. [Determinare se i numeri di direct routing esistenti sono assegnati online o in locale](#determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises).

2. [Eseguire la migrazione dei numeri da Direct Routing a Teams Phone Mobile](#migrate-the-numbers-from-direct-routing-to-teams-phone-mobile).

2. [Rimuovere i criteri di routing vocale online associati all'utente](#remove-the-online-voice-routing-policy-associated-with-your-user).

3. [Acquisisci numeri di telefono](#acquire-phone-numbers).

4. [Assegna numeri di telefono](#assign-phone-numbers).

Questi passaggi sono descritti in modo più dettagliato nelle sezioni seguenti.

#### <a name="determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises"></a>Determinare se i numeri di direct routing esistenti sono assegnati online o in locale.

La modalità di rimozione dei numeri di direct routing esistenti dipende dal fatto che il numero sia assegnato in locale o online.

1. Prima di tutto, verificare che all'utente sia assegnato un numero di routing diretto eseguendo il comando PowerShell di Teams seguente. NumberType deve essere DirectRouting:

   ```PowerShell
   Get-CsPhoneNumberAssignment -AssignedPstnTargetId <user> 
   ```

2. Determinare se il numero è assegnato online o in locale eseguendo il comando PowerShell di Teams seguente:

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

   Se OnPremLineUri viene popolato con un numero di telefono E.164, il numero di telefono è stato assegnato in locale e sincronizzato con Microsoft 365.

#### <a name="migrate-the-numbers-from-direct-routing-to-teams-phone-mobile"></a>Eseguire la migrazione dei numeri da Direct Routing a Teams Phone Mobile

Per eseguire la migrazione dei numeri, eseguire la procedura seguente.  

> [!Important]
> Durante la migrazione, il numero di telefono non sarà più disponibile. Coordinarsi con l'operatore Teams Phone Mobile prima di iniziare la migrazione.

- **Per eseguire la migrazione dei numeri direct routing assegnati online a Teams Phone Mobile**, contattare l'operatore. Per trovare il sito Web del tuo operatore, vedi [Directory di Microsoft 365 Teams Phone Mobile](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). In base alla data e all'ora stabilite, l'operatore eseguirà la migrazione dei numeri da Direct Routing a Teams Phone Mobile. Ciò può implicare la rimozione del numero di telefono di cui viene eseguita la migrazione dal tenant e aggiungerlo di nuovo come nuovo numero di telefono associato a Teams Phone Mobile.

- **Per eseguire la migrazione dei numeri di routing diretto assegnati in locale a Teams Phone Mobile**, eseguire il comando di PowerShell Skype for Business Server seguente:

   ```PowerShell
   Set-CsUser -Identity <user> -LineURI $null 
   ```
  Per verificare se il numero locale è stato rimosso e le modifiche sono state sincronizzate dalla versione locale a Microsoft 365, eseguire il comando powershell di Teams seguente:

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

Dopo la sincronizzazione delle modifiche con la directory online di Microsoft 365, l'output previsto è:

```
ConsoleCopy
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              
```

Per verificare se il numero di telefono è stato rimosso, eseguire il comando PowerShell di Teams seguente:

```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

> [!NOTE]
> La quantità di tempo necessaria per rendere effettiva la rimozione dipende dalla configurazione. La rimozione del numero di telefono può richiedere fino a 10 minuti, in rari casi possono richiedere fino a 24 ore. 

#### <a name="remove-the-online-voice-routing-policy-associated-with-your-user"></a>Rimuovere i criteri di routing vocale online associati all'utente

Dopo aver rimosso l'assegnazione del numero, rimuovere i criteri di routing vocale online associati all'utente eseguendo il comando di PowerShell di Teams seguente:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="acquire-phone-numbers"></a>Ottieni i numeri di telefono

Contatta il tuo operatore per trasferire i tuoi numeri in Teams Phone Mobile con un piano vocale wireless idoneo abilitato per la SIM.

Dopo aver completato l'ordine, l'operatore caricherà i numeri nel tenant. Puoi visualizzare i numeri e il provider nell'interfaccia di amministrazione di Teams accedendo a **Numeri di telefono > vocali**. 

#### <a name="assign-phone-numbers"></a>Assegnare numeri di telefono

È possibile assegnare numeri di Teams Phone Mobile agli utenti usando l'interfaccia di amministrazione di Teams o PowerShell. Per altre informazioni, vedere [Assegnare numeri](assign-change-or-remove-a-phone-number-for-a-user.md).


## <a name="manage-your-operators"></a>Gestire gli operatori

Nella scheda **Operatori personali** è possibile visualizzare gli operatori e il relativo stato e apportare le modifiche seguenti alle selezioni:  

- Gestire i servizi operatore per paese
- Sospendere un operatore
- Rimuovere un operatore

> [!NOTE]
> Prima di rimuovere un operatore dalla tua organizzazione o da un paese, devi rimuovere tutti i numeri di telefono assegnati agli utenti dell'organizzazione o del paese e contattare l'operatore per rilasciare i numeri.

## <a name="release-numbers"></a>Numeri di rilascio

Per rilasciare i numeri di telefono dall'interfaccia di amministrazione di Teams, vai alla pagina **Numeri di telefono** e seleziona un numero.

- Se il numero di telefono non è assegnato a un utente, seleziona **Rilascia**.

- Se il numero di telefono è assegnato a un utente, dovrai annullare l'assegnazione del numero. Seleziona **Modifica**, quindi **Rimuovi utente**. Dopo aver salvato le modifiche, selezionare **Rilascia**.

## <a name="manage-user-incoming-calling-policies"></a>Gestire i criteri per le chiamate in arrivo degli utenti

È possibile gestire i criteri per le chiamate in arrivo di un utente usando l'interfaccia di amministrazione di Teams o PowerShell. Per impostazione predefinita, le chiamate in arrivo per gli utenti di Teams Phone Mobile squilleranno prima dell'app Teams sul dispositivo mobile abilitato per la SIM dell'utente. 

- Se la preferenza per le chiamate in arrivo di un utente è impostata sull'app Teams, tutte le chiamate in arrivo squilleranno contemporaneamente sull'app Teams sullo smartphone abilitato per la SIM e su qualsiasi altro endpoint di Teams su altri dispositivi. 

- Se la preferenza per le chiamate in arrivo di un utente è impostata sul dialer nativo, tutte le chiamate in arrivo squillano sul dialer nativo sullo smartphone abilitato per la SIM e squillano contemporaneamente tutti gli altri endpoint di Teams su altri dispositivi. 

### <a name="use-the-teams-admin-center"></a>Usare l'interfaccia di amministrazione di Teams

Per gestire i criteri per le chiamate in arrivo di un utente tramite l'interfaccia di amministrazione di Teams:

1. Nella scheda voce seleziona **Criteri dispositivi mobili**. 

2. Per aggiungere un nuovo criterio per dispositivi mobili, fare clic su **Aggiungi**.

3. Selezionare un nome, aggiungere una descrizione del criterio e scegliere una delle opzioni seguenti nell'elenco a **discesa Selezionare una dialer mobile** :

   -  **Microsoft Teams** per far squillare prima l'app Teams sullo smartphone abilitato per la SIM. 

   - **Nativo Dialer** per far squillare prima il Dialer nativo sullo smartphone abilitato per la SIM.

4. Assegnare i criteri agli utenti. Vedere [Assegnare criteri](assign-policies-users-and-groups.md).


### <a name="use-powershell"></a>Usare PowerShell

1. Connettersi al tenant: Connect-MicrosoftTeams.
 
2. Creare criteri per le chiamate in arrivo per far squillare prima il dialer nativo o l'app Teams. È possibile scegliere il nome del criterio. Questo esempio usa TeamsFirst e NativeFirst. 

   ```PowerShell
   New-CsTeamsMobilityPolicy -identity TeamsFirst -MobileDialerPreference Teams 
   New-CsTeamsMobilityPolicy -identity NativeFirst -MobileDialerPreference Native 
   ```

3. Concedere criteri agli utenti: 

   ```PowerShell
   Grant-CsTeamsMobilityPolicy NativeFirst -Identity user@xyz.onmicrosoft.com
   Grant-CsTeamsMobilityPolicy TeamsFirst -Identity user@xyz.onmicrosoft.com
   ```

4. Controllare i criteri utente: 

   ```PowerShell
   get-CsUserpolicyassignment -identity user@xyz.onmicrosoft.com
   ```
 
 5. Controlla tutte le opzioni dei criteri di mobilità: 
    
    ```PowerShell
    Get-CsTeamsMobilityPolicy
    ```  

 








