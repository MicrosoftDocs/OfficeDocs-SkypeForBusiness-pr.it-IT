---
title: Contattare il service desk PSTN
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.pstnservicedesk
- ms.teamsadmincenter.voice.contactPSTNsupport
- Calling Plans
ROBOTS: NOINDEX, NOFOLLOW
description: Quando si ottengono numeri di telefono o numeri di porta (trasferimento) per l'organizzazione, potrebbe essere necessario ottenere assistenza e supporto presso il service desk PSTN.
ms.openlocfilehash: b3925fbd473094b06133fb7cfe31479396434b80
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510277"
---
# <a name="pstn-service-desk"></a>PSTN Service Desk 

Esiste un nuovo processo per interagire con il service desk PSTN. Ora è possibile aprire i ticket, visualizzare i ticket e tenere traccia delle comunicazioni in un'unica posizione integrata con l'Teams di amministrazione. Questo articolo descrive tutto ciò che è necessario sapere per contattare il service desk.

> [!NOTE]
> A partire dal 22 luglio 2021, il sistema di posta elettronica corrente è stato ritirato.

Per contattare il service desk:

1. Accedere all'interfaccia Teams di amministrazione - admin.teams.microsoft.com.

2. Nel riquadro sinistro selezionare Telefono **numeri**.

3. Nella parte superiore della pagina selezionare Ottieni supporto **per i numeri di telefono.** Verrà visualizzato il centro Telefono numero di telefono.  

> [!NOTE]
> Solo un utente dello stesso tenant sarà autorizzato a creare un caso. In altri casi, un utente di @fabrikam.com non può creare un caso per conto di @contoso.com. 

Dal centro Telefono numero di telefono è possibile creare nuovi casi, visualizzare i casi esistenti, comunicare con il service desk e gestire il profilo utente. Queste attività sono descritte in modo più dettagliato nelle sezioni seguenti.

- **Telefono numero di telefono**   – Passare alla home page del portale. 

