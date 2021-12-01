---
title: Configurare le Connessione con operatore conferenza
author: DaniEASmith
ms.author: danismith
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
description: Altre informazioni su come configurare le conferenze Connessione con operatore conferenza.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87358190d919519b39494576a05235df26ad4c7a
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257523"
---
# <a name="configure-operator-connect-conferencing"></a>Configurare le Connessione con operatore conferenza

Questo articolo descrive in dettaglio come configurare le conferenze Connessione con operatore per l'organizzazione e gli utenti.

Prima di configurare le conferenze Connessione con operatore, vedere Pianificare Connessione con operatore [conferenza](operator-connect-conferencing-plan.md) per informazioni sui vantaggi e i requisiti di licenza.

Gli argomenti trattati in questo articolo includono:

- [Configurare un operatore](#set-up-an-operator)
- [Acquisire numeri per il bridge di audioconferenza](#acquire-numbers-for-your-audio-conferencing-bridge)
- [Modificare i numeri di telefono predefiniti inclusi negli inviti alla riunione degli utenti](#change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users)
- [Invio di chiamate in uscita da Microsoft Teams riunioni tramite un operatore](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)
- [Gestire gli operatori](#manage-your-operators)
- [Numeri di rilascio dal bridge di audioconferenza](#release-numbers-from-your-audio-conferencing-bridge)
- [Altre informazioni sulla gestione delle audioconferenze Microsoft](#additional-information-on-managing-microsoft-audio-conferencing)

## <a name="set-up-an-operator"></a>Configurare un operatore

È possibile configurare, modificare e rimuovere operatori nell'Teams di amministrazione. Nel riquadro di spostamento sinistro passare a Operatori > **vocali.**

Per configurare un operatore:

1. **Scegliere un operatore.**   Nella scheda  **Tutti gli operatori** filtrare gli operatori disponibili in base all'area geografica o al servizio per trovare l'operatore più giusto per le proprie esigenze   vocali. Selezionare quindi l'operatore da usare. Per Connessione con operatore conferenza, verificare che l'operatore abbia **l'opzione Servizi di** conferenza elencata come prodotto disponibile.

2. **Selezionare i paesi.**   In  **Impostazioni operatore** selezionare i paesi da abilitare con l'operatore selezionato.

3. **Fornisci informazioni di contatto**   Le informazioni di contatto, inclusi il nome completo e l'indirizzo di posta elettronica, verranno condivise con l'operatore. È possibile modificare queste informazioni in un secondo momento. Inoltre, dovrai fornire le dimensioni dell'azienda, con l'opzione per fornire il tuo numero di telefono. Gli operatori usano queste informazioni per contattare l'utente con altri dettagli su Connessione con operatore Conferenza telefonica.

4. Accettare l'avviso di trasferimento dei dati.

5. **Aggiungere l'operatore.**   Selezionare  **Aggiungi come operatore per**   salvare.

## <a name="acquire-numbers-for-your-audio-conferencing-bridge"></a>Acquisire numeri per il bridge di audioconferenza

Il bridge di audioconferenza dell'organizzazione include i numeri di telefono disponibili per tutti gli utenti dell'organizzazione per partecipare a Microsoft Teams riunioni con numeri di telefono PSTN. È possibile visualizzare i numeri di telefono associati al bridge di audioconferenza dell'organizzazione nell'interfaccia di amministrazione di Teams in Riunioni **> Bridge di conferenza**.

Per acquisire i numeri di telefono per il bridge di audioconferenza, seguire questa procedura:

1. **Abbonamento a Audio Conferencing Standard o Connessione con operatore Conferencing.** Gli utenti che devono Connessione con operatore numeri di conferenza per partecipare alle riunioni che organizzano devono avere una licenza di abbonamento a Audio Conferencing Standard o una licenza Connessione con operatore Conferencing assegnata. Per altre informazioni, vedere [Pianificare le conferenze Connessione con operatore.](operator-connect-conferencing-plan.md)

2. **Acquisire numeri.**   Accedi al sito Web del tuo operatore per ordinare e acquisire numeri di telefono. Per un elenco dei siti Web degli operatori, passare alla [directory Microsoft 365 Connessione con operatore.](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) È necessario specificare l'ID tenant. Se non si conosce l'ID tenant, vedere Trovare [l'ID tenant Microsoft 365 tenant.](/onedrive/find-your-office-365-tenant-id) Una volta completato l'ordine, l'operatore carica i numeri nel tenant. Per visualizzare i numeri e il provider nell'interfaccia Teams di amministrazione, accedere a Numeri > Telefono **vocali.**

3. **Assegnare numeri al bridge di audioconferenza.** È possibile assegnare numeri al bridge di audioconferenza dall'interfaccia di amministrazione di Teams riunioni in Riunioni > Bridge di **conferenza > Aggiungi**. Per altre informazioni, vedere [Modificare i numeri di telefono nel bridge di audioconferenza.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

>[!NOTE]
>Non è possibile assegnare i Connessione con operatore conferenza come numeri predefiniti di un bridge. Una volta assegnato un numero di telefono al bridge di  audioconferenza, il numero verrà elencato nella pagina Trova un numero locale incluso negli inviti a riunioni di utenti dell'organizzazione con una licenza di audioconferenza o una licenza di conferenza telefonica Connessione con operatore.
>
>Per instradare le chiamate in uscita tramite un operatore, vedere la sezione Invio di chiamate in uscita da riunioni Teams tramite un [**operatore**](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator) più avanti in questo articolo.

## <a name="change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users"></a>Modificare i numeri di telefono predefiniti inclusi negli inviti alla riunione degli utenti

 Questo passaggio è facoltativo.

I numeri di telefono predefiniti di un utente sono quelli inclusi negli inviti alle riunioni quando pianificano una riunione. È possibile aggiornare i numeri di telefono inclusi negli inviti alla riunione degli utenti nell'interfaccia di amministrazione di Teams in Utenti **> Gestisci utenti**. Per aggiornare i numeri di telefono inclusi negli inviti alla riunione degli utenti, selezionare l'utente e selezionare **Modifica** nella sezione **Audioconferenza.**

Dopo l'applicazione delle modifiche, i nuovi inviti alle riunioni degli organizzatori includeranno i nuovi numeri di telefono predefiniti. Tuttavia, gli inviti alle riunioni esistenti pianificati prima della modifica manderanno i numeri predefiniti originali.

## <a name="sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator"></a>Invio di chiamate in uscita da Microsoft Teams riunioni tramite un operatore

Se si ha un abbonamento a Microsoft Audio Conferencing Standard o una licenza per le conferenze Connessione con operatore, è possibile configurare il servizio di audioconferenza in modo che instradi tutte le chiamate o un set di chiamate in uscita da riunioni di Teams tramite l'operatore configurando un criterio routing audioconferenza.

>[!NOTE]
>Con una licenza Connessione con operatore Conferencing, le chiamate in uscita possono essere effettuate solo dall'operatore. Se si hanno licenze Connessione con operatore conferencing, è necessario configurare il servizio come descritto di seguito per abilitare le chiamate in uscita dalle riunioni Teams ai numeri di telefono.

È possibile applicare criteri di routing delle audioconferenze a livello utente, il che significa che l'operatore instrada solo le chiamate in uscita da riunioni Teams organizzate dagli utenti con i criteri associati. È anche possibile applicare questi criteri a livello globale, il che significa che l'operatore instrada le chiamate in uscita Teams riunioni organizzate da tutti gli utenti dell'organizzazione.

Usando PowerShell, creare i nuovi criteri di routing delle audioconferenze dell'organizzazione. Per specificare un operatore come route principale per le chiamate in uscita da riunioni Teams, seguire i passaggi seguenti usando i comandi di PowerShell indicati:

1. [Passaggio 1: Aggiungere una nuova stringa ai criteri di utilizzo PSTN online](#step-1-add-a-new-string-to-the-online-pstn-usage-policy)
2. [Passaggio 2: Creare un nuovo criterio route vocale online](#step-2-create-a-new-online-voice-route-policy)
3. [Passaggio 3: Creare un nuovo criterio di routing delle audioconferenze online](#step-3-create-a-new-online-audio-conferencing-routing-policy)
4. [Passaggio 4: Assegnare il nuovo criterio agli utenti](#step-4-assign-the-new-policy-to-users)

### <a name="step-1-add-a-new-string-to-the-online-pstn-usage-policy"></a>Passaggio 1: Aggiungere una nuova stringa ai criteri di utilizzo PSTN online

Per altre informazioni sull'uso di questo cmdlet, vedere [Set-CsOnlinePstnUsage.](/powershell/module/skype/set-csonlinepstnusage)

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### <a name="step-2-create-a-new-online-voice-route-policy"></a>Passaggio 2: Creare un nuovo criterio route vocale online

Per altre informazioni sull'uso di questo cmdlet, vedere [Set-CsOnlineVoiceRoute.](/powershell/module/skype/set-csonlinevoiceroute)

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### <a name="step-3-create-a-new-online-audio-conferencing-routing-policy"></a>Passaggio 3: Creare un nuovo criterio di routing delle audioconferenze online

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### <a name="step-4-assign-the-new-policy-to-users"></a>Passaggio 4: Assegnare il nuovo criterio agli utenti

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy”
```

>[!NOTE]
>Per impostare un criterio di routing delle audioconferenze come globale e applicarlo a tutti gli utenti dell'organizzazione, è possibile usare il parametro ``-Global`` al posto del ``-Identity`` parametro. Ad esempio, ``Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy”`` .

Quando si crea un criterio routing audioconferenza e lo si applica a un utente, l'operatore che fornisce il numero di telefono specificato nel parametro instrada Teams chiamate in uscita ai numeri di telefono ``BridgeSourcePhoneNumber`` PSTN. Inoltre, il parametro specifica il numero di telefono da usare come numero di telefono identificativo della linea di chiamata delle chiamate in uscita verso i numeri di telefono ``BridgeSourcePhoneNumber`` PSTN.

Lo schema specificato in è in formato regex e specifica le chiamate da ``NumberPattern`` instradare tramite l'operatore. Lo ``"\d+"`` schema nell'esempio precedente corrisponde a tutte le chiamate in uscita Teams riunioni. È anche possibile impostare il parametro NumberPattern su , che corrisponde ai numeri dialed con i formati  ``“^\+1(425|206)(\d{7})$”`` seguenti: +1 425 XXX XX XX o +1 206 XXX XX XX oppure , che corrisponde ai numeri dialed con il formato ``“^\+1(\d{10})$”`` seguente: +1 425 XXX XX XX.

Dopo aver assegnato un criterio di routing delle audioconferenze a un utente, tutte le chiamate delle riunioni  vengono effettuate a un numero  di telefono corrispondente all'espressione regolare specificata nel criterio Routing audioconferenza, incluso Chiamami alle chiamate e le chiamate avviate tramite l'opzione Invita qualcuno o comporre un numero di riunione.

## <a name="manage-your-operators"></a>Gestire gli operatori

Nella scheda **Operatori** personalizzati è possibile visualizzare gli operatori, il relativo stato e apportare le modifiche   seguenti alle selezioni:

- Gestire i servizi dell'operatore per paese
- Sospendere un operatore
- Rimuovere un operatore

>[!NOTE]
>Prima di rimuovere un operatore dall'organizzazione o da un paese, è necessario rimuovere tutti i numeri di telefono assegnati agli utenti e al bridge di audioconferenza, quindi contattare l'operatore per rilasciare i numeri.

## <a name="release-numbers-from-your-audio-conferencing-bridge"></a>Numeri di rilascio dal bridge di audioconferenza

Per rilasciare i numeri di telefono dal bridge di audioconferenza dall'interfaccia di amministrazione di Teams, vedere Procedura per annullare l'assegnazione di un numero di telefono di servizio per un **bridge** di conferenza in Modificare i numeri di telefono nel [bridge di audioconferenza.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge)

## <a name="additional-information-on-managing-microsoft-audio-conferencing"></a>Altre informazioni sulla gestione delle audioconferenze Microsoft

Per altre informazioni su come gestire i servizi di audioconferenza Microsoft per l'organizzazione, vedere gli articoli seguenti:

- Gestione delle impostazioni del servizio di audioconferenza Microsoft per l'organizzazione: [Gestire le impostazioni di audioconferenza per l'organizzazione in Microsoft Teams](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

- Gestione dell'impostazione del servizio di audioconferenza Microsoft degli utenti dell'organizzazione: Gestire le [impostazioni di audioconferenza](manage-the-audio-conferencing-settings-for-a-user-in-teams.md) per un utente in Microsoft Teams

- Modifica delle lingue degli operatori automatici dei numeri di telefono delle audioconferenze: Impostare le lingue degli [operatori automatici per i servizi di audioconferenza in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)
