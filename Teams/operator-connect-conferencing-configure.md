---
title: Configurare Conferenze con connessione tramite operatore
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
- highpri
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Altre informazioni su come configurare Conferenze con connessione tramite operatore.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b31c66e2621051ed96c13d6f414eec9dadb02495
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2022
ms.locfileid: "68585079"
---
# <a name="configure-operator-connect-conferencing"></a>Configurare Conferenze con connessione tramite operatore

Questo articolo spiega come configurare Conferenze con connessione tramite operatore per l'organizzazione e gli utenti.

Prima di configurare Conferenze con connessione tramite operatore, leggere [Plan for Conferenze con connessione tramite operatore](operator-connect-conferencing-plan.md) per informazioni sui vantaggi e i requisiti di licenza.

Gli argomenti trattati in questo articolo includono:

- [Configurare un operatore](#set-up-an-operator)
- [Acquisire numeri per il bridge di audioconferenza](#acquire-numbers-for-your-audio-conferencing-bridge)
- [Modificare i numeri di telefono predefiniti inclusi negli inviti alle riunioni degli utenti](#change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users)
- [Invio di chiamate in uscita dalle riunioni di Microsoft Teams tramite un operatore](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)
- [Gestire gli operatori](#manage-your-operators)
- [Numeri di rilascio dal bridge di audioconferenza](#release-numbers-from-your-audio-conferencing-bridge)
- [Ulteriori informazioni sulla gestione dei servizi di audioconferenza Microsoft](#additional-information-on-managing-microsoft-audio-conferencing)

## <a name="set-up-an-operator"></a>Configurare un operatore

È possibile configurare, modificare e rimuovere operatori nell'interfaccia di amministrazione di Teams. Nel riquadro di spostamento sinistro passare a **Operatori > vocali**.

Per impostare un operatore:

1. **Scegli un operatore.** Nella scheda **Tutti gli operatori** filtra gli operatori disponibili per area geografica o servizio per trovare l'operatore più adatto alle tue esigenze vocali. Seleziona quindi l'operatore che vuoi usare. Per Conferenze con connessione tramite operatore, verifica che l'operatore abbia elencato le **conferenze** come prodotto disponibile.

2. **Seleziona paesi.** In **Impostazioni operatore** seleziona i paesi che vuoi abilitare con l'operatore selezionato.

3. **Fornisci le informazioni di contatto** Le informazioni di contatto, inclusi il nome completo e l'indirizzo di posta elettronica, verranno condivise con l'operatore. È possibile modificare queste informazioni in un secondo momento. Inoltre, dovrai fornire le dimensioni dell'azienda, con la possibilità di fornire il tuo numero di telefono. Gli operatori usano queste informazioni per contattare l'utente con altri dettagli su Conferenze con connessione tramite operatore.

4. Accetta la notifica di trasferimento dati.

5. **Aggiungi il tuo operatore.** Seleziona **Aggiungi come operatore** per salvare.

## <a name="acquire-numbers-for-your-audio-conferencing-bridge"></a>Acquisire numeri per il bridge di audioconferenza

Il bridge di audioconferenza dell'organizzazione include i numeri di telefono disponibili a tutti gli utenti dell'organizzazione per partecipare alle riunioni di Microsoft Teams con numeri di telefono PSTN. Puoi vedere i numeri di telefono associati al bridge di audioconferenza della tua organizzazione nel Centro Amministrazione Teams in **Riunioni > Conference Bridge**.

Per acquisire numeri di telefono per il bridge di audioconferenza, attieniti alla seguente procedura:

1. **Abbonamento o licenza Conferenze con connessione tramite operatore standard per i servizi di audioconferenza.** Gli utenti che hanno bisogno di Conferenze con connessione tramite operatore numeri per partecipare alle riunioni che organizzano devono avere una licenza di abbonamento a Audioconferenza Standard o una licenza di Conferenze con connessione tramite operatore assegnata. Per altre informazioni, vedere [Pianificare Conferenze con connessione tramite operatore](operator-connect-conferencing-plan.md).

2. **Acquisisci numeri.** Vai al sito Web del tuo operatore per ordinare e acquisire numeri di telefono. Per un elenco dei siti Web degli operatori, vai alla [directory Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Dovrai fornire il tuo ID tenant. Se non si conosce l'ID tenant, vedere [Trovare l'ID tenant di Microsoft 365](/onedrive/find-your-office-365-tenant-id). Una volta completato l'ordine, l'operatore caricherà i numeri nel tenant. Puoi visualizzare i numeri e il provider nell'interfaccia di amministrazione di Teams accedendo a **Numeri di telefono > vocali**.

3. **Assegna numeri al bridge di audioconferenza.** È possibile assegnare numeri al bridge di audioconferenza dall'interfaccia di amministrazione di Teams **in Riunioni > Conference Bridges > Aggiungi**. Per ulteriori informazioni, vedi [Modificare i numeri di telefono nel bridge di audioconferenza](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

>[!NOTE]
>Non è possibile assegnare Conferenze con connessione tramite operatore numeri come numeri predefiniti di un bridge. Una volta assegnato un numero di telefono al bridge di audioconferenza, il numero sarà elencato nella **pagina Trova un numero locale** incluso negli inviti alle riunioni degli utenti dell'organizzazione con una licenza per i servizi di audioconferenza o una licenza per Conferenze con connessione tramite operatore.
>
>Per instradare le chiamate in uscita attraverso un operatore, vedere la sezione [**Invio di chiamate in uscita dalle riunioni di Teams tramite un operatore**](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator) più avanti in questo articolo.

## <a name="change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users"></a>Modificare i numeri di telefono predefiniti inclusi negli inviti alle riunioni degli utenti

 Questo passaggio è facoltativo.

I numeri di telefono predefiniti di un utente sono quelli inclusi negli inviti alle riunioni quando pianificano una riunione. È possibile aggiornare i numeri di telefono inclusi negli inviti alle riunioni degli utenti nel Centro Amministrazione teams in **Utenti > Gestisci utenti**. Per aggiornare i numeri di telefono inclusi negli inviti alle riunioni degli utenti, seleziona l'utente e seleziona **Modifica** nella sezione **Audioconferenza** .

Dopo l'applicazione delle modifiche, i nuovi inviti alle riunioni degli organizzatori includeranno i nuovi numeri di telefono predefiniti. Tuttavia, gli inviti alle riunioni esistenti pianificati prima della modifica manterranno i numeri predefiniti originali.

## <a name="sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator"></a>Invio di chiamate in uscita dalle riunioni di Microsoft Teams tramite un operatore

Se hai un abbonamento Microsoft Audio Conferencing Standard o una licenza di Conferenze con connessione tramite operatore, puoi configurare il servizio Audioconferenza in modo da instradare tutte le chiamate in uscita o una serie di chiamate in uscita dalle riunioni di Teams tramite il tuo operatore configurando un criterio di Routing audioconferenza.

>[!NOTE]
>Con una licenza di Conferenze con connessione tramite operatore, le chiamate in uscita possono essere effettuate solo dall'operatore. Se si hanno licenze di Conferenze con connessione tramite operatore, è necessario configurare il servizio come descritto di seguito per abilitare le chiamate in uscita dalle riunioni di Teams ai numeri di telefono.

È possibile applicare i criteri routing audioconferenza a livello di utente, il che significa che l'operatore instrada solo le chiamate in uscita dalle riunioni di Teams organizzate dagli utenti con i criteri associati. È anche possibile applicare questi criteri a livello globale, il che significa che l'operatore instrada le chiamate in uscita dalle riunioni di Teams organizzate da tutti gli utenti dell'organizzazione.

Con PowerShell, crea i nuovi criteri routing audioconferenza della tua organizzazione. Per specificare un operatore come percorso principale per le chiamate in uscita dalle riunioni di Teams, seguire la procedura seguente usando i comandi di PowerShell indicati:

1. [Passaggio 1: Aggiungere una nuova stringa ai criteri Utilizzo PSTN online](#step-1-add-a-new-string-to-the-online-pstn-usage-policy)
2. [Passaggio 2: Creare un nuovo criterio Route vocale online](#step-2-create-a-new-online-voice-route-policy)
3. [Passaggio 3: Creare un nuovo criterio routing audioconferenza online](#step-3-create-a-new-online-audio-conferencing-routing-policy)
4. [Passaggio 4: Assegnare il nuovo criterio agli utenti](#step-4-assign-the-new-policy-to-users)

### <a name="step-1-add-a-new-string-to-the-online-pstn-usage-policy"></a>Passaggio 1: Aggiungere una nuova stringa ai criteri Utilizzo PSTN online

Per altre informazioni sull'uso di questo cmdlet, vedere [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage) .

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### <a name="step-2-create-a-new-online-voice-route-policy"></a>Passaggio 2: Creare un nuovo criterio Route vocale online

Leggi [Set-CsOnlineVoiceRoute](/powershell/module/skype/set-csonlinevoiceroute) per altre informazioni sull'uso di questo cmdlet.

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### <a name="step-3-create-a-new-online-audio-conferencing-routing-policy"></a>Passaggio 3: Creare un nuovo criterio routing audioconferenza online

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### <a name="step-4-assign-the-new-policy-to-users"></a>Passaggio 4: Assegnare il nuovo criterio agli utenti

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy"
```

>[!NOTE]
>Per impostare un criterio routing audioconferenza come globale e applicarlo a tutti gli utenti dell'organizzazione, è possibile usare il ``-Global`` parametro al posto del ``-Identity`` parametro. Ad esempio, ``Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy"``.

Quando si crea un criterio routing audioconferenza e lo si applica a un utente, l'operatore che fornisce il numero di telefono specificato nel ``BridgeSourcePhoneNumber`` parametro indirizza le chiamate in uscita di Teams ai numeri di telefono PSTN. Inoltre, il ``BridgeSourcePhoneNumber`` parametro specifica il numero di telefono da utilizzare come numero di telefono di identificazione della linea di chiamata delle chiamate in uscita ai numeri di telefono PSTN.

Il modello specificato in ``NumberPattern`` è in formato regex e specifica quali chiamate instradare tramite l'operatore. Il ``"\d+"`` modello nell'esempio precedente corrisponde a tutte le chiamate in uscita dalle riunioni di Teams. È anche possibile impostare il parametro NumberPattern come  ``"^\+1(425|206)(\d{7})$"``, che abbina i numeri comporre con i seguenti formati: +1 425 XXX XX XX o +1 206 XXX XX XX o ``"^\+1(\d{10})$"``, che corrisponde ai numeri comporre con il formato seguente: +1 425 XXX XX XX.

Dopo aver assegnato un criterio Routing audioconferenza a un utente, tutte le chiamate dalle loro riunioni a un numero di telefono corrispondente al regex specificato nei criteri di routing delle audioconferenze tramite l'operatore, tra cui **Chiamami alle** chiamate e chiamate avviate tramite l'opzione **Invita qualcuno o comporre un numero** di riunione.

## <a name="manage-your-operators"></a>Gestire gli operatori

Nella scheda **Operatori personali** è possibile visualizzare gli operatori, il relativo stato e apportare le modifiche seguenti alle selezioni:

- Gestire i servizi operatore per paese
- Sospendere un operatore
- Rimuovere un operatore

>[!NOTE]
>Prima di rimuovere un operatore dalla tua organizzazione o da un paese, devi rimuovere tutti i numeri di telefono assegnati agli utenti e il bridge di audioconferenza, quindi contatta l'operatore per rilasciare i numeri.

## <a name="release-numbers-from-your-audio-conferencing-bridge"></a>Numeri di rilascio dal bridge di audioconferenza

Per rilasciare i numeri di telefono dal bridge di audioconferenza dall'interfaccia di amministrazione di Teams, consulta **Passaggi per l'annullamento dell'assegnazione di un numero di telefono di servizio per un bridge di conferenza** in [Modificare i numeri di telefono nel bridge di audioconferenza](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge).

## <a name="additional-information-on-managing-microsoft-audio-conferencing"></a>Ulteriori informazioni sulla gestione dei servizi di audioconferenza Microsoft

Per ulteriori informazioni su come gestire i servizi di audioconferenza Microsoft per l'organizzazione, vedi gli articoli seguenti:

- Gestione delle impostazioni del servizio Di audioconferenza Microsoft per l'organizzazione: [Gestire le impostazioni dei servizi di audioconferenza per l'organizzazione in Microsoft Teams](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

- Gestione dell'impostazione del servizio Di audioconferenza Microsoft degli utenti dell'organizzazione: [Gestire le impostazioni dei servizi di audioconferenza per un utente in Microsoft Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

- Modifica delle lingue dell'operatore automatico dei numeri di telefono dei servizi di audioconferenza: [impostare le lingue dell'operatore automatico per le audioconferenze in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)
