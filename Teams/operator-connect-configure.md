---
title: Configurare Operator Connect
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
description: Scopri di più su come configurare Operator Connect.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c37c6e52eac53e2cf3e43e45566243a6c83025a7
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240505"
---
# <a name="configure-operator-connect"></a>Configurare Operator Connect

Questo articolo descrive come configurare Operator Connect. Prima di configurare Operator Connect, assicurati di leggere [Plan for Operator Connect](operator-connect-plan.md) per informazioni sui prerequisiti e sulle licenze.

## <a name="enable-an-operator"></a>Abilitare un operatore

È possibile abilitare, modificare e rimuovere operatori nell'interfaccia di amministrazione di Teams. Nel riquadro di spostamento sinistro passare a **Operatori > vocali**.

Per abilitare un operatore:

1. **Scegli un operatore.** Nella scheda **Tutti gli operatori** filtra gli operatori disponibili per area geografica o servizio per trovare l'operatore più adatto alle tue esigenze vocali. Seleziona quindi l'operatore che vuoi abilitare.  

2. **Seleziona paesi.** In **Impostazioni operatore** seleziona i paesi che vuoi abilitare con l'operatore selezionato.

3. **Fornisci le informazioni di contatto** Le informazioni di contatto, inclusi il nome completo e l'indirizzo di posta elettronica, verranno condivise automaticamente con l'operatore. È possibile modificare queste informazioni in un secondo momento. Inoltre, dovrai fornire le dimensioni dell'azienda e avrai la possibilità di fornire il tuo numero di telefono. Gli operatori useranno queste informazioni per contattarti con altri dettagli su Operator Connect.

4. Accetta la notifica di trasferimento dati.

5. **Aggiungi il tuo operatore.** Seleziona **Aggiungi come operatore** per salvare.

## <a name="set-up-phone-numbers"></a>Configurare i numeri di telefono

La modalità di configurazione dei numeri di telefono varia a seconda che tu stia configurando i numeri per i nuovi utenti o spostando i numeri esistenti da Piani per chiamate Microsoft o Routing diretto.