- **[Creare un nuovo caso](#create-a-new-case)**   – Inviare una nuova richiesta o una richiesta generale. 

- **[Visualizzare i casi esistenti:](#view-and-manage-existing-cases)** tenere traccia e monitorare i casi esistenti. 

- **[Visualizzare i casi aziendali](#view-and-manage-existing-cases)**   – Tenere traccia e monitorare i casi esistenti dell'azienda. Se i colleghi dell'azienda hanno aperto un caso, è possibile cercarlo in questa visualizzazione.  

- **[Invia feedback:](#view-and-manage-existing-cases)** condividi il tuo feedback con noi. 

- **[Il tuo nome]**   – Aggiornare la pagina del profilo. 


## <a name="create-a-new-case"></a>Creare un nuovo caso

Per creare un nuovo caso, seguire questa procedura:

1. Selezionare **Crea un nuovo caso** da una delle posizioni seguenti:  

   - Nella pagina **Telefono numero,** nella parte superiore della pagina o nella parte inferiore della pagina.

   - Nella pagina **Visualizza casi**  esistenti.

   - Nella pagina **Visualizza casi aziendali.**

2. Fornire i dettagli del caso come descritto in dettaglio nella [sezione successiva.](#provide-case-details)

3. Dopo aver immesso tutti i valori, selezionare **Invia**. Verrà visualizzata una nuova schermata in cui è possibile visualizzare il numero del caso.  

### <a name="provide-case-details"></a>Fornire i dettagli del caso

Per comprendere i dettagli del caso, Microsoft ha bisogno delle informazioni seguenti:

- [Categoria caso](#case-category)
- [Paese o area geografica](#country-or-region)
- [Tipo di caso](#case-type)
- [Titolo del caso](#case-title)
- [Altri contatti per le notifiche](#additional-contacts-for-notifications)
- [Descrizione](#description)
- [Altri documenti di supporto](#additional-supporting-documents)

#### <a name="case-category"></a>Categoria caso

Un caso può avere una delle due categorie seguenti: 

- **Invia una nuova richiesta:** scegliere questa opzione se si vuole inviare una nuova richiesta. Ad esempio, si vuole inviare una richiesta di portabilità o acquistare numeri di telefono da Microsoft.  

- **Richiesta generale: scegliere** questa opzione in caso di domande utili per determinare la richiesta. Ad esempio, è necessario sapere se è possibile convertire i numeri wireless in Microsoft oppure se Microsoft supporta i numeri verde vanity. 

#### <a name="country-or-region"></a>Paese o area geografica

Selezionare il paese/area geografica per cui si sta inviando il caso. Se si hanno richieste per più paesi, è necessario aprire un caso per paese/area geografica.  

#### <a name="case-type"></a>Tipo di caso

Il tipo di case può essere uno dei seguenti:

- **Nome chiamante personalizzato (solo STATI UNITI)** - Impostare un nome di chiamata personalizzato sui numeri di telefono Microsoft. Questa opzione è applicabile solo ai numeri di telefono degli Stati Uniti. 

  - **Nome chiamata personalizzato da impostare (solo 15 caratteri)** - Nome della chiamata personalizzata che si vuole impostare. Name ha un limite massimo di 15 caratteri.  

  - **Elenco di numeri di telefono:** elenco di numeri di telefono per cui si vuole impostare un valore personalizzato per il nome della chiamata. Upload un file CSV con l'elenco dei numeri di telefono.  

- **Porta inter tenant:** spostare i numeri di telefono da un tenant a un altro. Ad esempio, si hanno due tenant diversi all'interno di Microsoft e si vogliono spostare i numeri di telefono da un tenant all'altro.  

  - **Nome di dominio del tenant di origine:** il tenant da cui si vogliono spostare i numeri di telefono in un tenant diverso.  

  - **Identificatore univoco del tenant di** origine: ID tenant per il tenant di origine. Si tratta di un campo facoltativo.  

  - **Nome di dominio tenant di destinazione:** il tenant in cui si vogliono spostare i numeri di telefono.  

  - **Identificatore univoco del tenant di destinazione:** ID tenant per il tenant di destinazione. Si tratta di un campo facoltativo.  

  - **Data richiesta ***- Data e ora in cui si vogliono spostare i numeri dal tenant di origine al tenant di destinazione. Vedere Data e ora.

  - **Elenco di numeri di telefono:** elenco di numeri di telefono da spostare dal tenant di origine al tenant di destinazione. Upload un file CSV con l'elenco dei numeri di telefono. 

- **Modifica tipo di inventario:** consente di modificare il tipo di numeri di telefono. Ad esempio, si vogliono convertire i numeri di abbonamento Microsoft in numeri di servizio. Per altre informazioni sui tipi di numeri di telefono supportati da Microsoft, vedere [Tipi di numeri di telefono](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

  - **Converti in:** selezionare questa opzione per convertire i numeri in numeri utente o in numeri di servizio. 

  - **Preferred Datetime*** - Data e ora in cui si vuole modificare il tipo di inventario dei numeri. Per altre informazioni, vedere Data e ora.

  - Casella di controllo: per poter aggiornare il tipo di **inventario,** è necessario che i numeri di telefono non siano assegnati. Microsoft non può elaborare richieste di modifica del tipo di numero di telefono a meno che i numeri di telefono all'interno del tenant non siano assegnati. Se si richiede questa modifica per una data futura, sarà necessario assicurarsi che i numeri non siano assegnati prima della data e dell'ora richieste. 

  - **Elenco di numeri di telefono:** elenco di numeri di telefono di cui si vuole modificare il tipo. Upload un file CSV con l'elenco dei numeri di telefono. 

- **Nuova acquisizione TN:** acquista nuovi numeri di telefono da Microsoft.  

  - **Tipo numero:** selezionare il tipo per i numeri. Vedere [Tipi di numeri di telefono](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

  - **Hai provato** a ottenere i numeri di telefono dal portale dell'interfaccia di amministrazione di Teams - Hai provato ad acquistare questi numeri di telefono dal portale dell'interfaccia di amministrazione di Microsoft Teams, dove puoi usare in autonomia?  

  - **Quantità di numeri di telefono obbligatori:** numero di numeri di telefono da acquistare.  

  - **Stato/Provincia:** stato/provincia all'interno del paese/area geografica per cui si vogliono i numeri di telefono.  

  - **Città:** città all'interno dello stato/provincia per cui si vogliono i numeri di telefono.  

  - **Office-** Si tratta di un indirizzo specifico solo per determinati paesi. Questo è l'indirizzo del sito dell'ufficio.  

  - **Elenco directory:** è specifico solo per determinati paesi. Si vogliono pubblicare le informazioni aziendali con i numeri di telefono?  

- **Porta in:** porta i numeri di telefono esistenti dal provider di servizi corrente a Microsoft.  

  - **Assegnare un nome all'ordine** di trasferimento: specificare un nome facile da ricordare per la richiesta di trasferimento. 

  -  **Data/ora di portabilità** richiesta * - Data e ora in cui si vuole che i numeri eseere il porting a Microsoft. Tieni presente che questa non è una data di portabilità garantita, perché il proprietario del numero corrente deve prima approvare la nostra richiesta di portabilità. Vedere Data e ora. 

  - **Elenco di numeri di portabilità:** l'elenco dei numeri di telefono da convertire in Microsoft. Upload un file CSV con l'elenco dei numeri di telefono. 

  - **Lettera di autorizzazione (LOA)** - Allegare qui una lettera di autorizzazione firmata e compilata. Microsoft non può elaborare una richiesta di porta senza loA.  

- **Aggiornamento dell'indirizzo:** aggiornare l'indirizzo per le chiamate di emergenza. Si noti che questo campo si applica solo a paesi selezionati. 

  - **ID località: l'ID** posizione per l'indirizzo di emergenza. 

  - **Elenco di numeri di telefono:** l'elenco dei numeri di telefono per cui si vuole modificare l'indirizzo di emergenza (immettere l'indirizzo desiderato nel campo Descrizione). Upload un file CSV con l'elenco dei numeri di telefono. 

***Data e ora.** Se si seleziona Paese = Francia, data = 14/08/2021 e ora = 10.00, la richiesta verrà eseguita il 14/08/2021 alle 10.00. Ora francese. 

#### <a name="case-title"></a>Titolo del caso

Immettere un titolo che riepiloga la richiesta.  

#### <a name="additional-contacts-for-notifications"></a>Altri contatti per le notifiche

Immettere l'elenco delle persone che riceveranno notifiche automatiche sullo stato da Microsoft. Ad esempio, si vuole inserire un ordine di trasferimento e si vuole che altri due colleghi oltre a se stessi ricevano notifiche di stato automatiche. Specificare gli indirizzi di posta elettronica dei colleghi nella sezione **Messaggi di posta elettronica di** notifica. Queste informazioni sono facoltative. 

#### <a name="description"></a>Descrizione

Descrivi cosa stai cercando di ottenere ed elenca le tue domande per il service desk Microsoft PSTN.  

#### <a name="additional-supporting-documents"></a>Altri documenti di supporto

Upload altri documenti per il caso.  

## <a name="view-and-manage-existing-cases"></a>Visualizzare e gestire i casi esistenti

È possibile visualizzare i casi selezionando **Visualizza casi esistenti** e selezionando il numero del caso. Se si seleziona un numero di caso, si reindirizza ai dettagli del caso. È anche possibile visualizzare i casi aziendali selezionando **Visualizza casi aziendali.**  È anche possibile:

- **Filtrare i casi** selezionando **Casi aperti**, Tutti  **i casi** o Casi **chiusi**.

- **Comunicare con il service desk PSTN** per quanto riguarda il caso aprendo un caso esistente, scorrendo verso il basso e selezionando **Aggiungi commento.** Verrà visualizzata una nuova finestra. Immettere il messaggio nella casella del commento. Allegare tutti i documenti di supporto (se disponibili) che potrebbero essere utili per la richiesta e selezionare **Invia**.  

  Le risposte del service desk PSTN verranno visualizzate sotto la stessa sequenza temporale. In caso di aggiornamento del caso, si riceverà una notifica automatica tramite posta elettronica dell'aggiornamento. 

- **Annullare un caso** passando a un caso esistente, scorrendo verso il basso e selezionando **Annulla caso.** Selezionare un motivo per l'annullamento nell'elenco a discesa e quindi scegliere **Annulla**.  

- **Risolvere un caso:** se si ritiene che la richiesta sia stata completata, è possibile risolvere un caso passando a un caso esistente, scorrendo verso il basso e selezionando **Risolvi caso.** Selezionare **Chiudi**; il caso verrà visualizzato come **Risolto - Problema risolto**.  


## <a name="related-topics-and-additional-resources"></a>Argomenti correlati e risorse aggiuntive

- Per assistenza relativa alla configurazione e alla configurazione dei numeri, alle licenze, ai costi o alla fatturazione, vedere Contatto di supporto per i prodotti aziendali [- Guida per gli amministratori.](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide)

- Per informazioni sui piani per chiamate disponibili nel proprio paese/area geografica, vedere Disponibilità di paesi e aree geografica per [audioconferenze e piani per chiamate.](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

- Per informazioni utili per selezionare i tipi di numeri di telefono appropriati per l'organizzazione, vedere [Diversi tipi di numeri di telefono.](../different-kinds-of-phone-numbers-used-for-calling-plans.md)

- Per informazioni sulla gestione dei numeri di telefono per l'organizzazione, vedere [Gestire i numeri di telefono per l'organizzazione.](manage-phone-numbers-for-your-organization.md)

- Per informazioni sui termini e le condizioni per le chiamate di emergenza, vedere Condizioni e [condizioni per le chiamate di emergenza.](../emergency-calling-terms-and-conditions.md)
