---
title: Creare una coda di chiamata in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Informazioni su come configurare il sistema telefonico per le code di chiamata con Microsoft teams, che offre un messaggio di saluto, detenere musica, reindirizzare le chiamate e altre funzionalità.
ms.openlocfilehash: 17e15e270492c4105f79ead6b2ce34ca37165ec3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125789"
---
# <a name="create-a-call-queue"></a>Creare una coda di chiamata

Le code di chiamata offrono un metodo per indirizzare i chiamanti alle persone dell'organizzazione che possono essere utili per un problema o una domanda particolare. Le chiamate vengono distribuite una alla volta per gli utenti della coda (noti come *agenti*). 

Le code di chiamata includono:

- Messaggio di saluto.

- Musica mentre gli utenti attendono il blocco in una coda.

- Chiamata routing-in *First in, First out* (FIFO) Order-to Agents.

- Opzioni di gestione per l'overflow e il timeout delle code.

Assicurarsi di aver letto [piano per gli operatori automatici di teams e le code di chiamata](plan-auto-attendant-call-queue.md) e aver seguito i [passaggi introduttivi](plan-auto-attendant-call-queue.md#getting-started) prima di seguire le procedure descritte in questo articolo.

Per configurare una coda di chiamata, nell'interfaccia di amministrazione di Team espandere **voce**, fare clic su **code di chiamata** e quindi fare clic su **Aggiungi**.

## <a name="resource-account-and-language"></a>Account e lingua delle risorse

![Screenshot delle impostazioni dell'account delle risorse e della lingua](media/call-queue-name-language.png)

1. Digitare un nome per la coda di chiamata. Gli agenti vedranno questo nome quando ricevono una chiamata in arrivo dalla coda.

2. Fare clic su **Aggiungi account**, cercare l'account risorse che si vuole usare con la coda di chiamata, fare clic su **Aggiungi** e quindi fare clic su **Aggiungi**.

3. Scegliere una lingua. Questa lingua verrà usata per le istruzioni vocali generate dal sistema e la trascrizione della segreteria telefonica (se abilitate).

## <a name="greetings-and-music-on-hold-in-queue"></a>Messaggi di saluto e musica in attesa in coda

Specificare se si vuole riprodurre un saluto ai chiamanti quando arrivano in coda. È necessario caricare un file MP3, WAV o WMA contenente il messaggio di saluto che si vuole riprodurre.

Teams offre musica predefinita ai chiamanti mentre sono in attesa in una coda. Se si vuole riprodurre un file audio specifico, scegliere **Riproduci un file audio** e caricare un file MP3, WAV o WMA.

> [!NOTE]
> La registrazione caricata non può essere superiore a 5 MB.
> La musica predefinita fornita nelle code delle chiamate di teams è priva di qualsiasi royalties pagabile dall'organizzazione. 

## <a name="call-agents"></a>Agenti di chiamata

Per poter aggiungere agenti a una coda di chiamata, vedere i [prerequisiti](plan-auto-attendant-call-queue.md#prerequisites) .

![Screenshot delle impostazioni di utenti e gruppi per le code di chiamata](media/call-queue-users-groups.png)

È possibile aggiungere fino a 20 agenti singolarmente e fino a 200 agenti tramite gruppi.

Per aggiungere un utente alla coda, fare clic su **Aggiungi utenti**, cercare l'utente, fare clic su **Aggiungi** e quindi fare clic su **Aggiungi**.

Per aggiungere un gruppo alla coda, fare clic su **Aggiungi gruppi**, cercare il gruppo, fare clic su **Aggiungi** e quindi fare clic su **Aggiungi**. È possibile usare le liste di distribuzione, i gruppi di sicurezza e i gruppi Microsoft 365 o Microsoft teams.

> [!NOTE]
> I nuovi utenti aggiunti a un gruppo possono richiedere fino a otto ore per la prima chiamata in arrivo.

## <a name="call-routing"></a>Routing delle chiamate

![Screenshot della modalità conferenza e delle impostazioni del metodo di routing](media/call-queue-conference-mode-routing-method.png)

La **modalità conferenza** riduce significativamente la quantità di tempo necessaria affinché un chiamante venga connesso a un agente, dopo che l'agente accetta la chiamata. Per il funzionamento della modalità conferenza, gli agenti nella coda di chiamata devono usare uno dei client seguenti:

  - La versione più recente di Microsoft teams desktop client, Android app o iOS app
  - Telefono Microsoft teams versione 1449/1.0.94.2020051601 o successiva
  
Gli account teams degli agenti devono essere impostati sulla modalità solo teams. Gli agenti che non soddisfano i requisiti non sono inclusi nell'elenco di routing delle chiamate. È consigliabile abilitare la modalità conferenza per le code di chiamata se gli agenti usano tutti i client compatibili.

Il **metodo di routing** determina l'ordine in cui gli agenti ricevono chiamate dalla coda. Scegliere una delle opzioni seguenti:

- Il **routing di Attendant** squilla tutti gli agenti della coda contemporaneamente. Il primo agente di chiamata a prendere la chiamata riceve la chiamata.

- Il **routing seriale** squilla tutti gli agenti di chiamata uno alla volta nell'ordine specificato nell'elenco **agenti di chiamata** . Se un agente respinge o non prende una chiamata, la chiamata suonerà l'agente successivo e proverà tutti gli agenti finché non viene prelevato o non viene ritirato.

- **Round Robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata ottenga lo stesso numero di chiamate dalla coda. Questo potrebbe essere auspicabile in un ambiente di vendita in entrata per assicurare la parità di opportunità tra tutti gli agenti di chiamata.

- Le rotte **inattive più lunghe** ogni chiamata all'agente che è stato inattivo il tempo più lungo. Un agente viene considerato inattivo se lo stato presenza è disponibile o se lo stato presenza è stato assente per meno di 10 minuti. Gli agenti il cui stato di presenza è stato assente per più di 10 minuti non sono considerati inattivi e non sono idonei a ricevere chiamate finché non modificano la loro presenza in available. 

![Screenshot delle impostazioni di routing, disattivazione e ora di avviso](media/call-queue-presence-agents-time.png)


Il **routing basato sulla presenza** usa lo stato di disponibilità degli agenti di chiamata per determinare se un agente deve essere incluso nell'elenco di routing delle chiamate per il metodo di routing selezionato. Gli agenti di chiamata il cui stato di disponibilità è impostato su **disponibile** sono inclusi nell'elenco di routing delle chiamate e possono ricevere chiamate. Gli agenti il cui stato di disponibilità è impostato su qualsiasi altro stato sono esclusi dall'elenco di routing delle chiamate e non ricevono le chiamate finché il loro stato di disponibilità non torna a **disponibile**. 

Puoi abilitare il routing delle chiamate basate sulla presenza con uno dei metodi di routing.

Se un agente sceglie di ricevere chiamate, non verrà incluso nell'elenco di routing delle chiamate, indipendentemente dal tipo di stato di disponibilità impostato. 

> [!NOTE]
> Gli agenti che usano il client Skype for business non sono inclusi nell'elenco di routing delle chiamate quando è abilitato il routing basato sulla presenza. Se si hanno agenti che usano Skype for business, non abilitare il routing delle chiamate basate sulla presenza.

L' **ora di avviso dell'agente** specifica il tempo di squillo del telefono di un agente prima che la chiamata venga reindirizzata all'agente successivo.

Per le code a volume elevato, è consigliabile seguire le impostazioni seguenti:

- **Modalità conferenza** per l' **auto**
- **Metodo di routing** per il **routing di Attendant**
- **Routing basato sulla presenza** **su** attivato
- **Tempo di avviso agente:** a **20 secondi**

## <a name="call-overflow-handling"></a>Gestione dell'overflow delle chiamate

![Screenshot delle impostazioni di overflow delle chiamate](media/call-queue-overflow-handling.png)

**Massimo chiamate nella coda** specifica il numero massimo di chiamate che possono essere attese nella coda in qualsiasi momento. Il valore predefinito è 50, ma può variare da 0 a 200. Quando viene raggiunto questo limite, la chiamata viene gestita come specificato dalla **quando viene raggiunta l'impostazione del numero massimo di chiamate** .

Puoi scegliere di disconnettere la chiamata o di reindirizzarla a qualsiasi destinazione di routing delle chiamate. Ad esempio, è possibile che il chiamante lasci un messaggio vocale per gli agenti nella coda. Per i trasferimenti esterni, vedere i [prerequisiti](plan-auto-attendant-call-queue.md#prerequisites) e i trasferimenti per i [numeri di telefono esterni-dettagli tecnici](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) per la formattazione dei numeri.

> [!NOTE]
> Se il numero massimo di chiamate è impostato su 0, il messaggio di saluto non verrà riprodotto.

## <a name="call-timeout-handling"></a>Gestione del timeout delle chiamate

![Screenshot delle impostazioni di timeout delle chiamate](media/call-queue-timeout-handling.png)

**Timeout chiamata: periodo di attesa massimo** specifica il tempo massimo che una chiamata può contenere nella coda prima che venga reindirizzata o disconnessa. È possibile specificare un valore da 0 secondi a 45 minuti.

Puoi scegliere di disconnettere la chiamata o di reindirizzarla a una delle destinazioni di routing delle chiamate. Ad esempio, è possibile che il chiamante lasci un messaggio vocale per gli agenti nella coda. Per i trasferimenti esterni, vedere i [prerequisiti](plan-auto-attendant-call-queue.md#prerequisites) e i trasferimenti per i [numeri di telefono esterni-dettagli tecnici](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) per la formattazione dei numeri.

Dopo aver selezionato le opzioni di timeout delle chiamate, fare clic su **Salva**.

## <a name="caller-id-for-outbound-calls"></a>ID chiamante per le chiamate in uscita

Poiché gli agenti in una coda di chiamata possono effettuare chiamate in uscita per restituire una chiamata al cliente, è consigliabile impostare l'ID chiamante per i membri di una coda di chiamata sul numero di servizio di un operatore automatico appropriato. Per altre informazioni, vedere [gestire i criteri di ID chiamante in Microsoft teams](caller-id-policies.md) .

## <a name="supported-clients"></a>Client supportati

I client seguenti sono supportati per gli agenti di chiamata in una coda di chiamata:

  - Client desktop Skype for business 2016 (versioni 32 e 64 bit)
  - Client desktop Lync 2013 (versioni 32 e 64 bit)
  - Tutti i modelli di telefono IP supportati per Microsoft teams. Vedere [ottenere telefoni per Skype for business online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).
  - Client Mac Skype for Business (versione 16.8.196 e versioni successive)
  - Client Android Skype for Business (versione 6.16.0.9 e versioni successive)
  - Client iPhone Skype for Business (versione 6.16.0 e versioni successive)
  - Client Mac Skype for Business (versione 6.16.0 e versioni successive)
  - Client Windows Microsoft Teams (versioni a 32 bit e 64 bit)
  - Client Microsoft Teams Mac
  - App per iPhone di Microsoft Teams
  - App Microsoft teams Android

    > [!NOTE]
    > Le code di chiamata assegnate a un numero di routing diretto non supportano i client Skype for business, i client Lync o i telefoni IP Skype for business come agenti.

## <a name="call-queue-cmdlets"></a>Cmdlet della coda di chiamata

Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata. Ecco i cmdlet usati per gestire una coda di chiamata.

- [New-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a>Argomenti correlati

[Vantaggi offerti dal Sistema telefonico](here-s-what-you-get-with-phone-system.md)

[Recuperare numeri di telefono del servizio](getting-service-phone-numbers.md).

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[Introduzione a Windows Powershell e Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