- Se è necessario acquisire numeri di telefono per nuovi utenti, vedere [Acquisire numeri per i nuovi utenti di Teams](#acquire-numbers-for-new-teams-users).

- Se desideri spostare i numeri esistenti da Piani per chiamate a Operator Connect, vedi [Spostare numeri da Piani per chiamate a Operator Connect](#move-numbers-from-calling-plans-to-operator-connect).

- Se vuoi spostare numeri esistenti da Routing diretto a Connessione operatore, vedi [Spostare numeri da Routing diretto a Connessione operatore](#move-numbers-from-direct-routing-to-operator-connect).

### <a name="acquire-numbers-for-new-teams-users"></a>Acquisire numeri per i nuovi utenti di Teams

Per acquisire numeri per i nuovi utenti di Teams, seguire questa procedura:

1. **Assegna una licenza Sistema telefonico.** È possibile assegnare una licenza Sistema telefonico agli utenti dal interfaccia di amministrazione di Microsoft 365 o tramite PowerShell. Per altre informazioni, vedere [Assegnare licenze per i componenti aggiuntivi di Teams agli utenti](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. Gli utenti a cui verranno assegnati numeri di telefono acquisiti con Operator Connect devono essere in modalità TeamsOnly. Se l'organizzazione è in modalità TeamsOnly, tutti gli utenti sono in modalità TeamsOnly. Per verificarlo, nell'interfaccia di amministrazione di Teams passare alle **impostazioni di aggiornamento di Teams > Teams**. Se la tua organizzazione è in modalità Isole, controlla se specifici utenti sono in modalità TeamsOnly. Passare a **Utenti** e selezionare un account utente. Nella scheda **Account** , in **Aggiornamento di Teams,** la modalità di coesistenza deve essere impostata su "TeamsOnly".

3. **Acquisisci numeri.** Vai al sito Web del tuo operatore per ordinare e acquisire numeri di telefono. Per un elenco dei siti Web degli operatori, vai alla [directory Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Dovrai fornire il tuo ID tenant. Se non si conosce l'ID tenant, vedere [Trovare l'ID tenant di Microsoft 365](/onedrive/find-your-office-365-tenant-id) per altre informazioni.

4. **Assegna numeri.** Una volta completato l'ordine, l'operatore caricherà i numeri nel tenant. Puoi visualizzare i numeri e il provider nell'interfaccia di amministrazione di Teams accedendo a **Numeri di telefono > vocali**. Assegnare numeri agli utenti dall'interfaccia di amministrazione di Teams o usando PowerShell. Per altre informazioni, vedere [Assegnare numeri](#assign-numbers).

> [!NOTE]
> Oltre a [ottenere numeri di telefono per gli utenti](getting-phone-numbers-for-your-users.md), puoi ottenere numeri a pagamento o numeri verdi per servizi come i servizi di audioconferenza (per il bridge delle conferenze), gli operatori automatici e le code di chiamata (chiamati anche numeri di servizio). I numeri di servizio hanno una capacità di chiamate contemporanee superiore ai numeri di telefono per utenti o abbonati. Ad esempio, un numero di servizio può gestire centinaia di chiamate contemporaneamente, mentre il numero di telefono di un utente può gestire solo alcune chiamate contemporaneamente. Per ottenere i numeri di servizio, contatta il tuo operatore.

### <a name="emergency-addresses"></a>Indirizzi di emergenza

L'indirizzo per gli interventi di emergenza è una posizione statica associata a un numero. Dopo aver creato gli indirizzi di emergenza nell'interfaccia di amministrazione di Teams, la modalità di assegnazione o modifica degli indirizzi dipenderà dall'operatore.

Per assegnare numeri agli indirizzi di emergenza, l'operatore implementerà uno dei tre scenari seguenti:

- L'operatore assegna gli indirizzi di emergenza ai numeri di telefono e consente di modificarli in un secondo momento nell'interfaccia di amministrazione di Teams.

- L'operatore non assegna indirizzi e consente di assegnare indirizzi di emergenza ai numeri di telefono nell'interfaccia di amministrazione di Teams.

- L'operatore assegna gli indirizzi per gli interventi di emergenza ai numeri di telefono e non consente di modificarli. In questo scenario dovrai contattare l'operatore per apportare modifiche ai numeri di telefono e all'indirizzo di emergenza assegnato.

Per ulteriori informazioni sulle chiamate di emergenza, vedi [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md) e [Pianificare e configurare le chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md).

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Spostare numeri da Piani per chiamate a Operator Connect

1. Contatta l'operatore per trasferire i numeri in Operator Connect. Vedi [la directory Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) per trovare il sito Web del tuo operatore.

2. Dopo che l'operatore ha completato l'ordine di trasferimento, puoi annullare l'assegnazione dei numeri di telefono del piano per chiamate degli utenti e rimuovere la licenza per il piano per chiamate. L'operatore potrà quindi caricare i numeri nel tenant.

3. Assegnare numeri Operator Connect agli utenti usando l'interfaccia di amministrazione di Teams o PowerShell. Per altre informazioni, vedere [Assegnare numeri](#assign-numbers).

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Spostare i numeri dal routing diretto alla connessione operatore

Per spostare i numeri da Direct Routing a Operator Connect, il numero di routing diretto esistente caricato nel tenant dall'operatore deve essere rimosso dall'utente a cui è assegnato. Quindi, dopo aver eseguito la migrazione del numero a Operator Connect, è possibile assegnarlo di nuovo all'utente. Per passare dal routing diretto all'operatore Connettiti con numeri di telefono locali o online, segui i passaggi seguenti:

>[!IMPORTANT]
> Il numero di telefono non sarà più in servizio durante la migrazione, quindi coordinati con l'operatore Operator Connect prima di iniziare.

#### <a name="step-1---remove-existing-direct-routing-numbers"></a>Passaggio 1 - Rimuovere i numeri di routing diretto esistenti.

Verificare che all'utente sia assegnato un numero di routing diretto eseguendo il comando modulo PowerShell di Teams:

```PowerShell
Get-CsPhoneNumberAssignment -AssignedPstnTargetId <user> 
```

Controlla che `NumberType` sia DirectRouting.

La modalità di rimozione dei numeri di direct routing esistenti dipende dal fatto che il numero sia assegnato in locale o online. Per verificarlo, eseguire il comando del modulo powershell di Teams seguente:
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```

Se `OnPremLineUri` viene popolato con un numero di telefono E.164, il numero di telefono è stato assegnato in locale e sincronizzato con Microsoft 365.
    
**Per rimuovere i numeri di routing diretto assegnati in locale,** eseguire il comando di PowerShell Skype for Business Server seguente:
    
```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

La quantità di tempo necessaria per rendere effettiva la rimozione dipende dalla configurazione. Per verificare se il numero locale è stato rimosso e le modifiche sono state sincronizzate dalla versione locale a Microsoft 365, eseguire il comando modulo PowerShell di Teams seguente: 
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```
       
Dopo la sincronizzazione delle modifiche con la directory online di Microsoft 365, l'output previsto è: 
       
 ```console
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              : 
```

<br> **Per rimuovere i numeri di routing diretto online assegnati online,** eseguire il comando modulo PowerShell di Teams seguente:


```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

La rimozione del numero di telefono può richiedere fino a 10 minuti. In rari casi, possono essere necessario fino a 24 ore. Per verificare se il numero di telefono è stato rimosso, eseguire il comando modulo PowerShell di Teams seguente: 


```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

#### <a name="step-2---remove-the-online-voice-routing-policy-associated-with-your-user"></a>Passaggio 2 - Rimuovere i criteri di routing vocale online associati all'utente

Una volta che il numero non è assegnato, rimuovere il criterio di routing vocale online associato all'utente eseguendo il seguente comando del modulo di Teams PowerShell:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="step-3---acquire-phone-numbers"></a>Passaggio 3 - Acquisire numeri di telefono

Vai al sito Web del tuo operatore per ordinare e acquisire numeri di telefono. Per trovare il sito Web degli operatori, vedi la [directory Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Dovrai fornire il tuo ID tenant. Se non si conosce l'ID tenant, vedere [Trovare l'ID tenant di Microsoft 365](/onedrive/find-your-office-365-tenant-id) per altre informazioni.

#### <a name="step-4---assign-phone-numbers"></a>Passaggio 4 - Assegnare numeri di telefono

Una volta completato l'ordine, l'operatore caricherà i numeri nel tenant. Puoi visualizzare i numeri e il provider nell'interfaccia di amministrazione di Teams accedendo a **Numeri di telefono > vocali**. Assegnare numeri Operator Connect agli utenti usando l'interfaccia di amministrazione di Teams o PowerShell. Per altre informazioni, vedere [Assegnare numeri](#assign-numbers).

### <a name="assign-numbers"></a>Assegna numeri

Per informazioni su come assegnare numeri di telefono agli utenti, vedi [Assegnare, modificare o rimuovere un numero di telefono per un utente](assign-change-or-remove-a-phone-number-for-a-user.md).

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

## <a name="related-topics"></a>Argomenti correlati

- [Pianificare gli operatori automatici di Teams e le code di chiamata](plan-auto-attendant-call-queue.md)
